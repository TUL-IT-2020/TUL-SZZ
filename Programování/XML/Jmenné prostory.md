#xml
# Jmenné prostory
`xmlns:prefix=“URI“`
Deklaruje jmenný prostor označený v kvalifikovaných jménech daným prefixem.
`xmlns=“URI“`
Deklaruje implicitní jmenný prostor, platí pro jména 
prvků bez prefixu; ne pro atributy – atribut bez 
prefixu je ve stejném prostoru jako jeho prvek.
```xml	
<h:html xmlns:xdc="http://www.xml.com/books"
		xmlns:h="http://www.w3.org/HTML/1998/html4">
<h:head><h:title>Book Review</h:title></h:head>
<h:body>
	<xdc:bookreview>
	<xdc:title h:style="color: red;">XML: A Primer</xdc:title>
	<h:p>Autor: <xdc:author>Simon St. Laurent</xdc:author></h:p>
	<h:p>Vydáno: <xdc:date>1998/01</xdc:date></h:p>
	<h:p>Dobrý úvod do XML.</h:p>
	</xdc:bookreview>
</h:body>
</h:html>
```

Rezervované jmenné prostory:
- xml – http://www.w3.org/XML/1998/namespace
- xmlns – http://www.w3.org/2000/xmlns/