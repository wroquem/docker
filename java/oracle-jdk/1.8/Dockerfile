FROM centos:centos7

MAINTAINER Warren Roque <wroquem@gmail.com>

#install required packages
RUN yum -y update && \
 yum -y install wget && \
 yum -y install tar

# set Oracle Java8 variables
ENV JAVA_VERSION 8u151
ENV JAVA_BUILD 8u151-b12
ENV JAVA_DL_HASH e758a0de34e24606bca991d704f6dcbf

RUN cd /opt; wget --no-cookies --no-check-certificate --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie" "http://download.oracle.com/otn-pub/java/jdk/${JAVA_BUILD}/${JAVA_DL_HASH}/jdk-${JAVA_VERSION}-linux-x64.tar.gz"
RUN cd /opt; tar -zxf jdk-${JAVA_VERSION}-linux-x64.tar.gz

RUN alternatives --install /usr/bin/java java /opt/jdk1.8.0_151/bin/java 2
RUN alternatives --install /usr/bin/jar jar /opt/jdk1.8.0_151/bin/jar 2
RUN alternatives --install /usr/bin/javac javac /opt/jdk1.8.0_151/bin/javac 2
RUN alternatives --set jar /opt/jdk1.8.0_151/bin/jar
RUN alternatives --set javac /opt/jdk1.8.0_151/bin/javac
	
ENV JAVA_HOME /opt/jdk1.8.0_151 
ENV JRE_HOME /opt/jdk1.8.0_151/jre 
ENV PATH $PATH:/opt/jdk1.8.0_151/bin:/opt/jdk1.8.0_151/jre/bin