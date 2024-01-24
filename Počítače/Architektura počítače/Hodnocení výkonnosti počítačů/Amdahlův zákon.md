# Amdahlův zákon
Amdahlův zákon je pravidlo používané v informatice k vyjádření maximálního předpokládaného zlepšení systému poté, co je vylepšena pouze některá z jeho částí. Využívá se např. u víceprocesorových systémů k předpovězení teoretického maximálního zrychlení při přidávání dalších procesorů.

- Úloh, které vyžadují čistě paralelní zpracování, je poměrně málo.
- V praxi jsou nejčastější úlohy, v nichž se střídají úseky výpočtu, který je nutno provádět sekvenčně s úseky vhodnými pro paralelní zpracování.
- Při posuzování účinku paralelizace na výkon systému lze použít analytický vztah, který je podle svého autora Gene Amdahla nazýván zákonem Amdahlovým.
- Předpokládejme, že určitý výpočet lze částečně paralelizovat. To znamená, že kromě části , kterou je nutno provést sériově na jednom procesoru (obvykle vstup a výstup dat, případně jejich předzpracování), lze zbytek výpočtu zadat několika procesorům, tak aby zpracování na nich probíhalo současně.

## Nevýhody

- Zákon byl formulován v roce 1967
- Má své nedostatky plynoucí hlavně z doby, kdy vzniknul.
- Zákon řeší pouze problém o konstantní velikosti.
- Jinými slovy, paralelní část je fixní.
- S rostoucím počtem procesorů se nemění rozsah problému.
- Nezvažuje vůbec dostupnost výpočetní síly

![Amdáhlův zákon](TUL-SZZ/assets/počítače/26_amdahl.png)
*Amdáhlův zákon*

## Výpočet zrychlení
Významný zákon informatiky. Popisuje výpočet výkonového zisku (zrychlení S) dosaženého vylepšením nějaké části počítače. 
Zrychlení **S** je číslo, které udává kolikrát je rychlejší běh úlohy na počítači s vylepšením oproti běhu stejné úlohy na původním počítači.
$$
S = \frac{P_{NEW}}{P_{OLD}}
$$
- $P_{NEW}$ - výkon při využití zrychlení 
- $P_{OLD}$ - výkon bez využití zrychlení

$$
S = \frac{T_{OLD}}{T_{NEW}}
$$
- $T_{OLD}$ - doba výpočtu bez využití vylepšení
- $T_{NEW}$ -  doba výpočtu při využití vylepšení


### Definujeme poměry:

![Definované poměry](TUL-SZZ/assets/počítače/26_pomery.png)
*Definované poměry*

### Doba výpočtu se skládá:
Doba výpočtu na nevylepšeném počítači:
![Doba výpočtu](TUL-SZZ/assets/počítače/26_doba.png)

Doba výpočtu na vylepšeném počítači:
$$
T_{NEW} = T_{OLD} 
\left( 
(1-F_E) + \frac{F_E}{S_E}
\right)
$$

### Příklad
![[Doba výpočtu na vylepšeném počítači příklad]]

## Výpočet na paralelním systému

Celkové zrychlení výpočtu multiprocesorového systému, který má **p** procesorů, a jehož část programu **fs** může být provedena pouze jediným procesorem (sériová, neparalelizovatelná část), resp. je-li **fp** poměr paralelizovatelné části výpočtu, je dáno:
$$
S = \frac{1}{
f_s + \frac{1-f_s}{p}
}
= \frac{1}{
(1-f_p) + \frac{f_p}{p}
}
$$
- $f_s + f_p = 1$
- Zrychlení multiprocesorového systému

![[Paralelní systém příklad]]