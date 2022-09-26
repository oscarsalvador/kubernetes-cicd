FROM jenkins/jenkins:lts-slim 

# Pipelines with Blue Ocean UI
USER root
RUN jenkins-plugin-cli --plugins blueocean

ARG MAVEN_VERSION=3.8.4
ARG USER_HOME_DIR="/root"
ARG SHA=a9b2d825eacf2e771ed5d6b0e01398589ac1bfa4171f36154d1b5787879605507802f699da6f7cfc80732a5282fd31b28e4cd6052338cbef0fa1358b48a5e3c8
ARG BASE_URL=https://apache.osuosl.org/maven/maven-3/${MAVEN_VERSION}/binaries
RUN apt-get update \
    && apt-get -y install maven \
    && apt-get -y install curl \
    && apt-get -y install docker

RUN curl -fsSL https://deb.nodesource.com/setup_17.x | bash -
RUN apt-get install -y nodejs

USER jenkins
