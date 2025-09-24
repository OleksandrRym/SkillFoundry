FROM openjdk:25-jdk AS builder

WORKDIR /app
COPY . .

RUN ./mvnw clean package -DskipTests

FROM openjdk:25-jdk

WORKDIR /app
COPY --from=builder /app/target/*.jar app.jar

ENTRYPOINT ["java", "-jar", "app.jar"]