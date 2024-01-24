#xml
# XML strom
## Typy uzlů
- **kořenový** (root element) - jediný element, který nemá rodiče
- **prvek** (element)
- **atribut** (attribute) - jeho rodičem je prvek
- **textový** (text) - vždy list
- **komentář** (comment)

## Vztahy mezi uzly
- **rodič** (parent)
- **potomek** (child)
- **sourozenec** (sibling)

# XPath
Výsledkem XPath výrazu je hodnota nebo skupina uzlů XML stromu vyhovujících podmínkám. **XPath cesta** je posloupnost uzlů, která začíná kořenovým uzlem a končí libovolným uzlem, sekvence je oddělena lomítkem `/`.

## Kroky cesty
- identifikátor osy
- test uzlu
- podmínka (predikát)

Vzor: `osa::test[predikát]`

### Oddělovače
- `/` - odděluje kroky cesty, další krok musí být potomkem předchozího
- `//` - odděluje kroky cesty, další krok obsahuje libovolného potomka předchozího

## Výběr uzlů
- `*` - všechny uzly
- `nazev` - všechny uzly s daným názvem
- `@nazev` - všechny atributy s daným názvem
- `node()` - všechny uzly
- `text()` - všechny textové uzly
- `comment()` - všechny komentáře
- `processing-instruction()` - všechny zpracovávané instrukce

## Osa
Typy os:
- self
- ancestor
- preceding
- descendant
- following

Přístup k uzlům pomocí osy:
- `ancestor::` - všechny předchůdce
- `ancestor-or-self::` - všechny předchůdce a aktuální uzel
- `child::` - všichni potomci (pouze první úroveň)
- `descendant::` - všichni potomci (všechny úrovně)
- `descendant-or-self::` - všichni potomci a aktuální uzel
- `self::` - aktuální uzel

## Podmínky (predikáty)
- `[podminka]` - vybere uzly, které splňují podmínku
- `[n]` - vybere n-tý uzel
- `[last()]` - vybere poslední uzel

## Funkce

### Hledání řetězce

- `contains(string1, string2)` - vrátí `true`, pokud `string1` obsahuje `string2`
- `starts-with(string1, string2)` - vrátí `true`, pokud `string1` začíná `string2`
- `ends-with(string1, string2)` - vrátí `true`, pokud `string1` končí `string2`
- `string-length(string)` - vrátí délku řetězce
- `substring(string, start, length)` - vrátí podřetězec
- `substring-before(string1, string2)` - vrátí podřetězec před `string2`
- `substring-after(string1, string2)` - vrátí podřetězec za `string2`
  

- `normalize-space(string)` - vrátí řetězec bez bílých znaků na začátku a na konci a všechny bílé znaky uvnitř nahradí jedním mezerou
- `translate(string, string1, string2)` - vrátí řetězec, ve kterém jsou znaky z `string1` nahrazeny znaky z `string2`