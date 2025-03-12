FROM eclipse-temurin:17
WORKDIR /app
COPY target/spring-petclinic-discovery-server-3.4.1.jar /app/discovery-server.jar
EXPOSE 8761
CMD ["java", "-jar", "/app/discovery-server.jar"]

