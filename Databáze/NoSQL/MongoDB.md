# Mongo DB
V současnosti nejpopulárnější  dokumentová databáze.
Cloud: Atlas
mají free verzi

Dokumenty ukládány ve formátu BSON.

## Architektura


## Agregace
- Agragační roura (pipeline)
- [[MapReduce|map-reduce]] (využití JavaScript funkcí)
- jednoúčelová agregace (pro dokumenty v jedné kolekci)

### Agregační roura
Dokumenty jsou zpracovány postupně v krocích až do konečného výsledku. Založená na principu roury na zpracování dat. Dokumenty vstupují do víceúrovňové roury, která je transformuje na agregovaný výsledek. 

fáze:
- match
- group

## Funkce:
`Date()`
