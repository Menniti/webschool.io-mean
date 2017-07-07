# MongoDB - Aula 02 - Exercicio
autor: Luiz Menniti

## Listagem das databases (passo 2)

```
use be-mean-pokemons
switched to db be-mean-pokemons

show dbs
be-mean            0.063GB
be-mean-instagram  0.063GB
be-mean-pokemons   0.031GB
be-mean_instagram  0.031GB
local              0.031GB

```

## Listagem de coleções (passo 3)

```
show collections
pokemons
system.indexes
teste

```

## Inserir pokemons (passo 4)

```

var pokemon = {name:'Moltres', description:'Molts fogo', attack:215, defense:219, height:3.5}
db.pokemons.insert(pokemons)
WriteResult({ "nInserted" : 1 })

```
## Listagem de pokemons (passo 5)

```
db.pokemons.find()
{ "_id" : ObjectId("58166effe902b522bf84dcf8"), "name" : "Bulbassauro", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 1, "type" : "grama", "active" : "FODASE", "moves" : [ "investida", "hgoho", "ae" ] }
{ "_id" : ObjectId("58166f3ae902b522bf84dcf9"), "name" : "Mew", "description" : "Pokemon que parece um nene feio", "attack" : 30, "defense" : 130, "height" : 1, "active" : "FODASE", "moves" : [ "investida", "hgoho", "ae" ] }
{ "_id" : ObjectId("58166f5ee902b522bf84dcfa"), "name" : "Articuno", "description" : "Passaro lendário", "attack" : 1530, "defense" : 2130, "height" : 2, "active" : "FODASE", "moves" : [ "investida", "hgoho", "ae" ] }
{ "_id" : ObjectId("58166f8ce902b522bf84dcfb"), "name" : "Jolteon", "description" : "Cachorro picachu", "attack" : 130, "defense" : 230, "height" : 1, "active" : "FODASE", "moves" : [ "investida", "hgoho", "ae" ] }
{ "_id" : ObjectId("58166face902b522bf84dcfc"), "name" : "Machop", "description" : "marombinha do milhao", "attack" : 230, "defense" : 130, "height" : 1, "active" : "FODASE", "moves" : [ "investida", "hgoho", "ae" ] }
{ "_id" : ObjectId("58173394c666abebec71f8a6"), "name" : "Bulbassauro", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 1, "active" : "FODASE", "moves" : [ "investida", "hgoho", "ae" ] }
{ "_id" : ObjectId("581733c7c666abebec71f8a7"), "name" : "Pikachu", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 1, "active" : "FODASE", "moves" : [ "investida", "hgoho", "ae" ] }
{ "_id" : ObjectId("5834ae3d28bd8f88db226235"), "name" : "bulbasauro", "description" : "bulba", "attack" : 15, "defense" : 19, "height" : 1.5 }
{ "_id" : ObjectId("5834aeaa28bd8f88db226236"), "name" : "Moltres", "description" : "Molts fogo", "attack" : 215, "defense" : 219, "height" : 3.5 }

```

## Busque pokemons e insira numa variável poke (passo 6)

```
poke = db.pokemons.findOne({name:'Articuno'})
{
        "_id" : ObjectId("58166f5ee902b522bf84dcfa"),
        "name" : "Articuno",
        "description" : "Passaro lendário",
        "attack" : 1530,
        "defense" : 2130,
        "height" : 2,
        "active" : "FODASE",
        "moves" : [
                "investida",
                "hgoho",
                "ae"
        ]
}

```

## Modifique sua description e salve (passo 7)


```
poke.description = 'Passo Lendario New description'
Passo Lendario New description

db.pokemons.save(poke)
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
poke
{
        "_id" : ObjectId("58166f5ee902b522bf84dcfa"),
        "name" : "Articuno",
        "description" : "Passo Lendario New description",
        "attack" : 1530,
        "defense" : 2130,
        "height" : 2,
        "active" : "FODASE",
        "moves" : [
                "investida",
                "hgoho",
                "ae"
        ]
}

```