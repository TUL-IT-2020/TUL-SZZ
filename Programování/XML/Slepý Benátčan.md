#xml
# Slepý Benátčan
Předem se (na globální úrovni) definují typy. Prvky a atributy se definují lokálně (jako v matrjošce), ovšem triviálně s využitím připravených typů. Nejflexibilnější, typy lze používat opakovaně, ale schéma je delší. Vhodné pro složité jazyky.

## Příklad
``` xml
<xsd:simpleType name=“nazevTyp“> 
	<xsd:restriction base=“xsd:string“> 
		<xsd:maxLength value=“50“/> 
	</xsd:restriction> 
</xsd:simpleType> 

<xsd:simpleType name=“cenaTyp“> 
	<xsd:restriction base=“xsd:decimal“> 
		<xsd:fractionDigits value=“2“/> 
	</xsd:restriction> 
</xsd:simpleType>

<xsd:simpleType name=“kodTyp“> 
	<xsd:restriction base=“xsd:integer“/> 
</xsd:simpleType>

<xsd:complexType name=“zboziTyp“> 
	<xsd:sequence> 
		<xsd:element name=“nazev“ type=“nazevTyp“/> 
		<xsd:element name=“cena“ type=“cenaTyp“/> 
	</xsd:sequence> 
	<xsd:attribute name=“kod“ type=“kodTyp“/> 
</xsd:complexType>

<xsd:element name=“zbozi“ type=“zboziTyp“/>
```