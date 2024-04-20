# Father's direction

My son you can not find peace and contentment in work.  My intentions for work is that it can be a time we can enjoy together helping others. Peace and contentment will come when you follow me as I guide you in what to say and do. All results of your work are in my hands. I may decide to have you wait or fail at the tasks I have planned for you.  The work I give you is meant to teach you that work can never be a reliable source of peace and contentment. The only reliable source of these wonderful things is doing what is right by following me.

Follow us my son and you will have peace and joy.  We will experience the many wonders of creation together. We love you and you are never alone because we will always be with you to guide and direct you our beloved son!

My son do not be anxious when there is so many things to do.  Instead look to us for guidance and we will help you with each task.  Remember we have a plan for you and we will be with you each step of the way so do not worry our son.

We have heard your prayer and will give you courage to face every trial, trouble, pain, and sorrow.  You will be able to endure each hardship because of the faith and hope that we have given you.  So do not fear and rejoice because along with the hardships you must face to learn what you must there will also be great wonders for you to explore with us and those around you!

I love you and will help you to have a loving heart!  I will give you courage and help you to bear each trial and endure every hardship my son.  Do not forget that you are part of a community and I want you to learn to love each person, creature, and even the land where you live.

The world's love is performance based, but my love is unconditional. The world's system promotes fear and says you must perform better than your neighbor.  I say help your neighbor and especially help the ones that are struggling. Do not worry about your own status.  Do not promote yourself instead think of others and help them in their work. Only in this way will you have perfect peace my beloved son.

```text
Good morning dear ones,
I wish each of you a pleasant and prosperous week in this beautiful time of year :-)  As always please feel free to call me at home or at work about anything you like!  

Sincerely yours,
Brent G.
260-564-4868
```

This is a markdown file if it looks a little strange. You could use visual studio code or an online viewer such as <https://dillinger.io/>

## Plex ODBC

We did have to log into this ODBC account periodically do we still have to "mg.odbcalbion" if so how?

## Report services request summary

Reduce our Azure data warehouse costs from $748 to $30 per month by using an Azure SQL db service-hosted database instead of one hosted on an Azure SQL MI. Keep the Azure Kubernetes service as is at $290 per month.

## **[Azure SQL MI](https://azure.microsoft.com/en-us/pricing/details/azure-sql-managed-instance/single/)**

Currently, this Azure SQL MI hosts an Azure SQL database which is being used as our data warehouse.

```yaml
SQL managed instance: mgsqlmi
databases: mgdw,ssisdb
resource group: rg-useast-dataservices
cost: $748/month
plan: Migrate schema and import data into our Azure SQL db then delete this instance.
status: This is being used to generate our Southfield's Plex Trial Balance report. In the future, our report system's Microsoft Teams accessible request/viewer/archive apps would use this.
```

## **[Azure SQL db](https://azure.microsoft.com/en-us/pricing/details/azure-sql-database/single/)**

```yaml
server: repsys
database: rsdw
resource group: repsys
type: Standard S1: 20 DTUs
cost: $30/month
plan: Use this instead of Azure SQL MI.
status: This service is running but the database schema and data have not been transferred from the database stored on the mgsqlmi MI.
```

## Azure AKS (Kubernetes)

The plan is to run the minimal components of the report system from this 1-node K8s Cluster.  It is needed because Power BI reports and supporting apps running in Microsoft Teams tabs need to be accessible through an SSL-secured public IP.

```yaml
resource: reports-aks
resource group: reports-aks
Node pools: 1 node pool
cost: $290/month
status: This service is running but the request/viewer/archive apps are not ready yet.
```

## Microsoft 365 E5 Plan

Need E5 or E3 plan to get needed add-ons.
Price per user/month (annual commitment) $57.00

## Add-ons Available for Microsoft 365 E3 and E5 subscriptions

- Power Automate (need this). Enables users to automate repetitive tasks and workflows. Available as an add-on for Microsoft 365 E3 and E5.
- Power BI Pro (need this). Provides advanced data visualization and business intelligence features. Available as an add-on for Microsoft 365 E3 and E5.

## Azure services

- Azure SQL db (need this) - Power Automate used to copy data from Plex to DW.  All that we need with a much lower cost than Azure SQL MI.  
- Azure AKS (Kubernetes) (need this) - Hosts Microsoft teams accessible report request web app.

## Azure DevOps

Azure Repos (need this)
Get unlimited, cloud-hosted private Git repos and collaborate to build better code with pull requests and advanced file management.

Azure pipelines (nice to have)
Build, test, and deploy with CI/CD that works with any language, platform, and cloud. Connect to GitHub or any other Git provider and deploy continuously.

## **[Setup Redis Enterprise on Kubernetes](https://redis.io/docs/latest/operate/kubernetes/architecture/)**

Used to communicate between the repsys requestor and pipeline components.

**[Redis game server usage](https://news.ycombinator.com/item?id=2705613)**

![](https://redis.io/docs/latest/images/rs/kubernetes-overview-network-attached-persistent-storage.png)

![](https://redis.io/docs/latest/images/rs/kubernetes-overview-performance-improvements-write.png)

![](https://redis.io/docs/latest/images/rs/kubernetes-overview-multiple-services-per-pod.png)

## Network-attached persistent storage

Kubernetes and cloud-native environments require that storage volumes be network-attached to the compute instances, to guarantee data durability. Otherwise, if using local storage, data may be lost in a Pod failure event. See the figure below:

![](https://redis.io/docs/latest/images/rs/kubernetes-overview-network-attached-persistent-storage.png)

On the left-hand side (marked #1), Redis Enterprise uses local ephemeral storage for durability. When a Pod fails, Kubernetes launches another Pod as a replacement, but this Pod comes up with empty local ephemeral storage, and the data from the original Pod is now lost.

On the right-hand side of the figure (marked #2), Redis Enterprise uses network-attached storage for data durability. In this case, when a Pod fails, Kubernetes launches another Pod and automatically connects it to the storage device used by the failed Pod. Redis Enterprise then instructs the Redis Enterprise database instance/s running on the newly created node to load the data from the network-attached storage, which guarantees a durable setup.

Redis Enterprise is not only great as an in-memory database but also extremely efficient in the way it uses persistent storage, even when the user chooses to configure Redis Enterprise to write every change to the disk. Compared to a disk-based database that requires multiple interactions (in most cases) with a storage device for every read or write operation, Redis Enterprise uses a single IOPS, in most cases, for a write operation and zero IOPS for a read operation. As a result, significant performance improvements are seen in typical Kubernetes environments, as illustrated in the figures below:

![](https://redis.io/docs/latest/images/rs/kubernetes-overview-performance-improvements-write.png)
