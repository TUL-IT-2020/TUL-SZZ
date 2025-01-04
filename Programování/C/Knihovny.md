# Knihovny

ctype.h
- isdigit(c) 
- isalphanum(c) 
- sizeof(int)

stdio.h
- printf(), 
- scanf(), 
- getchar(), 
- fopen()

stdlib.h
- malloc()
- free()
- rand()
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

## Vkládání hlavičkových souborů
1. `#include <soubor>` – soubor se hledá v systémovém adresáři 
2. `#include ”soubor”` – soubor musí být ve stejném adresáři jako „volající“ soubor

stdio.h  - knihovna standardního vstupu výstupu
```C
#include <stdio.h>
```
