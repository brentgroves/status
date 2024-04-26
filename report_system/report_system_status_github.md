# Report System Status

This is a work in progress.  When finished we will have a Microsoft Teams tab accessible way to request, view, and archive both parameterized reports requiring long running SQL scripts and those requiring live Plex data. It will also be able to use the **[Azure Graph API](https://learn.microsoft.com/en-us/graph/overview)** to email excel files or about anything else having to do with any Microsoft apps.

## references

<https://mermaid.js.org/intro/syntax-reference.html>
<https://mermaid.js.org/syntax/gantt.html>

```mermaid
gantt
    dateFormat  YYYY-MM-DD
    title       Projects
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
    title       Task List
    excludes    weekends
    %% (`excludes` accepts specific dates in YYYY-MM-DD format, days of the week ("sunday") or "weekends", but not the word "weekdays".)

    section K8s
    Redis Operator                                :d1,2024-04-22,5d
    section Development
    K8s API access                                :d1,2024-04-22,1d
    Redis Pub/Sub TB queue                        :d2,after d1,2d
    Redis TB mutex                                :d3,after d2,2d

```

## Task Notes

- **[Research Redis mutex](https://dev.to/jdvert/handling-mutexes-in-distributed-systems-with-redis-and-go-5g0d)**
- **[Research Redis Pub/Sub](https://redis.io/docs/latest/develop/interact/pubsub/)**
- Create K8s API tutorial in **[go/tutorials/k8s](~/src/repsys/volumes/go/tutorials/k8s)**
  - **[In-Cluster K8s API access](https://github.com/kubernetes/client-go/tree/master/examples/in-cluster-client-configuration)**
  - **[Out-of-Cluster K8s API access](https://github.com/kubernetes/client-go/blob/master/examples/out-of-cluster-client-configuration/README.md)**

![](https://mermaid.ink/img/pako:eNqFUk1v4kAM_SvWnEDKooRE-ZgblB4qipollSqtcpkmhh0tM04nk1Up4r_vkDSUPfVm-9nPzx8nVlGNjDMlda1EU2oAQ2Qnky02ZCwUx9aimk4vAMDiozMIz6hR2yEC8LDYjOYAFz8fYbUcY5zLivRkJ2AnfrwS_ZmOyPJAr1BYMmKPV4Z1MZpOCNayvXV7RQbfOnSizIDkB3yH-23-fb-CRAMv6Hqi-SsrvFI_rZZ3UAsroKXOVE7MgDxpyA0q2V7lbWRlaJ3eiFqT3sMif-hJR0196tHt4cvNqbV7gzeVG1dJX3sC2P4_7ucBtp3WF17mMYVGCVm7a50uaSWzv1Fhybgza9yJ7mBLVuqzSxWdpeKoK8at6dBjXePmw5UUeyMU4ztxaK_R-1q6I4yZjdC_iNSNy_iJvTMeZ7MwnEeJn4TJPAhjjx0ZD6L5LMviJPL9KM7S2E_PHvvo6_1Z6qfzMEmywI-DyA8ij2HfajO8XP95538_hrzz?type=png)

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

## Run TB Report

![](https://mermaid.ink/img/pako:eNptkstuwyAQRX8FzdqN8EN-sMiiSnbtJsmq8oaYaYsUDwSD1DTKvxfbsZSqZQPMPfeONJordEYhCBjwHJA63Gj54WTfEovHSud1p60kz5QkJge2kfRXc3getd2YMXh0_xFqJpQe_lHDlL0LRIs5tntar2OwGNPH2Hhb4_wsx9okK8E0Deg8Ozwv4J0ItBBDOA6d00dk3oxcpALO1MkYy-bngymQYHsv59Tt4YVZbfGk6W5CUm2cAiTQo-ulVnF-11FqwX9ijy2I-FT4LsPJt9DSLaIyeLO_UAfCu4AJBKukX8b9u7hV2hu31OKE3ozpH74grvAFomxWeZ4VFa_yKkvzMoELiLTIVk1TVgXnRdnUJa9vCXxPfr6qeZ3lVdWkvEwLnhYJ4NTqdd6BaRVuP90VqvI?type=png)

## Trial Balance Runner

![](https://images.techhive.com/images/article/2017/02/pressure-water-line-100707995-large.jpg?auto=webp&quality=85,70)

![](https://mermaid.ink/img/pako:eNqVU01Pg0AQ_SubOWMDhUDhoIlpb-rBaoyWhmxhUGLZxf1Iq03_u8tCK_XjICRk3-ybN2-G3R3kvEBIoFzzTf5ChSJ3lykj5pHKoMW8_ZJbzRiKJTk7OydSr2QuqhVmbxo1LuYHTBQnt1hU0kgQu7fslU4zrMqGVipTq0ygiUm1eDCYlFwQhtvWA-k3lqTT-Ma3GgXfsKzWCreLqVl-FbexvvgXyeSQY5krnr927bQNZmUlpMpal82hZxsis7sr0oWXg7Gc8K1MzQX2WO6uDRhkyot9lzsktW4eUQ48tJ2fWrCz-MPBgP3DwO_Vbrgl6qaf2X3zfVaHrf_9oZS1LzhQo6hpVZjTtGv1UlAvWGMKiVkWWFK9VimkbG-oVCs-f2c5JEpodEA3BVU4reizoDUkJV3LY3RWVIqLA7Oh7InzegAh2cEWkjAe-f44iNzIj8aeHzrwDokXjEdxHEaB6wZhPAndyd6BD5vvjibuZOxHUey5oRe4XuAA2lLX3ZWwN2P_CbfZEOI?type=png)
