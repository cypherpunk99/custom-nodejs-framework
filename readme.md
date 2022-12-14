Configuration system  
Request processing, routing (similar to Express.js)  
Ability to add middlewares  
Handling different types of requests  
Working with databases (implement reading / writing to the Mongo database)  
Return of results (types: json, blob, stream)  
Sending static files // res.sendFile  
Error processing  
Logging  
  
Instructions
------------

start mongodb for mac: 

```
brew services start mongodb-community
```
Setup server-framework

```
cd server-framework && npm i
```

How to start server

```
cd my-server && npm i && npm start
```

config file format
```
{
  "appPort": 8000,              // port server starts
  "dbConfig": {
    "mongoUrl": "",             // mongo connection url 
    "dbName": "credential",     // db name 
    "collName": "credentials",  // collection name
    "validatorObj": {}          // collection validation object 
  },
  "logger": {
    "errorFile": "error.log",   // file with error logs
    "combinedFile": "combined.log", // other logs
    "env": "production"         // hardcoded ENV
  }
}
```
examples

```
curl -X POST http://localhost:8000/products/ -H 'Content-Type: application/json' -d '{"login":"my_login","password":"my_password"}' // id from mongodb

curl -X 'GET' 'http://localhost:8000/protected' // Unauthorized
curl -X 'GET' 'http://localhost:8000/protected' -H 'Authorization: a123' // protected route

etc..
```

