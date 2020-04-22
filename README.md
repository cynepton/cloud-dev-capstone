# GitHub link
https://github.com/cynepton/cloud-dev-capstone

# Serverless Science Record App

Serverless Science Record App is an application that allows scientists and researchers to keep a log of all their findings and also attach images. The aaplication is built off code from Udacity's Cloud Developer Nanodegree Program.

## Functionality 

- The application allows users to create, update, delete research entry items.
- The application allows users to upload a file. 
- The application only displays entries created by the user currently logged in.
- A user needs to authenticate in order to use an application

## Codebase

- The code is split into multiple layers separating business logic from I/O related code.
- Code is implemented using async/await and Promises without using callbacks.

## Best Pratices

- All AWS resources in the application are defined in the `serverless.yml` file.
- Each function has its own set of permissions.
- Application has sufficient monitoring.
- HTTP requests are validated.

## Architecture

- Data is stored in a table with a composite key.

```
KeySchema:
      - AttributeName: partitionKey
        KeyType: HASH
      - AttributeName: sortKey
        KeyType: RANGE
```

- items are fetched using the `query()` method and not `scan()` method (which is less efficient on large datasets)


# How to run the application

## Backend

To deploy an application run the following commands:

```
cd backend
npm install
npx serverless deploy -v
```

## Client

To run a client application first edit the `client/src/config.ts` file to set correct parameters. And then run the following commands:

```
cd client
npm install
npm run start
```
In case of any errors while running the start script, install react dependencies with
```
npm install react-scripts --save-dev
```
