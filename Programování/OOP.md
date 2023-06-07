# OOP - Objektově orientované programování
Z pohledu například jazyka Java.

Objektový přístup modeluje entity reálného světa:
- Třída: entita reálného světa,
- Atributy: data, členské proměnné,
- Metody: funkční možnosti,
- Interface: množina souvisejících metod (rozhraní), které jiná třída implementuje,
- Objekt: instance třídy,
- Instance: jeden daný objekt (Objekt je jako recept a instance je dort, který upekla babička),
- Enum: výčtový typ.

Principy:
- Abstrakce: zobecnění pohledů a částečná řešení,
- Dědičnost: získávání vlastností děděním z jiné třídy,
- Polymorfismus: jednotné zacházení s různými objekty dědícími společné schopnosti,
- Zapouzdření: skrývání částí tříd a rozhraní.

Například v jazyce Java:
Každá třída je potomkem třídy Object. Není nutné uvádět extends Object. Object definuje 11 generálních metod, které dědí všichni (toString, hashCode, equals, clone, notify, wait, …).

## Dědičnost
Vztah rodičovské a odvozené třídy. Umožňuje tvorbu nových tříd a rozhraní děděním existujících vlastností. Dědí se pouze viditelné členy podle přístupových modifikátorů. 

Klíčová slova extends, implements:
- Třída extends třída
- Rozhraní extends rozhraní
- Třída implements rozhraní

### Abstraktní třída
Klíčové slovo abstract. Má konstruktor, ale nelze vytvořit instanci. Může mít abstraktní metody – místo definice těla jen středník.

### Rozhraní (inteface)
Omezená abstraktní třída. Má implicitně všechny metody abstraktní. Slouží jako norma či požadavek. Může mít jen konstantní atributy – public final static. Nemá implicitního předka, nemusí mít ani explicitního. Nemůže být potomkem třídy.

Na co dát pozor:
- Zastínění proměnné (shadowing) - Metoda definuje lokální proměnnou se stejným jménem, jako má některý atribut.
- Překrytí proměnné (hiding) - Potomek může definovat stejnojmenný atribut, jako má rodič. Nový atribut nemusí zachovat statičnost, viditelnost ani typ.
- Kolize - Třída dědí stejnojmenné metody od více předků -> Chyba při překladu.

## Statické atributy a metody
Statické atributy a metody náleží třídě. V deklaraci klíčové slovo static. Volání pomocí jména třídy. Metody mají přístup jen k dalším statickým metodám a atributům.

### Nestatické metody
Náleží jediné instanci. Volání pomocí reference na objekt a operuje nad volaným objektem. Metody mají přístup k instančním i statickým metodám a atributům.

### Statické metody
Mohou být definovány v (abstraktních) třídách, rozhraních i enumech. Nemohou být abstraktní. Nelze je přepsat (@Override), lze je překrýt v potomkovi.

Statické inicializátory atributů 
“Metody bez hlavičky”, provádějí se jen jednou, v pořadí zápisu při zavádění třídy, nedědí se.



