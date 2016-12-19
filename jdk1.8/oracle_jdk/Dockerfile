FROM test/glibc

MAINTAINER docker_user docker_user@email.com

WORKDIR /tmp


RUN apk --update add unzip wget bash 



#install JDK1.8
RUN apk --update add unzip wget bash && \
     wget --no-check-certificate --no-cookies --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u111-b14/jdk-8u111-linux-x64.tar.gz && \
         tar zxvf jdk-8u111-linux-x64.tar.gz && \
         mv jdk1.8.0_111/jre /jre && \
       rm /jre/bin/jjs && \
  rm /jre/bin/keytool && \
  rm /jre/bin/orbd && \
  rm /jre/bin/pack200 && \
  rm /jre/bin/policytool && \
  rm /jre/bin/rmid && \
  rm /jre/bin/rmiregistry && \
  rm /jre/bin/servertool && \
  rm /jre/bin/tnameserv && \
  rm /jre/bin/unpack200 && \
  rm /jre/lib/ext/nashorn.jar && \
  rm /jre/lib/jfr.jar && \
  rm -rf /jre/lib/jfr && \
  rm -rf /jre/lib/oblique-fonts && \
  rm jdk-8u111-linux-x64.tar.gz && \
  rm -rf jdk1.8.0_111 && \
  apk del unzip wget && \
 rm -rf /tmp/* /var/cache/apk/*  



ENV JAVA_HOME /jre
ENV PATH=$JAVA_HOME/bin:$PATH