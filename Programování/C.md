#C
# C

## Hlavičkové soubory
1. `#include <soubor>` – soubor se hledá v systémovém adresáři 
2. `#include ”soubor”` – soubor musí být ve stejném adresáři jako „volající“ soubor

stdio.h  - knihovna standardního vstupu výstupu
```C
#include <stdio.h>
```

### Knihovny
ctype.h
- isdigit(c) 
- isalphanum(c) 
- sizeof(int)

stdlib.h
- malloc()
- free()
- int atoi(char *string); 
- long atol(char *string); 
- double atof(char *string);

string.h 
- int strlen(char *s); 
- char *strcpy(char *kam, char *odkud); 
- char *strcat(char *s1, char *s2); – spojení řetezců 
- char *strchr(char *kde, char co); – Hledání znaku co 
- int strcmp(char *s1, char *s2);
- char *strstr(char *kde, char *co);

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

### NULL
**NULL** je speciální hodnota, která označuje velké nic. Používá se v souvislosti s ukazateli. `NULL` můžete vložit do ukazatele a pak můžete testovat, zda ukazatel obsahuje `NULL`, nebo adresu někam. `NULL` se také často používá jako argument funkcí, když tam, kde je vyžadován jako argument ukazatel, žádný ukazatel vložit nechcete. Praktické využití této hodnoty ukáži později, například [v ukázce použití NULL](https://www.sallyx.org/sally/c/c10.php#null) (zatím na to nekoukejte, nebo vám to vypálí oči).

## Alokace paměti
Statiská vs dynamická
- Statická na [[Rozdělení paměti#Zásobník|stack]]
- dynamický na [[Rozdělení paměti#Halda|heap]]

Globální proměnné jsou definované mimo funkce.

### Paměťové třídy
- **auto** - implicintě pro lokální proměné (stack),
- **extern** - pro globální proměné definované v jiných souborech,
- **static** - proměnná existuje od prvního spuštění programu až do jeho skončení (a pouze v daném modulu),
- **registr** - proměnná je pak uložena přímo v registru a ne v paměti.

### Statická alokace
Můžeme použít pokud známe předem paměťové nároky našeho programu. Překladač alokuje paměť se spuštěním programu.

### Dynamická alokace
Ukazuje na ní pointer. Paměť se vymezuje v heapu (hromadě).

### Ukazatele (pointery)

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
#### Předání argumentu do funkce referencí
```C
void vymen(int *p_x, int *p_y){ 
	int pom; 
	pom = *p_x; 
	*p_x = *p_y; 
	*p_y = pom; 
}

vymen (&i, &j);
```

#### Ukazatel na funkci
```C
double pol1(double x){ 
	return (x*x);
} 
double pol2(double x){ 
	return x*5;
}

int main(){ 
	double (*p_f)(double); 
	for (int i = 0; i < 2; i++){ 
		p_f = (i == 0)? pol1 : pol2; 
		printf("%f\n", (i == 1)?p_f(10):(*p_f)(10)); 
	} 
}
```

Pole pointerů na funkce
```C
int min(int pole[]); 
int max(int pole[]); 
int med(int pole[]); 

typedef void (* P_FCE)(); 
P_FCE funkce[] = {min, max, med}; 
funkce[1](pole);
```

#### Pointerová aritmetika
Platné operace jsou: 
- součet pointeru a celého čísla 
- rozdíl pointeru a celého čísla 
- porovnání pointerů stejných typů
- rozdíl dvou pointerů stejných typů

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

2) Pole pointrů
dynamická alokace
```C
int *x[2]
x2[0] = (int *)malloc(3*sizeof(int)); 
x2[1] = (int *)malloc(3*sizeof(int));
```

3) pointer na pole
```C
int (*x3)[3];
x3 = (int (*)[3])malloc(2*3*sizeof(int));
```

4) pointer na pointer
```C
int **x = malloc..;
for () {
	x[i] = malloc...;
}
```

### Textový řetězec
Staticky:
```C
char string[10]; 
```
dynamicky:
```C
char *string; 
string=(char*)malloc(10*sizeof(char))
string[0] = ‘\0’; //nulovy retezec zakoncujici pole
```

### Strukturovaný datový typ
Struktury jsou vlastně normální datové typy a lze je tedy jak předávat tak i vracet z a do funkcí. Při předávání hodnotou je nutný vytvořit kopii struktury ve stacku a to může být náročné, proto je lépe předávat pointer.

Třída bez metod
```C
typedef struct nazevStruktury {
	atributy
} NAZEVDatovehoTypu;

struct nazve instane; //deklarace

instance.atribut = ; // pristup
```

Struktura není pojmenovaná a nedá se tedy použít, ale lze použít proměnné.
```C
struct { 
	int vaha; 
	int vyska; 
} petra, jana, lucka;
```

Struktura je pojmenovaná:
```C
struct nazev {
	atributy
} instance;
```

Ukázka definice datového typu list
```C
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
V C nejsou procedury v pravém slova smyslu, pouze funkce. Všechny parametry jsou volané hodnotou!!

Procedury využívají návratový typ void.

### Definice funkce
funkční prototyp:
```C
double kruh(int r);

int main(){ 
	printf(“Polomer: %d\n”, kruh(10)); 
} 

double kruh(int r){ 
	return 2 * 3.14159 * r; 
}
```

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

### Rekurzivní funkce
Funkce volající sama sebe.
```C
int faktorial(int n){ 
	return ((n<=0)? 1 : n*faktorial(n-1)); 
}
```

![[fibonaci_rekurze_c]]

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

## Zdroje:
- https://www.sallyx.org/sally/c/c05.php