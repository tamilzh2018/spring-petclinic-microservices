FROM maven:3.9.4-eclipse-temurin-21-alpine AS builder
WORKDIR /app
COPY src /app/
COPY pom.xml /app/
RUN mvn clean package -Dmaven.test.skip=true

FROM eclipse-temurin:21-alpine
WORKDIR /app
COPY --from=builder /app/target/*.jar /app/spring-petclinic-customers-service.jar
EXPOSE 8082
CMD ["java", "-jar", "/app/spring-petclinic-customers-service.jar"]
