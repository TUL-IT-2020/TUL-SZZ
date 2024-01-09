#xml
# XML
eXtensible Markup Language

## XML dokument
### prolog
nepovinný
``` xml
<?xml version=“1.0“ ... ?>
```
nepovinné součásti: 
- `encoding=“název“` – použité kódování, implicitně UTF-8 
- `standalone=“yes|no“` – zda je dokument soběstačný (neodkazuje se na externí definice)

### Značky
#### Atributy
```xml
<div class="poznamka">...</div>
```

### Entity
Psaní speciálních znaků:
- &lt; <
- &gt; >
- &amp; &
- &quot; “
- &apos; '
### Komentáře
```xml
<!-- text komentáře -->
```
