FROM centos:centos7

MAINTAINER Warren Roque <wroquem@gmail.com>

#install required packages
RUN yum -y update && \
 yum -y install wget && \
 yum -y install tar && \
 yum -y install zip && \
 yum -y install unzip

RUN mkdir -p /usr/lib/jvm && \
echo "Download Oracle JDK ${JAVA_VERSION}..." && \
wget http://ftp.osuosl.org/pub/funtoo/distfiles/oracle-java/jdk-7u80-linux-x64.tar.gz -O /tmp/jdk-${JAVA_VERSION}.tgz && \
tar xzf /tmp/jdk-${JAVA_VERSION}.tgz -C /usr/lib/jvm && \
rm /tmp/jdk-${JAVA_VERSION}.tgz

RUN alternatives --install /usr/bin/java java /usr/lib/jvm/jdk1.7.0_80/bin/java 2
RUN alternatives --install /usr/bin/jar jar /usr/lib/jvm/jdk1.7.0_80/bin/jar 2
RUN alternatives --install /usr/bin/javac javac /usr/lib/jvm/jdk1.7.0_80/bin/javac 2
RUN alternatives --set jar /usr/lib/jvm/jdk1.7.0_80/bin/jar
RUN alternatives --set javac /usr/lib/jvm/jdk1.7.0_80/bin/javac
	
ENV JAVA_HOME /usr/lib/jvm/jdk1.7.0_80
ENV JRE_HOME /usr/lib/jvm/jdk1.7.0_80/jre
ENV PATH $PATH:${JAVA_HOME}:${JRE_HOME}/bin
