FROM maven:3.6.0-jdk-8-alpine
RUN ln -snf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo Asia/Shanghai > /etc/timezone
COPY settings.xml /usr/share/maven/ref/