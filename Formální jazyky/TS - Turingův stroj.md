# Turingův stroj
Turingův stroj je teoretický model počítače, který se používá pro modelování algoritmů.

Popsal jej britský matematik Alan Turing v roce 1936, kdy ještě neexistovaly klasické počítače. Turing vyslovil hypotézu, že každý možný výpočet lze úspěšně uskutečnit algoritmem běžícím na počítači, je-li k dispozici dostatek času a paměti.

(Churchova-)Turingova teze: Ke každému algoritmu existuje ekvivalentní TS (mohou ale existovat algoritmicky nerozhodnutelné problémy). Každý počítačový program lze přeložit do jazyka TS (a také naopak). Vše, co lze řešit na reálném počítači, je možné řešit pomocí TS a naopak.

Turingův stroj je podobný konečnému automatu, obsahuje kromě vlastního automatu také vstupní pásku se čtecí/zapisovací hlavou.

Charakteristickými vlastnostmi jsou:
- páska je jednorozměrná (lineární) a nekonečně dlouhá,
- hlava se může po vstupní pásce pohybovat oběma směry,
- na aktuální pozici hlavy je možné zapisovat.

## Deterministický Turingův stroj
Deterministický Turingův stroj je definován uspořádanou šesticí $M = (Q, \Sigma, Γ, \delta, q_o, F)$, přičemž:
- Q je konečná neprázdná množina všech stavů,
- \sum je konečná neprázdná množina vstupních symbolů, tedy vstupní abeceda (bez znaku a, tj. o $\Sigma$),
- Γ je konečná neprázdná množina páskových symbolů (včetně množiny $\Sigma$), které TS umí číst a zapisovat, tedy pásková abeceda (obsahuje i prázdný znak a), $\Sigma C Γ \\ \{o\}, o \in Γ$,
- $\delta$ jsou přechodové funkce, které stanoví, do kterého stavu má TS přejít, jaký symbol zapsat, kam posunout čtecí hlavu, a to v závislosti na původním stavu a znaku, na kterém se hlava nachází. Formálně: $\Sigma: (Q \\ F) x Γ -> Q x Γ x \{-1, 0, +1\}$
- $q_o$ je počáteční Stav, $q_o \in Q$,
- F je množina koncových stavů, $F C Q$ (často jediný $q_F$).