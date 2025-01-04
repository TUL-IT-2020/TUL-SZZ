#C
# C

## Knihovny
![[Knihovny]]
## Výstup na konzoli
- printf()

Speciální znaky:
- `\n` (newline) 
- `\t` (tab) 
- `\v` (vertical tab) 
- `\f` (new page)
- `\b` (backspace) 
- `\r` (carriage return)

Formátování výstupu:
- `%c` – znak 
- `%d` – signed int 
- `%ld` – signed long 
- `%u` – unsigned int   
- `%lu` – unsigned long   
- `%f` – float (např %06.3f)  
- `%Lf` – long double 
- `%lf` – double 
- `%x` – hexadecimální číslo malými písmeny (1a2c) 
- `%X` - hexadecimální číslo velkými písmeny (1A2C) 
- `%o` – osmičkové číslo 
- `%s` - řetězec

## Základní datové typy 

|Název|Bitů|Význam|Příklad|
|---|---|---|---|
|char|8|celé číslo, znak|0, 255, 'a', 'A', 'e'|
|[short](https://www.sallyx.org/sally/c/c05.php#sup1)|16|krátké celé číslo|65535, -32767|
|int|16/32|celé číslo|--\|--|
|[long](https://www.sallyx.org/sally/c/c05.php#sup1)|32|dlouhé celé číslo|--\|--|
|[long long](https://www.sallyx.org/sally/c/c05.php#sup1)|64|ještě delší celé číslo|9223372036854775807, -9223372036854775807|
|[enum](https://www.sallyx.org/sally/c/c16.php#enum)|8/16/32|výčtový typ||
|float|32|racionální číslo|5.0, -5.0|
|double|64|racionální číslo s dvojitou přesností|5.0l, 5l, -5.0L|
|long double|80|velmi dlouhé racionální číslo|5.5L, 5l, -5.0l|
|[pointer](https://www.sallyx.org/sally/c/c05.php#ukazatele)|16/32/64|ukazatel|

### Reprezentace čísel v paměti počítače

![[Dvojkový doplněk]]

![[Float]]

### NULL
**NULL** je speciální hodnota, která označuje velké nic. Používá se v souvislosti s ukazateli. `NULL` můžete vložit do ukazatele a pak můžete testovat, zda ukazatel obsahuje `NULL`, nebo adresu někam. `NULL` se také často používá jako argument funkcí, když tam, kde je vyžadován jako argument ukazatel, žádný ukazatel vložit nechcete. Praktické využití této hodnoty ukáži později, například [v ukázce použití NULL](https://www.sallyx.org/sally/c/c10.php#null) (zatím na to nekoukejte, nebo vám to vypálí oči).

## Operátory
![[Operátory]]

## Řízení toku programu
![[Řízení toku programu]]
## Cykly
![[Cykly]]
## Ukazatele (pointery)
![[Ukazatele (pointery)]]
## Alokace paměti
Statiská vs dynamická
- Statická na [[Rozdělení paměti#Zásobník|stack]]
- dynamický na [[Rozdělení paměti#Halda|heap]]

Globální proměnné jsou definované mimo funkce.

### Paměťové třídy
- **auto** - implicitně pro lokální proměnné (stack),
- **extern** - pro globální proměnné definované v jiných souborech,
- **static** - proměnná existuje od prvního spuštění programu až do jeho skončení (a pouze v daném modulu),
- **registr** - proměnná je pak uložena přímo v registru a ne v paměti.

### Statická alokace
Můžeme použít pokud známe předem paměťové nároky našeho programu. Překladač alokuje paměť se spuštěním programu.

### Dynamická alokace
Ukazuje na ní pointer. Paměť se vymezuje v heapu (hromadě).

### dynamické přidělení paměti
```C
#include <stdlib.h>
int *p_a = (int *)malloc(sizeof(int));
if (p_a == NULL) return 1;
free((void *) p_a);
p_a = NULL
```

## Funkce
![[Funkce]]

## Abstraktní a složené datové typy

### Pole
![[Pole]]

### Textový řetězec
![[Textový řetězec]]

### Výčtový datový typ
![[Výčtový datový typ]]
### Strukturovaný datový typ
![[Strukturovaný datový typ]]

## Práce se soubory
![[Práce se soubory]]
## Preprocesor
![[Makra preprocesoru]]
## Zdroje:
- https://www.sallyx.org/sally/c/c05.php