# Activity
Základní komponenta aplikace. Aplikace může mít více aktivit. Každá aktivita má svůj životní cyklus (ActivityManager). Aktivita je zodpovědná za zobrazování UI.
`android.app.Activity`

## Životní cykly aktivit
- **Aktivita spuštěna** – došlo ke spuštění aplikace
- **Aktivita běží** – aktivita spuštěna a je v popředí
- **Aktivita v pozadí** – je vidět, ale překryta jinou 
aplikací (příchozí SMS, hovor, jiná notifikace ..)
- **Aktivita zastavená** – není vidět, bez přístupu, ale 
není úplně zničena 
- **Aktivita ukončená** – úplné ukončení aktivity

![[Android-Activity-Lifecycle.png]]

`onCreate()`
- Volána při spuštění aktivity, která nebyla spuštěna nebo byla předtím zničena / odstraněna z paměti
- Zde se zavádí např. úvodní UI, načítá konfigurace atd.

`onStart()`
- Následuje metodu onCreate() nebo když je aktivita opět aktivována po svém skrytí – např. po vyřízení příchozí SMS

`onResume()`
- Volána těsně předtím, než je aktivita posunuta do popředí

`onPause()`
- Volána před přechodem aktivity do pozadí
- Systém získává pravomoc aktivitu násilně ukončit

`onStop()`
- Aktivita již není viditelná
- Volána při zastavení aktivity.

`onDestroy()`
- Volána těsně předtím, než je aktivita úplně 
odstraněna/zrušena
- Vhodné jako „hook“ pro úklid atd ..

`onRestart()`
- Volána po metodě onStop() při restartu aplikace

## Vytvoření aktivity
Jediná povinná metoda v naší aktivitě je onCreate().
Tuto metodu je nutno vždy překrýt a implementovat.
Parametr typu Bundle slouží při znovuzavedení aktivity z pozadí k obnovení stavu aktivity.