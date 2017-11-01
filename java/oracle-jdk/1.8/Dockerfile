FROM centos:centos7

MAINTAINER Warren Roque <wroquem@gmail.com>

#install required packages
RUN yum -y update && \
 yum -y install wget && \
 yum -y install tar

#set Oracle Java8 variables
ENV JAVA_VERSION 8u151
ENV JAVA_BUILD 8u151-b12
ENV JAVA_DL_HASH e758a0de34e24606bca991d704f6dcbf
ENV ORACLE_MIRROR_URL http://download.oracle.com

RUN mkdir -p /usr/lib/jvm && \
echo "Download Oracle JDK ${JAVA_VERSION}..." && \
wget --no-cookies --no-check-certificate --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie" "${ORACLE_MIRROR_URL}/otn-pub/java/jdk/${JAVA_BUILD}/${JAVA_DL_HASH}/jdk-${JAVA_VERSION}-linux-x64.tar.gz" -O /tmp/jdk-${JAVA_VERSION}.tgz && \
tar xzf /tmp/jdk-${JAVA_VERSION}.tgz -C /usr/lib/jvm && \
rm /tmp/jdk-${JAVA_VERSION}.tgz

RUN alternatives --install /usr/bin/java java /usr/lib/jvm/jdk1.8.0_151/bin/java 2
RUN alternatives --install /usr/bin/jar jar /usr/lib/jvm/jdk1.8.0_151/bin/jar 2
RUN alternatives --install /usr/bin/javac javac /usr/lib/jvm/jdk1.8.0_151/bin/javac 2
RUN alternatives --set jar /usr/lib/jvm/jdk1.8.0_151/bin/jar
RUN alternatives --set javac /usr/lib/jvm/jdk1.8.0_151/bin/javac

ENV JAVA_HOME /usr/lib/jvm/jdk1.8.0_151
ENV JRE_HOME /usr/lib/jvm/jdk1.8.0_151/jre
ENV PATH $PATH:${JAVA_HOME}:${JRE_HOME}/bin