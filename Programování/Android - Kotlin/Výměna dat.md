# Výměna dat
Nejčastější formáty:
- XML
- JSON


## XML
- SAX parser API
- DOM parser API
- XmlPullParser

### Čtení XML
Ukázka pro XmlPullParser:
``` Kotlin
val parser = XmlPullParserFactory.newInstance().newPullParser()

parser.setInput(input)
```

Kde input může být:
- InputStream
- FileReader
- StringReader
- BufferedReader

Parsování je řízeno událostmi:
- START_DOCUMENT
- START_TAG - String getName()
- TEXT - String getText()
- END_TAG - String getName()
- END_DOCUMENT

### Zápis XML
XMLSerializer
``` Kotlin
XmlSerializer serializer = Xml.newSerializer();
```
Zápis pomocí funkcí:
- setOutput(writer) - určení výstupu
- startDocument()
- startTag()
- attribute()
- text()
- endTag()
- endDocument()


## JSON
Vytváření JSON řetězců: 
- JSONObject – sada mapování klíč / hodnota
- JSONArray – indexované pole hodnot
- JsonWriter – helper pro vytváření JSON včetně výstupního proudu

Parsování JSON řetězců:
- JSONTokener – parsuje JSON ze zadaného řetězce, umí JSONObject
- JsonReader – parsuje JSON ze vstupního proudu