FROM daocloud.io/library/alpine:latest

MAINTAINER docker_user docker_user@email.com

 
RUN apk --update add  ca-certificates tar bash wget
 
#COPY glibc-2.21-r2.apk .
#COPY glibc-bin-2.21-r2.apk .

RUN wget -q -O /etc/apk/keys/sgerrand.rsa.pub https://raw.githubusercontent.com/sgerrand/alpine-pkg-glibc/master/sgerrand.rsa.pub
RUN wget https://github.com/sgerrand/alpine-pkg-glibc/releases/download/2.23-r3/glibc-2.23-r3.apk
RUN apk add glibc-2.23-r3.apk 
