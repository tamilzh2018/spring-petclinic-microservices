FROM maven:3.9.4-eclipse-temurin:21 AS builder
WORKDIR /app
COPY src /app/
COPY pom.xml /app/
RUN mvn clean package -Dmaven.test.skip=true

FROM eclipse-temurin:21-alpine
WORKDIR /app
COPY --from=builder /app/target/spring-petclinic-genai-service-2.4.5.jar /spring-petclinic-genai-service-2.4.5.jar
EXPOSE 8083
CMD ["java", "-jar", "/spring-petclinic-genai-service-2.4.5.jar"]