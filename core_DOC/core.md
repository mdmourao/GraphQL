# Core Concepts

SDL 
https://www.prisma.io/blog/graphql-sdl-schema-definition-language-6755bcb9ce51

```
type Person {
    id: ID!
    name: String!
    age: Int!
}
```

```
type Post {
    title: String!
}
```

(!) - Required field

## Relation

```
type Person {
    name: String!
    age: Int!
    posts: [Post!]!
}
```

```
type Post {
    title: String!
    author: Person!
}
```

## Query (R)

```
{
    allPerson (last: 2){ // Root Field
        name // Payload
        age
    }
}
```

```
{
    allPerson{ 
        name
        posts {
            title
        }
    }
}
```

## Mutations (CUD)

```
mutation {
    createPerson(name: "Joana", age: 29){ // Root Field
        id // this field will be returned!
    }
}
```

## Subscriptions!!! (nice)

Keep connection open to the server.
Event-based realtime functionality

```
subscription {
    newPerson{
        name
        age
    }
}
```

## GraphQL Schema

Defines API capabilities
Contract client-server
Special Root Types

## Types

String
Int
Float
Boolean
ID

Enums
Interface
Union Types


### Root Types

Query
Mutation
Subscription

### Examples

```
type Query {
    allPersons(last: Int) : [Person!]!
    allPosts(last: Int) : [Post!]!
}
```

```
type Mutation {
    createPerson(name: String!, age: Int!) : Person!
    updatePerson(id: ID!, name: String!, age: Int!) : Person!
}
```

```
type Subscription {
    newPerson() : Person!
    updatedPerson() : Person!
}
```

