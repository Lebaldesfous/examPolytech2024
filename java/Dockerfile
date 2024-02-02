FROM maven:3.9-eclipse-temurin-8 AS builder

WORKDIR /app

COPY . .

RUN mvn clean package -DskipTests

FROM eclipse-temurin:8-jre

WORKDIR /app

COPY --from=builder /app/target/java-*.jar backend.jar

EXPOSE 8448

LABEL maintaineur="Guillaume HUET"

CMD ["java", "-jar" ,"backend.jar"]
