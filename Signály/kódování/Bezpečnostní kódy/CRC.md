# CRC - Cyclic Redundancy Check

Ke zprávě libovolné délky se přidá daný počet kontrolních bitů (nejčastěji 32).
Detekuje shluky shyb až do délky počtu kontrolních bitů.

Pravděpodobnost selhání CRC32 je $\frac{1}{2^{32}}$

Teoreticky: zbytek po dělení polynomů

1. polynom - zpráva 1101001 = x^6+x^5+x^3+1
2. polynom - vybraný polynom stupně n
n - počet kontrolních bitů
CRC3 - x^3+x+1

Prakticky:
11010011|000
1011
provedeme XOR
01100011000
-1011
-0111011|000
--010111|000
---10111|000
---00001|000
--------1011
--------0|011

Problém 0, sekvence 0 na začátku
-> přidat 1 před začátek zprávy