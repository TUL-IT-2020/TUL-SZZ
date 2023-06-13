# Rekurze
Rekurze v programovacím jazyku Python se používá k vytváření funkcí, které volají samy sebe. Tato technika je užitečná pro řešení problémů, které mají rekurzivní strukturu, tj. problémy, které lze rozdělit na menší části stejného typu.

Při použití rekurze je důležité stanovit podmínku ukončení, která zastaví rekurzivní volání a umožní vrácení výsledku. Pokud tato podmínka není správně nastavena, může rekurze způsobit nekonečnou smyčku a přetečení zásobníku.

## Algoritmy

1. **Vyhledávání v adresářové struktuře**: Rekurze může být použita k procházení složek a souborů v adresářové struktuře. Funkce se volá sama pro každou podadresář a umožňuje tak prohledávání všech úrovní složek.
2. **Binární stromy**: Rekurze se často používá při práci s binárními stromy, které mají hierarchickou strukturu. Rekurzivní funkce může být použita k procházení stromu, vyhledávání konkrétního uzlu nebo provádění různých operací na jednotlivých uzlech.
3. **Řazení**: Některé algoritmy řazení, jako například quicksort nebo mergesort, jsou implementovány rekurzivně. Tyto algoritmy rozdělují problém na menší části, řadí je a následně je spojují do výsledného řazeného pole.
4. **Vyhledávání v grafu**: Při prohledávání grafu (např. algoritmy DFS - hloubkové prohledávání nebo BFS - prohledávání do šířky) se často používá rekurze. Funkce může volat sama sebe pro každý sousední vrchol a tak procházet celý graf.
5. **Fraktály**: Rekurze se používá pro generování fraktálů, jako je například Mandelbrotova množina. V případě fraktálů se rekurzivní volání opakuje pro každý bod v komplexní rovině.
6. **Backtracking**: Algoritmy backtrackingu, jako například řešení problému osmibajtové dámy, používají rekurzi k systematickému procházení možných kombinací řešení.

## Faktoriál
Příklad jednoduché rekurzivní funkce v Pythonu, která vypočítá faktoriál čísla:
```python
def factorial(n):     
	if n == 0:        
		return 1     
	else:         
		return n * factorial(n - 1)
```

V této funkci je podmínka ukončení stanovena pro n == 0, kdy je vrácena hodnota 1. V opačném případě je volána sama funkce `factorial()` s argumentem n-1 a výsledek je vynásoben aktuálním číslem n.

Při volání této funkce s argumentem 5 (`factorial(5)`) dojde k rekurzivním voláním a výpočet bude vypadat následovně:

```bash
factorial(5) = 5 * factorial(4) 
factorial(4) = 4 * factorial(3) 
factorial(3) = 3 * factorial(2) 
factorial(2) = 2 * factorial(1) 
factorial(1) = 1 * factorial(0) 
factorial(0) = 1
```

Výsledek je tedy $5! = 5 * 4 * 3 * 2 * 1 = 120$.

Při implementaci rekurze je třeba dávat pozor na správnou podmínku ukončení a zajištění postupného přibližování se k této podmínce. Také je nutné dbát na efektivitu rekurzivních funkcí, protože nevhodná implementace může vést ke zbytečně velkému množství rekurzivních volání a výraznému snížení výkonu programu.

## Fibonacci
Fibonacciho posloupnost je další příklad, který se často používá k ilustraci rekurze. Fibonacciho posloupnost je posloupnost čísel, kde každé číslo je součtem dvou předcházejících čísel.

Zde je příklad rekurzivní funkce v Pythonu pro výpočet Fibonacciho posloupnosti:
```Python
`def fibonacci(n):     
	if n <= 1:         
		return n     
	else:         
		return fibonacci(n - 1) + fibonacci(n - 2)
```

V této funkci je podmínka ukončení stanovena pro n <= 1, kdy jsou vráceny samotné čísla 0 a 1. V opačném případě je volána sama funkce `fibonacci()` dvakrát, se sníženými argumenty n-1 a n-2, a výsledky jsou sečteny.

Při volání této funkce s argumentem 6 (`fibonacci(6)`) dojde k rekurzivním voláním a výpočet bude vypadat následovně:

```bash
fibonacci(6) = fibonacci(5) + fibonacci(4) 
fibonacci(5) = fibonacci(4) + fibonacci(3) 
fibonacci(4) = fibonacci(3) + fibonacci(2) 
fibonacci(3) = fibonacci(2) + fibonacci(1) 
fibonacci(2) = fibonacci(1) + fibonacci(0) 
fibonacci(1) = 1 fibonacci(0) = 0
```

Výsledek je tedy $fib(6) = 8$.

Při implementaci Fibonacciho posloupnosti je důležité si uvědomit, že rekurzivní přístup je neefektivní pro větší hodnoty n, protože dochází k opakovanému výpočtu stejných podposloupností. Pro výpočet Fibonacciho posloupnosti s vyššími hodnotami se doporučuje použít dynamické programování nebo iterativní přístup.