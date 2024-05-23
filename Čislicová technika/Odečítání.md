# Odečítání
Pro odečítání s výhodou využijeme sčítačku popsanou v předchozím odstavci doplněnou o případné obvody vytvářející jednotkový nebo dvojkový doplněk z menšitele.

Jednotkový doplněk kladného čísla je číslo samo, ze záporného čísla získáme doplněk tím, že invertujeme všechny bity absolutní hodnoty čísla. Odečtení provedeme jako součet jednotkových doplňků kladného a záporného čísla a přičtením výstupního přenosu do nejnižšího řádu (kruhový přenos). Výsledek odečítání bude v kódu jednotkového doplňku.

> [!NOTE] Odečítání s jednotkovým doplňkem
> **S pomocí jednotkového doplňku odečtěte číslo $6_{10}$ od čísla $11_{10}$**
> ---
> $0 1011_2$ | $11_{10}$
> $1 1010_2$ | $-6_{10}$
> ---
> $1+00101_2$ | $5_{10}$

Nevýhodou využití jednotkového doplňku je dvojí obraz nuly. Získáme kladnou a zápornou
representaci nuly, z nichž jedna nemá využití.

Při použití dvojkového doplňku změníme u menšitele nuly na jedničky (a naopak) a
přičteme jedničku, výstupní přenos se nevyužije. Předpokládejme, že od čísla A odečítáme číslo B.

![[Odečítačka.png]] 
>Odečítačka

Odečítání provedeme ve sčítačce, kterou doplníme invertory na vstupech bitů operandu B a vstupním přenosem do sčítačky, který zajistí přičtení jedničky do nejnižšího řádu  Výsledek odečítání bude opět v kódu dvojkového doplňku.

> [!NOTE] Odečítání s dvojkovým doplňkem
> **S pomocí dvojkového doplňku odečtěte číslo $6_{10}$ od čísla $11_{10}$**
> ---
> $0 1011_2$ | $11_{10}$
> $1 1010_2$ | $-6_{10}$
> ---
> $1|00101_2$ | $5_{10}$
> 
>Při odečítání se místo pojmu výstupní přenos $q*$ používá pojem výpůjčka $v*$ (borrow).
>Platí  𝑞̅̅∗̅ =$𝑣*$
>$q*$=1↔ $𝑣*$=0 ↔A-B≥0
>$q*$=0↔ $𝑣*$=1 ↔A-B<0
>
>Je-li výsledek záporný, jeho absolutní hodnotu je možné získat opět dvojkovým doplňkem.

Porovnáme-li schéma paralelní sčítačky s odečítačkou vidíme, že oba obvody můžeme sloučit do univerzálního schématu sčítačky-odečítačky (Obr. 66). Ze schématu je vidět, že sčítačka-odečítačka vytváří dvojkový doplněk operandu B a standardně sčítá dva operandy, které v případě, že jsou v kódu dvojkového doplňku, mohou být kladné i záporné, výsledek bude vždy správný, jestliže nedojde k jejímu přeplnění. Z tohoto důvodu je možné uvažovat o sčítačce jako o sčítačce-odečítačce pracující s operandy v kódu dvojkového doplňku.

![[Sčítačka-odečítačka v dvojkové doplňku.png]]
>Sčítačka-odečítačka v dvojkové doplňku