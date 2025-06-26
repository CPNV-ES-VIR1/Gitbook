# Lec03 - Writing Docker File

## Pedagogical intent

After reviewing the principles of virtualization and the basics of Docker, it's time to build our first images.

Here are the contents of this theoretical part:

* Best practices Docker,
* Layer concept,
* Multi-stage build,
* Studying a first Docker file (for java)

## Best Practices

{% embed url="https://docs.docker.com/develop/develop-images/guidelines/" %}

## Layer concept

{% embed url="https://docs.docker.com/build/guide/layers/" %}

## Muti-stage build

{% embed url="https://docs.docker.com/build/building/multi-stage/" %}

## Docker File Sample

```docker
## syntax=docker/dockerfile:1
FROM eclipse-temurin:21.0.2_13-jdk-jammy AS builder
WORKDIR /opt/app
COPY .mvn/ .mvn
COPY mvnw pom.xml ./
RUN ./mvnw dependency:go-offline
COPY ./src ./src
RUN ./mvnw clean install

FROM eclipse-temurin:21.0.2_13-jre-jammy AS final
WORKDIR /opt/app
EXPOSE 8080
COPY --from=builder /opt/app/target/*.jar /opt/app/*.jar
ENTRYPOINT ["java", "-jar", "/opt/app/*.jar"]
```

### Analyzis

* How many layers will the image contain?
* How many stages?
* Are you able to describe each step?



