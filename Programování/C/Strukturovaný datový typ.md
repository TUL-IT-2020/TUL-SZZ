#C
# Strukturovaný datový typ
Struktury jsou vlastně normální datové typy a lze je tedy jak předávat tak i vracet z a do funkcí. Při předávání hodnotou je nutný vytvořit kopii struktury ve stacku a to může být náročné, proto je lépe předávat pointer.

> [!info] Struktura 
> Je vlastně třída bez metod

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
} LIST_t;
```

operátory přístupu:
. chci na atribut
-> skoč na ukazatel a vrat atribut, ekvivalentní k (*instance).atribut

```C
struct person {
	char age;
	int weight;
};

struct person Jack;
Jack.age = 20;
```