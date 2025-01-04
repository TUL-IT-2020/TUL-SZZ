#C 
# Direktivy preprocesoru
> \# 
> - tohle patří preprocesoru!!

```C
// vloží hlavičkový soubor
#include "file.h"
#include <file.h>
```

### Deklarace konstant
```C
// defince konstant
#define NOK 0	
#define OK 1
#define DEBUG true
#define MAX 1000 
#define PI 3.141592 
#define DVE_PI (2 * PI) 
#define MOD % 
#define SOUBOR ”c:/program \
	files/program/data.txt”
```

### Makra
Pokud mnohokrát používáme krátkou funkci, pak je rychlejší ji napsat jako makro s parametrem, protože pokud by to byla klasická funkce pak její administrativa (uchovávání návratové hodnoty, parametrů atd.) je náročnější než použití makra. Použití maker tedy zvyšuje rychlost programu. Někdy se makrům s parametry říká vkládané (in-line) funkce.

```C
// makra
// používejte makra je to rychlejší!!!
// primo vloží výraz do kódu
#define MAXIMUM(a, b) ((a) > (b)) ? a : b
#define MULT(a) (a)*(a)
#define sqr(x) ((x) * (x))
```

### Podmíněný překlad
```
// podmineny preklad
#if vyraz
	#...
#else
	#...
#endif

#ifdef	// pokud je definovan
#undef	// oddefinuj

#define PCAT 1 
/* #define PCAT 0 */ 

#if PCAT 
	#include 
#else 
	#include 
#endif

#define TEST
/* #undef TEST */
#ifdef TEST
	// testy
#endif
```
