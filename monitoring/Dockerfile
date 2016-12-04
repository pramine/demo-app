FROM java:8

MAINTAINER Pradeep <pradeep@mail.com>

VOLUME /tmp

ADD target/conference-monitoring*.war monitoring.war

RUN bash -c 'touch /monitoring.war'

ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/monitoring.war"]
