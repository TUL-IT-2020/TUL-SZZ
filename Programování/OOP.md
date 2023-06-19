# OOP - Objektově orientované programování
Z pohledu například jazyka Java, C++.

Objektový přístup modeluje entity reálného světa:
- Třída: entita reálného světa,
- Atributy: data, členské proměnné,
- Metody: funkční možnosti,
- Interface: množina souvisejících metod (rozhraní), které jiná třída implementuje,
- Objekt: instance třídy,
- Instance: jeden daný objekt (Objekt je jako recept a instance je dort, který upekla babička),
- Enum: výčtový typ.

## Principy:
- Abstrakce: zobecnění pohledů a částečná řešení,
- [[Dědičnost|Dědičnost]]: získávání vlastností děděním z jiné třídy,
- Polymorfismus: jednotné zacházení s různými objekty dědícími společné schopnosti,
- Zapouzdření: skrývání částí tříd a rozhraní.

Například v jazyce Java:
Každá třída je potomkem třídy Object. Není nutné uvádět extends Object. Object definuje 11 generálních metod, které dědí všichni (toString, hashCode, equals, clone, notify, wait, …).

## Statické atributy a metody
Statické atributy a metody náleží třídě. V deklaraci klíčové slovo static. Volání pomocí jména třídy. Metody mají přístup jen k dalším statickým metodám a atributům.

### Nestatické metody
Náleží jediné instanci. Volání pomocí reference na objekt a operuje nad volaným objektem. Metody mají přístup k instančním i statickým metodám a atributům.

### Statické metody
Mohou být definovány v (abstraktních) třídách, rozhraních i enumech. Nemohou být abstraktní. Nelze je přepsat (@Override), lze je překrýt v potomkovi.

Statické inicializátory atributů 
“Metody bez hlavičky”, provádějí se jen jednou, v pořadí zápisu při zavádění třídy, nedědí se.

## Genericita
Jako `void*` v C. 

Deklarace třídy
```c++
public Trida(T promenna) { 
	this.promenna = promenna; 
}
```

Ukázka použití
```c++
List<string> list = new List<string>();
list.Add("položka");

string polozka = list[0];

Console.WriteLine(polozka);
```
[kolekce-a-genericita](https://www.itnetwork.cz/csharp/kolekce-a-linq/c-sharp-tutorial-uvod-do-kolekci-a-genericita)
