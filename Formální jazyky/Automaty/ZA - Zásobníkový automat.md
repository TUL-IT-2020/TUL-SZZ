# ZA - Zásobníkový automat
Zásobníkový automat (ZA) je teoretický výpočetní model používaný v informatice pro studium BJ. Někdy se pro ZA používá zkratka PDA (pushdown automaton). ZA obsahuje konečnou stavovou jednotku, zásobník a vstupní pásku. 

Obecně je ZA:
- jednocestný (po vstupní pásce se pohybujeme zleva doprava),
- nedeterministický,
- s nekonečnou pamětí (zásobníkem, LIFO).

## DZA - Deterministický zásobníkový automat
Deterministický zásobníkový automat (DZA) je definován jako uspořádaná sedmice $(Q, E, r, G, q_0, Z_0, F)$, kde:
- Q je konečná množina stavů vnitřních stavů,
- E je konečná množina (abeceda) vstupních symbolů,
- r je konečná množina (abeceda) zásobníku,
- G je přechodová funkce, popisující pravidla činnosti (program) G: Q x (E U {e}) x r —> Qxr*
- $Z_o$ popisuje symbol uložený na počátku v zásobníku, Z_0 e r,
- $q_0$ je počáteční stav (iniciální Stav), $q_0 \in Q$,
- F je množina přijímajících (koncových) stavů, F c Q.

Přechodová funkce přiřazuje trojici (okamžitý Stav, vstupní symbol, symbol na vrcholu zásobníku) dvojici (následující Stav, řetězec zásobníkových symbolů).

Vstupní a zásobníková abeceda mohou obsahovat stejné symboly.

## NZA - Nedeterministický zásobníkový automat
## RZA - Rozšířený zásobníkový automat