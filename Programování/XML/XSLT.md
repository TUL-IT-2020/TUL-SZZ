#xml 
# XSLT transformace

Definice vzhledu XML dokumentu:
- CSS - jednoduchá varianta
- XSLT - přímo pro XML

Výstupní formáty:
- HTML
- XML
- Text
- PDF
- ...

Vazba na XML dokument:
- `<?xml-stylesheet type="text/xsl" href="style.xsl"?>`
- jako parametr při zpracování XML dokumentu

## XSL dokument

```xml
<xsl:stylesheet
    xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
    version="1.0">

<-- definice vzhledu -->

</xsl:stylesheet>
```

## Šablony

```xml
<xsl:template match="element">
    <xsl:apply-templates select="element" />
</xsl:template>
```
Určuje, na které elementy se šablona vztahuje. Pokud není uveden `match`, vztahuje se na všechny elementy.

Vybírá elementy pomocí [[XPath|XPath]] výrazu.

## For

```xml
<xsl:for-each select="XPath vyraz">
    <xsl:apply-templates select="element" />
</xsl:for-each>
```

