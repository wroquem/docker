FROM wroquem/open-jdk:1.8

MAINTAINER Warren Roque <wroquem@gmail.com>

#TOMCAT_TARGZ_URLS
#https://www-us.apache.org/dist/tomcat/tomcat-${TOMCAT_MAJOR}/v${TOMCAT_VERSION}/bin/apache-tomcat-${TOMCAT_VERSION}.tar.gz
#https://www-eu.apache.org/dist/tomcat/tomcat-${TOMCAT_MAJOR}/v${TOMCAT_VERSION}/bin/apache-tomcat-${TOMCAT_VERSION}.tar.gz
#https://www.apache.org/dist/tomcat/tomcat-${TOMCAT_MAJOR}/v${TOMCAT_VERSION}/bin/apache-tomcat-${TOMCAT_VERSION}.tar.gz

#TOMCAT_MIRRORS_URLS
#https://www-us.apache.org
#https://www-eu.apache.org
#https://www.apache.org

ENV TOMCAT_MIRROR_URL https://www-us.apache.org
ENV TOMCAT_MAJOR 8
ENV TOMCAT_VERSION 8.5.23
ENV CATALINA_HOME /opt/tomcat

RUN echo "Installing Tomcat ${TOMCAT_VERSION}..." && \
wget -nv ${TOMCAT_MIRROR_URL}/dist/tomcat/tomcat-${TOMCAT_MAJOR}/v${TOMCAT_VERSION}/bin/apache-tomcat-${TOMCAT_VERSION}.tar.gz -O /tmp/tomcat.tgz && \
tar xzf /tmp/tomcat.tgz -C /opt && \
mv /opt/apache-tomcat-${TOMCAT_VERSION} ${CATALINA_HOME} && \
rm /tmp/tomcat.tgz


ENV PATH $PATH:$CATALINA_HOME/bin

EXPOSE 8080

# Launch Tomcat
CMD ["/opt/tomcat/bin/catalina.sh", "run"]