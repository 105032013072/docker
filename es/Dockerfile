FROM test/jdk1.8

MAINTAINER docker_user docker_user@email.com

#RUN yum -y install unzip

RUN apk add --no-cache 'su-exec>=0.2' bash

#install es
ENV esversion elasticsearch-2.4.1
copy $esversion /opt/$esversion
RUN chmod -R 777 /opt/$esversion

#modify configuration file
RUN { \
   echo 'bootstrap.memory_lock: true';\
   echo 'network.host: 0.0.0.0';\
}>>/opt/$esversion/config/elasticsearch.yml

#modify service file
RUN {\
 echo 'ES_STARTUP_SLEEP_TIME=5';\
 echo 'ES_HEAP_SIZE=8g';\
 echo 'MAX_OPEN_FILES=65535';\
 echo 'MAX_LOCKED_MEMORY=unlimited';\
}>>/opt/$esversion/bin/elasticsearch


#install ik for es
RUN mkdir -p /opt/$esversion/plugins/elasticsearch-analysis-ik
ADD elasticsearch-analysis-ik-1.10.1.zip /opt
RUN unzip /opt/elasticsearch-analysis-ik-1.10.1.zip -d /opt/$esversion/plugins/elasticsearch-analysis-ik
RUN rm -f /opt/elasticsearch-analysis-ik-1.10.1.zip


RUN addgroup -S es && adduser -S -G es es
RUN chown es /opt/$esversion
USER es

CMD ["/opt/elasticsearch-2.4.1/bin/elasticsearch"]
EXPOSE 9200
EXPOSE 9300


EXPOSE 9200
EXPOSE 9300
