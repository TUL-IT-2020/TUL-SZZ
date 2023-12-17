# Intenty
Základní asynchronní komunikační nástroj mezi prvky aplikací. Třída, která obsahuje popis a data nějakého záměru. Objekt s definicí cílového procesu s možností zaslat mu data. Záměr může být implicitní či explicitní
- **Explicitní intent** – má informaci o konkrétní třídě, kterou chce spustit
``` Kotlin
Intent i = new Intent(context, MojeActivity.class)
startActivity(i)
```

- **Implicitní intent** – má pouze info o záměru (např. chci psát 
email) a případná data k předání. Nechá na systému, 
kterou aplikaci (aktivitu) spustí nebo nabídne. 
``` Kotlin
Intent intent = new Intent(Intent.ACTION_VIEW, uri)
startActivity(intent)
```

Další ukázky Intentu:
``` Kotlin
fun callBrowser(v: View){
    val url = "[https://www.google.com/search?q=how+to+gain+weight](https://www.google.com/search?q=how+to+gain+weight)".toUri()
    val zamer = Intent(Intent.ACTION_VIEW)
    zamer.setData(url)
    startActivity(zamer)
}
fun callByPhone(v: View){
    try {
        val cislo = "tel: +420123123123".toUri()
        val zamerCall = Intent(Intent.ACTION_DIAL)
        zamerCall.setData(cislo)
        startActivity(zamerCall)
    } catch (e:Exception){
        Log.v("call",e.stackTrace.toString())
    }
}
```

## Atributy intentu
- **Action** – akce, kterou chceme provést
- **Category** – kategorie, do které záměr spadá
  - `CATEGORY_BROWSABLE`
  - `CATEGORY_LAUNCHER`
  - `CATEGORY_HOME`
- **Extras** – předávaná data

## Intent se zasílá pomocí
- `startActivity(intent)` – spustí aktivitu a nečeká na návratovou hodnotu
- `startActivityForResult(intent, requestCode)` – spustí aktivitu a čeká na návratovou hodnotu
- `onActivityResult(requestCode, resultCode, data)` - metoda, která se volá po návratu z aktivity

## Intent a přenos dat
S intentem se data předávají jako instance Bundle. Bundle zapouzdřuje mapu (klíč, hodnota).

Odesílání dat:
``` Kotlin
Intent intent = new Intent(this, SecondActivity.class)
intent.putExtra("key", 42)
\\ or 
intent.getExtras().putInt("key", 42)
```

příklad odpovědi:
``` Kotlin
@Override
public void finish() {
    Intent data = new Intent()
    data.putExtra("vysledek", vypocet)
    setResult(RESULT_OK, data)
    super.finish()
} 
```

## Příklady
Webová stránka
`new Intent(Intent.ACTION_VIEW, Uri.parse("http://www.tul.cz"))`

Volání čísla
`new Intent(Intent.ACTION_CALL, Uri.parse("tel:(+420)485353111"))`

Vytočení čísla
`new Intent(Intent.ACTION_DIAL, Uri.parse("tel:(+420)485353111"))`

GEO data
`new Intent(Intent.ACTION_VIEW, Uri.parse("geo:50.125,8.65?z=17"))`

Otevření kontaktů
`new Intent(Intent.ACTION_VIEW, Uri.parse("content://contacts/people/"))`

Otevření konkrétního kontaktu
`new Intent(Intent.ACTION_VIEW, Uri.parse("content://contacts/people/1"))`

Získání obrázku
`new Intent("android.media.action.IMAGE_CAPTURE")`