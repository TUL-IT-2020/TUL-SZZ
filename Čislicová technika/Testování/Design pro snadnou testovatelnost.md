# Design pro snadnou testovatelnost

> [!warning] Pravidla
> - NE zpětná vazba v kombinačních obvodech!
> - NE křížem propojená hradla!
> - NE dělat návrh na úrovni tranzistorů!
> - NE nedefinovaná logika! (stavové automaty)
> - NE asynchronní logika!
> - Hodiny nejsou data! (dělička hodin)
> 	- Nehradlovat hodiny!
> 	- Ne DDR návrh v našem obvodu!
> - Data nejsou hodiny! 

> [!tip] 
> - Možnost zastavit hodiny.


> [!tip] Přidáme: 
>- Testovací body do obvodu (sledovací).
>- Nastavovací body (pro nastavení citlivé cesty)

Potřeba přístupu do všech registrů!
Problém -> příliš mnoho pinů.

Nahradilo se to posuvnými registry (máme přístup ke všem registrům).

Příliš mnoho registrů, dlouhá doba nahrávání do obvodu!
Přidání generátoru testů přímo do čipu.

[[BIST]] -> Build-in Self-Test
LSFR nám vygeneruje náhodné vstupu pro otestování.

Ad-Hoc metody:
- Rozdělení obvodu,
- Sběrnicová architektura,
- Testovací vstupy.
Strukturovaný návrh:
- LSSD - scanovací návrh
- RAS - random access scan - servisní přístup do registrů
Boundry scan
- Možnost serializace všech registrů po posuvného registru.

Při přepisu všech registrů v posuvném registru dochází k rapidnímu přenastavovaní vnitřní kombinační logiky -> velká spotřeba.

Přidá se šedou registr a po nastavení vnitrní hodnoty do kýženého stavu se najednou všechny přepíšou. 
