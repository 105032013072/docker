FROM daocloud.io/library/alpine:latest

MAINTAINER docker_user docker_user@email.com

WORKDIR /tmp
 
RUN apk --update add  ca-certificates tar bash wget && \
    wget -q -O /etc/apk/keys/sgerrand.rsa.pub https://raw.githubusercontent.com/sgerrand/alpine-pkg-glibc/master/sgerrand.rsa.pub && \
   wget https://github.com/sgerrand/alpine-pkg-glibc/releases/download/2.23-r3/glibc-2.23-r3.apk && \
   apk add glibc-2.23-r3.apk && \
  apk del ca-certificates tar wget && \
  rm -rf /tmp/* /var/cache/apk/*