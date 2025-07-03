# Start from Maven with Java 17
FROM maven:3.9.6-eclipse-temurin-17

# Install Docker CLI
USER root
RUN apt-get update && \
    apt-get install -y docker.io && \
    apt-get clean

# Set workdir for Jenkins agent use
WORKDIR /app

# Copy JAR only if you're using this as runtime (Spring Boot)
ARG artifact=target/spring-boot-web.jar
COPY ${artifact} app.jar

# Allow dual usage: Jenkins agent and app runner
ENTRYPOINT ["java", "-jar", "app.jar"]
