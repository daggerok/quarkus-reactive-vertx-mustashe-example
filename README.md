# quarkus k8s reactive vertx [![Build Status](https://travis-ci.org/daggerok/quarkus-reactive-vertx-mustashe-example.svg?branch=master)](https://travis-ci.org/daggerok/quarkus-reactive-vertx-mustashe-example)
Handlebars with reactive Vertx quarkus

## getting started

### local development

```bash
./mvnw quarkus:dev
http :8080
```

### jar

```bash
./mvnw clean compile quarkus:build
java -jar target/*-runner.jar
http :8080
```

### jvm in docker

```bash
./mvnw clean compile quarkus:build
docker build -f src/main/docker/Dockerfile.jvm -t daggerok/jvm-app .
docker run -i --rm -p 8080:8080 --name app daggerok/jvm-app
http :8080
docker rm -f -v app
```

### native in docker

```bash
./mvnw package -Pnative -Dquarkus.native.container-build=true
docker build -f src/main/docker/Dockerfile.native -t daggerok/native-app .
docker run -i --rm -p 8080:8080 --name app -v "$(pwd)/src/main/resources/templates:/work/templates" daggerok/native-app
http :8080
docker rm -f -v app
```

## features

* native app
* global headers
* mustache reactive vertx handlebars templating

## resources

* [vertx-web-examples](https://github.com/vert-x3/vertx-examples/tree/master/web-examples)
* [vertx templates](https://vertx.io/docs/vertx-web/java/#_templates)
* [vertx web](https://vertx.io/docs/vertx-web/java/)
* https://vertx.io/docs/vertx-web/java/#_capturing_path_parameters
