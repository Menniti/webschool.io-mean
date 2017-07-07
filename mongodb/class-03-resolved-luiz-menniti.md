# MongoDB - Aula 03 - Exercicio
autor: Luiz Menniti

## Listagem pokemons **menor que 0.5** (passo 1)

```
db.pokemons.find({height: {$lt:0.5}})
{ "_id" : ObjectId("5834b3a028bd8f88db226238"), "name" : "caterpie", "description" : "catepiando", "attack" : 5, "defense" : 9, "height" : 0.3 }

```

## Listagem pokemons **maior igual que 0.5** (passo 2)

```
db.pokemons.find({height: {$gte:0.5}})
{ "_id" : ObjectId("58166effe902b522bf84dcf8"), "name" : "Bulbassauro", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 1, "type" : "grama", "active" : "FODASE", "moves" : [ "investida", "hgoho", "ae" ] }
{ "_id" : ObjectId("58166f3ae902b522bf84dcf9"), "name" : "Mew", "description" : "Pokemon que parece um nene feio", "attack" : 30, "defense" : 130, "height" : 1, "active" : "FODASE", "moves" : [ "investida", "hgoho", "ae" ] }
{ "_id" : ObjectId("58166f5ee902b522bf84dcfa"), "name" : "Articuno", "description" : "Passo Lendario New description", "attack" : 1530, "defense" : 2130, "height" : 2, "active" : "FODASE", "moves" : [ "investida", "hgoho", "ae" ] }
{ "_id" : ObjectId("58166f8ce902b522bf84dcfb"), "name" : "Jolteon", "description" : "Cachorro picachu", "attack" : 130, "defense" : 230, "height" : 1, "active" : "FODASE", "moves" : [ "investida", "hgoho", "ae" ] }
{ "_id" : ObjectId("58166face902b522bf84dcfc"), "name" : "Machop", "description" : "marombinha do milhao", "attack" : 230, "defense" : 130, "height" : 1, "active" : "FODASE", "moves" : [ "investida", "hgoho", "ae" ] }
{ "_id" : ObjectId("58173394c666abebec71f8a6"), "name" : "Bulbassauro", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 1, "active" : "FODASE", "moves" : [ "investida", "hgoho", "ae" ] }
{ "_id" : ObjectId("581733c7c666abebec71f8a7"), "name" : "Pikachu", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 1, "active" : "FODASE", "moves" : [ "investida", "hgoho", "ae" ] }
{ "_id" : ObjectId("5834ae3d28bd8f88db226235"), "name" : "bulbasauro", "description" : "bulba", "attack" : 15, "defense" : 19, "height" : 1.5 }
{ "_id" : ObjectId("5834aeaa28bd8f88db226236"), "name" : "Moltres", "description" : "Molts fogo", "attack" : 215, "defense" : 219, "height" : 3.5 }
{ "_id" : ObjectId("5834b35428bd8f88db226237"), "name" : "diglete", "description" : "digletando", "attack" : 5, "defense" : 9, "height" : 0.5 }

```

## Listagem pokemons **menor igual 0.5 E do tipo grama** (passo 3)

```
var poke = db.pokemons.find({ $and: [{height: {$lte:0.5}}, {type:'grama'}]})
db.pokemons.findOne(poke)
{ "_id" : ObjectId("58166effe902b522bf84dcf8"), "name" : "Bulbassauro", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 0.1, "type" : "grama", "active" : "FODASE", "moves" : [ "investida", "hgoho", "ae" ] }

```

## Listagem de **name:Pokemon ou attack menor ou igual 0.5** (passo 4)

```

db.pokemons.find({$or: [{name:'Pikachu'}, {attack: {$lte:0.5}}]})
{ "_id" : ObjectId("581733c7c666abebec71f8a7"), "name" : "Pikachu", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 1, "active" : "FODASE", "moves" : [ "investida", "hgoho", "ae" ] }



```

## Listagem de **pokemons com attack <= 48 E height <= 0.5** (passo 5)

```

> db.pokemons.find({$and: [{attack:{$gte:48}}, {height: {$lte:0.5}}]})
{ "_id" : ObjectId("58166effe902b522bf84dcf8"), "name" : "Bulbassauro", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 0.1, "type" : "grama", "active" : "FODASE", "moves" : [ "investida", "hgoho", "ae" ] }

```