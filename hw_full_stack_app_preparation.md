# Homework: Full Stack Games Hub App

### Learning Objectives

- Understand the relationship between client, server and database
- Be able to navigate a codebase that you haven't written

## Brief

Your boss has asked to you look over the codebase of a full-stack JavaScript application. The front-end is written in JavaScript using React, the back-end uses an Express server and a MongoDB database. Your task is to make yourself familiar with the codebase.

The application includes a README.md with instructions on running the application.

![Overview of the tech stack and tooling with commands](images/tech_stack_with_commands.png)

*Overview of the tech stack and tooling with commands*

*EDIT: Frontend is now written in React with the command to run `npm start`*

## MVP

### Task

Draw a diagram showing the dataflow through the application starting with a form submission, ending with the re-rendering of the page. This will involve a multi-direction data-flow with the client posting data to the server and the server sending data back to the client with the response. Detail the client, server and database in the diagram and include the names of the files involved in the process.

### Questions

1. What is responsible for defining the routes of the `games` resource?
ANSWER: 'gamesRouter' which is an instance of our 'CreateRouter'

2. What do you notice about the folder structure?  Whats the client responsible for? Whats the server responsible for?
ANSWER: The folders structure separates the concerns, making it easier for us to navigate through our files. The information stored within the client folder is responsible for everything that the user/client sees(front end) and the server folder holds all the files responsible for the back end stuff. 

3. What are the the responsibilities of server.js?
ANSWER: 'server.js' is responsible for configuring the server. 
We tell the server to use the npm package 'bodyParser' which allows us us to extract the body from POST/PUT requests. 
It allows us to delegate the routing for our games resource and we could easily add additional resources and create additional modular routers here. 
It listens for requests being made on the specific port. 
Allows us to configure our server to use CORS.
Connects to the database 'games_hub' using MongoDB

4. What are the responsibilities of the `gamesRouter`?
ANSWER: It defines the routes of our application.

5. What process does the the client (front-end) use to communicate with the server?
ANSEWR: The client sends fetch requests to the server. 

6. What optional second argument does the `fetch` method take? And what is it used for in this application? Hint: See [Using Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) on the MDN docs
ANSWER: The fetch method can optionally accept a second parameter, an init object that allows you to control a number of different settings. In this application, there is an exammple of a POST request passing fetch an object that specifies the body type as json. 

7. Which of the games API routes does the front-end application consume (i.e. make requests to)?
ANSWER: GET, POST, DELETE

8. What are we using the [MongoDB Driver](http://mongodb.github.io/node-mongodb-native/) for?
ANSWER: The official MongoDB Node.js driver allows Node.js applications to connect to MongoDB and work with data. The driver features an asynchronous API which allows you to interact with MongoDB using Promises or via traditional callbacks.

## Extension

Why do we need to use [`ObjectId`](https://mongodb.github.io/node-mongodb-native/api-bson-generated/objectid.html) from the MongoDB driver?

Add to your diagram the dataflow for removing a game.
