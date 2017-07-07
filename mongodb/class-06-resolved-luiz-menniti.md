# MongoDB - Aula 06 - Exercício
User: [menniti](https://github.com/Menniti)
Autor: Luiz Menniti
# Fazer uma query para o campo name utilizando `explain` para ver o resultado da busca.

```
 db.restaurantes.find({name:"P & S Deli Grocery"}).explain('executionStats').executionStats
{
        "executionSuccess" : true,
        "nReturned" : 1,
        "executionTimeMillis" : 65,
        "totalKeysExamined" : 0,
        "totalDocsExamined" : 25359,
        "executionStages" : {
                "stage" : "COLLSCAN",
                "filter" : {
                        "name" : {
                                "$eq" : "P & S Deli Grocery"
                        }
                },
                "nReturned" : 1,
                "executionTimeMillisEstimate" : 30,
                "works" : 25378,
                "advanced" : 1,
                "needTime" : 25359,
                "needFetch" : 17,
                "saveState" : 207,
                "restoreState" : 207,
                "isEOF" : 1,
                "invalidates" : 0,
                "direction" : "forward",
                "docsExamined" : 25359
        }
}


db.restaurantes.find({ "_id" : ObjectId("5839d5eea630d6ff77e246c6")}).explain('executionStats').executionStats
{
        "executionSuccess" : true,
        "nReturned" : 1,
        "executionTimeMillis" : 0,
        "totalKeysExamined" : 1,
        "totalDocsExamined" : 1,
        "executionStages" : {
                "stage" : "IDHACK",
                "nReturned" : 1,
                "executionTimeMillisEstimate" : 0,
                "works" : 2,
                "advanced" : 1,
                "needTime" : 0,
                "needFetch" : 0,
                "saveState" : 0,
                "restoreState" : 0,
                "isEOF" : 1,
                "invalidates" : 0,
                "keysExamined" : 1,
                "docsExamined" : 1
        }
}

```


# Criar um `index` um para o campo `name`.

```
db.restaurantes.createIndex({name: 1})
{
        "createdCollectionAutomatically" : false,
        "numIndexesBefore" : 1,
        "numIndexesAfter" : 2,
        "ok" : 1
}


> db.restaurantes.getIndexes()
[
        {
                "v" : 1,
                "key" : {
                        "_id" : 1
                },
                "name" : "_id_",
                "ns" : "be-mean.restaurantes"
        },
        {
                "v" : 1,
                "key" : {
                        "name" : 1
                },
                "name" : "name_1",
                "ns" : "be-mean.restaurantes"
        }
]

```

# Refazer a query para o campo `name` utilizando `explain` para ver o resultado da busca.

```
 db.restaurantes.find({name:"P & S Deli Grocery"}).explain('executionStats').executionStats
{
        "executionSuccess" : true,
        "nReturned" : 1,
        "executionTimeMillis" : 0,
        "totalKeysExamined" : 1,
        "totalDocsExamined" : 1,
        "executionStages" : {
                "stage" : "FETCH",
                "nReturned" : 1,
                "executionTimeMillisEstimate" : 0,
                "works" : 2,
                "advanced" : 1,
                "needTime" : 0,
                "needFetch" : 0,
                "saveState" : 0,
                "restoreState" : 0,
                "isEOF" : 1,
                "invalidates" : 0,
                "docsExamined" : 1,
                "alreadyHasObj" : 0,
                "inputStage" : {
                        "stage" : "IXSCAN",
                        "nReturned" : 1,
                        "executionTimeMillisEstimate" : 0,
                        "works" : 2,
                        "advanced" : 1,
                        "needTime" : 0,
                        "needFetch" : 0,
                        "saveState" : 0,
                        "restoreState" : 0,
                        "isEOF" : 1,
                        "invalidates" : 0,
                        "keyPattern" : {
                                "name" : 1
                        },
                        "indexName" : "name_1",
                        "isMultiKey" : false,
                        "direction" : "forward",
                        "indexBounds" : {
                                "name" : [
                                        "[\"P & S Deli Grocery\", \"P & S Deli Grocery\"]"
                                ]
                        },
                        "keysExamined" : 1,
                        "dupsTested" : 0,
                        "dupsDropped" : 0,
                        "seenInvalidated" : 0,
                        "matchTested" : 0
                }
        }
}

```


# Fazer uma query para dois campos juntos utilizando `explain` para ver o resultado da busca.

```

db.restaurantes.find({$and: [{name:"P & S Deli Grocery"}, {borough : "Manhattan"}]}).explain('executionStats').executionStats
{
        "executionSuccess" : true,
        "nReturned" : 10259,
        "executionTimeMillis" : 15,
        "totalKeysExamined" : 0,
        "totalDocsExamined" : 25359,
        "executionStages" : {
                "stage" : "SUBPLAN",
                "nReturned" : 10259,
                "executionTimeMillisEstimate" : 10,
                "works" : 25361,
                "advanced" : 10259,
                "needTime" : 15101,
                "needFetch" : 0,
                "saveState" : 198,
                "restoreState" : 198,
                "isEOF" : 1,
                "invalidates" : 0,
                "inputStage" : {
                        "stage" : "COLLSCAN",
                        "filter" : {
                                "$or" : [
                                        {
                                                "borough" : {
                                                        "$eq" : "Manhattan"
                                                }
                                        },
                                        {
                                                "name" : {
                                                        "$eq" : "P & S Deli Grocery"
                                                }
                                        }
                                ]
                        },
                        "nReturned" : 10259,
                        "executionTimeMillisEstimate" : 10,
                        "works" : 25360,
                        "advanced" : 10259,
                        "needTime" : 15101,
                        "needFetch" : 0,
                        "saveState" : 198,
                        "restoreState" : 198,
                        "isEOF" : 1,
                        "invalidates" : 0,
                        "direction" : "forward",
                        "docsExamined" : 25359
                }
        }
}


```


# Criar um `index` para esses dois campos juntos.

```
db.restaurantes.createIndex({ name:1, borough:1})
{
        "createdCollectionAutomatically" : false,
        "numIndexesBefore" : 2,
        "numIndexesAfter" : 3,
        "ok" : 1
}

```

# Refazer a query para os dois campos juntos utilizando `explain` para ver o resultado da busca.

```
> db.restaurantes.find({$and: [{name:"P & S Deli Grocery"}, {borough : "Manhattan"}]}).explain('executionStats').executionStats
{
        "executionSuccess" : true,
        "nReturned" : 1,
        "executionTimeMillis" : 0,
        "totalKeysExamined" : 1,
        "totalDocsExamined" : 1,
        "executionStages" : {
                "stage" : "FETCH",
                "nReturned" : 1,
                "executionTimeMillisEstimate" : 0,
                "works" : 3,
                "advanced" : 1,
                "needTime" : 0,
                "needFetch" : 0,
                "saveState" : 0,
                "restoreState" : 0,
                "isEOF" : 1,
                "invalidates" : 0,
                "docsExamined" : 1,
                "alreadyHasObj" : 0,
                "inputStage" : {
                        "stage" : "IXSCAN",
                        "nReturned" : 1,
                        "executionTimeMillisEstimate" : 0,
                        "works" : 2,
                        "advanced" : 1,
                        "needTime" : 0,
                        "needFetch" : 0,
                        "saveState" : 0,
                        "restoreState" : 0,
                        "isEOF" : 1,
                        "invalidates" : 0,
                        "keyPattern" : {
                                "name" : 1,
                                "borough" : 1
                        },
                        "indexName" : "name_1_borough_1",
                        "isMultiKey" : false,
                        "direction" : "forward",
                        "indexBounds" : {
                                "name" : [
                                        "[\"P & S Deli Grocery\", \"P & S Deli Grocery\"]"
                                ],
                                "borough" : [
                                        "[\"Manhattan\", \"Manhattan\"]"
                                ]
                        },
                        "keysExamined" : 1,
                        "dupsTested" : 0,
                        "dupsDropped" : 0,
                        "seenInvalidated" : 0,
                        "matchTested" : 0
                }
        }
}

```