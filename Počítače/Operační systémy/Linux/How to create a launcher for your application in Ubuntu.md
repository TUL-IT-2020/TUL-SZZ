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

## Instalace záznamu
```Bash
xdg-desktop-menu install myapp.desktop
```

## Jednotlivé položky
For reference see the Freedesktop Desktop Entry Specification, but this should work:

```
[Desktop Entry]
Version=1.0
Name=Unipro UGENE
Comment=Unipro UGENE is a cross-platform visual environment for DNA and protein sequence analysis.
Exec=/home/samuel/ugene-1.11.5/ugene -ui
Path=/home/samuel/ugene-1.11.5/
Icon=/usr/share/icons/Humanity/apps/32/access.svg
Terminal=false
Type=Application
Categories=Utility;Development;
```

### Version

Should be 1.0, it refers to the .desktop file version, not to the program version.
Name

The name that should be displayed on the menu.
### Exec

The full path to the executable. No need to use '.', it just means the current dir
### Path

The dir that will be set as current when the entry is run. You usually don't need to set it, but I have added it just in case. It is the same as using 'cd' in your command line
### Icon

The path to the icon file that will be used for the file, it's likely that the one that you put doesn't exists, I have changed it for a generic one. You should change this to the file that you want the icon to use
### Mimetype

Specifies the kind of files that this program is able to open. I've left it empty.
### StartupWMClass

Only needed for some programs, It is usually needed by java programs but only set it if you notice some problems.


To use the desktop file from the Dash you will need to copy it to `/usr/share/applications` for any user to be able to use it (you will need administrator permissions) or to `~/.local/share/applications` if you just want it to be available for one user.

## GUI
Instead of manually adding `.desktop` files, you can use the little GUI tool `alacarte` (Main Menu) to do this for you.
```Bash
sudo apt install alacarte
```

![alacarte](https://i.stack.imgur.com/QGmgu.png)