# Dokumentové databáze
Na úrovni DB bez schématu. Podle [[CAP teorém|CAP]] jsou dokumentové databáze buď CP nebo AP. 
Replikace typu master-slave. Horizontální škálování.

## Koncept
Nejpoužívanější typ NoSQL databází. Princip podobný [[Key-value uložiště|key-valu uložištím]]. Základem jsou key-value páry.
Value obsahuje strukturovaná nebo částečně strukturovaná data. 

Samotná data mohou bát indexována a dotazována. [[NoSQL databáze#Indexování|Indexy]] nad atributy dat. 

## Dokument
Základní stavební prvek databáze. Data jsou ukládána v JSON / XML formátu. 

Textová forma:
XML, YAML, JSON

Binární froma:
BSON, PDF, MS office dokumenty


Koncepčně odpovídají objektům v OOP.  Dokumenty mají [[NoSQL databáze#NoSQL databáze#Volné schéma|volné schéma]]. K dokumentům jsou často přidružena i metadata. 

Jsou zpravidla identifikovány cestou k souboru.

Dvě řešení:
- embedded dokumenty (data atributů jsou rovnou zde)
- reference (id dokumentu - vazba)

## Operace s daty
Operace [[CRUD]], mohou také podporovat transakce [[SQL - ACID|ACID]].

## Kolekce
Skupiny dokumentů. Jeden dokument může být ve více kolekcích. 
