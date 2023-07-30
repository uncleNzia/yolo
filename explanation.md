Creating Docker baseImage in Dockerfile for both the backend and client 
Used apline as my base to reduce image size
Also used .dockerignore files to reduce size of the docker images
Pushed docker images to dockerhub and tagged them
Docker-compose.yaml was created to manage different services in the microservices
Created a mongodb image for the database containers
Created a network and volume to persist for the created containers
