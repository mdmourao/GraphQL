# GraphQL GO Tutorial


## Commands

```
go run github.com/99designs/gqlgen init
DEFINE SCHEMA
go run github.com/99designs/gqlgen generate (*1)
go run server.go

```
Go to - http://localhost:8080/

(*1) - edit graph/schema.resolvers.go file and delete functions CreateTodo and Todos. Now run the command again.


Link: https://www.howtographql.com/graphql-go/1-getting-started/

## Files

gqlgen.yml — The gqlgen config file, knobs for controlling the generated code.


graph/generated/generated.go — The GraphQL execution runtime, the bulk of the generated code.


graph/model/models_gen.go — Generated models required to build the graph. Often you will override these with your own models. Still very useful for input types.


graph/schema.graphqls — This is the file where you will add GraphQL schemas.


graph/schema.resolvers.go — This is where your application code lives. generated.go will call into this to get the data the user has requested.


server.go — This is a minimal entry point that sets up an http.Handler to the generated GraphQL server. start the server with go run server.go and open your browser and you should see the graphql playground, So setup is right!