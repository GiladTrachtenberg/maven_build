FROM maven:3.6.3-jdk-8 AS build

WORKDIR /usr/jav
COPY . .

RUN mvn clean install && mvn verify 

FROM openjdk:8-jre 

COPY --from=0 /usr/jav/target/hello-java.jar /usr/jav/target/hello-java.jar
ENTRYPOINT ["java","-jar","/usr/jav/target/hello-java.jar"]

