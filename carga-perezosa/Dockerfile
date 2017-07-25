FROM centos-config
MAINTAINER Harold Jimenez, alexjf197@gmail.com

ENV SERVICE_HOME /con
ENV SERVICE_VERSION 1.0.0
ENV SERVICE_GROUP com.gco.siconline
ENV SERVICE_ARTIFACT siconline-oleada-services
ENV SERVICE_PORT 8084
ENV JAVA_OPTS="-Xmx1024m -Xms512m -server"

RUN mvn org.apache.maven.plugins:maven-dependency-plugin:2.8:get -Dartifact=$SERVICE_GROUP:$SERVICE_ARTIFACT:$SERVICE_VERSION:jar -Dtransitive=false -Ddest=$SERVICE_HOME/$SERVICE_ARTIFACT.jar
COPY application.properties $SERVICE_HOME/application.properties

ENTRYPOINT [ "sh", "-c", "cd $SERVICE_HOME && java $JAVA_OPTS -Djava.security.egd=file:/dev/./urandom -jar  $SERVICE_HOME/$SERVICE_ARTIFACT.jar" ]

EXPOSE $SERVICE_PORT


