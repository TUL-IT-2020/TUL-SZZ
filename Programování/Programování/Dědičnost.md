# Dědičnost
Vztah rodičovské a odvozené třídy. Umožňuje tvorbu nových tříd a rozhraní děděním existujících vlastností. Dědí se pouze viditelné členy podle přístupových modifikátorů. 

Klíčová slova extends, implements:
- Třída extends třída
- Rozhraní extends rozhraní
- Třída implements rozhraní

## Přístupová práva
Specifikace přístupových práv určuje přístupová práva pro složku a všechny za ní následující do další specifikace přístupových práv nebo }.
- private – všechny zděděné složky (ty které jsou specifikována v předkovi jako public, či protected) budou v potomkovi private 
- public – zděděné složky mají stejná přístupová práva jako v předkovi 
- protected – veřejné (public) a chráněné (protected) budou v potomkovi chráněné, private zůstanou soukromé

## Abstraktní třída
Klíčové slovo abstract. Má konstruktor, ale nelze vytvořit instanci. Může mít abstraktní metody – místo definice těla jen středník.

## Rozhraní (inteface)
Omezená abstraktní třída. Má implicitně všechny metody abstraktní. Slouží jako norma či požadavek. Může mít jen konstantní atributy – public final static. Nemá implicitního předka, nemusí mít ani explicitního. Nemůže být potomkem třídy.

## Na co dát pozor:
- Zastínění proměnné (shadowing) - Metoda definuje lokální proměnnou se stejným jménem, jako má některý atribut.
- Překrytí proměnné (hiding) - Potomek může definovat stejnojmenný atribut, jako má rodič. Nový atribut nemusí zachovat statičnost, viditelnost ani typ.
- Kolize - Třída dědí stejnojmenné metody od více předků -> Chyba při překladu.