# Father's direction

My son you can not find peace in contentment in work.  My intentions for work is that it can be a time we can enjoy together and that you can enjoy helping others. Peace and contentment will come when you follow me as I guide you in what to say and do. All results for the work I have for you are in my hands. I may decide to have you wait or fail at the tasks you take on in order to teach you that work can never be a reliable source of peace and contentment.

My son do not be anxious when there is so many things to do.  Instead look to us for guidance and we will help you with each task.  Remember we have a plan for you and we will be with you each step of the way so do not worry our son.

We have heard your prayer and will give you courage to face every trial, trouble, pain, and sorrow.  You will be able to endure each hardship because of the faith and hope that we have given you.  So do not fear and rejoice because along with the hardships you must face to learn what you must there will also be great wonders for you to explore with us and those around you!

I love you and will help you to have a loving heart!  I will give you courage and help you to bear each trial and endure every hardship my son.  Do not forget that you are part of a community and I want you to learn to love each person, creature, and even the land where you live.

The world's love is performance based, but my love is unconditional. The world's system promotes fear and says you must perform better than your neighbor.  I say help your neighbor and especially help the ones that are struggling. Do not worry about your own status.  Do not promote yourself instead think of others and help them in their work. Only in this way will you have perfect peace my beloved son.

```text
Good morning dear ones,
I hope you all had a peaceful and happy Easter, and I wish Brad and his new wife safe travels and a joyous marriage!  As always please feel free to call me at home or at work about anything you like!  

Sincerely yours,
Brent G.
260-564-4868
```

**![MySQL Operator Architecture](https://dev.mysql.com/doc/mysql-operator/en/images/mysql-operator-architecture.png)**


## How to deal with planned and unplanned reboots

Used operators to install a 2 instance Postgres and MySQL InnoDB Cluster, and Redis cache database on 3 node K8s Clusters. Then rebooted the nodes in different ways to see what problems can arise and what can be done to fix them. Tested Kured which is meant to assist in the node reboot process while keeping software running on other nodes using a draining technique.

## Old to new schemas

- Migrate MySQL 8.0 Server to MySQL InnoDB which has a router and a group replication feature.  The requirement for group replication is that all tables must have a primary key explicitly defined, but most of our MI tables do so this migration should not be difficult.
- Azure CLI script to create an Azure SQL db that meets our data warehousing needs.
- Migrate Azure SQL MI to Azure SQL db. Unfortunately, can't simply backup MI and import into SQL db, so, must write an ETL script.
- Test backup for Azure SQL db once our Azure SQL MI schema is migrated to it.
- Install Redis cache database onto k8s cluster running MySQL InnoDB and Postgres Clusters.  
- Then do planned and unplanned rebooting of K8s nodes trying to crash the software and figuring out what to do in each case. 
