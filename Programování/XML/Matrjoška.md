#xml 
# Matrjoška
Definice prvků se do sebe ve schématu vkládají přímo, stejně jako prvky v dokumentu. Na nejvyšší úrovni vždy jen jeden prvek. Krátké a kompaktní schéma. Pro složitější jazyky nepřehledné. Nelze opakovaně využívat dílčí definice.

## Příklad
``` xml
<xsd:element name=“zbozi“ maxOccurs=“unbounded“> 
	<xsd:complexType> 
		<xsd:sequence> 
			<xsd:element name=“nazev“ type=“xsd:string“/> 
			<xsd:element name=“cena“ type=“xsd:decimal“/> 
		</xsd:sequence> 
		<xsd:attribute name=“kod“ type=“xsd:integer“/> 
	</xsd:complexType> 
</xsd:element>
```