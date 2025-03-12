FROM maven:3.9.4-eclipse-temurin-21-alpine AS builder
WORKDIR /app
COPY src /app/
COPY pom.xml /app/
RUN mvn clean package D.maven.test.skip=true

FROM elcipse-temurin:21:mbopm/temurin-alpine
WORKDIR /app
COPY --from=builder /app/target/*.jar /app//app/spring-petclinic-discovery-server.jar
EXPOSE 8761
CMD ["java", "-jar", "/app//app/spring-petclinic-discovery-server.jar"]


