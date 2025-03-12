FROM maven:3.9.4-eclipse-temurin-21-alpine as builder
WORKDIR /app
COPY src /app/src
COPY pom.xml /app
RUN mvn clean package _Dmaven.test.skip=true

FROM eclipse-temurin:21-alpine
WORKDIR /app
COPY --from=builder /app/target/*.jar /app/spring-petclinic-admin-server.jar
EXPOSE 8081
CMD ["java", "-jar", "/app/spring-petclinic-admin-server.jar"]
