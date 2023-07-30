#Project overview for DockerCompose
##Creating a baseimage for backend and client 
 1.Creating Docker baseImage in Dockerfile for both the backend and client 
 2.Used apline as my base to reduce image size
 3.Also used .dockerignore files to reduce size of the docker images
###Process of creating the Dockerfile
 [a].defined alpine as my base image
 [b].created my working directory
 [c] copied the necessary package.json
 [d] installed depedencies
 [e] run npm command to start the application
###Tagging and uploading to dockerhub 
 1. Pushed docker images to dockerhub and tagged them
##Creating Docker-compose.yaml
 1. Docker-compose.yaml was created to manage different services in the microservices
 2. Created a mongodb image for the database containers
 3. Created a network and volume to persist for the created containers
