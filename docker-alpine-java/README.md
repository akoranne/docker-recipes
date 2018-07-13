# Docker Alpine Java

This project is to create a java alpine image.

## Pre-requisites
* Download `Java Cryptography Extension (JCE) Unlimited Strength Jurisdiction Policy Files from Oracle` zip and unzip in local folder called `files`.

## Build the image
```
  $ docker build --tag=alpine-java:base --rm=true .
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
   $ docker tag 76bb2c4a6eaf askxtreme/alpine-java:base
```

* push the image to docker hub
```
   $ docker push askxtreme/alpine-java:base
```

## Docker image

[askxtreme/alpine-java](https://hub.docker.com/r/askxtreme/alpine-java)


#### References / Credit
* [Dockerizing a Spring Boot Applciation](http://www.baeldung.com/dockerizing-spring-boot-application)
* [Pushing and Pulling to and from Docker Hub](https://ropenscilabs.github.io/r-docker-tutorial/04-Dockerhub.html)
