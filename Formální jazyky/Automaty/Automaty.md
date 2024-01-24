# KA - konečné automaty
KA lze chápat jako abstraktní model určitého specifického typu výpočtu. Výpočet neprobíhá s čísly, ale objekty, které budeme nazývat symboly.

KA najdou využití např.: 
- při návrhu sekvenčních logických obvodů 
- při návrhu, specifikaci a implementaci protokolů pro komunikaci 
- v překladačích programovacích jazyků 
- při řešení úloh z oblasti umělé inteligence 
- při modelování architektury softwarových komponent 
- v řídicích systémech logického typu

KA se v každém svém okamžiku nachází v některém ze stavů **konečné množiny stavů** (v daném okamžiku se nachází právě v jednom stavu). Stav se může měnit na základě vnějšího podnětu z okolí (zpracováním konkrétního vstupního symbolu), které nejčastěji přicházejí v diskrétních časových okamžicích.

Tři typy KA:
1. rozpoznávací (ano/ne)
2. klasifikační (třídy)
3. s výstupní funkcí (překlad, [[Mealyho automat|Mealy]], [[Mooreův automat|Moore]])

KA lze zapsat (zadat) jedním z následujících způsobů:
- **zápisem výčtu jednotlivých prvků pětice**, resp. šestice KA – málo přehledné (málo používané);
- **stavovým diagramem** (přechodovým grafem) – názorné pro návrháře (zejména u menších KA);
- **tabulkou** – méně názorné, vhodné i pro větší KA, vhodné východisko pro softwarovou implementaci;
- **stavovým (výpočetním) stromem** – kompromis mezi oběma předchozími způsoby.

Obecnější je například zásobníkový automat nebo [[TS - Turingův stroj|Turingův stroj]].
## ZNKA - zobecněný nedeterministický konečný automat
Obsahuje $\epsilon$ hrany ( ε ∉ Σ), které provádí automat neustále, bez čtení symbolu ze vstupu. Teoreticky jich může proběhnout nekonečné množství
## NKA - nedeterministický konečný automat
Základní rozdíly mezi DKA a NKA:
- NKA nemusí začínat jen v jednom počátečním stavu (může jich mít více – můžeme si vybrat, kde začít);
- přechodová funkce je zobrazením do potenční množiny P(Q), tedy množiny všech podmnožin množiny Q; ze stavu se na vstupní symbol může jít nejen do jednoho stavu, ale do libovolného počtu (podmnožiny) nebo i nikam (do prázdné podmnožiny).
- každý NKA lze převést na DKA.

A = (Q, Σ, δ, I, F), kde:
- Q je konečná neprázdná množina stavů, 
- Σ je konečná neprázdná množina vstupních symbolů, 
- δ: Q × Σ → P(Q) je přechodová funkce, P(Q) je potenční množina
- I ⊆ Q je množina počátečních stavů,
- F ⊆ Q je množina koncových stavů.

## DKA - deterministický konečný automat
K přechodu do jiného stavu může dojít pouze na základě zpracování vstupního symbolu. V každém stavu a pro každý vstupní symbol je následující stav definován jednoznačně.

### Totální (úplný) automat
Totální (úplný) konečný automat je deterministický konečný automat, ve kterém lze ve všech stavech reagovat na kterýkoliv symbol abecedy, tj. přechodová funkce $\delta$ je totální: 

$$\forall q \in Q,\forall a \in \Sigma, \exists p \in Q : \delta(q,a) = p
$$

(ke každému stavu a symbolu abecedy existuje stav, do kterého přejdeme z daného stavu na daný symbol). 
Ke každému deterministickému konečnému automatu $A$ existuje totální automat $A1$ takový, že $L(A) = L(A1)$. 
Totální automat má tedy definované přechody ze všech stavů pro všechny symboly vstupní abecedy. Chceme-li neúplný KA převést na totální, můžeme přidat jeden stav navíc, kam budou mířit „chybějící“ přechody. Tento stav nebude koncový a budou v něm cyklit všechny další vstupní symboly.

### Redukovaný konečný automat
Automat bez nedosažitelných a nadbytečných stavů se označuje jako redukovaný konečný automat (automat s redukovanou množinou stavů). 

### Minimální konečný automat
Konečný automat je minimální, jestliže neexistuje žádný s ním ekvivalentní automat, který má menší počet stavů. Ke každému konečnému automatu lze sestrojit ekvivalentní minimální konečný automat. 

Minimalizací automatu rozumíme nalezení ekvivalentního automatu, který obsahuje minimální možný počet stavů. Postup minimalizace automatu: 
1. odstraníme [[Nalezení dosažitelných stavů|nedosažitelné stavy]], 
2. odstraníme [[Nadbytečné stavy|nadbytečné stavy]], 
3. odstraníme [[Algoritmus redukce stavů|ekvivalentní stavy]]. 

### Normovaný automat
![[Normovaný automat]]

### Moore a Mealy
Mooreův a Mealyho DKA se používají zejména v hardwarové formě (sekvenční logické obvody) pro řízení číslicových systémů. U těchto KA přidáváme čas - vesměs se jedná o synchronní obvody řízené hodinovým signálem (jeho změnou nastává změna vnitřního stavu).

- [[Mooreův automat|Mooreův automat]] – výstupní funkce je závislá pouze na aktuálním stavu (výstupní funkce je zobrazení Q —> O),
- [[Mealyho automat|Mealyho automat]] – výstupní funkce je závislá na aktuálním stavu a na aktuálním vstupním symbolu (výstupní funkce je zobrazení Q x E —> O).

Oba typy automatů jsou mezi sebou převoditelné, u Mealyho automatu se výstup může měnit asynchronně (ihned po změně vstupů) — nebezpečí hazardů a přechodových jevů.  Mealyho automat může mít složitější přechodovou a výstupní funkci (vlivem menšího počtu vnitřních stavů). Mooreho automat může vést na větší počet vnitřních stavů.

Výstupní funkce je u obou automatů kombinační —> možnost hazardů —> za výstupní funkci se někdy doplňují registry.

## ZA - Zásobníkový automat
![[ZA - Zásobníkový automat]]

## Převod automatů
### Převod ZNKA na NKA
![[Převod ZNKA na NKA]]
### Převod ZNKA na DKA
![[Převod ZNKA na DKA]]

### Převod NKA na DKA
![[Převod NKA na DKA]]

## Přechod Mealy ↔ Moore
### Převod z Mealyho automatu na Mooreův:
1. Rozštěpíme stavy automatu, do kterých směřují hrany s odlišnými výstupními hodnotami (do každého stavu budou vcházet pouze hrany se stejným výstupem).
2. Přesuneme výstupní hodnoty do stavů.
3. Připojíme vstupní a výstupní hrany nově doplněných uzlů.

### Převod z Mooreova automatu na Mealyho:
1. Hodnoty výstupů u stavů přepíšeme k hranám, které do těchto uzlů směřují (doplníme tabulku výstupů).
2. Provedeme sloučení hran — lze sloučit hrany, které vycházejí i končí ve stejných stavech a mají stejné hodnoty výstupů.
3. Provedeme sloučení stavů — lze sloučit stavy, pokud hrany, které z nich vycházejí, vstupují do stejných dalších stavů a mají přiřazeny stejné výstupní hodnoty.
