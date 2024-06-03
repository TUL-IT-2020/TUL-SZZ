# Stromové indexy
## ISAM 
- statická struktura
- počet diskových operací je roven hloubce stromu
- problém přetékání při vkládání nových záznamů

## B+
- dynamická struktura
- odstraňuje problém s přetékáním (u ISAM) 
- operace vložení a mazání jsou vážené
- minimální obsazenost 50% pro každý uzel mimo root
- vyhledávání je sekvenční projití od kořene k listu
- operace na B+ stromech je nutné udržovat podle pravidel dále...

**Vložení dat do B+ stromu**

1. najít požadovaný list „L“
2. vložit data do L - pokud je volný tak pouze zapsat; v opačném případě rozdělit L na nový uzel L a L2, provést redistribuci záznamů, vložit index ukazující z L2 na otce L

Tento postup se může rekurzivně propagovat do celé větve stromu. Tímto strom roste.

**Mazání dat z B+ stromu**

1. najít požadovaný list „L“
2. odstranit záznam	- pokud je L nejméně z poloviny plný tak smazat; pokud má L pouze (d-1) záznamů provést redistribuci, půjčit si záznamy od sousedních uzlů; jinak spojit L a souseda	

V případě spojování L a souseda je třeba smazat i záznamy ukazující	na tyto dva uzly. Spojování lze propagovat až do root a tím snížit hloubku stromu.

## R-stromy
![[R-stromy]]