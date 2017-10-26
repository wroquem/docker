FROM wroquem/oracle-jdk:8

MAINTAINER Warren Roque <wroquem@gmail.com>

ENV CATALINA_HOME /opt/tomcat
ENV PATH $CATALINA_HOME/bin:$PATH
RUN mkdir -p "$CATALINA_HOME"
WORKDIR $CATALINA_HOME

#TOMCAT_BASE_URLS
#https://www-us.apache.org
#https://www-eu.apache.org
#https://www.apache.org

ENV TOMCAT_BASE_URLS https://www-us.apache.org
ENV TOMCAT_MAJOR 8
ENV TOMCAT_VERSION 8.5.23

#TOMCAT_TARGZ_URLS
#https://www-us.apache.org/dist/tomcat/tomcat-${TOMCAT_MAJOR}/v${TOMCAT_VERSION}/bin/apache-tomcat-${TOMCAT_VERSION}.tar.gz
#https://www-eu.apache.org/dist/tomcat/tomcat-${TOMCAT_MAJOR}/v${TOMCAT_VERSION}/bin/apache-tomcat-${TOMCAT_VERSION}.tar.gz
#https://www.apache.org/dist/tomcat/tomcat-${TOMCAT_MAJOR}/v${TOMCAT_VERSION}/bin/apache-tomcat-${TOMCAT_VERSION}.tar.gz

RUN wget ${TOMCAT_BASE_URLS}/dist/tomcat/tomcat-${TOMCAT_MAJOR}/v${TOMCAT_VERSION}/bin/apache-tomcat-${TOMCAT_VERSION}.tar.gz && \
	tar -xvf apache-tomcat-${TOMCAT_VERSION}.tar.gz && \
	rm apache-tomcat*.tar.gz && \
	mv apache-tomcat* ${CATALINA_HOME}
 
EXPOSE 8080

# Launch Tomcat
CMD ["${CATALINA_HOME}/bin/catalina.sh", "run"]
