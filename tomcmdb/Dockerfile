FROM tomcat:9.0.74-jre17-temurin-jammy

#MOVEMOS WEBAPPS
RUN mv /usr/local/tomcat/webapps /usr/local/tomcat/webapps2
RUN mv /usr/local/tomcat/webapps.dist /usr/local/tomcat/webapps

#COPIA ARCHIVOS CONF
COPY ./files/context.xml /usr/local/tomcat/webapps/manager/META-INF/context.xml
COPY ./files/tomcat-users.xml /usr/local/tomcat/conf/tomcat-users.xml
COPY ./files/cmdbuild-3.4.1.war /usr/local/tomcat/webapps/cmdbuild-3.4.1.war
COPY ./files/postgresql-42.4.1.jar /usr/local/tomcat/lib/postgresql-42.4.1.jar

#INSTALACION TOMCAT
RUN apt-get update && \
    apt-get install postgresql-client -y

#CAMBIAMOS PERMISO
RUN groupadd tomcat && \
    useradd -s /bin/false -g tomcat -d /usr/local/tomcat tomcat && \
    chown -RH tomcat: /usr/local/tomcat
  
USER tomcat

#PORT
EXPOSE 8080
