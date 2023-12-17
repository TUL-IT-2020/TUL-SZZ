# Platforma Android
Platforma Android poskytuje nejen OS, ale i:
- Uživatelské prostředí pro koncové uživatele
- Specifikace ovladačů pro výrobce HW
- Nástroje pro vývoj (SDK)

HTC Dream
![[T-Mobile_G1_launch_event_2.jpg]]

[Historie verzí Androidu](https://cs.wikipedia.org/wiki/Historie_verzí_Androidu)

## Linux Kernel
Android < 4.1 – Linux 2.6, později 3.x, dnes 5.x
HAL – Hardware Abstract Layer – vrstva mezi HW a SW kernelu nebo knihoven


### Sada knihoven (C/C++)
Systémová knihovna C (libc) – upravená pro Android 
- Media Libraries (multimédia) 
- LibWebCore – webový prohlížeč 
- SQLite – relační DB knihovna 
- FreeType – rendering fontů 
- 3D, SGL (2D), WebKit, OpenSSL, OpenGL, aj. 
- Vulkan API – náhrada za Open GL

## Android Runtime
Aplikační virtuální stroj (analogie s JVM). Původně Dalvik Virtual Machine (DVM). Každá aplikace má vlastní proces a vlastní instanci DVM.

Spuštení android aplikace: .java -> .class -> Dalvik code -> DVM

Od verze 4.4 nový Android RunTime (ART) – kompilace do nativního kódu při instalaci aplikace. Instalace je díky kompilaci pomalejší, ale je to jednorázová 
záležitost.
- .java -> .class (Java kompilace)
- .class -> .dex (byte code Dalviku)
- .dex -> při instalaci kompilován do nativního kódu 
procesoru

## Android Application Framework
Nejdůležitější vrstva z pohledu vývojáře. Obsahuje:
- Sada View prvů – UI aplikací (button, checkbox, list ..)
- Content providers – sdílení dat mezi aplikacemi
- Resource manager – zdroje jako lokalizace, grafika, design
- Notification manager – zasílání notifikací do stavového 
řádku
- Activity manager – životní cyklus aplikací, zásobník aplikací

 
![[Android – sw stack.jpg]]

### Android SDK
IDE - Android Studio

SDK Tools:
- Android Debug Bridge (adb) – připojení k zařízení přes USB
- Android Virtual Devices (AVD) + AVD manager
- Android emulátor pro vývoj na PC (SDK + AVD)

Kotlin
Inteoperabilita mezi Kotlinem, Javou a JavaScriptem.


