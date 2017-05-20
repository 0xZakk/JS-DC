# Deployment

## Class Structure
- Welcome to Class
- Do the warm up exercise
- Go over Learning Objectives
- Deliver Lesson
- Go over Learning Objectives
- Review the Final Project
- Closing Questions / Tying up loose ends
- Exit Tickets

## Install Docker for Mac or Docker for Windows
-- https://docs.docker.com/docker-for-mac/install/
-- https://docs.docker.com/docker-for-windows/install/

## Single Page Applications

An application delivered to the browser that doesn't reload the page during use.

We can think of a fat client that's loaded from a web server.

### Architecture
Weight:
  - we started with just the client
  - we then worked our way backwards, adding a server and then a database
  - then we built full stack applications that used all three of these, but the majority of our logic lived in the middle ( in the server )
  - that's how a lot of applications work today
  - SPAs fatten up or push a lot of logic to the client here

What kind of logic might we want to push to the client?
  - views/rendering
  - simple calculations and data manipulation


## Introduction to Microservices and Containers

__Monolithic Applications:__  Single-tiered software applications in which the user interface and data access code are combined into a single program from a single platform - no modularity.

Modularity is desirable, in general, as it supports reuse of parts of the application logic and also facilitates maintenance by allowing repair or replacement of parts of the application without requiring wholesale replacement.

__Microservices:__ Google, Amazon, Netflix etc have all moved to Microservices. Microservices are designed to encapsulate a core business capability. The architecture is a method of developing the application as a suite of independently deployable, small, modular services in which each service runs a unique process and communicates through a well-defined, lightweight mechanism to serve a business goal.

__Containers:__ Containers and Microservices are not the same thing. Containers encapsulate discrete components of application logic provisioned only with the minimal resources needed to do their job.

They are an alternative to virtual machines, which require entire embedded operating systems.

Containers allow you to easily package an application's code, configurations, and dependencies into easy to use building blocks that deliver environmental consistency, operational efficiency, developer productivity, and version control

Containers make calls for OS resources through an API

Containerisation is OS-level virutalisation. VMs run on hypervisors, with fully embedded operating systems.

How do Microservices and Containers relate? A Microservice may run in a container, but it could as run as a fully provisioned VM. A container need not be used for a microservice.

Containers are a good way of developing and deploying microservices, and the tools and platforms for running containers are a good way to manage microservice-based applications.

## Start getting familiar with Docker - 10 minutes ( students do on their own )
https://github.com/docker/labs/blob/master/beginner/chapters/setup.md

First do the setup, then proceed to 1.0 - Running your first container

__Images__ - The file system and configuration of our application which are used to create containers.

__Containers__ - Running instances of Docker images — containers run the actual applications. A container includes an application and all of its dependencies. It shares the kernel with other containers, and runs as an isolated process in user space on the host OS.

__Docker daemon__ - The background service running on the host that manages building, running and distributing Docker containers.

__Docker client__ - The command line tool that allows the user to interact with the Docker daemon.

__Docker Hub__ - A registry of Docker images. You can think of the registry as a directory of all available Docker images. You'll be using this later in this tutorial.


## Code along with containers

__Flask App__: Follow along (20 minutes) Starts at 2.3
https://github.com/docker/labs/blob/master/beginner/chapters/alpine.md
- Navigate to the flask-app folder in exercises
- Create the necessary files and add the code

__Debugging Node.js__: Follow along (10 minutes)
- Exercise-1
- All of the necessary files are there, we are going to do a debugging exercise
https://github.com/docker/labs/blob/master/developer-tools/nodejs-debugging/VSCode-README.md

## Break

## Deployment - Quick Intro

## Deployment - Now with Dockerfile

Deploy a docker app with Now

https://zeit.co/now#whats-now
https://zeit.co/blog/now-dockerfile

-npm install -g now
-mkdir
-Touch Dockerfile
-Touch index.html
  -Add some content
-Add to Dockerfile:

FROM kstaken/apache2
LABEL name "my-docker-deployment"
RUN apt-get update && apt-get install -y php5 libapache2-mod-php5 php5-mysql php5-cli && apt-get clean && rm -rf /var/lib/apt/lists/*
COPY index.html /var/www
EXPOSE 80
CMD ["/usr/sbin/apache2", "-D", "FOREGROUND"]

- Run 'now' every time you want to deploy

## Deployment - Github Pages

Github Pages - 10/15 minutes - Exercise 2
- Students follow instructions on github pages to create their own portfolio repos
https://pages.github.com/

## Deployment - AWS

Intro to AWS - 15 minutes
- Introduce AWS and explain some of the high level options it offers
- Have the students set up their AWS accounts
  -http://docs.aws.amazon.com/gettingstarted/latest/deploy/setting-up.html
- Install the EB CLI with brew install
  - http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-install-osx.html
  - There are separate installs for mac and windows available
- Create and IAM role: http://docs.aws.amazon.com/gettingstarted/latest/deploy/setting-up.html#create-role

Start up our first deployment: 15 minutes
- $ mkdir HelloWorld
- $ cd HelloWorld
- $ eb init -p PHP
- $ echo "Hello World" > index.html
- $ eb create dev-env
- $ eb open


Deploy a more advanced application (we do): 20 minutes
- Follow along the instructions within the cloned repo in the exercises folder (eb-node-express-signup): http://docs.aws.amazon.com/gettingstarted/latest/deploy/overview.html
- Students do Setting Up through DynamoDB Table on their own
- We come back together at Step 2


Introduce MLab  - 10 mins
- Have everyone create accounts - Help them integrate it into the tunr solution
- Remember you have to create a user every time you make a new db so you can access it in code
- The port must match the deployment configuration - 8081 is AWS common
- Bundle the application files and save to desktop in a compressed file

Deploy the SPA Tunr solution - we do : ~20 minutes
- Have everyone create a new db instance for Tunr on mlab - save the config info
- Edit the Exercise-3 file so it has access to their own credentials
- Open the AWS console: https://us-west-2.console.aws.amazon.com/elasticbeanstalk/home?region=us-west-2#/applications
- Create new application
- Create new environment


## You Do: Deploy Todo App
