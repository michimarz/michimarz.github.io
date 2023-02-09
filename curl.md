Basic one. Gives me the result of a HTTP request:

```sh
curl http://localhost:8080/pokemons
```

This one prints HTTP response headers first.

```sh
curl http://localhost:8080/pokemons -i
```

And this one get rids of the % signs at the ends of lines.

```sh
curl -w "\n" http://localhost:8080/pokemons
```

POST request:

```sh
curl http://localhost:8080/pokemons -i -XPOST -H 'Content-Type: application/json'  -d '{"name":"Gyarados", "types":["water", "flying"]}'
```



