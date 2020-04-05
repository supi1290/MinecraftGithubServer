FROM alpine:latest

LABEL description "Minecraft Forge Server"

# this fork is maintained by supi1290
MAINTAINER Haider Sebastian <haider.sebastian.michael@gmail.com>

WORKDIR /opt/mcserver

RUN echo "## Installing base ##" && \
    echo "@main http://dl-cdn.alpinelinux.org/alpine/edge/main/" >> /etc/apk/main && \
    echo "@testing http://dl-cdn.alpinelinux.org/alpine/edge/testing/" >> /etc/apk/repositories && \
    echo "@community http://dl-cdn.alpinelinux.org/alpine/edge/community/" >> /etc/apk/repositories && \
    apk upgrade --update-cache --available && \
    \
    apk add --force \
        bash@main \
        gcc@main \
        git@main \
        libc-dev@main \
        libstdc++@main \
        openjdk8-jre@community \
        tini@community \
        unzip@main

COPY docker-entrypoint.sh /opt/mcserver

ENTRYPOINT ["/sbin/tini", "--", "./docker-entrypoint.sh"]