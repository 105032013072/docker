FROM test/jdk1.8 
MAINTAINER docker_user docker_user@email.com

RUN apk add --no-cache 'su-exec>=0.2' bash



#install tomcat
ADD apache-tomcat-8.0.30 /opt/apache-tomcat
ENV CATALINA_HOME /opt/apache-tomcat
ENV PATH $CATALINA_HOME/bin:$PATH
RUN mkdir -p "$CATALINA_HOME"
WORKDIR $CATALINA_HOME

RUN set -x\
    && touch ./logs/catalina.log

ENTRYPOINT ./bin/startup.sh && tail -f ./logs/catalina.log
EXPOSE 80



