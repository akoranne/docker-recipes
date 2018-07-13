# get alpine edge from docker hub
FROM alpine:edge

MAINTAINER askxtreme

# install openjdk 8
RUN apk add --no-cache openjdk8

# unlimited cryptography policy
COPY files/UnlimitedJCEPolicyJDK8/* /usr/lib/jvm/java-1.8-openjdk/jre/lib/security/
