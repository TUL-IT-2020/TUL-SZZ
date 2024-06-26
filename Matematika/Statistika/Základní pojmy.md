# Základní pojmy
**Teorie pravděpodobnosti** je matematická disciplína, jejíž logická struktura je budována axiomaticky. To znamená, že její základ tvoří několik tvrzení, která vyjadřují základní vlastnosti pravděpodobnosti a všechna další tvrzení jsou z nich odvozena deduktivně.
- Př. Kolika způsoby jsme schopni …, kolik existuje kombinací … 
- Výsledky úlohy jsou stejné, ať správně počítá Tonda nebo Jarda. 

**Matematická statistika** je věda zahrnující studium dat vykazujících náhodná kolísání, ať už jde o data získaná pečlivě připraveným pokusem provedeným pod stálou kontrolou experimentálních podmínek v laboratoři, či o data provozní, případně o data získaná počítačovými simulacemi (tzv. metodou Monte-Carlo).
- Př. Tonda i Jarda měli každý 10 výrobků a zjišťovali jejich dobu do poruchy.
- Oba mají odlišné výsledky

**Náhodný pokus** - je každý dej, jehož výsledek není předem jednoznačně určen podmínkami, za kterých probíhá. 
- Například hod mincí či kostkou, životnost výrobku, přesná velikost určitého rozměru.

Množina možných výsledků 𝜔 pokusu, tzv. základní prostor 𝛺 – Množina možných výsledků musí být volena tak, aby žádné z nich nemohly nastat současně. 
- Ω – rub, líc
- hod kostkou 1,2,3,4,5,6 
- Ω – doba do poruchy R+
- počet poruch Z+ + 0
- Základní prostor není – sjednocení množin lichých čísel a čísel dělitelných tří beze zbytku.

## Náhodný jev
představuje každou podmnožinu A základního prostoru Ω. 
- Na kostce padne číslo 3; výška člověka je vyšší než 180 cm

**Elementární jev** jednoprvkové podmnožiny základního prostoru Ω. 
- Na kostce padne číslo 3; náhodný jev již nelze dále rozdělit na dílčí náhodné jevy.

**Složený jev** víceprvkové podmnožiny základního prostoru Ω. 
- Na kostce padne sudé číslo. Jedná se o složený jev, protože mohou padnout čísla {2,4,6} . Čísla {2,4,6} tvoří elementární jevy.

## Pravděpodobnost

Výsledek náhodného jevu nelze s jistotou předpovědět. Při častějších opakování však některé náhodné pokusy vykazují zákonitosti a pravidelnost výskytu. 

**Pravděpodobností označujeme míru očekávatelnosti výskytu náhodného jevu**. S rostoucí pravděpodobností roste i šance, že jev nastane.

**Pravděpodobnost se obecně označuje číslem z intervalu  <0,1>**.

## Podmíněná pravděpodobnost
Pravděpodobnost, že nastane jev 𝐴 za podmínky, že nastal jev 𝐵 se vypočte podle vzorce: 
$$
P(A|B) = \frac{P(A∩B)}{P(B)}
$$