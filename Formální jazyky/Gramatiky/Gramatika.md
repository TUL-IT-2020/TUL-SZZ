# Gramatika
Gramatika se skládá z množiny pravidel, pomocí kterých může být každé slovo jazyka vygenerováno z předem daného počátečního symbolu. Generování probíhá tak, že vezmeme počáteční symbol, na něj aplikujeme kterékoli z pravidel. Na získaný řetězec opět aplikujeme kterékoliv z pravidel atd., dokud nevygenerujeme požadované slovo.

**Terminální symboly** (zkráceně terminály) — jsou symboly, které už nemohou být dále přepisovány (přepisovacími pravidly). Slova generovaná gramatikou obsahují pouze terminální symboly. V teorii formálních jazyků se terminální symboly označují malými písmeny latinské abecedy (příp. někdy číslicemi).

**Neterminální symboly** (zkráceně neterminály) jsou pomocné symboly, které se používají v přepisovacích pravidlech pro popis struktury jazyka. 
Někdy se nazývají proměnné (variables). Pro označování neterminálů obvykle používají velká písmena latinské abecedy nebo slova (řetězce) ve špičatých závorkách.

Řetězce neterminálů a terminálů se nejčastěji označují řeckými písmeny, řetězce pouze terminálů se nejčastěji označují malými písmeny z konce latinské abecedy (u, v, w )

## Definice
Gramatika G je uspořádaná čtveřice (N, T, P, S).

## Chomského hierarchie gramatik a jazyků

![[Chomského hierarchie gramatik a jazyků]]
## Algoritmus odstranění ε-pravidel
![[Algoritmus odstranění ε-pravidel]]

## Rekurze
Rekurze v (bezkontextové) gramatice je situace, kdy lze určitý neterminální symbol přepsat v jednom nebo více krocích na řetězec, který obsahuje stejný neterminální symbol. 

Speciálními případy jsou:
- levá rekurze: A ⇒ Aα
- pravá rekurze: A ⇒ αA

## Regulární gramatiky
![[Regulární gramatiky]]