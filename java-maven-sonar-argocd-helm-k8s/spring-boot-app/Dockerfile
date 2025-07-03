# Use Java 17 runtime
FROM eclipse-temurin:17-jre-alpine

# Define the location of the built jar file
ARG artifact=target/spring-boot-web.jar

# Set working directory
WORKDIR /opt/app

# Copy the jar to the container
COPY ${artifact} app.jar

# Run the jar
ENTRYPOINT ["java", "-jar", "app.jar"]
