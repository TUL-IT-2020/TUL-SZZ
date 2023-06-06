#C
# C

## Základní datové typy 
#TODO

## Alokace paměti
Statiská vs dynamická
- Statická na stack
- dynamický na heap

Ukazuje na ní pointer.
Globální proměnné jsou definované mimo funkce.


auto - implicintě pro lokální proměné
extern - pro globální proměné definované v jiných proměných
static - WTF?? private? global?
registr - bude bydlet v registru počítače

### pointery

\* - běž na adresu kam ukazuje pointer
& - dej mi adresu paměti
```C
int a = 42;
int * p_a = NULL;
p_a = &a;
printf("%d\n", *p_a);
```

```C
int *p;
...
*(p + 10) = k;	// posun v poli o deset kroku bazoveho typu

typedef * int P_INT;	// definujeme novy datovy typ ukazatelu, funguje jako makro
```

### dynamické přidělení paměti
```C
#include <stdlib.h>
int *p_a = (int *)malloc(sizeof(int));
if (p_a == NULL) return 1;
free((void *) p_a);
p_a = NULL
```

### pole
#### statické pole
```C
char string[30]
```
#### dynamická alokace pole
```C
int size = 20;
int *array = (int *) malloc(sizeof(int)*size);

pole[1] = 10;
*(pole +1) = 10;
```

#### Více dimenzionální pole
1) Statické pole:
`int x[2][3];`

2) dynamická alokace
Pole pointrů
`int *x[2] = malloc...;`

3) pointer na pole
// TODO opravit z prezentace
```C
int (*x)[3];
x = (int (*)[3])malloc(2*3*sizeof(int));
```

4) pointer na pointer
```C
int **x = malloc..;
for () {
	x[i] = malloc...;
}
```

### Strukturovaný datový typ
Třída bez metod
```C
struct nazev {
	atributy
} instance;

typedef struct nazevStruktury {
	atributy
} NAZEVDatovehoTypu;

struct nazve instane; //deklarace

instance.atribut = ; // pristup

typedf struct list {
	int size = 0;
	int *array = NULL;
	struct list *next;
} LIST;
```

operátory přístupu:
. chci na atribut
-> skoč na ukazatel a vrat atribut, ekvivalnetni k (*instance).atribut

## Funkce
![[fibonaci_rekurze_c]]

### main
```C
/* Funkce main
 * argc - počet parametrů
 * argv - je pole řetězců
 */
int main (int atgc, char *argc[]) {
	return 0
}
```

## Práce se soubory
### textové soubory
```C
#include <stdio.h>

FILE *file;
file = fopen("file.txt", mode);
if ( file == NULL ) return 1;

int a, b;
scanf("%d %d", &a, &b);
int size = fprintf(file, "%d %d\n", a, b);
if ( size < 0 ) return 2;
fclose(file);

int output = 0;
while (fscanf(file, "%d", &output) != 0EF ) {
	printf("%d ", output);
}
fclose(file);
```
mode = \[ r, w, a, ra, wa \]
- a append

### Binární soubory
```C
// bin soubory

FILE *filebin;

int i = 10;
double d = 3.14;

file = fopen("DATA.dat", "wb");
if ( file == NULL ) return 1;
fwrite(&i, sizeof(i), 1, filebin);	
// sizeof(i) - velikost i, bunky, ukazatele
// sizeof(int) - velikost int
fwrite(&d, sizeof(d), 1, filebin);

int ii;
double dd;
filebin = fopen("DATA.dat", "rb");
fread(&ii, sizeof(int), 1, filebin);
fread(&dd, sizeof(double), 1, filebin);
fclose(filebin);
```

## Preprocesor
tohle patří preprocesoru!!
```C
#include	// vloží hlavičkový soubor
#include "file.h"
#include <file.h>
// defince konstant
#define NOK 0	
#define OK 1
#define PI 3.14
#define DEBUG true

// podmineny preklad
#if vyraz
	#...
#else
	#...
#endif

#ifdef	// pokud je definovan
#undef	// oddefinuj

#define TEST
#ifdef TEST
	// testy
#endif

// makra
// používejte makra je to rychlejší!!!
// primo vloží výraz do kódu
#define MAXIMUM(a, b) ((a) > (b)) ? a : b
#define MULT(a) (a)*(a)
```

