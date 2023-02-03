We can set the "scope" property in pom.xml as provided:
```xml
	<scope>provided</scope>
```
That tells maven to build only a thin jar (or war) without including the dependencies.
This is possible because the application servers already have those libraries included.
In other words, we only have to deploy our application, leaving out the whole runtime infrastructure. We use one that is **provided** by the application server.

So:
- we build our jar locally using the libraries installed on our machine
- we deploy the thin jar to the remote application server
- the application server uses its own included libraries to execute our jar

Main idea:
- I don't care if I change from Payara to another server - as long as it conforms to the Jakarta EE standards, the app will run on it, and I only need to deploy a small jar




