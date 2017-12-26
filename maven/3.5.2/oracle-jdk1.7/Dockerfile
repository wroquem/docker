FROM wroquem/oracle-jdk:1.7

MAINTAINER Warren Roque <wroquem@gmail.com>

WORKDIR /opt

ENV MAVEN_VERSION 3.5.2

RUN curl -fsSL https://archive.apache.org/dist/maven/maven-3/$MAVEN_VERSION/binaries/apache-maven-$MAVEN_VERSION-bin.tar.gz | tar xzf - -C /opt
RUN ln -s /opt/apache-maven-$MAVEN_VERSION /opt/maven
RUN ln -s /opt/maven/bin/mvn /usr/bin/mvn

ENV MAVEN_HOME /opt/maven