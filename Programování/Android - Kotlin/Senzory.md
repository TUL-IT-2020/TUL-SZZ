# Senzory
## Tři katogorie senzorů:

Motion Sensors - pohybové senzory
- Akcelerometr, G-senzor (Gravity Sensor)
- Gyroskop


Environmental Sensors – senzory sledující prostředí, okolí
- Barometr
- Teploměr
- Světelný senzor
- Proximity Sensor – senzor přiblížení
- Hallův senzor – detekce magnetického pole, agnetometr (kryty)


Position Sensors – senzory snímající polohu
- GPS
- Tyto soubory jsou "veřejně" přístupné aplikacemi i po připojení přes USB

## Dva typy senzorů:

Hardwarové
- Fyzické komponenty součástí HW zařízení
- Často založené i na mechanickém principu

Softwarové
- Emulují (napodobují) skutečné HW zařízení
- Často odvozují svou funkci od více HW komponent
- Virtuální (syntetické) senzory

## Přístup k senzorům pomocí Sensor Framework
Třídy a rozhraní v balíčku `android.hardware`:

SensorManager
- Vytvoření instance služby senzoru
- Poskytuje metody pro přístup, výpis senzorů, registraci posluchačů aj.
- Konstanty pro přesnost, rychlost, kalibraci aj.

Sensor
- Třída pro vytvoření instance konkrétního senzoru
- Sada metod schopností (funkcionalit) senzorů

SensorEvent
- Události senzorů včetně nezpracovaných dat ze senzoru
- Zdroj události, přesnost, timestamp aj.

SensorEventListener
- Listener (naslouchač) pro jednotlivé události senzorů
