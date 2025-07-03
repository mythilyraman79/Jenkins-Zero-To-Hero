# Use Maven with Java 17 as base image
FROM maven:3.9.6-eclipse-temurin-17

# Install Docker CLI tools (to allow Docker commands inside container)
USER root
RUN apt-get update && \
    apt-get install -y docker.io && \
    apt-get clean

# Set working directory (used by Jenkins and/or application)
WORKDIR /app

# Optional: add Maven dependencies cache (improves rebuild times)
COPY pom.xml .
RUN mvn dependency:go-offline

# Copy entire project if you're building here (optional)
# COPY . .

# Copy the built JAR (runtime use)
ARG artifact=target/spring-boot-web.jar
COPY ${artifact} app.jar

# Use this only if you're running the app directly from this image
ENTRYPOINT ["java", "-jar", "app.jar"]
