#xml 
# Relax NG
Relax NG je alternativním schématem pro XML.
- **DTD** – staré, jednoduché, nevyhovuje pro složitější dokumenty
- **XML Schema** – složité, nepřehledné, nevyhovuje pro jednoduché dokumenty
- **Relax NG** – jednoduché, přehledné, vyhovuje pro jednoduché i složité dokumenty

## Syntaxe
Relax NG má dvě syntaxe:
- **XML syntax** – je to XML dokument, který popisuje schéma
- **Kompaktní syntax** – je to textový dokument, který popisuje schéma

Ukázka kompaktní syntaxe:
```xml
start = element osoba { 
    attribute jmeno { text }, 
    attribute prijmeni { text }, 
    attribute rokNarozeni { xsd:gYear },
}
```

### Opakování
- **zero or more** – `*`
- **one or more** – `+`
- **zero or one** – `?`
- **exactly n** – `{n}`
  
### Výběr
- **choice** – `|`
- **interleave** – `,`
- **group** – `&`

```xml
start = element osoba { 
    attribute jmeno { text }, 
    attribute prijmeni { text }, 
    attribute rokNarozeni { xsd:gYear },
    (element adresa { text } | element telefon { text })*
}
```

## Pojmenované vzory
```xml
start = element osoba { 
    jmeno, 
    attribute rokNarozeni { xsd:gYear },
    (element adresa { text } | element telefon { text })*
}

jmeno = attribute jmeno { text }, 
        attribute prijmeni { text }
```

## Vkládání definic
```xml
include "adresa.rng"
include "telefon.rng"
```

### Odkazy
```xml
start = element osoba { 
    external jmeno, 
    attribute rokNarozeni { xsd:gYear },
    (element adresa { text } | element telefon { text })*
}
```


