#MVD 
# Normalizace textu 
Cílem je nalezení slov i v případě odlišností v posloupnosti znaků tokenu => Redukce slova na jeho základní tvar:
1. Rozdělení textu na tokeny + lowercase 
2. Odstranění stop words 
3. Stematizace (Stemming) / Lematizace 
4. PoS tagging Stemming vs. Lematizace 

## Tokenizace 
- Rozdělení textu na menší prvky (tokeny) 
	"+" Odstranění interpunkce
- Závislá na jazyku 
- Je potřeba jasná definice pravidel

## Stop words 
Nežádoucí slova v textu 
- Příliš častý výskyt 
- Ovlivnění výsledku algoritmu 
Metody a vytěžování dat -> Metody vytěžování dat
- Např. odstranění spojek a předložek 
- Vytvoření stop listu 
	- Malé 7-12 slov 
	- Velké 200-300 slov 
- Moderní systémy je nepotřebují používat (viz Inverse Document Frequency)

## Stemming 
Stemming (kořen slova) může redukovat token na slovo, které neodpovídá gramatice: 
- people -> peopl 
- V některých aplikacích nemusí vadit 

## Lematizace
Lematizace převádí token do základního gramatického tvaru: 
- am, are, is -> be
