# MongoDB - Aula 04 - Exercicio
autor: Luiz Menniti

## 1.**adicionar** 2 ataques ao mesmo tempo para os seguintes pokemons:
## Pikachu, Squirtle, Bulbassauro, e Charmander (passo 1)

```
var poke_query = { $or: [{name:/Pikachu/i}, {name:/Squirtle/i}, {name:/Charmander/i}, {name:/Bulbassauro/i}] }
poke_query
{
        "$or" : [
                {
                        "name" : /Pikachu/i
                },
                {
                        "name" : /Squirtle/i
                },
                {
                        "name" : /Charmander/i
                },
                {
                        "name" : /Bulbassauro/i
                }
        ]
}

var poke_moves = { $set: {moves: ['chute na bunda', 'voadora na teta']} }
poke_moves
{ "$set" : { "moves" : [ "chute na bunda", "voadora na teta" ] } }

var multi = {multi:true}
multi
{ "multi" : true }

db.pokemons.update(poke_query, poke_moves, multi)
WriteResult({ "nMatched" : 5, "nUpserted" : 0, "nModified" : 5 })

{ "_id" : ObjectId("58166effe902b522bf84dcf8"), "name" : "Bulbassauro", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 0.1, "type" : "grama", "active" : "FODASE", "moves" : [ "chute na bunda", "voadora na teta" ] }
{ "_id" : ObjectId("58166f3ae902b522bf84dcf9"), "name" : "Mew", "description" : "Pokemon que parece um nene feio", "attack" : 30, "defense" : 130, "height" : 1, "active" : "FODASE", "moves" : [ "investida", "hgoho", "ae" ] }
{ "_id" : ObjectId("58166f5ee902b522bf84dcfa"), "name" : "Articuno", "description" : "Passo Lendario New description", "attack" : 1530, "defense" : 2130, "height" : 2, "active" : "FODASE", "moves" : [ "investida", "hgoho", "ae" ] }
{ "_id" : ObjectId("58166f8ce902b522bf84dcfb"), "name" : "Jolteon", "description" : "Cachorro picachu", "attack" : 130, "defense" : 230, "height" : 1, "active" : "FODASE", "moves" : [ "investida", "hgoho", "ae" ] }
{ "_id" : ObjectId("58166face902b522bf84dcfc"), "name" : "Machop", "description" : "marombinha do milhao", "attack" : 230, "defense" : 130, "height" : 1, "active" : "FODASE", "moves" : [ "investida", "hgoho", "ae" ] }
{ "_id" : ObjectId("58173394c666abebec71f8a6"), "name" : "Bulbassauro", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 1, "active" : "FODASE", "moves" : [ "chute na bunda", "voadora na teta" ] }
{ "_id" : ObjectId("581733c7c666abebec71f8a7"), "name" : "Pikachu", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 1, "active" : "FODASE", "moves" : [ "chute na bunda", "voadora na teta" ] }
{ "_id" : ObjectId("58173cc4c666abebec71f8a8"), "name" : "Mew", "active" : "FODASE", "moves" : [ "investida", "hgoho", "ae" ] }
{ "_id" : ObjectId("5834ae3d28bd8f88db226235"), "name" : "bulbasauro", "description" : "bulba", "attack" : 15, "defense" : 19, "height" : 1.5 }
{ "_id" : ObjectId("5834aeaa28bd8f88db226236"), "name" : "Moltres", "description" : "Molts fogo", "attack" : 215, "defense" : 219, "height" : 3.5 }
{ "_id" : ObjectId("5834b35428bd8f88db226237"), "name" : "diglete", "description" : "digletando", "attack" : 5, "defense" : 9, "height" : 0.5 }
{ "_id" : ObjectId("5834b3a028bd8f88db226238"), "name" : "caterpie", "description" : "catepiando", "attack" : 5, "defense" : 9, "height" : 0.3 }
{ "_id" : ObjectId("583629b017e789bec1c1a471"), "name" : "Charmander", "description" : "fogo", "attack" : 15, "defense" : 19, "height" : 1.5, "moves" : [ "chute na bunda", "voadora na teta" ] }
{ "_id" : ObjectId("583629cf17e789bec1c1a472"), "name" : "Squirtle", "description" : "agua", "attack" : 12, "defense" : 13, "height" : 0.5, "moves" : [ "chute na bunda", "voadora na teta" ] }


```

## 2.**Adicionar 1** movimento em todos os pokemons: desvio.

```
var poke_query = {}
poke_query
{ }

var poke_moves = { $pull : {moves: ['desvio'] } }
poke_moves
{ "$pull" : { "moves" : [ "desvio" ] } }

var multi = {multi:true}
multi
{ "multi" : true }

db.pokemons.update(poke_query, poke_moves, multi)
WriteResult({ "nMatched" : 18, "nUpserted" : 0, "nModified" : 18 })

{ "_id" : ObjectId("58166effe902b522bf84dcf8"), "name" : "Bulbassauro", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 0.1, "type" : "grama", "active" : "FODASE", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("58166f3ae902b522bf84dcf9"), "name" : "Mew", "description" : "Pokemon que parece um nene feio", "attack" : 30, "defense" : 130, "height" : 1, "active" : "FODASE", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("58166f5ee902b522bf84dcfa"), "name" : "Articuno", "description" : "Passo Lendario New description", "attack" : 1530, "defense" : 2130, "height" : 2, "active" : "FODASE", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("58166f8ce902b522bf84dcfb"), "name" : "Jolteon", "description" : "Cachorro picachu", "attack" : 130, "defense" : 230, "height" : 1, "active" : "FODASE", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("58166face902b522bf84dcfc"), "name" : "Machop", "description" : "marombinha do milhao", "attack" : 230, "defense" : 130, "height" : 1, "active" : "FODASE", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("58173394c666abebec71f8a6"), "name" : "Bulbassauro", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 1, "active" : "FODASE", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("581733c7c666abebec71f8a7"), "name" : "Pikachu", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 1, "active" : "FODASE", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("5818b8d6c666abebec71f8a9"), "description" : "Pokemon teste", "name" : "testemon", "attack" : 8150, "defense" : 8000, "moves" : [ "desvio" ], "active" : "FODASE" }
{ "_id" : ObjectId("5818d0d383dbe7d7f84ae603"), "active" : "FODASE", "name" : "naoExistMon", "attack" : null, "defense" : null, "height" : null, "description" : "Sem maiores infos", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("5818d1e783dbe7d7f84ae604"), "active" : "FODASE", "name" : "naoExistMon", "attack" : null, "defense" : null, "height" : null, "description" : "Sem maiores infos", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("58173cc4c666abebec71f8a8"), "name" : "Mew", "active" : "FODASE", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("5818cf5f83dbe7d7f84ae602"), "active" : "FODASE", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("5834ae3d28bd8f88db226235"), "name" : "bulbasauro", "description" : "bulba", "attack" : 15, "defense" : 19, "height" : 1.5, "moves" : [ "desvio" ] }
{ "_id" : ObjectId("5834aeaa28bd8f88db226236"), "name" : "Moltres", "description" : "Molts fogo", "attack" : 215, "defense" : 219, "height" : 3.5, "moves" : [ "desvio" ] }
{ "_id" : ObjectId("5834b35428bd8f88db226237"), "name" : "diglete", "description" : "digletando", "attack" : 5, "defense" : 9, "height" : 0.5, "moves" : [ "desvio" ] }
{ "_id" : ObjectId("5834b3a028bd8f88db226238"), "name" : "caterpie", "description" : "catepiando", "attack" : 5, "defense" : 9, "height" : 0.3, "moves" : [ "desvio" ] }
{ "_id" : ObjectId("583629b017e789bec1c1a471"), "name" : "Charmander", "description" : "fogo", "attack" : 15, "defense" : 19, "height" : 1.5, "moves" : [ "desvio" ] }
{ "_id" : ObjectId("583629cf17e789bec1c1a472"), "name" : "Squirtle", "description" : "agua", "attack" : 12, "defense" : 13, "height" : 0.5, "moves" : [ "desvio" ] }
> var poke_moves = { $push : {moves: ['desvio', 'voadora'] } }
> db.pokemons.update(poke_query, poke_moves, multi)
WriteResult({ "nMatched" : 18, "nUpserted" : 0, "nModified" : 18 })
> db.pokemons.find()

{ "_id" : ObjectId("58166f5ee902b522bf84dcfa"), "name" : "Articuno", "description" : "Passo Lendario New description", "attack" : 1530, "defense" : 2130, "height" : 2, "active" : "FODASE", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("58166f8ce902b522bf84dcfb"), "name" : "Jolteon", "description" : "Cachorro picachu", "attack" : 130, "defense" : 230, "height" : 1, "active" : "FODASE", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("58166face902b522bf84dcfc"), "name" : "Machop", "description" : "marombinha do milhao", "attack" : 230, "defense" : 130, "height" : 1, "active" : "FODASE", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("581733c7c666abebec71f8a7"), "name" : "Pikachu", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 1, "active" : "FODASE", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("5834ae3d28bd8f88db226235"), "name" : "bulbasauro", "description" : "bulba", "attack" : 15, "defense" : 19, "height" : 1.5, "moves" : [ "desvio", "investida", "voadora" ] }
{ "_id" : ObjectId("5834aeaa28bd8f88db226236"), "name" : "Moltres", "description" : "Molts fogo", "attack" : 215, "defense" : 219, "height" : 3.5, "moves" : [ "desvio" ] }
{ "_id" : ObjectId("5834b35428bd8f88db226237"), "name" : "diglete", "description" : "digletando", "attack" : 5, "defense" : 9, "height" : 0.5, "moves" : [ "desvio" ] }
{ "_id" : ObjectId("5834b3a028bd8f88db226238"), "name" : "caterpie", "description" : "catepiando", "attack" : 5, "defense" : 9, "height" : 0.3, "moves" : [ "desvio", "investida", "voadora" ] }
{ "_id" : ObjectId("583629b017e789bec1c1a471"), "name" : "Charmander", "description" : "fogo", "attack" : 15, "defense" : 19, "height" : 1.5, "moves" : [ "desvio" ] }
{ "_id" : ObjectId("583629cf17e789bec1c1a472"), "name" : "Squirtle", "description" : "agua", "attack" : 12, "defense" : 13, "height" : 0.5, "moves" : [ "desvio", "investida", "voadora" ] }
{ "_id" : ObjectId("58173cc4c666abebec71f8a8"), "name" : "Mew", "active" : "FODASE", "moves" : [ "desvio", "investida", "voadora" ] }
{ "_id" : ObjectId("58166effe902b522bf84dcf8"), "name" : "Bulbassauro", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 0.1, "type" : "grama", "active" : "FODASE", "moves" : [ "desvio", "investida", "voadora" ] }
{ "_id" : ObjectId("58166f3ae902b522bf84dcf9"), "name" : "Mew", "description" : "Pokemon que parece um nene feio", "attack" : 30, "defense" : 130, "height" : 1, "active" : "FODASE", "moves" : [ "desvio", "investida", "voadora" ] }
{ "_id" : ObjectId("58173394c666abebec71f8a6"), "name" : "Bulbassauro", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 1, "active" : "FODASE", "moves" : [ "desvio", "investida", "voadora" ] }

```

## 3. **Adicionar** o pokemon AindaNaoExisteMon caso ele não exista com todos os dados com o valor null e a descrição: "Sem maiores informações".

```
var poke_query = {name:'AindaNaoExisteMon', "description" : "Sem maiores informacoes", "attack" : null, "defense" : null, "height" : null, "moves" : [ "null" ] }
poke_query
{
        "name" : "AindaNaoExisteMon",
        "description" : "Sem maiores informacoes",
        "attack" : null,
        "defense" : null,
        "height" : null,
        "moves" : [
                "null"
        ]
}

var mod = {$set: {active:true}}
mod
{ "$set" : { "active" : true } }

var options = {upsert:true}
options
{ "upsert" : true }

db.pokemons.update(poke_query, mod,options)
WriteResult({
        "nMatched" : 0,
        "nUpserted" : 1,
        "nModified" : 0,
        "_id" : ObjectId("583634cfe1ee03c20abab20a")
})


db.pokemons.findOne({name: 'AindaNaoExisteMon'})
{
        "_id" : ObjectId("583634cfe1ee03c20abab20a"),
        "attack" : null,
        "defense" : null,
        "description" : "Sem maiores informacoes",
        "height" : null,
        "moves" : [
                "null"
        ],
        "name" : "AindaNaoExisteMon",
        "active" : true
}
> 

```
## 4.Pesquisar todos o pokemons que possuam o ataque investida e mais um que você adicionou, escolha seu pokemon favorito.

```
var poke_moves = { moves: {$in:[/investida/i, /voadora/i]}}
db.pokemons.find(poke_moves)
{ "_id" : ObjectId("5834ae3d28bd8f88db226235"), "name" : "bulbasauro", "description" : "bulba", "attack" : 15, "defense" : 19, "height" : 1.5, "moves" : [ "desvio", "investida", "voadora" ] }
{ "_id" : ObjectId("5834b3a028bd8f88db226238"), "name" : "caterpie", "description" : "catepiando", "attack" : 5, "defense" : 9, "height" : 0.3, "moves" : [ "desvio", "investida", "voadora" ] }
{ "_id" : ObjectId("583629cf17e789bec1c1a472"), "name" : "Squirtle", "description" : "agua", "attack" : 12, "defense" : 13, "height" : 0.5, "moves" : [ "desvio", "investida", "voadora" ] }
{ "_id" : ObjectId("58173cc4c666abebec71f8a8"), "name" : "Mew", "active" : "FODASE", "moves" : [ "desvio", "investida", "voadora" ] }
{ "_id" : ObjectId("58166effe902b522bf84dcf8"), "name" : "Bulbassauro", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 0.1, "type" : "grama", "active" : "FODASE", "moves" : [ "desvio", "investida", "voadora" ] }
{ "_id" : ObjectId("58166f3ae902b522bf84dcf9"), "name" : "Mew", "description" : "Pokemon que parece um nene feio", "attack" : 30, "defense" : 130, "height" : 1, "active" : "FODASE", "moves" : [ "desvio", "investida", "voadora" ] }
{ "_id" : ObjectId("58173394c666abebec71f8a6"), "name" : "Bulbassauro", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 1, "active" : "FODASE", "moves" : [ "desvio", "investida", "voadora" ] }
```


## 5.Pesquisar todos os pokemons que possuam os ataques que você adicionou, escolha seu pokemon favorito.

```
var poke = {moves: {$in : ['desvio']}}
> db.pokemons.find(poke)
{ "_id" : ObjectId("58166f5ee902b522bf84dcfa"), "name" : "Articuno", "description" : "Passo Lendario New description", "attack" : 1530, "defense" : 2130, "height" : 2, "active" : "FODASE", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("58166f8ce902b522bf84dcfb"), "name" : "Jolteon", "description" : "Cachorro picachu", "attack" : 130, "defense" : 230, "height" : 1, "active" : "FODASE", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("58166face902b522bf84dcfc"), "name" : "Machop", "description" : "marombinha do milhao", "attack" : 230, "defense" : 130, "height" : 1, "active" : "FODASE", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("581733c7c666abebec71f8a7"), "name" : "Pikachu", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 1, "active" : "FODASE", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("5818b8d6c666abebec71f8a9"), "description" : "Pokemon teste", "name" : "testemon", "attack" : 8150, "defense" : 8000, "moves" : [ "desvio" ], "active" : "FODASE" }
{ "_id" : ObjectId("5818d0d383dbe7d7f84ae603"), "active" : "FODASE", "name" : "naoExistMon", "attack" : null, "defense" : null, "height" : null, "description" : "Sem maiores infos", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("5818d1e783dbe7d7f84ae604"), "active" : "FODASE", "name" : "naoExistMon", "attack" : null, "defense" : null, "height" : null, "description" : "Sem maiores infos", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("5818cf5f83dbe7d7f84ae602"), "active" : "FODASE", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("5834ae3d28bd8f88db226235"), "name" : "bulbasauro", "description" : "bulba", "attack" : 15, "defense" : 19, "height" : 1.5, "moves" : [ "desvio", "investida", "voadora" ] }
{ "_id" : ObjectId("5834aeaa28bd8f88db226236"), "name" : "Moltres", "description" : "Molts fogo", "attack" : 215, "defense" : 219, "height" : 3.5, "moves" : [ "desvio" ] }
{ "_id" : ObjectId("5834b35428bd8f88db226237"), "name" : "diglete", "description" : "digletando", "attack" : 5, "defense" : 9, "height" : 0.5, "moves" : [ "desvio" ] }
{ "_id" : ObjectId("5834b3a028bd8f88db226238"), "name" : "caterpie", "description" : "catepiando", "attack" : 5, "defense" : 9, "height" : 0.3, "moves" : [ "desvio", "investida", "voadora" ] }
{ "_id" : ObjectId("583629b017e789bec1c1a471"), "name" : "Charmander", "description" : "fogo", "attack" : 15, "defense" : 19, "height" : 1.5, "moves" : [ "desvio" ] }
{ "_id" : ObjectId("583629cf17e789bec1c1a472"), "name" : "Squirtle", "description" : "agua", "attack" : 12, "defense" : 13, "height" : 0.5, "moves" : [ "desvio", "investida", "voadora" ] }
{ "_id" : ObjectId("58173cc4c666abebec71f8a8"), "name" : "Mew", "active" : "FODASE", "moves" : [ "desvio", "investida", "voadora" ] }
{ "_id" : ObjectId("58166effe902b522bf84dcf8"), "name" : "Bulbassauro", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 0.1, "type" : "grama", "active" : "FODASE", "moves" : [ "desvio", "investida", "voadora" ] }
{ "_id" : ObjectId("58166f3ae902b522bf84dcf9"), "name" : "Mew", "description" : "Pokemon que parece um nene feio", "attack" : 30, "defense" : 130, "height" : 1, "active" : "FODASE", "moves" : [ "desvio", "investida", "voadora" ] }
{ "_id" : ObjectId("58173394c666abebec71f8a6"), "name" : "Bulbassauro", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 1, "active" : "FODASE", "moves" : [ "desvio", "investida", "voadora" ] }
```

## 6.Pesquisar todos os pokemons que não são do tipo elétrico.

```

var poke_not_eletrico = { type:{ $ne:'grama'} }
db.pokemons.find(poke_not_eletrico)
{ "_id" : ObjectId("58166f5ee902b522bf84dcfa"), "name" : "Articuno", "description" : "Passo Lendario New description", "attack" : 1530, "defense" : 2130, "height" : 2, "active" : "FODASE", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("58166f8ce902b522bf84dcfb"), "name" : "Jolteon", "description" : "Cachorro picachu", "attack" : 130, "defense" : 230, "height" : 1, "active" : "FODASE", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("58166face902b522bf84dcfc"), "name" : "Machop", "description" : "marombinha do milhao", "attack" : 230, "defense" : 130, "height" : 1, "active" : "FODASE", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("581733c7c666abebec71f8a7"), "name" : "Pikachu", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 1, "active" : "FODASE", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("5818b8d6c666abebec71f8a9"), "description" : "Pokemon teste", "name" : "testemon", "attack" : 8150, "defense" : 8000, "moves" : [ "desvio" ], "active" : "FODASE" }
{ "_id" : ObjectId("5818d0d383dbe7d7f84ae603"), "active" : "FODASE", "name" : "naoExistMon", "attack" : null, "defense" : null, "height" : null, "description" : "Sem maiores infos", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("5818d1e783dbe7d7f84ae604"), "active" : "FODASE", "name" : "naoExistMon", "attack" : null, "defense" : null, "height" : null, "description" : "Sem maiores infos", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("5818cf5f83dbe7d7f84ae602"), "active" : "FODASE", "moves" : [ "desvio" ] }
{ "_id" : ObjectId("5834ae3d28bd8f88db226235"), "name" : "bulbasauro", "description" : "bulba", "attack" : 15, "defense" : 19, "height" : 1.5, "moves" : [ "desvio", "investida", "voadora" ] }
{ "_id" : ObjectId("5834aeaa28bd8f88db226236"), "name" : "Moltres", "description" : "Molts fogo", "attack" : 215, "defense" : 219, "height" : 3.5, "moves" : [ "desvio" ] }
{ "_id" : ObjectId("5834b35428bd8f88db226237"), "name" : "diglete", "description" : "digletando", "attack" : 5, "defense" : 9, "height" : 0.5, "moves" : [ "desvio" ] }
{ "_id" : ObjectId("5834b3a028bd8f88db226238"), "name" : "caterpie", "description" : "catepiando", "attack" : 5, "defense" : 9, "height" : 0.3, "moves" : [ "desvio", "investida", "voadora" ] }
{ "_id" : ObjectId("583629b017e789bec1c1a471"), "name" : "Charmander", "description" : "fogo", "attack" : 15, "defense" : 19, "height" : 1.5, "moves" : [ "desvio" ] }
{ "_id" : ObjectId("583629cf17e789bec1c1a472"), "name" : "Squirtle", "description" : "agua", "attack" : 12, "defense" : 13, "height" : 0.5, "moves" : [ "desvio", "investida", "voadora" ] }
{ "_id" : ObjectId("58173cc4c666abebec71f8a8"), "name" : "Mew", "active" : "FODASE", "moves" : [ "desvio", "investida", "voadora" ] }
{ "_id" : ObjectId("583634cfe1ee03c20abab20a"), "attack" : null, "defense" : null, "description" : "Sem maiores informacoes", "height" : null, "moves" : [ "null" ], "name" : "AindaNaoExisteMon", "active" : true }
{ "_id" : ObjectId("58166f3ae902b522bf84dcf9"), "name" : "Mew", "description" : "Pokemon que parece um nene feio", "attack" : 30, "defense" : 130, "height" : 1, "active" : "FODASE", "moves" : [ "desvio", "investida", "voadora" ] }
{ "_id" : ObjectId("58173394c666abebec71f8a6"), "name" : "Bulbassauro", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 1, "active" : "FODASE", "moves" : [ "desvio", "investida", "voadora" ] }


```


## 7.Pesquisar todos pokemons que tenham o ataque investida E tenham a defesa não menor ou igual a 49.

```

var poke_query = { $and: [ {moves:'investida'}, {defense: {$gt:49}}]}
db.pokemons.find(poke_query)
{ "_id" : ObjectId("58166effe902b522bf84dcf8"), "name" : "Bulbassauro", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 0.1, "type" : "grama", "active" : "FODASE", "moves" : [ "desvio", "investida", "voadora" ] }
{ "_id" : ObjectId("58166f3ae902b522bf84dcf9"), "name" : "Mew", "description" : "Pokemon que parece um nene feio", "attack" : 30, "defense" : 130, "height" : 1, "active" : "FODASE", "moves" : [ "desvio", "investida", "voadora" ] }
{ "_id" : ObjectId("58173394c666abebec71f8a6"), "name" : "Bulbassauro", "description" : "Chicote de vinha", "attack" : 50, "defense" : 150, "height" : 1, "active" : "FODASE", "moves" : [ "desvio", "investida", "voadora" ] }

```


## 8.Remova todos os pokemons do tipo água e com attack menor que 50.


```
var poke = db.pokemons.findOne({$and: [{description:'agua'}, {attack: {$lt:50}}] })
db.pokemons.remove(poke)
WriteResult({ "nRemoved" : 1 })
```
