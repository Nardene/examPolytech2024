# Partie permettant la generation d'un .jar
FROM maven:3-eclipse-temurin-8-alpine as maven
WORKDIR /app
COPY . .
RUN mvn clean package -DskipTests

FROM eclipse-temurin:8-jre-alpine  	

WORKDIR /usr/src/app

COPY --from=maven /app/target/java-0.0.1-SNAPSHOT.jar .

CMD ["java","-jar","java-0.0.1-SNAPSHOT.jar"]

LABEL maintainer="vincent_remy"