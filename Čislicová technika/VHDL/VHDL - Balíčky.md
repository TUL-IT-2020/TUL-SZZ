# Balíčky

Package:
```VHDL
PACKAGE system IS
	CONSTANT pocet : INTEGER := 2;
	PROCEDURE add (SIGNAL a, b : IN BIT; suma : OUT BIT );
END system;

PACKAGE BODY system IS
	PROCEDURE add (SIGNAL a, b : IN BIT; suma : OUT BIT );
	BEGIN
		suma <= a  XOR b;
	END add;
END system;
```

> [!tip] Co umístit do balíčku?
> - Opakující se části kódu, které nemají vnitřní stav - funkce a procedury,
> - Definice datových typů - vnitřní stavy automatů, výčtové typy,
> - Konstanty a globální genericity.
## Funkce
Je podprogram, který vrací hodnotu (datový typ). Mají vstupní operandy a jeden výstupní operand. Typ hodnoty může být skalární nebo složený. Ve funkci nemohou být deklarovány signály (pouze konstanty a proměnné – jejich platnost je omezena pouze na funkci).

Syntaxe definice funkce:
```VHDL
FUNCTION nazev_funkce (seznam_parametru) RETURN typ_vystupu IS
    -- deklarace promennych
BEGIN
    -- telo funkce (sekvencni prikazy)
    RETURN hodnota;
END nazev_funkce;
```

> [!tip]
> Procesy, které nemají vrnitřní stav a opakují se, se dají extrahovat do funkce.

## Procedury
Podprogram, který modifikuje vstupní parametry. Módy parametrů mohou být: 
- IN, 
- OUT, 
- INOUT (implicitně IN);

Proceduře lze předávat signály, konstanty i proměnné. Z procedury lze volat další proceduru.

Syntaxe definice procedury:
```VHDL
PROCEDURE nazev_procedury (seznam_parametru) IS
    -- deklarace promennych
BEGIN
    -- telo funkce (sekvencni prikazy)
END jméno_procedury;
```
