# =====================================================================
# Jenkins with DooD (Docker outside of Docker) and integration maven
# =====================================================================
FROM openjdk:8-jdk-alpine

ARG MAVEN_VERSION=3.6.0 \
  MAVEN_SHA=fae9c12b570c3ba18116a4e26ea524b29f7279c17cbaadc3326ca72927368924d9131d11b9e851b8dc9162228b6fdea955446be41207a5cfc61283dd8a561d2f \
  MAVEN_BASE_URL=https://apache.osuosl.org/maven/maven-3/${MAVEN_VERSION}/binaries

ENV MAVEN_HOME /usr/share/maven \
  JENKINS_HOME $JENKINS_HOME

