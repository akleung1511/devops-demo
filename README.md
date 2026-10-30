# devops-demo

## Single-stage Build

- Maven builds the Java JAR.
- Docker build creates the Docker image.
- Docker run creates and starts a container.

## Single-stage vs Multi-stage Docker Builds

A single-stage Docker build requires me to build the Spring Boot JAR locally before Docker copies it into an image.

In a multi-stage Docker build, Maven runs inside Docker during the first stage to compile the application and create the JAR file.

In the second stage, Docker copies the compiled JAR into a separate Java runtime image, which can then be used to run a container.

The benefit of multi-stage builds is that the build process is automated, and the final image does not need to include Maven and its build tools.

