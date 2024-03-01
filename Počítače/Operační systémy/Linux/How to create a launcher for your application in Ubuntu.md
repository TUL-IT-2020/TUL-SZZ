#HowTo 
# How to create a launcher for your application in Ubuntu

Kroky jak vytvořit spouštěč pro aplikaci:
1. Nejprve si můžete stáhnout ikonu pro aplikaci.
2. Aby bylo možné vytvořit spouštěč aplikace v dashboardu, vytvořte pojmenovaný soubor v `/usr/share/applications` s příponou `.desktop` s obsahem níže.

```
[Desktop Entry]  
Encoding=UTF-8  
Type=Application  
Name=[application name you want to show in the dashboard]  
Icon=[location of the icon]  
Exec=[command to run the appplication]  
Comment=[any comment you like]  
Categories=[choose a category for your app]  
Terminal=false
```