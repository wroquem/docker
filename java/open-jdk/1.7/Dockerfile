FROM centos:centos7

MAINTAINER Warren Roque <wroquem@gmail.com>

#install required packages
RUN yum -y update	&& \
	yum -y install wget	&& \
	yum -y install tar	&& \
 yum -y install zip	&& \
	yum -y install unzip
 
RUN yum -y install java-1.7.0-openjdk-devel

ENV JAVA_HOME /usr/lib/jvm/java-1.7.0-openjdk
ENV JRE_HOME /usr/lib/jvm/java-1.7.0-openjdk/jre
ENV PATH $PATH:${JAVA_HOME}:${JRE_HOME}/bin
