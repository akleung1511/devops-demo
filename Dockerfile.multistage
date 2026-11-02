# First stage: Build with Maven
FROM maven:3.9-eclipse-temurin-21 AS build

WORKDIR /app

COPY . .

RUN mvn clean install -DskipTests

# Second stage: Create slim runtime image
FROM eclipse-temurin:21-jdk-alpine

ENV PORT=8080

COPY --from=build /app/target/*.jar /app.jar

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "/app.jar"]