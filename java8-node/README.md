# Docker Alpine Node Java

This project is to create a alpine image with node, and java.

It also has following packages ...

- markdown-pdf : convert '.md' to 'pdf' files
- newman : for running smoke-test against endpoints.


## Pre-requisites
* This docker image is built from `mhart/alpine-node:latest` image
* Download `Java Cryptography Extension (JCE) Unlimited Strength Jurisdiction Policy Files from Oracle` zip and unzip in local folder called `files`.

## Build the image
```
  $ docker build --tag=java8-node:base --rm=true .
```

## Run the image 
```
  $ docker run java8-node:base node --version
  v10.6.0

  $ docker run java8-node:base npm --version
  6.1.0

  $ docker run java8-node:base java -version
  openjdk version "1.8.0_171"
  OpenJDK Runtime Environment (IcedTea 3.8.0) (Alpine 8.171.11-r0)
  OpenJDK 64-Bit Server VM (build 25.171-b11, mixed mode)

  $ docker run java8-node:base markdown-pdf --version
  8.1.1

  $ docker run java8-node:base newman --version
  3.10.0
```

```
  # run interactively
  $ docker run -it java8-node:base /bin/sh
```

## Upload the image to docker hub
* login to your docker hub account
```
   $ docker login --username=yourhubusername --email=youremail@company.com
   $ docker login --username=askxtreme
```    

* tag the created image
```
   $ docker images
   $ docker tag 76bb2c4a6eaf askxtreme/java8-node:base
```

* push the image to docker hub
```
   $ docker push askxtreme/java8-node:base
```

## Docker image

* [askxtreme/java8-node](https://hub.docker.com/r/askxtreme/java8-node)
* [mhart/alpine-node](https://hub.docker.com/r/mhart/alpine-node)


#### References / Credit
* [Minimal Node.js Docker Images built on Alpine Linux](https://github.com/mhart/alpine-node)
* [Dockerizing a Spring Boot Applciation](http://www.baeldung.com/dockerizing-spring-boot-application)
* [Pushing and Pulling to and from Docker Hub](https://ropenscilabs.github.io/r-docker-tutorial/04-Dockerhub.html)
