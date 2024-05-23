#xml
# Schema
Označováno XSD (XML Schema Definition).
Jmenný prostor: `xmlns:xsd="http://www.w3.org/2001/XMLSchema"`
Oproti DTD umožnuje pokročilou definici datových typů (jiných než string).

https://www.w3.org/TR/xmlschema-2/#built-in-datatypes

![[type-hierarchy.gif]]

## Odvozování typů
- **restriction** – omezí se rozsah hodnot
- **extension** – rozšíří se rozsah hodnot
- **list** – seznam hodnot
- **union** – sjednocení typů

### Restrikce řetězců

#### omezení délky
příklad: jméno – maximálně 20 znaků 
``` xml
<xsd:simpleType name="jmenoType"> 
	<xsd:restriction base="xsd:string"> 
		<xsd:maxLength value="20"/> 
	</xsd:restriction>
</xsd:simpleType>
```

Omezení minimální a maximální délky: 
``` xml
<xsd:simpleType name="zkratkaType">
	<xsd:restriction base="xsd:string">
		<xsd:minLength value="3"/>
		<xsd:maxLength value="5"/>
	</xsd:restriction>
</xsd:simpleType>
```

#### enumeration

výčet hodnot: enumeration 
příklad: fakulty naší univerzity 

``` xml
<xsd:simpleType name="fakultaTULType">
	<xsd:restriction base="xsd:string"> 
		<xsd:enumeration value="FS"/> 
		<xsd:enumeration value="FT"/> 
		<xsd:enumeration value="FP"/> 
		<xsd:enumeration value="EF"/> 
		<xsd:enumeration value="FM"/> 
		<xsd:enumeration value="FA"/> 
	</xsd:restriction> 
</xsd:simpleType>
```

#### patern
příklad: telefon – 3 skupiny 3 číslic, lze s mezerami 
``` xml
<xsd:simpleType name="telefonType"> 
	<xsd:restriction base="xsd:token"> 
		<xsd:pattern value="\d{3} ?\d{3} ?\d{3}"/> 
	</xsd:restriction> 
</xsd:simpleType>
```

### Složené datové typy
Popisují strukturu dokumentu. Definují vzájemné vztahy jednotlivých prvků. 
Tři základní druhy: 
- **sequence** – prvky se musí vyskytovat v daném pořadí 
- **all** – prvky se mohou vyskytovat v libovolném pořadí 
- **choice** – vyskytuje se jeden z uvedených prvků 
lze vnořovat (kromě all)

#### sequence
``` xml
<xsd:complexType name="adresaType"> 
	<xsd:sequence> 
		<xsd:element name="ulice" type="xsd:string"/> 
		<xsd:element name="mesto" type="xsd:string"/> 
		<xsd:element name="psc" type="xsd:string"/> 
	</xsd:sequence>
</xsd:complexType>
```


## Prvky
Prvek element, atributy: 
- **name** – jméno prvku, povinný 
- **type** – typ prvku (co je jeho obsahem); pokud chybí, může být typ obsahu definován přímo na místě jako obsah prvku element 
- **default** – implicitní obsah prvku 
- **fixed** – pevně definovaný obsah prvku

## Atributy
Prvek attribute, jeho atributy: 
- **name** – jméno atributu, povinný 
- **type** – typ atributu (omezuje hodnotu), povinný 
- **use** – hodnota "required" stanoví povinný atribut 
- **default** – implicitní hodnota 

Musí být na konci (za prvky). Do složených typů se přidává normálně 

`<xsd:attribute name="id" type="xsd:ID" use="required"/>`

## Jak vytvářet schéma?
- matrjoška 
- plátkování 
- slepý Benátčan

### Matrjoška
![[Matrjoška]]

### Plátkování
![[Plátkování]]
### Slepý Benátčan
![[Slepý Benátčan]]

