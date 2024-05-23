# Přirozené prohledávání
> [!tldr] Postupné procházení celého řetězce a pro každou pozici testujeme, zda na ní není začátek hledaného řetězce. 

> [!info] Složitost: 
>- nejhorší případ $O(m*n)$ , 
>- běžně $O(m+n)$.

Algoritmus je rychlý pokud je abeceda textu „velká“ (A-Z, a-z, 1-9 atd)
Algoritmus je pomalý pro malou abecedu – tedy binární soubory, obrázkové soubory atd.

Pro přirozené hledání je typické opakované procházení již prohledaných částí, klíčem ke zrychlení procesu je inteligentní řízení procesu, toho dosáhneme heuristickou analýzou často prováděnou předem (preprocesing).