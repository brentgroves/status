# Status

```text
Good morning dear ones,
I hope all is going well for you and your loved ones :-)  As always please feel free to call me at home or at work about anything you like!  

Sincerely yours,
Brent G.
260-564-4868
```

## **[Link to view this Markdown document](https://github.com/brentgroves/status/blob/main/2024/week18.md)**

You will get an "unable to render error" just press the "<-->" button above mermaid diagram.

## Best ways to create and view Markdown with Mermaid

- **[Markdown Mermaid extension](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-mermaid)**
- **[JebBrains IDE](https://www.jetbrains.com/guide/go/tips/mermaid-js-support-in-markdown/)**

![Click this link to view mindmap](https://mermaid.ink/img/pako:eNqFUk1v4kAM_SvWnEDKooRE-ZgblB4qipollSqtcpkmhh0tM04nk1Up4r_vkDSUPfVm-9nPzx8nVlGNjDMlda1EU2oAQ2Qnky02ZCwUx9aimk4vAMDiozMIz6hR2yEC8LDYjOYAFz8fYbUcY5zLivRkJ2AnfrwS_ZmOyPJAr1BYMmKPV4Z1MZpOCNayvXV7RQbfOnSizIDkB3yH-23-fb-CRAMv6Hqi-SsrvFI_rZZ3UAsroKXOVE7MgDxpyA0q2V7lbWRlaJ3eiFqT3sMif-hJR0196tHt4cvNqbV7gzeVG1dJX3sC2P4_7ucBtp3WF17mMYVGCVm7a50uaSWzv1Fhybgza9yJ7mBLVuqzSxWdpeKoK8at6dBjXePmw5UUeyMU4ztxaK_R-1q6I4yZjdC_iNSNy_iJvTMeZ7MwnEeJn4TJPAhjjx0ZD6L5LMviJPL9KM7S2E_PHvvo6_1Z6qfzMEmywI-DyA8ij2HfajO8XP95538_hrzz?type=png)]

**[Click link to edit mindmap](https://mermaid.live/edit#pako:eNqFUk1v4kAM_SvWnEDKooRE-ZgblB4qipollSqtcpkmhh0tM04nk1Up4r_vkDSUPfVm-9nPzx8nVlGNjDMlda1EU2oAQ2Qnky02ZCwUx9aimk4vAMDiozMIz6hR2yEC8LDYjOYAFz8fYbUcY5zLivRkJ2AnfrwS_ZmOyPJAr1BYMmKPV4Z1MZpOCNayvXV7RQbfOnSizIDkB3yH-23-fb-CRAMv6Hqi-SsrvFI_rZZ3UAsroKXOVE7MgDxpyA0q2V7lbWRlaJ3eiFqT3sMif-hJR0196tHt4cvNqbV7gzeVG1dJX3sC2P4_7ucBtp3WF17mMYVGCVm7a50uaSWzv1Fhybgza9yJ7mBLVuqzSxWdpeKoK8at6dBjXePmw5UUeyMU4ztxaK_R-1q6I4yZjdC_iNSNy_iJvTMeZ7MwnEeJn4TJPAhjjx0ZD6L5LMviJPL9KM7S2E_PHvvo6_1Z6qfzMEmywI-DyA8ij2HfajO8XP95538_hrzz)**

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
    title       Project List
    excludes    weekends
    %% (`excludes` accepts specific dates in YYYY-MM-DD format, days of the week ("sunday") or "weekends", but not the word "weekdays".)

    section Projects
    Report System                                   :p1,2024-04-22,5d
    Tool Tracker                                    :p2,2024-04-22,5d
    Observability System                            :p3,2024-04-22,5d

```

```mermaid
gantt
    dateFormat  YYYY-MM-DD
    title       This Week's tasks
    excludes    weekends
    %% (`excludes` accepts specific dates in YYYY-MM-DD format, days of the week ("sunday") or "weekends", but not the word "weekdays".)

    section K8s
    Redis Operator                                :d1,2024-04-22,5d
    section Development
    Runner                                        :d1,2024-04-22,5d

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
    MySQL InnoDB              :db1,after s2,5d
    Postgres                  :db2, after db1, 5d
    MongoDB                   :db3, after db2, 5d
    Redis Operator            :active,db4, after db3, 5d

    section Ingres
    NGinx IC                  :i1,after db4, 5d
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

## Run TB Report

```mermaid
sequenceDiagram
    participant dan as Dan
    participant req as Requester
    participant red as Redis
    participant run as Runner
    dan->>req: request report
    req->>red: insert TB request
    run->>red: subscribe to TB queue
    loop 
        run->>run: Start TB ETL pipeline
    end
```

## Trial Balance Runner

```mermaid
flowchart TB
    start[Start Runner] --> subscribe_queue[Subscribe to Redis TB queue]
    subscribe_queue --> wait_tb_request[Wait for next TB request] 
    wait_tb_request --> down_mutex[Down Redis TB mutex]
    down_mutex -- Wait for Lock --> start_first_script[Start first ETL script]
    start_first_script --> more_scripts{More ETL scripts?}
    more_scripts -- Yes --> start_next_script[Start next ETL script]
    start_next_script --> more_scripts
    more_scripts -- No --> up_mutex[Up TB mutex]
    up_mutex --> wait_tb_request[Wait for next TB request]
```

## Ticketing System Help

Rejection occurred because bar code engraver not working for a long period of time and management was unaware of the issue.

Issue: CNC operators are expected to keep asking and calling management if important issues are not getting resolved.
Suggestion: Allow the CNC operators to enter priority issues that could lead to a rejection.
Question: What would be the best way for a CNC operator to inform management of critical issues.

- call Jake
- maintenance ticketing system
- plex suggestion system
- it ticketing system

## Repsys Operator

Make a k8s operator to install and monitor repsys.

## Plex ODBC

We did have to log into this ODBC account periodically do we still have to "mg.odbcalbion" if so how?
