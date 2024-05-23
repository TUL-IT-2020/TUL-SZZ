# Násobička
Násobičky jsou často užívanými obvody, jelikož pomocí nich je možné realizovat filtry signálů při jejich zpracování. Rozdělujeme je na sériové a paralelní.

## Sériová násobička
Při sériovém násobení využíváme faktu, že v binární soustavě je aritmetické násobení dvou bitů rovno jejich logickému součinu. Operandy A a B a výsledek násobení C vyjádříme pomocí následujících výrazů: 
$$
A= \sum_{i=0}^{m}a_iz^i
$$
$$B=\sum_{j=0}^{m}b_jz^j$$
$$C=A*B=\sum_{j=0}^{m+n+1}c_jz^j$$
$$C=\sum_{j=0}^{n}Ab_jz^j$$
Poslední z uvedených výrazů je využitelný pro sériové násobení čísla A koeficienty z čísla B a postupnému přičítání výsledků k odpovídajícím řádům výsledku.


> [!NOTE] Ruční násobení v binární soustavě
> **Znásobte čísla $7_{10}$ a $5_{10}$**
> $111_2$
> $101_2$
> ---
> xx  111
> x 000
>111
>---
>$100011_2$

Násobení provádíme pomocí operací logického součinu přičítání a posunů v registrech C0 a C1. Počáteční hodnota registrů C0 a C1 je nulová. V prvním kroku k registru C0 přičteme výsledek logického součinu LSB čísla B a všech bitů čísla A. Výsledek posuneme o jednu pozici doprava ve spojeném posuvném registru C0C1. Proces opakujeme pro další bity čísla B. Po třech cyklech se vytvoří v registrech C0C1 výsledek C.

![[Sériová násobička.png]]
>Sériová násobička

| Operace | C1 | C0 |
| ---- | ---- | ---- |
| Přičtení 111 | 0111 | 000 |
| Posuv | 0011 | 1000 |
| Přičtení 000 | 0011 | 100 |
| Posuv | 0001 | 110 |
| Přičtení 111 | 1000 | 110 |
| Posuv | 0010 | 011 |
## Paralelní násobička
Násobení se provádí během jediného taktu hodin. Využívá se při tom  následujícího rozkladu výsledku C:
$$
C = \sum_{i=0}^{m}\sum_{j=0}^{n}a_j b_j2^{i+j}
$$
Výraz ai.bj ve dvojkové soustavě realizujeme jako log. součin, $2^{i+j}$ representuje posuv o $i+j$ míst doleva. Příklad realizace 4bitové paralelní násobičky je uveden v Obr. 71. Při realizaci násobičky pomocí logických obvodů vzniká pravidelná struktura se součinovými hradly (v Obr. 71 označeno &) a úplnými jednobitovými sčítačkami (na Obr. 70 označeny jako FA) a polo-sčítačkami (HA tamtéž).
>![[Paralelní násobička.png]]
>Paralelní násobička