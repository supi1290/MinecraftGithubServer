FROM alpine:latest

LABEL description "Minecraft Forge Server"

# this fork is maintained by supi1290
MAINTAINER Haider Sebastian <haider.sebastian.michael@gmail.com>

WORKDIR /opt/ts3server

COPY docker-entrypoint.sh /opt/ts3server

ENTRYPOINT ["/sbin/tini", "--", "./docker-entrypoint.sh"]