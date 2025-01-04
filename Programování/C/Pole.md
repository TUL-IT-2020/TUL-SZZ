#C 
# Pole
Bázový prvek může být libovolný datový typ vyjma void. Velikost uvádíme při deklaraci do `[]`.

## Jednorozměrná pole
- Pole v C nemají volitelnou dolní mez, vždy začínají 0
- Kvůli efektivnosti práce s poli C nekontroluje rozsahy polí
- Kontrolu musíte provádět sami!!

### Statická
```c
define ROZSAH 10
typedef int P_INT[10];
typedef int P_INT2[ROZSAH * 2];

void main(){
	int pole [255]; //alokuje pole 10 int ů s indexy : 0,1,2,3,4,5,6,7,8,9
	char pole [255];
	
	P_INT a;
	P_INT2 b;
	a[1] = 10;
	b[4] = 6;
	int a = 10;
	int b[a]; a];//pozor tohle nelze, musi byt konstanta
}
```

```C
char string[30]

int array[5] = {1, 2, 3, 4, 5};
```

### Dynamická
Předpokládejme definice:
```c
*int pint [10]*;
*int p_int*;
```
Jak `pint` tak i `p_int` jsou oba pointery na int , resp. na první prvek pole. Hodnota `pint` se ale nedá měnit, ukazuje konstantně na jedno místo v paměti, kde začíná naše pole. `p_int` je proměnná, která není inicializovaná a ukazuje na náhodnou adresu paměti. 
```c
//Alokace dynamického pole
int *p_int;
p_int = (int *) malloc (4*sizeof(int));

p_int [0]= *(p_int + 0);
p_int [1]= *(p_int + 1);
p_int [2]= *(p_int + 2);
p_int [3]= *(p_int + 3);
```

```C
int size = 20;
int *array = (int *) malloc(sizeof(int)*size);

pole[1] = 10;
*(pole +1) = 10;
```

## Vícerozměrná pole
Jazyk C  přistupuje k polím stále stejně, tedy při prvním pohledu je dvourozměrné pole
pole jednorozměrné
- Vícerozměrné pole je v paměti uloženo po řádcích
- prvky prvního rozměru jsou pointery na jednorozměrná pole
- máme-li *int x\[2]\[3]*
pak
- x - pointer na dvourozměrné pole
- x\[i] - pointer na i tou řádku
- \*(x + 1) == x\[1] adresa první řádky
- x \[i]\[j] - hodnota prvku s indexy i a j
také platí
že adresa indexované proměnné je:
	\&x\[i]\[j] == x\[i] + j == \*(x+i) + j
hodnota je:
	x\[i]\[j] == \*(x\[i]+j) == y*(\*(x+i)+j)

### Alokace
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


## Práce s celým polem najednou
- v C nelze pracovat s celým polem najednou
- Je třeba vždy použít cyklu
## Přístup pouze pomocí pointerů a pointerové aritmetiky
- přístup do pole pomocí pointerů je obvykle daleko efektivnější než pomocí indexů
- záleží na překladači, jak moc dobře optimalizuje
## Zjištění velikosti pole
- Rozdíl mezi statickým a dynamickým polem
```c
int p [10];
int *p_int = (int*)malloc(10*sizeof(int));
sizeof(p) -> 10* sizeof int
sizeof p_int ) -> sizeof (*p_int) -> velikost adresy
```
- U dynamického pole je nutné si předávat velikost jako parametr, či jako prvek na indexu 0
## Pole s proměnnou délkou
- Jednoduše definuje dynamické pole
- při potřebě jej zvětšit, zmenšit pak alokujeme nové pole a to staré musíme překopírovat
- kopírování polí je časově náročné a proto je třeba si rozmyslet o kolik jej zmenšovat/zvětšovat 
## Funkce pracující s poli
- Pokud je pole parametrem funkce je předáno **odkazem**, předá se adresa prvního prvku pole
- Položky pole je možné ve funkci měnit a tato změna se zachovává


