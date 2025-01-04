#C 
# Výčtový datový typ - enumerátor
Slouží pro automatické vytváření mnemotechnických názvů číslovaných položek.
Položky jsou číslovány od 0 není-li nastaveno jinak.
Položky jsou typu int.

```C
typedef enum {
	value_0 [= 1],
	value_1 [= 2],
	value_unknown
} enum_type_t;

enum_type_t x = value_unknown;
```

> [!tip] Proč `value_unknown`?
Umožní nám inicializovat proměnou daného typu bezpečnou hodnotou.

```C
typedef enum {
    EN,
    CZ,
    GE,
    PL,
    NBR_LANGUAGES
} languages_t;
```

> [!tip] Proč `NBR_LANGUAGES`?
Umožnuje to alokovat pole pointerů o počtu jazyků v aplikaci, takže s přidáním dalšího se výčet při kompilaci alokuje rovnou větší a všechno bude sedět.


```C
for (int lang = 0; i < NBR_LANGUAGES; i++) {
    printf("%s\n", translated_strings[lang][AHOJ]);
}
```