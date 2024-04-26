# Report System Status

This is a work in progress.  When finished we will have a Microsoft Teams tab accessible way to request, view, and archive both parameterized reports requiring long running SQL scripts and those requiring live Plex data. It will also be able to use the **[Azure Graph API](https://learn.microsoft.com/en-us/graph/overview)** to email excel files or about anything else having to do with any Microsoft apps.

## references

https://mermaid.js.org/intro/syntax-reference.html
https://mermaid.js.org/syntax/gantt.html

```mermaid
mindmap
  root((Report System))
    Azure Tenent
      IAM
      Azure SQL DB
      ::icon(fa fa-book)
      Blob Storage
      AKS
        redis
        report requester
    Plex ERP
      ::icon(fa fa-book)
      Soap Web Services
      ODBC data source

    On Premise
      MicroK8s
        Kong API Server
        MySQL
        Postgres
        MongoDB
        Redis
        Report Runner

```

```mermaid
gantt
    dateFormat  YYYY-MM-DD
    title       Report System IT & Development
    excludes    weekends
    %% (`excludes` accepts specific dates in YYYY-MM-DD format, days of the week ("sunday") or "weekends", but not the word "weekdays".)

    section Platforms
    Dell R620s                :p1,2024-03-01,30d
    OpenStack                 :p2,2024-03-01,30d
    MicroK8s                  :p3,2024-03-01,30d

    section Storage
    Micro Ceph                :s1,2024-03-01,5d
    Minio S3 Object Storage   :s2,after s1, 5d

    section Databases
    Azure SQL DB              :db1,after s2,5d
    MySQL InnoDB              :db2,after db1,5d
    Postgres                  :db3, after db2, 5d
    MongoDB                   :db4, after db3, 5d
    Redis Operator            :active,db5, after db4, 5d

    section Ingres
    NGinx IC                  :i1,after db5, 5d
    Kong API Gateway          :i2, after i1, 5d  

    section Observability
    Metric Server             :o1,after i2,5d
    Prometheus                :o2,after o1,5d
    Grafana                   :o3,after o2,5d

    section Maintenance
    Kured Operator            :m1,after o3, 5d
    Transfer from MI to Azure SQL db :m2, after m1,5d

    section Development
    Runner                  :active,d1,2024-04-22,5d
    Requester               :d2,after d1,5d

```

# Trial Balance Pipeline

```mermaid
sequenceDiagram
    participant dan as Dan
    participant req as Requestor
    participant red as Redis
    participant run as Runner
    dan->>req: request report
    req->>red: insert report request
    run->>red: subscribe to report mutex and queue
    loop Check for report request
        run->>run: If mutex up then start etl pipeline
    end
```

## ETL pipeline

```mermaid
sequenceDiagram
    participant run as Runner
    participant s1 as AccountingYearCategoryType
    participant s2 as AccountingAccount
    participant s3 as AccountingPeriod
    participant s4 as AccountingPeriodRanges

    run->>s1: start AccountingYearCategoryType
    s1->>s2: start AccountingAccount
    s2->>s3: start AccountingPeriod
    s3->>s4: start AccountingPeriodRanges

```

## continuation

```mermaid
sequenceDiagram
    participant s4 as AccountingPeriodRanges
    participant s5 as AccountingBalanceAppendPeriodRange
    participant s6 as AccountActivitySummaryGetOpenPeriodRange
    participant s7 as AccountPeriodBalanceRecreatePeriodRange
    participant s8 as AccountPeriodBalanceRecreateOpenPeriodRange
    s4->>s5: start AccountingBalanceAppendPeriodRange
    s5->>s6: start AccountActivitySummaryGetOpenPeriodRange
    s6->>s7: start AccountPeriodBalanceRecreatePeriodRange
    s7->>s8: start AccountPeriodBalanceRecreateOpenPeriodRange

```

## Trial Balance Runner

The ETL pipeline is a set of Go routines (threads) each of which is responsible for 1 ETL script. The TB runner's main thread begins the ETL pipeline by sending a message the first ETL script go routine.  Each ETL script go routine completes and then calls the next ETL script's go routine.  The final ETL script finishes and then sets the TB mutex up so that the runner's main thread can start the pipeline again.

```psuedo_code
create go routines (threads) and communitcation channels for each tb etl script in tb etl pipeline
subscribe to redis tb mutex and request queue 

infinite while loop
    if tb queue not empty
        remove request from queue
        when tb mutex up
            down tb mutex 
            send request to 1st ETL script's go routine
        end
    end
```

```mermaid
flowchart TD
    A[Start] --> B{Are items in queue and pipeline idle?}
    B -- Yes --> C[Start Pipeline]
    C --> D[Repeat]
    D --> B
    B -- No --> D[Repeat]
```

## Trial Balance ETL script go routine

Each ETL script's go routine either waits for a message from the runner's main thread in the case of the first ETL script's go routine or the previous ETL scripts go routine before it starts. If it completes successfully it sends a message to the next ETL script's go routine or in the case of the final ETL script's go routine inserts a record in the redis result list indicating it's completion status.

```psuedo_code
infinite while loop
    if redis 
    runner's main thread calls 1st ETL scripts go routine.
    while more ETL scripts to run
        if ETL script complete successfully
            call the next ETL script's go routine
        else
            update redis result list to failed
            send error message via email
        end
    end
    last ETL script's go routine sets redis TB mutex up and inserts a record in the redis TB result list indicating it's completion status.
end
```



**[Power BI paginated reports (.rdl files)](https://learn.microsoft.com/en-us/power-bi/paginated-reports/parameters/report-builder-parameters)** with parameters.

![](https://learn.microsoft.com/en-us/power-bi/paginated-reports/parameters/media/report-builder-parameters/report-builder-parameters-power-bi-service.png)

Current Status:

- The Southfield Trial Balance report which is generated by Python ETL scripts and viewed from a Power BI paginated report accessible from a Microsoft Teams tab is online now. This report is needed because of an Plex issue isolated to certain PCN. This is the Plex recommended way of generating this important report for the affected PCN.  
- An internal Kubernetes cluster is hosting a MySQL database which is being used in tandem with our Azure SQL db.  Both the MySQL and Azure SQL databases perform the same function but the Azure SQL database is needed because it is secured by a Microsoft public IP and SSL certificate needed for Microsoft Teams apps.
- Our internal Kubernetes cluster can handle most tasks for the report system but since it is not publicly accessible we still need an Azure Kubernetes service for hosting the reports and apps which are to be accessible from Microsoft Teams tabs.
- The report system request, viewer, and archive app are not complete yet but the Kubernetes Cluster used to run the supporting software such a the MySQL, Redis, and the Kong API server is up and running.
