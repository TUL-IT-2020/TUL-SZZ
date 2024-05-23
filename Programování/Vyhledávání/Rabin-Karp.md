# Rabin-Karp
> [!tldr] Založen na použití [[Hashovaní|hašování]] – porovnání dvou otisků (hashů).

Vypočteme hash pro vzor P (délky m) a pro každý podřetězec řetězce délky m. Procházíme řetězcem T ale místo jednotlivých znaků porovnáváme hash každého podřetězce a vzoru, v případě shody provedeme test podřetězce a vzoru znak po znaku – ochrana proti kolizi haše.

## Volba hašovací funkce:
Klíčová volba pro efektivitu celého algoritmu. Podřetězec se posouvá po znaku – části podřetězců jsou shodné. Potřebujeme funkci která umožní vypočítat hash následujícího podřetězce s využitím již vypočtených hashů.

### Hashovací funkce
Zvolíme prvočíslo $q$ – určuje velikost hašovacího prostoru. Zvolíme základ $d$, může být roven velikosti $|A|$ nebo libovolnému většímu číslu, ideálně $d = 2X$. Čím větší $q$, tím menší pravděpodobnost kolize, $d$ jako mocnina dvou umožňuje efektivní implementaci násobení.

> [!tip]
Pro efektivní výpočet využíváme [[Hornerovo schéma|Hornerovo schéma]] (polynom je v monotické formě).

Nenumerické znaky převádíme pomocí kódovací tabulky na čísla (ASCII, Unicode).

## Časová náročnost
Přes stejnou složitost běží algoritmus pomaleji než KMP na stejných datech (díky režii výpočtů). Algoritmus lze ovšem snadno rozšířit na vyhledávání víc vzorů (slov) najednou – používá se v testování plagiátorství, detekce virů v binárních souborech.