# Use OpenJDK 17 as the base image
FROM eclipse-temurin:17-jdk-alpine

# Set the working directory inside the container
WORKDIR /app

# Copy the JAR file from the target directory
COPY target/patient-service-0.0.1-SNAPSHOT.jar app.jar

# Expose the port that the application runs on
EXPOSE 8081

# Run the application
ENTRYPOINT ["java", "-jar", "app.jar"]