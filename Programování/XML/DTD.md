#xml
# DTD
DTD je zkratka pro Document Type Definition.

Definuje jazyk dokumentu. 
- Jaké existují prvky
- co mohou obsahovat (a tedy jaká jsou pravidla pro jejich vzájemné vnořování) 
- jaké mají atributy

``` xml
<!ELEMENT jméno obsah>
```
- **jméno** určuje jméno prvku, musí být jednoznačné. 
- **obsah** omezuje, co prvek smí a nesmí obsahovat. 

Dva typy textových obsahů: 
- PCDATA (Parsed Character Data) – text analyzovaný procesorem, rozpoznávají se prvky, expandují entity,... 
- CDATA (Character Data) – text není analyzován, bere se jako konstanta

## Jednoduché obsahy
- EMPTY – prvek je prázdný `<!ELEMENT br EMPTY>` 
- ANY – prvek může mít libovolný analyzovatelný obsah; vzdáváme se přísnější kontroly
- (#PCDATA) – prvek obsahuje text `<!ELEMENT den (#PCDATA)>`

(prvek) – daný prvek 
(prvek1,prvek2,...) – prvky v daném pořadí 
(prvek*) – libovolný počet těchto prvků 
(prvek+) – alespoň jeden tento prvek 
(prvek?) – nepovinný výskyt daného prvku 
(prvek1|prvek2) – jeden nebo druhý 

Pomocí závorek lze operátory aplikovat na více prvků.

DTD pro datum:
```DTD
<!ELEMENT datum (den,mesic,rok)>
<!ELEMENT den (#PCDATA)>
<!ELEMENT mesic (#PCDATA)>
<!ELEMENT rok (#PCDATA)>
```

Validní XML:
```xml
<datum>
	<den>17</den>
	<mesic>10</mesic>
	<rok>2006</rok>
</datum>
```

## Typy atributů
- **CDATA** – libovolný (nezpracovávaný) text 
- **(hod1|hod2|...)** – výčet přípustných hodnot
- **ID** – jednoznačný identifikátor (definice ident.) omezení: XML identifikátory nesmí začínat číslicí 
- **IDREF** – identifikátor jiného prvku (odkaz na něj) 
- **IDREFS** – seznam identifikátorů jiných prvků, oddělovány mezerami
- **NMTOKEN** – platné XML jméno (písmena, číslice, -, _, ., :) 
- **NMTOKENS** – seznam jmen oddělených mezerami 
- **ENTITY, ENTITIES** – jméno entity, seznam entit 
- **NOTATION** – jméno notace definované pomocí <!NOTATION...>, nepoužívá se 
- **xml:** – předdefinovaná XML hodnota

## Implicitní hodnota
- “hodnota“ – konkrétní hodnota 
- \#REQUIRED – atribut je povinný 
- \#IMPLIED – atribut lze vynechat, implicitní hodnota není definována 
- \#FIXED “hodnota“ – hodnota je neměnná

## Klady DTD
Nejstarší definiční jazyk, který je široce podporován. Nástroje jsou běžně dostupné.
Jednoduché, v podstatě tři konstrukce: 
- ELEMENT, 
- ATTLIST, 
- ENTITY
## Nedostatky DTD
Neumí datové typy. Velmi omezené možnosti pro definici obsahu prvků a hodnot atributů. Nepodporuje jmenné prostory, problém při kombinování několika DTD.

Nezvyklá syntaxe:
- formálně je XML
- obsahem je vůbec nepřipomíná
