Helidon - Java libs collection for microservices, from Oracle
- cloud-native ready
- fast start-up time
- low memory consumption
- small disk footprint
- full observability stack included by default: health checks, metrics, tracing and logging
- supports GraalVM native image

Two flavours:
1) Helidon SE - functional style, reactive
2) Helidon MP - declarative, depencency injection

## How to use

### Generate code

To start, use mvn archetype (here is for MP version):
```sh
mvn -U archetype:generate -DinteractiveMode=false \
-DarchetypeGroupId=io.helidon.archetypes \
-DarchetypeArtifactId=helidon-quickstart-mp \
-DarchetypeVersion=3.1.0 \
-DgroupId=io.helidon.examples \
-DartifactId=helidon-demo \
-Dpackage=io.helidon.examples.quickstart.mp
```

### Build

Build it:
```sh
mvn package
```

It creates small helidon-demo.jar (name taken from artefactId param above) in the target directory.
- small jar containing business logic in target directory - allows many small fast (and cheap) deploys
- other jars in target/lib directory - infrastructure that you deploy only once (in a while)

### Run

Run the app:
```sh
java -jar target/helidon-demo.jar
```

### Try it
```sh
curl -X GET http://localhost:8080/greet {"message":"Hello World!"} 
curl -X GET http://localhost:8080/greet/Joe {"message":"Hello Joe!"} 
curl -X PUT -H "Content-Type: application/json" -d '{"greeting" : "Hola"}' http://localhost:8080/greet/greeting 
curl -X GET http://localhost:8080/greet/Jose {"message":"Hola Jose!"}
```

You also get health and metrics for free:
```sh
curl -s -X GET http://localhost:8080/health
curl -s -X GET http://localhost:8080/metrics
curl -H 'Accept: application/json' -X GET http://localhost:8080/metrics
```
