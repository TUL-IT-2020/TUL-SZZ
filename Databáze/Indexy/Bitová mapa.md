# Bitová mapa
Ukládá `True`, `False` pro daný sloupec a indikuje, zda je atribut má danou vlastnost. 

| Jméno | Pohlaví | bit map |
| ----- | ------- | ------- |
| Pepa  | můž     | 1       |
| Alena | žena    | 0       |

Hodí se pro atributy s malou kardinalitou a pro statické tabulky. Díky malé kardinalitě je vhodná pro dotazy s více podmínkami ve WHERE klauzuli.

*Příklad Bitmap indexu:*

|    datum   |           místo výskytu          | id_druhu | část_dne | BI AM | BI PM |
|------------|----------------------------------|----------|----------|-------|-------|
| 23.2.2007  | povodí Berounky – oblast Alkazar | 300812   | AM       | 1     | 0     |
| 14.1.1999  | Lidečko – Pulčínské skály        | 3403412  | PM       | 0     | 1     |
| 31.11.2009 | Rejvíz – malé mechové jezírko    | 130045   | AM       | 1     | 0     |
| 1.11.2008  | Niagarské vodopády               | 8459712  | PM       | 0     | 1     |
| 11.4.2004  | Ostrava – Pod Sýkorovým mostem   | 7239710  | PM       | 0     | 1     |
