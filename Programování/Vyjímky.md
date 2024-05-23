#C 
# Výjimky (Exceptions)
V jazyce C++, pro ošetřování vyjímek se používá mechanismus try-catch. Tento mechanismus umožňuje zachytit vyjímku (exception) v bloku kódu a provést odpovídající zpracování nebo manipulaci s ní.

```cpp
try { 
	int age = 15; 
	if (age >= 18) { 
		cout << "Access granted - you are old enough."; 
	} else { 
		throw (age); 
	} 
} 

catch (int myNum) { 
	cout << "Access denied - You must be at least 18 years old.\n"; 
	cout << "Age is: " << myNum;
}
```

## Výběr handleru
1. Handler s parametrem typu T, cont T nebo const T&, kde T je objektový typ zachytí i výjimku typu TT, kde TT je jednoznačný a přístupný potomek typu T.
2. Handler s parametrem typu T*, kde T je objektový typ zachytí i výjimku typu TT*, pokud lze ukazatel na T přetypovat na ukazatel na TT pomocí standartních konverzí ukazatelů

=> výjimku zachytí první handler, který to udělat může

Zde je příklad použití try-catch bloku:
```cpp
try {     
	// Kód, ve kterém může dojít k vyhození vyjímky     
	// ...     
	throw SomeException(); // Vyhození vyjímky     
	// ... 
} catch (const SomeException &e) {     
	// Zpracování vyjímky typu SomeException     
	// ... 
} catch (const AnotherException &e) {     
	// Zpracování vyjímky typu AnotherException     
	// ... 
} catch (std::exception &e) {     
	// Zpracování všech ostatních vyjímek     
	// ... 
}
```
