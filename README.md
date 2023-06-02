# GraphQL (created by Facebook)

New API standard

Alternative to REST
1. More Efficient (no over/underfetching - less unused data and endpoints)
2. More Powerful
3. More Flexible


Enables Declarative Data Fetching - Client can specify what data it needs from the API!

Only exposes ONE endpoint! (client uses queries)

Analytics - evolving API (removing unused features)

GraphQL uses strong type system (define API)

Advantages:
Reduced data transfer (client asks only for the required information!)

# GraphQL VS REST

Example BLOG app (w/ user name, user post, user followers)

REST - 3 Requests (to get the user name we will need to request a lot of needed data that is useless)

GraphQL - 1 Request (with all information)

Query

```
query {
    User(id: "iusfgh"){
        name
        posts{
            title
        }
        followers(last: 3){
            name
        }
    }
}
```

Return 

```
{
    "data":{
        "User":{
            "name":"Joana",
            "posts":[...],
            followers:[...]
        }
    }
}
```


Refs:

https://github.com/graphql/graphiql
https://www.prisma.io/blog/graphql-sdl-schema-definition-language-6755bcb9ce51
https://github.com/graphql/graphql-playground