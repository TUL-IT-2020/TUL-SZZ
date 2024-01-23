# Převod ZNKA na NKA
Každý ZNKA lze převést jak na NKA (bez t-přechodů).
Algoritmus převodu ZNKA na NKA:
1) Pokud existují stavy, do kterých se lze přesunout pomocí t-přechodu a jejich předchozí stav byl vstupní (počáteční), pak i tyto stavy se nově stanou vstupními stavy.
2) Pro Stav, který je vyústěním t-přechodu, musíme jít v hierarchii o dva stavy zpět (včetně t-přechodu) a vytvořit přímé propojení mezi tímto stavem a vyústěním t-přechodu.
3) Odstraníme E-přechod.
4) Pokud existuje další E-přechod, postupujeme krokem číslo 2.
