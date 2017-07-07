# MongoDB - Aula 05 - Exercicio
autor: Luiz Menniti

# Importar as collections `restaurantes` e `pokemons`.

```
restaurantes
menniti:~/workspace $ mongoimport --db be-mean --collection restaurantes --drop --file restaurantes.json
2016-11-26T18:35:26.040+0000    connected to: localhost
2016-11-26T18:35:26.040+0000    dropping: be-mean.restaurantes
2016-11-26T18:35:27.685+0000    imported 25359 documents

pokemons
menniti:~/workspace $ mongoimport --db be-mean --collection pokemons --drop --file pokemons.json
2016-11-26T18:38:57.139+0000    connected to: localhost
2016-11-26T18:38:57.140+0000    dropping: be-mean.pokemons
2016-11-26T18:38:57.158+0000    imported 610 documents


```


# Distinct por `cuisine` na restaurantes.

```
db.restaurantes.distinct('cuisine')
[
        "Irish",
        "Jewish/Kosher",
        "American ",
        "Hamburgers",
        "Bakery",
        "Delicatessen",
        "Ice Cream, Gelato, Yogurt, Ices",
        "Other",
        "Chicken",
        "Chinese",
        "Turkish",
        "Caribbean",
        "Donuts",
        "Sandwiches/Salads/Mixed Buffet",
        "Bagels/Pretzels",
        "Continental",
        "Pizza",
        "Italian",
        "Steak",
        "Polish",
        "Latin (Cuban, Dominican, Puerto Rican, South & Central American)",
        "French",
        "German",
        "Pizza/Italian",
        "Mexican",
        "Spanish",
        "Café/Coffee/Tea",
        "Tex-Mex",
        "Soul Food",
        "Pancakes/Waffles",
        "Greek",
        "Seafood",
        "Hotdogs",
        "Not Listed/Not Applicable",
        "African",
        "Japanese",
        "Indian",
        "Armenian",
        "Thai",
        "Chinese/Cuban",
        "Mediterranean",
        "Korean",
        "Bottled beverages, including water, sodas, juices, etc.",
        "Russian",
        "Eastern European",
        "Middle Eastern",
        "Asian",
        "Ethiopian",
        "Vegetarian",
        "Barbecue",
        "Egyptian",
        "English",
        "Sandwiches",
        "Portuguese",
        "Indonesian",
        "Chinese/Japanese",
        "Filipino",
        "Juice, Smoothies, Fruit Salads",
        "Brazilian",
        "Afghan",
        "Vietnamese/Cambodian/Malaysia",
        "CafÃ©/Coffee/Tea",
        "Soups & Sandwiches",
        "Tapas",
        "Moroccan",
        "Pakistani",
        "Peruvian",
        "Bangladeshi",
        "Czech",
        "Salads",
        "Creole",
        "Fruits/Vegetables",
        "Iranian",
        "Cajun",
        "Scandinavian",
        "Polynesian",
        "Soups",
        "Australian",
        "Hotdogs/Pretzels",
        "Southwestern",
        "Nuts/Confectionary",
        "Hawaiian",
        "Creole/Cajun",
        "Californian",
        "Chilean"
]


```


# Distinct por `types` na pokemons.


```
db.pokemons.distinct('types')
[
        "normal",
        "fire",
        "water",
        "bug",
        "poison",
        "flying",
        "electric",
        "steel",
        "ice",
        "ghost",
        "fighting",
        "psychic",
        "grass",
        "ground",
        "fairy",
        "rock",
        "dark",
        "dragon"
]


```
# As primeiras 3 pág. com .limit() e .skip() de pokemons (5 em 5).

```
db.pokemons.find({}, {name: 1}).limit(5).skip(5 * 0)
{ "_id" : ObjectId("564b1dad25337263280d0479"), "name" : "Rattata" }
{ "_id" : ObjectId("564b1dad25337263280d047a"), "name" : "Charmander" }
{ "_id" : ObjectId("564b1dad25337263280d047b"), "name" : "Charmeleon" }
{ "_id" : ObjectId("564b1dad25337263280d047c"), "name" : "Wartortle" }
{ "_id" : ObjectId("564b1dad25337263280d047d"), "name" : "Blastoise" }

db.pokemons.find({}, {name: 1}).limit(5).skip(5 * 1)
{ "_id" : ObjectId("564b1dad25337263280d047e"), "name" : "Caterpie" }
{ "_id" : ObjectId("564b1dad25337263280d047f"), "name" : "Metapod" }
{ "_id" : ObjectId("564b1dad25337263280d0482"), "name" : "Kakuna" }
{ "_id" : ObjectId("564b1dad25337263280d0481"), "name" : "Spearow" }
{ "_id" : ObjectId("564b1dae25337263280d0485"), "name" : "Magneton" }

db.pokemons.find({}, {name: 1}).limit(5).skip(5 * 2)
{ "_id" : ObjectId("564b1dae25337263280d0484"), "name" : "Magnemite" }
{ "_id" : ObjectId("564b1dae25337263280d0486"), "name" : "Doduo" }
{ "_id" : ObjectId("564b1dae25337263280d0487"), "name" : "Seel" }
{ "_id" : ObjectId("564b1dae25337263280d0488"), "name" : "Dodrio" }
{ "_id" : ObjectId("564b1dae25337263280d0483"), "name" : "Farfetchd" }


```
# Group ou Aggregate contando a quantidade de pokemons de cada tipo.

```
Group 
db.pokemons.group({
        initial: {total:0},
        reduce: function(curr, result){
                curr.types.forEach(function(type){
                        if(result[type]){
                                result[type]++;
                        } else {
                                result[type]= 1;
                        }
                        result.total ++
                });
        }
})

[
        {
                "total" : 915,
                "normal" : 78,
                "fire" : 47,
                "water" : 105,
                "bug" : 61,
                "poison" : 54,
                "flying" : 77,
                "steel" : 37,
                "electric" : 40,
                "ice" : 24,
                "ghost" : 34,
                "fighting" : 38,
                "psychic" : 62,
                "grass" : 75,
                "ground" : 51,
                "fairy" : 28,
                "rock" : 46,
                "dark" : 38,
                "dragon" : 20
        }
]



```

# Realizar 3 counts na pokemons.

```
db.pokemons.group({
        initial:{total: 0, defense:0, attack:0, speed:0},
        reduce: function(current, result){
                result.total++;
                result.defense += current.defense;
                result.attack += current.attack;
                result.speed += current.speed;
        }
})

[
        {
                "total" : 610,
                "defense" : 43623,
                "attack" : 45445,
                "speed" : 39777
        }
]

```