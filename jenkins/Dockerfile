# Jenkins with DooD (Docker outside of Docker)
FROM jenkins/jenkins:alpine
USER root
RUN apk --update add docker \
  && apk add shadow \
  && usermod -aG docker jenkins
USER jenkins