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

  $ docker run java8-node:base jfrog --version
  1.17.1

```

```
  # run interactively
  $ docker run -it java8-node:base /bin/bash
  root@57c80c276344:/# jfrog
    NAME:
       jfrog - See https://github.com/jfrog/jfrog-cli-go for usage instructions.
    
    USAGE:
       jfrog [global options] command [command options] [arguments...]
    
    VERSION:
       1.17.1
    
    COMMANDS:
       rt		Artifactory commands
       bt		Bintray commands
       mc		Mission Control commands
       xr		Xray commands
       help, h	Shows a list of commands or help for one command
    
    GLOBAL OPTIONS:
       --help, -h		show help
       --version, -v	print the version
    
    Environment Variables:
    	JFROG_CLI_LOG_LEVEL
    		[Default: INFO]
    		This variable determines the log level of the JFrog CLI.
    		Possible values are: INFO, ERROR, and DEBUG.
    		If set to ERROR, JFrog CLI logs error messages only.
    		It is useful when you wish to read or parse the JFrog CLI output and do not want any other information logged.
    
    	JFROG_CLI_OFFER_CONFIG
    		[Default: true]
    		If true, JFrog CLI prompts for product server details and saves them in its config file.
    		To avoid having automation scripts interrupted, set this value to false, and instead,
    		provide product server details using the config command.
    
    	JFROG_CLI_HOME
    		[Default: ~/.jfrog]
    		Defines the JFrog CLI home directory path.
    
    
  root@57c80c276344:/#
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


#### References / Credit
* [Minimal Node.js Docker Images built on Alpine Linux](https://github.com/mhart/alpine-node)
* [Dockerizing a Spring Boot Applciation](http://www.baeldung.com/dockerizing-spring-boot-application)
* [Pushing and Pulling to and from Docker Hub](https://ropenscilabs.github.io/r-docker-tutorial/04-Dockerhub.html)
