# ✅ Use Java 17 lightweight base image
FROM eclipse-temurin:17-jre-alpine

# 💡 Set the working directory inside the container
WORKDIR /opt/app

# 🔄 ARG lets you pass the JAR path during build (defaults to standard)
ARG artifact=target/spring-boot-web.jar

# 🗂 Copy the JAR into the container
COPY ${artifact} app.jar

# 🚀 Run the app
ENTRYPOINT ["java", "-jar", "app.jar"]
