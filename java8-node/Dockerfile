# get latest openjdk from docker hub
FROM openjdk:latest

MAINTAINER askxtreme

# image already has curl installed

RUN curl -sL https://deb.nodesource.com/setup_9.x | bash - \
  && apt-get install -y nodejs \
  && curl -L https://www.npmjs.com/install.sh | sh


# install some required packages
RUN npm install -g markdown-pdf newman --unsafe-perm=true --allow-root

# install jfrog-cli
RUN curl -fL https://getcli.jfrog.io | sh
