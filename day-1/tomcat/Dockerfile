FROM asilnikov:maven-8jdk
LABEL maintainer="Alexey Silnikov"
ARG user=tomcat
ARG group=tomcat
ARG CATALINA_HOME=/opt/tomcat 
ENV CATALINA_HOME $CATALINA_HOME
ENV PATH $CATALINA_HOME/bin:$PATH
RUN groupadd tomcat \
    && useradd -g tomcat -m tomcat \ 
    && apt-get install -y \
    unzip \
    wget \
    && cd /opt \
    && wget https://archive.apache.org/dist/tomcat/tomcat-8/v8.5.47/bin/apache-tomcat-8.5.47.zip \
    && unzip apache-tomcat-8.5.47.zip \
    && rm apache-tomcat-8.5.47.zip \
    && mv apache-tomcat-8.5.47 tomcat \
    && sh -c 'chmod +x tomcat/bin/*.sh' \
    && chown -R tomcat:tomcat /opt/tomcat 
COPY tomcat-users.xml /opt/tomcat/conf/tomcat-users.xml
COPY context.xml /opt/tomcat/webapps/manager/META-INF/context.xml
COPY hello-world-war-1.0.0.war /opt/tomcat/webapps/
WORKDIR /opt/tomcat
EXPOSE 8080
CMD ["catalina.sh", "run"]

