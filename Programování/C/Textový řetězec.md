#C
# Textový řetězec
Jde vlastně o speciální typ pole, kdy bázový typ je `char` - charakter (znak).

- řetězec je vždy u končen znakem '\0’
- řetězec může mít libovolnou délku (omezenou pouze velikostí)
- konec a délka se určí právě znakem '\0’
- maximální index pole je tedy N-1

```C
#include <string.h> 
#include <stdlib.h>
```
## Alokace
Staticky:
```C
char string[10]; 
char str[] = "Staticky vytvořené";
char str2[24] = "Nedostatečně velké pole!";
```
dynamicky:
```C
char *string; 
string=(char*)malloc(10*sizeof(char))
string[0] = ‘\0’; //nulovy retezec zakoncujici pole
```
