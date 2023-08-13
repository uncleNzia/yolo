# **Project overview for DockerCompose**

## **Creating a baseimage for backend and client**
 1.Creating Docker baseImage in Dockerfile for both the backend and client 
 2.Used apline as my base to reduce image size
 3.Also used .dockerignore files to reduce size of the docker images 

### **Process of creating the Dockerfile**
 1.defined alpine as my base image
 2.created my working directory
 3.copied the necessary package.json
 4.installed depedencies
 5.run npm command to start the application

### Tagging and uploading to dockerhub 
 1. Pushed docker images to dockerhub and tagged them

## **Creating Docker-compose.yaml**
 1. Docker-compose.yaml was created to manage different services in the microservices
 2. Created a mongodb image for the database containers
 3. Created a network and volume to persist for the created containers

# **Using Ansible to Provision Vagrant for Docker Node.js**
The process of using Ansible to provision a Vagrant virtual machine (VM) for Docker. THe project has backend and cliend containers spinned up. Ansible is a powerful automation tool that helps set up and configure systems, while Vagrant simplifies the creation and management of VMs. 

###  Prerequistes
Make sure the following is installed
   1. Vagrant: Download and install Vagrant from https://www.vagrantup.com/.
   2. VirtualBox: Install VirtualBox from https://www.virtualbox.org/.
   3. Ansible: Install Ansible using your package manager or pip.

##  **Creating your working directory and intializing vagrant**
 Create and cd into your working directory. 
  In the root directory intialize vagrant using vagrant init which creates a vagrantfile

##  **Editing the Vagrantfile**
Open the vagrantfile in text editor and modify the following
   1.the vm base image
   2.the virtual network and ip-address
   3.virtualbox as the provider
   4.the ansible playbook for provision
This creates vagrant vms using ubuntu2004 as the baseimage and necessary network

##  **Creating hosts file**
Create hosts file in the root directory to specify your web server and db server as well as the chosen private ip-addresses

##  **Creating the roles**
Create roles directory
### 1.clone-dependencies role
Create roles for installing software dependencies and cloning the git repo. This downloads all software needed including docker, git and docker-compose. I have used variable for the git URL to hide it and specificied it in the vars folder.
### 2.client role
Create its directory and cd into it. This role builds and runs docker containers from the specified dockerimage for the client side.
### 3.backend role
Create its directory and cd into it. This role builds and runs docker containers from the specified dockerimage for the backend side.

##  **Create the Ansible Playbook**
In the root project directory, create a new file called playbook.yml. This playbook will contain the tasks to provision the VM with Docker and Node.js. Instead i have used my roles [clone-dependencies, client and backend] and set my user as root 

### Run ansible-playbook -i playbook.yml 
 THis runs the playbook in your project directory and start the vm using ansible. 
