FROM maven:3.8.5-openjdk-17 AS build

WORKDIR /app

COPY . .

RUN mvn clean package

FROM openjdk:17-alpine

COPY --from=build /app/target/loans-0.0.1-SNAPSHOT.jar .

EXPOSE 8090

ENTRYPOINT ["java","-jar","loans-0.0.1-SNAPSHOT.jar"]
