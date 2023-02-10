* **JAX-RS**

maps HTTP requests to Java methods

```java
@GET
@Path("items")
@Produces(MediaType.APPLICATION_JSON)
public Set<Item> getAllItems() {
	//...
}

@POST
@Consumes(MediaType.APPLICATION_JSON)
public Response createItem() {
	//...
}
```

* **JSON-B**

binds JSON to classes

```java
public static void main(String[] args) { 
	// Create a dog instance 
	Dog dog = new Main.Dog(); 
	dog.name = "Falco"; 
	dog.age = 4; 
	dog.bitable = false; 
	
	// Create Jsonb and serialize 
	Jsonb jsonb = JsonbBuilder.create(); 
	String result = jsonb.toJson(dog);
	
	System.out.println(result); 
	
	// Deserialize back
	dog = jsonb.fromJson("{\"name\":\"Falco\",\"age\":4,\"bitable\":false}", Dog.class); 
}
```

* **JSON-P**

parses JSON to Map-like structure

```java
public static void main(String[] args) { 
	// Create Json and serialize
	JsonObject json = Json.createObjectBuilder() 
		.add("name", "Falco") 
		.add("age", BigDecimal.valueOf(3)) 
		.add("biteable", Boolean.FALSE).build(); 
	String result = json.toString();
	
	System.out.println(result);
}
```


* **CDI**

makes your code leaner and more testable

```java
@Inject
ItemRepository repository;
```

