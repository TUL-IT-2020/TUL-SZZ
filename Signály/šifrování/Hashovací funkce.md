# Hashovací funkce

x -> h() -> c = h(x)

Obecná pravidla pro hashovací funkci:
- $x$ - libovolné číslo/zpráva
- $c$ - hodnota z omezeného intervalu $\left<0, 2^{63}-1\right>$

Tyto předpoklady splnují například funkce:
- $sin(x)$,
- $e^{-x}$, 
- $mod()$.

Jako kryptografické funkce jsou však nepraktické.

## Kryptografické hashovací funkce
- $x$ - předloha
- $c$ - otisk (otisk palce)

### Vlastnosti:
1) Odolnost vůči získání předlohy (pro $c$ je těžké najít $x$, takové že $h(x) = c$ ).
2) Odolnost vůči získání druhé předlohy. Pro dané x je těžké najít x' takové, že $h(x) = h(x')$.
3) Odolnost vůči kolizím. Je těžké najít $x_1$ a x_2 takové že $h(x_1) = h(x_2)$.

Doplňující podmínky:
4) Nekorelovanost vstupu a výstupu.
5) Odolnost proti skoro kolizím. Je těžké najít $x_1$ a $x_2$, takových že $h(x)$ a $h(x_2)$ se liší v malém počtu bitů.
6) Lokální vůči získání předlohy. Ze znalosti $c$ je těžké určit i část $x$.
7) Snadno vypočitatelná (relativně)

Důsledky:
- Otisk $c$ závisí na všech bitech $x$. 
- Při změně jednoho bitu $x$ se statisticky změní polovina bitů příslušného otisku $c$.

## Hashovací funkce

- [[CRC|CRC]] není kryptografická hashovací funkce.
- MD4, MD5 - již prolomené.
- SHA - Secure Hashing Algorithm
	- SHA 0 ... 3
	- SHA 2, SHA 3 - bezpečné

### Použití:
- [[Elektronický podpis|elektronický podpis]],
- ukládání hesel.

