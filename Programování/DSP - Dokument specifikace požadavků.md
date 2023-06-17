# DSP
Dokument specifikace požadavků.
Uživatelské a systémové požadavky, požadavky na HW. 
ISO normy, licence.
Standard na webu v prezentaci: ANSI 830
Seznam požadavků pro implementaci.
Formuláře, Use case, UML.
Vstupy a výstupy.
Externí zdroje a jejich formát.

Interview
Max 2 hodiny. Připravené otázky.

Funkční vs mimo funkční požadavky
Odůvodnění
Každý požadavek má svůj identifikátor

## UML
- Diagram tříd

Modelování: 
- slovníku systému
- rozdělení zodpovědnosti
- datové typy

| Name |
| --- |
| OPS  |

| ATR  |
| ---  |
| Note |

**Práva**
```UML
+ public
# protected
- private
~ package
```

**Atributy**
práva název : datový typ = výchozí hodnota

**Funkce**
práva název_metody() : návratový typ
Abstraktní *kurzívou*


Vztahy:
- **Závislost**
	- čerchovaná čára (s nebo bez šipky)
- **Dědičnost**
	- čára s plnou šipkou (od potomka k rodiči)
- **Asociace**
	- čára s šipkou
	- **Agregace**
		- třída složená z menších částí
		- čára s kosočtvercem
	- **Kompozice**
		- je složená z menších objektů a o ty stará (vznik a zánik)
		- čára s plným kosočtvercem

## SRS
Software requirements specification 
Pseudokód a algoritmy.

## Diagramy
### Sekvenční diagram
Sekvence života objektu, zpráv (funkcí objektů).

### Komunikační diagram