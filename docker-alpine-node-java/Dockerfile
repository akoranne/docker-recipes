# get alpine edge from docker hub
FROM mhart/alpine-node:latest

MAINTAINER askxtreme

# install openjdk 8
RUN apk add --no-cache openjdk8

# unlimited cryptography policy
COPY files/UnlimitedJCEPolicyJDK8/* /usr/lib/jvm/java-1.8-openjdk/jre/lib/security/

# install some required packages
RUN npm install -g markdown-pdf newman --unsafe-perm=true --allow-root

