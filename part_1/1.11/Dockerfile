FROM openjdk:8

WORKDIR /app

## Copy the project files
COPY . .

# Build the project
RUN ./mvnw package

# Set the entrypoint to run the application with Java
ENTRYPOINT ["java", "-jar", "./target/docker-example-1.1.3.jar"]

EXPOSE 8080
