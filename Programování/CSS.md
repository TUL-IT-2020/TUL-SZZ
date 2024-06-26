#CSS
# CSS (Cascading Style Sheets) - Základní Koncepty:

**1. Vlastnosti:**

- **CSS vlastnosti** definují vizuální vzhled a chování webových prvků. Příklady základních vlastností zahrnují `color` (barva textu), `font-size` (velikost písma), `margin` (okraje) a mnoho dalších.

**2. Hodnoty:**

- **CSS hodnoty** jsou přiřazeny vlastnostem a určují, jak má být vzhled nebo chování daného prvku upraveno. Například hodnoty pro `color` mohou být konkrétní barvy nebo názvy barev.

**3. Dědění:**

- **Dědění v CSS** znamená, že některé vlastnosti prvků jsou převzaty z jejich rodičů. Například, pokud nastavíte barvu textu na nadřazeném (rodičovském) elementu, děti budou tuto barvu zdědovat, pokud není specifikována jinak.

**4. Kaskádování:**

- **Kaskádování v CSS** označuje proces, kterým jsou určeny a aplikovány hodnoty vlastností na základě různých zdrojů a pravidel. Kaskádování umožňuje kombinovat styly definované na různých úrovních, například globálně, lokálně nebo v rámci jednotlivých prvků.

## Blokový Model CSS:

**Blokový model CSS** se používá k definování a rozdělení prostoru, který prvek zabírá v dokumentu. Každý prvek v HTML dokumentu je obklopen tzv. blokovým rámcem, který se skládá z několika částí:

1. **Content (Obsah):**
    - Obsahuje samotný obsah elementu, například text nebo obrázek.
2. **Padding (Vnitřní okraj):**
    - Je to prostor mezi obsahem a vnějším okrajem (margin). Padding definuje vnitřní prostor uvnitř blokového rámu.
3. **Border (Ohraničení):**
    - Ohraničení kolem obsahu a vnitřního okraje. Má vlastnosti jako barva, tloušťka a styl.
4. **Margin (Vnější okraj):**
    - Je to prostor mezi vnějším okrajem a okolními prvky. Margin definuje vzdálenost mezi prvkem a jeho okolím.
## Příklad:

```css
/* CSS pro blokový model */
div {
  width: 200px;         /* Šířka bloku */
  height: 150px;        /* Výška bloku */
  padding: 10px;        /* Vnitřní okraj */
  border: 2px solid #333; /* Ohraničení */
  margin: 20px;          /* Vnější okraj */
}
```

Tento kód definuje blokový model pro `div` element. Obsah má šířku 200px, výšku 150px, vnitřní okraj (padding) je 10px, ohraničení (border) je 2px silná čára ve stylu solid s barvou #333 a vnější okraj (margin) je 20px. Tato konfigurace ovlivňuje, jak se bude element zobrazovat a jak bude interagovat s okolními prvky.