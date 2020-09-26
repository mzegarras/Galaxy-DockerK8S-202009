

FROM openjdk:11.0.8-slim

EXPOSE 8080

ADD ./app.jar app.jar
VOLUME /application.yml

ENTRYPOINT ["java","-jar","app.jar","--spring.config.location=/application.yml"]
