## Android resources - struktura /res
Kořenový adresář pro resources má následující strukturu:

- drawable/ - bitmapové obrázky (png, gif, jpg)
- layout/ - kontejnery pro grafické komponenty (xml)
- menu/ - XML soubory s definicemi jednotlivých menus
- raw/ - jakékoli soubory, které nespadají do uvedených 
kategorií
- values/ - XML soubory s definicemi textů, stylů, polí 
stringů, barev, rozměrů, parametrů aj.
- xml/ - jakékoli další XML soubory pro aplikaci

## res/values/strings.xml
Definice řetězců pro aplikaci a manifest
``` xml
<resources>
    <string name=“hello“>Ahoj</string>
    <string name=“home“>Domů</string>
    
    <string-array name=“days“>
        <item>Pondeli</item>
        <item>@string/utery</item>
    </string-array>
</resources>
```
Přístup k nim:
- Java 
``` java
text = getString(R.string.hello);

Resources res = getResources();
res.getStringArray(R.array.days);
```

### lokalizace
Vytvoření adresáře s příslušným kódem jazyka.
`/res/values-cs/strings.xml`
``` xml
<resources>
    <string name=“hello“>Ahoj</string>
    <string name=“home“>Domů</string>
</resources>
```
`/res/values-en/strings.xml`
``` xml
<resources>
    <string name=“hello“>Hello</string>
    <string name=“home“>Home</string>
</resources>
```
Při spuštění aplikace se automaticky zvolí jazyk podle nastavení telefonu.

## Zdroje:
- https://developer.android.com/guide/topics/resources/providing-resources.html
- https://www.zdrojak.cz/clanky/vyvijime-pro-android-suroviny-intenty-a-jednotky/

