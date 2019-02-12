FROM maven:3.6.0-jdk-8-alpine

COPY settings.xml /usr/share/maven/ref/

RUN apk add --no-cache tzdata \
  && cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo Asia/Shanghai > /etc/timezone \
  && apk del tzdata