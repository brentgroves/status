
# Father's direction

I love you and will help you to have a loving heart!  I will give you courage and help you to bear each trial and endure every hardship my son.  Do not forget that you are part of a community and I want you to learn to love each person, creature, and even the land where you live.

## Schema-Driven Development

In GraphQL your API starts with a schema that defines all your types, queries and mutations, It helps others to understand your API. So it’s like a contract between server and the client. Whenever you need to add a new capability to a GraphQL API you must redefine schema file and then implement that part in your code. GraphQL has its Schema Definition Language for this purpose. gqlgen is a Go library for building GraphQL servers and has a nice feature that generates code based on your schema definition.

## Execute **[Stored Procedure with GraphQL](https://stackoverflow.com/questions/73944424/execute-stored-procedure-with-graphql)**

We have database with a lot of stored procedures. I need to implement GraphQL, but I can't find information about is it possible to Execute stored procedures with GraphQL.

GraphQL has nothing to do with stored procedures. It is only a wrapper over your http requests.

In your GraphQL resolvers, you can execute any code that needs to talk to your database.

```graphql
const resolvers = {
  Query: {
    executeInsertReportRequest() {  
      return db.execute('select insert_report_request();');
    }
  }
}
```

## **[How to Perform Database Migrations using Go Migrate](https://www.freecodecamp.org/news/database-migration-golang-migrate/)**

### What is a Database Migration?

A database migration, also known as a schema migration, is a set of changes to be made to a structure of objects within a relational database.

It is a way to manage and implement incremental changes to the structure of data in a controlled, programmatic manner. These changes are often reversible, meaning they can be undone or rolled back if required.

The process of migration helps to change the database schema from its current state to a new desired state, whether it involves adding tables and columns, removing elements, splitting fields, or changing types and constraints.

By managing these changes in a programmatic way, it becomes easier to maintain consistency and accuracy in the database, as well as keep track of the history of modifications made to it.

## Why **[OpenStack](https://microstack.run/)**

We have K8s clusters spanning 3 dell Optiplexes in both Avilla and Albion. So, if one machine breaks the cluster continues to run the report system on the other two.  We also have K8s clusters on various virtual machines on Nutanix and WMware vSphere hypervisors. If one of those virtual machines go down K8s maybe able to run the software on the other nodes but we have not tested this.  If we create an OpenStack cluster on three or more bare Dell R620s we can ensure the report system stays running even if one or more nodes goes down.

How OpenStack differs from other hypervisors is its API.  It is made to be automated and controlled by clients through it's API.
