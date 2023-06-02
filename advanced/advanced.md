# Clients

No need for  HTTP Requests! (but can be used with http)

https://github.com/apollographql/apollo-client (UI!)
https://relay.dev/

# Server

GraphQL.js - you don’t need to specify resolvers when the parent object of the resolver contains a field with the correct name.


Ref: https://www.apollographql.com/blog/graphql/basics/graphql-explained/

Queue up a bunch of fetches if needed!

## Fragments

Colection Fields

Example:

```
type User {
  name: String!
  age: Int!
  email: String!
  street: String!
  zipcode: String!
  city: String!
}

```

Fragment: 

```
fragment addressDetails on User {
  name
  street
  zipcode
  city
}
```

## Default Values

Example:

```
type Query {
  allUsers(olderThan: Int = -1): [User!]!
}
```

## Query Results with Aliases

Error:

```
{
  User(id: "1") {
    name
  }
  User(id: "2") {
    name
  }
}
```

Correct:

```
{
  first: User(id: "1") {
    name
  }
  second: User(id: "2") {
    name
  }
}
```

## Conditional fragments

Example:

```
{
  allPersons {
    name # works for `Adult` and `Child`
    ... on Child {
      school
    }
    ... on Adult {
       work
    }
  }
}

```

## Introspection

Ask for specification

Example:

```
query {
  __schema {
    types {
      name
    }
  }
}
```

## Security

GraphQL server is able to reject or accept a request based on its depth!!

Query Complexity - Query complexity allows you to define how complex these fields are!

Throttling 
1. Based on Server Time
2. Based on Query Complexity

Auth - https://www.prisma.io/blog/graphql-directive-permissions-authorization-made-easy-54c076b5368e

## Errors handling

Example:

```
{
  "data": { ... },
  "errors": [ ... ]
}
```