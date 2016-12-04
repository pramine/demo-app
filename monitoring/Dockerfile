FROM java:8

MAINTAINER Pradeep <pradeep@mail.com>

VOLUME /tmp

ADD target/conference-monitoring*.jar monitoring.jar

RUN bash -c 'touch /monitoring.jar’

ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/monitoring.jar”]
