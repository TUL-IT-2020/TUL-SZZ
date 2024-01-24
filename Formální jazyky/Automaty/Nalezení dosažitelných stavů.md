# Nalezení dosažitelných stavů
Algoritmus nalezení dosažitelných stavů:
1. Použijeme tabulku přechodů s definicí konečného automatu.
2. Označíme počáteční stav (příp. počáteční stavy).
3. Pro každý označený stav postupně procházíme hierarchii přechodových definic tak, že vždy označíme další stavy, které lze z daného stavu dosáhnout.
4. Pokud již nevznikají nově označené stavy a prošli jsme celou strukturu konečného automatu, pak všechny označené stavy jsou dosažitelné a všechny neoznačené stavy jsou nedosažitelné.
