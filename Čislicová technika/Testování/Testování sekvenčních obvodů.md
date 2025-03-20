# Testování sekvenčních obvodů

## Stavový automat

> [!tip] Rozlišovací posloupnost  
> Rozlišovací posloupnost nám umožnujě s daným vektorem vstupů rozlišit do jakého stavu jsme se dostali (podle výstupů) a následně lze dopočítat výchozí stav.

> [!tip] Synchronizační posloupnost
> Umožní nám pomocí posloupnosti vstupů přejít do určitého stavu.

Synchronizační posloupností lze použít jako "reset".

> [!tip] Nastavovací posloupnost
> Použijeme když selže synchronizační.

## Strukturní sekvenční testy

Na sekvenční obvody nelze použít [[D-algoritmus|D algoritmus]].

Chceme vytvořit acyklický obvod.
Transformace zpětných vazeb do vazby dopředné (na změnu registru v budoucnu).

Rozkopírujeme obvod do bloků, které jdou za sebou. Zpětné vazby vedou do následující kopie obvodu. 
Můžeme tak sledovat vývoj obvodu v jednotlivých časových blocích. 