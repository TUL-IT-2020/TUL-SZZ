# Indexování
Vylepšuje rychlost vyhledávání. Bez indexování se provádí sken celé databáze. Vhodný index výrazně omezuje rozsah, který je potřeba skenovat. 

## Index
Speciální datová struktura definovaná na úrovni setů, polí, kolekcí. Obsahují ukazatel na data. Ukládá hodnotu specifického pole v seřazené formě. Využití i pro rychlé řazení. Základ pro 
[[Sharding|sharding]].

Vylepšuje rychlost vyhledávání. 
Vkládání prvků vynutí aktualizaci indexu a ta je pomalá, proto není vhodné mít mnoho indexů. 