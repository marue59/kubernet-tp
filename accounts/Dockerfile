FROM maven:3.8.5-openjdk-17 AS build

WORKDIR /app

COPY . .

#COPY pom.xml .

RUN mvn clean package
RUN ls target

FROM openjdk:17-alpine

COPY --from=build /app/target/accounts-0.0.1-SNAPSHOT.jar .

EXPOSE 8080

ENTRYPOINT ["java","-jar","accounts-0.0.1-SNAPSHOT.jar"]
