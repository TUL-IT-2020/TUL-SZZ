# Práce se soubory
Módy přístupu:

mode = \[ r, w, a, ra, wa \]
- a append

## textové soubory
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


## Binární soubory
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
