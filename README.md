
# Developping with Docker


## What it does:

This application shows a user profile set up using:
<ul>
  <li>index.html with pure js and css style</li>
  <li>nodejs backend with express module</li>
  <li>mongodb for datastorage</li>
</ul>

All components are docker-based

## What I have learned:
<ul>
  <li>How to use docker commands</li>
  <li>How to write a docker-compose file</li>
  <li>How to Dockerize an application with Dockerfile</li>
</ul>

## How to run ?

### With Docker

 Step1: Create a docker Network <br/>
  `docker network create mongo-network` <br/>
  
 Step 2: start mongodb <br/>
 `docker run -d -p 27017:27017 -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=password --name mongodb --net mongo-network mongo` <br/>
 
 Step 3: start mongo-express <br/>
 `docker run -d -p 8081:8081 -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin -e ME_CONFIG_MONGODB_ADMINPASSWORD=password --net mongo-network --name mongo-express -e ME_CONFIG_MONGODB_SERVER=mongodb mongo-express` <br/>
  
 Step 4: open mongo-express from browser <br/>
`http://localhost:8081` <br/>

 Step 5: create user-account db and users collection in mongo-express <br/>
 
 Step 6:  go to app directory of project and start your nodejs application: <br/>
``` 
npm install 
node server.js
``` 

Step 7: Access you nodejs application UI from browser <br/>
`http://localhost:3000`
