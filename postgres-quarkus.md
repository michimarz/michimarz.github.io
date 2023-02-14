# Using Postgres database with Quarkus app

Maven dependencies you need to add to connect your Quarkus application to a PostgreSQL database using Hibernate Panache:

```xml
<dependency>
	<groupId>io.quarkus</groupId>
	<artifactId>quarkus-hibernate-orm-panache</artifactId>
</dependency>
<dependency>
	<groupId>io.quarkus</groupId>
	<artifactId>quarkus-jdbc-postgresql</artifactId>
</dependency>
```

Another way to add these dependencies to pom.xml file is to run a maven command:
```sh
./mvnw quarkus:add-extension -Dextensions="quarkus-hibernate-orm-panache,quarkus-jdbc-postgresql"
```

or Quarkus CLI command:

```sh
quarkus-cli add quarkus-hibernate-orm-panache quarkus-jdbc-postgresql
```


You also need to configure the database connection details in your `application.properties` or `application.yaml` file:

```text
quarkus.datasource.url=jdbc:postgresql://<host>:<port>/<database> quarkus.datasource.username=<username> quarkus.datasource.password=<password> quarkus.datasource.driver=org.postgresql.Driver
```

