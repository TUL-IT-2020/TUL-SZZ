# Services
V principu se podobají aktivitám, ale bez UI. Určeny hlavně pro dlouhou kontinuální činnost. Přehrávání hudby, dlouhé stahování dat aj. Nevadí jim přesunutí do pozadí a práce s jinou aplikací. Mají vlastní životní cyklus nezávislý na aktivit.

Méně náchylné k násilnému ukončení systémem než
activity na pozadí. Pokud jsou přeci jen ukončeny, systém je po získání potřebných prostředků restartuje
Jsou spouštěny, zastavovány a kontrolovány z jiných
komponent aplikace (např. jiné Service, Activity nebo
BroadcastReceiveru). Je nutné je registrovat v AndroidManifestu.

## Životní cyklus Service

- onCreate( ) - zavoláno, když je Service vytvořena jakýkoliv způsobem 
- onStartCommand( ) - zavoláno, když je vyvolána metoda startService( ) 
- onBind( ) - zavoláno, pokud klient zavolá bindService()
- onDestroy( ) - zavoláno, když má být Service odstraněna

![[Lifecycle of a Service.png]]

## Spuštění Service
`onStartCommand()` - spuštění pomocí `startService()`, vrací: 
- `START_STICKY` - pokud je Service zastavena systémem, bude znovu spuštěna, jakmile budou k dispozici prostředky
- `START_NOT_STICKY` - pokud je Service zastavena systémem, nebude znovu spuštěna, dokud nebude znovu vyvolána metodou `startService()`
- `START_REDELIVER_INTENT` - pokud je Service zastavena systémem, bude znovu spuštěna, jakmile budou k dispozici prostředky a bude jí předána původní intent

## Zastavení Service
`onDestroy()` - zastavení pomocí `stopService()` nebo `stopSelf()`

## Flagy pro startService()
- `START_FLAG_REDELIVERY` - při restartu Service bude předán původní intent
- `START_FLAG_RETRY` - při restartu Service bude předán původní intent

## Provázání Service s aktivitou
`onBind()` - spuštění pomocí `bindService()`, vrací `IBinder` pro komunikaci s Service.

`BIND_AUTO_CREATE` - Service bude vytvořena, pokud neexistuje.