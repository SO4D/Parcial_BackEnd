FROM alpine:latest as build

RUN apk update
RUN apk add openjdk17

COPY . .
RUN chmod +x ./ApiRestPag_47749-main/gradlew
RUN ./ApiRestPag_47749-main/gradlew bootJar --no-daemon

FROM openjdk:17-alpine
EXPOSE 9000
COPY --from=build ./ApiRestPag_47749-main/build/libs/apiRestSinPaginacion-0.0.1-SNAPSHOT.jar ./app.jar

ENTRYPOINT ["java", "-jar", "app.jar"]
