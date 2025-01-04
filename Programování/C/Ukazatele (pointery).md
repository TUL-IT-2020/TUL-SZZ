#C 
# Ukazatele (pointery)

\* - běž na adresu kam ukazuje pointer
& - dej mi adresu paměti
```C
int a = 42;
int * p_a = NULL;
p_a = &a;
printf("%d\n", *p_a);
```

```C
typedef *int P_INT;	// definujeme novy datovy typ ukazatelu, funguje jako makro
```
## Pointerová aritmetika
Platné operace jsou: 
- součet pointeru a celého čísla 
- rozdíl pointeru a celého čísla 
- porovnání pointerů stejných typů
- rozdíl dvou pointerů stejných typů

```C
int *p;
...
*(p + 10) = k;	// posun v poli o deset kroku bazoveho typu
```
