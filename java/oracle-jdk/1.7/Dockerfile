FROM centos:centos7

MAINTAINER Warren Roque <wroquem@gmail.com>

#install required packages
RUN yum -y update && \
 yum -y install wget && \
 yum -y install tar

RUN echo "Download Oracle JDK ${JAVA_VERSION}..." && \
wget http://ftp.osuosl.org/pub/funtoo/distfiles/oracle-java/jdk-7u80-linux-x64.tar.gz -O /tmp/jdk-${JAVA_VERSION}.tgz && \
tar xzf /tmp/jdk-${JAVA_VERSION}.tgz -C /opt && \
rm /tmp/jdk-${JAVA_VERSION}.tgz

RUN alternatives --install /usr/bin/java java /opt/jdk1.7.0_80/bin/java 2
RUN alternatives --install /usr/bin/jar jar /opt/jdk1.7.0_80/bin/jar 2
RUN alternatives --install /usr/bin/javac javac /opt/jdk1.7.0_80/bin/javac 2
RUN alternatives --set jar /opt/jdk1.7.0_80/bin/jar
RUN alternatives --set javac /opt/jdk1.7.0_80/bin/javac
	
ENV JAVA_HOME /opt/jdk1.7.0_80
ENV JRE_HOME /opt/jdk1.7.0_80/jre 
ENV PATH $PATH:/opt/jdk1.7.0_80/bin:/opt/jdk1.7.0_80/jre/bin