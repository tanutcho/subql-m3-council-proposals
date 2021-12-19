# SubQuery - Module 3 Lesson 2 : Councilor Proposals

The package for tutorial in module 3 lesson 2 from Hero course (SubQuery project)

This example for Many to many entities showcase

## Preparation

#### Environment

- [Typescript](https://www.typescriptlang.org/) are required to compile project and define types.  

- Both SubQuery CLI and generated Project have dependencies and require [Node](https://nodejs.org/en/).
     

#### Install the SubQuery CLI

Install SubQuery CLI globally on your terminal by using NPM:

```
npm install -g @subql/cli
```

Run help to see available commands and usage provide by CLI
```
subql help
```

Last, under the project directory, run following command to install all the dependency.
```
yarn install
```


#### Code generation

In order to index your SubQuery project, it is mandatory to build your project first.
Run this command under the project directory.

````
yarn codegen
````

## Build the project

In order to deploy your SubQuery project to our hosted service, it is mandatory to pack your configuration before upload.
```
yarn build
```

## Indexing and Query

#### Run required systems in docker


Under the project directory run following command:

```
docker-compose pull && docker-compose up
```
#### Query the project

Open your browser and head to `http://localhost:3000`.

Finally, you should see a GraphQL playground is showing in the explorer and the schemas that ready to query.

Run following graphql script to query the sample of this package

````graphql
{
  query{
    councillors(first:3 orderBy:NUMBER_OF_VOTES_DESC){
      nodes{
        id,
        numberOfVotes,
        voteHistory(first:5){
          totalCount
          nodes{
            approvedVote
          }
        }
      }
    }
  }
}
````
