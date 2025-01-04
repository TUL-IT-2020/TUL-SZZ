#C 
# Funkce
V C nejsou procedury v pravém slova smyslu, pouze funkce. Všechny parametry jsou volané hodnotou!!

Procedury využívají návratový typ `void`.

## Funkce main
Hlavní funkce programu, zde se začne vykonávat kód.
```C
/* Funkce main
 * argc - počet parametrů
 * argv - je pole řetězců
 */
int main (int atgc, char *argc[]) {
	return 0
}
```

## Definice funkce
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

## Předání argumentů do funkce
![[Předávání parametrů]]
### Hodnotou

### Referencí
```C
void vymen(int *p_x, int *p_y){ 
	int pom; 
	pom = *p_x; 
	*p_x = *p_y; 
	*p_y = pom; 
}

vymen (&i, &j);
```

## Rekurzivní funkce
[[Rekurze|Rekurzivní]] funkce volající sama sebe.
```C
int faktorial(int n){ 
	return ((n<=0)? 1 : n*faktorial(n-1)); 
}
```

![[fibonaci_rekurze_c]]

## Ukazatel na funkci
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
