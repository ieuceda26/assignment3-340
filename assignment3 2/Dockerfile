FROM eclipse-temurin:25-jdk-alpine AS build
WORKDIR /app
COPY . .
RUN ./mvnw clean package -DskipTests


FROM eclipse-temurin:25-jre-alpine
WORKDIR /app
COPY --from=build /app/target/*.jar assignment3.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "assignment3.jar"]
