
# Father's direction

I love you and will help you to have a loving heart!  I will give you courage and help you to bear each trial and endure every hardship my son.  Do not forget that you are part of a community and want you to learn to love each person.

## Schema-Driven Development

In GraphQL your API starts with a schema that defines all your types, queries and mutations, It helps others to understand your API. So it’s like a contract between server and the client. Whenever you need to add a new capability to a GraphQL API you must redefine schema file and then implement that part in your code. GraphQL has its Schema Definition Language for this purpose. gqlgen is a Go library for building GraphQL servers and has a nice feature that generates code based on your schema definition.

## Getting Started

What are you going to build?

In this tutorial we are going to create a Hackernews clone with Go and gqlgen, So our API will be able to handle registration, authentication, submitting links and getting list of links.

### Project Setup

Create a directory for project and initialize go modules file:

```bash
pushd .
cd ~/src
git clone git@github.com:brentgroves/hackernews.git
cd hackernews
go mod init github.com/brentgroves/hackernews
```

after that use ‍‍gqlgen init command to setup a gqlgen project.

```bash
go run github.com/99designs/gqlgen init
```

<https://github.com/99designs/gqlgen>
