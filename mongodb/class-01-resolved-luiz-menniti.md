# MongoDB - Aula 01 - Exercicio
autor: Luiz Menniti

## Importando os restaurantes

```
root@menniti-webschoolmean-3962214:/home/ubuntu/workspace# mongoimport --db be-mean --collection restaurantes --host=127.0.0.1 --drop --file restaurantes.json
2016-11-22T20:25:33.260+0000    connected to: 127.0.0.1
2016-11-22T20:25:33.261+0000    dropping: be-mean.restaurantes
2016-11-22T20:25:35.253+0000    imported 25359 documents

```

## Contando os restaurantes

```
db.restaurantes.count()
25359
```