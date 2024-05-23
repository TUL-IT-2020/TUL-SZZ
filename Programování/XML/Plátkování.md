#xml
# Plátkování
Všechny prvky a atributy se definují na stejné (nejvyšší) úrovni. Odkazují se na sebe pomocí ref=“jméno“. Definované prvky/atributy lze používat opakovaně. Koncepce blízká DTD. Obsah prvku se nemůže lišit podle kontextu (rodiče).

## Příklad
``` xml
<xsd:element name=“nazev“ type=“xsd:string“/> 
<xsd:element name=“cena“ type=“xsd:decimal“/> 
<xsd:attribute name=“kod“ type=“xsd:integer“/> 

<xsd:element name=“zbozi“> 
	<xsd:complexType> 
		<xsd:sequence> 
			<xsd:element ref=“nazev“/> 
			<xsd:element ref=“cena“/> 
		</xsd:sequence> 
		<xsd:attribute ref=“kod“/> 
	</xsd:complexType> 
</xsd:element>
``` 