# Persistentní ukládání dat
[[SharedPreferences|SharedPreferences]]
- Ukládání primitivních datových typů v podobě key / value
- Původně určeno pro ukládání nastavení, ale obecně možno použít pro jakýkoli účel

Internal Storage
- Ukládání souborů do interní paměti zařízení
- Tyto soubory jsou chápány jako "privátní" pro danou aplikaci
- Při deinstalaci aplikace jsou tyto soubory smazány

External Storage
- Ukládání souborů na SD kartu nebo interní veřejnou paměť
- Tyto soubory jsou "veřejně" přístupné aplikacemi i po připojení přes USB

SQLite databáze
- Ukládání strukturovaných dat do privátní databáze. Pouze primitivní datové typy, 
String, Bundle, Blob, jiné DT nutno serializovat.
- Databázi prohledává standardně za pomoci `query` a metod cursoru, nebo `rawQuery`.