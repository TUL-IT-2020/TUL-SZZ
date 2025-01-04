# Řízení toku programu

## if-else
If (podmínka) {kód}, ano seznamme se s blokem kódu {}
Splněná podmínka může být libovolná nenulový výraz
```C
if (1) 
if (x = 4) 
if (4 == 4) 
if (sizeOf(char))
```
Nulový výraz je nesplněná podmínka
```C
if (0) 
if (!1) 
if (4 != 4) 
if (sizeOf(char)-1)
```
## Switch – case
Větvení na základě výrazu
Default je vykonán vždy

```C
switch (expression) {
	case constant_expression:
		// není třeba blok kódu
	case constant_expression2:
		// pokud je splněno, tak je také vykonán
		break;
	default:
		// vykonáno vždy
}
```

