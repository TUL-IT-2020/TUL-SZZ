# Manifest
Soubor `AndroidManifest.xml` obsahuje metadata o aplikaci. Definuje se zde:
- Informace o package a verzi aplikace
- Název, ikona, theme aplikace
- Komponenty aplikace (Activity, Service aj.)
- Permissions (práva)
- Minimální a maximální Android API level
- Použité knihovny

Manifest též řeší i oprávnění aplikace a jednotlivých 
komponent. U Android verzích se při instalaci / spuštění zkontroloval úplný definovaný strom požadovaných oprávnění. Pokud některé z oprávnění nebylo povoleno, aplikace se nenainstaluje / nespustí.

Manifest pro využití telefonního volání:
``` xml
<uses-permission android:name="android.permission.CALL_PHONE"></uses-permission>
<uses-feature android:name="android.hardware.telephony" android:required="false"></uses-feature>
```

## API level
`uses-sdk>` - verze SDK (API Level) pro aplikaci:
- android:minSdkVersion – minimální API Level
- android:targetSdkVersion – API Level doporučená, když není, použije se minimální verze
- android:maxSdkVersion – maximální API Level, od SDK verze 2.0.1 (API 6) ignorovaná / nedoporučovaná

## Oprávnění
`uses-permission>` - oprávnění aplikace:
- android:name – název oprávnění

## Konfigurace
`<uses-configuration>` - SW a HW požadavky:
- android:reqNavigation – dpad,trackball, wheel, nonav …
- android:reqTouchScreen– notouch, stylus, finger …
- android:reqKeyboardType – nokeys, querty, twelvekey …
- android:reqHardKeyboard – true / false
- android:reqFiveWayNav – true / false

## Intenty
`<intent-filter>` - definice [[Intent|intentů]], které komponenta zpracovává. Element se může v aktivitě opakovat několikrát. Obsahuje akci, na kterou umí aktivita zareagovat. Volitelně obsahuje kategorii záměru a předávaná data.

``` xml
<activity android:name=".MainActivity" >
    <intent-filter>
    <action android:name="android.intent.action.MAIN" />
        <category android:name="android.intent.category.LAUNCHER" />
    </intent-filter>
</activity>
```

Aktivita typu browser
``` xml
<activity android:name=".BrowserActivity">
	<intent-filter>
		<action android:name="android.intent.action.VIEW" />
		<category android:name="android.intent.category.DEFAULT" />
		<data android:scheme="http"/> 
	</intent-filter>
</activity>
```
