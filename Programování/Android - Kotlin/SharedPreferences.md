# SharedPreferences
Kotlin: 
``` kotlin

val sharedPreference = getSharedPreferences("NAHODNY_RETEZEC", Context.MODE_PRIVATE)

var editor = sharedPreference.edit() //pro ukladani

//Nacteni ze shared preferences
var nejakeCislo = sharedPreference.getInt("nejakeCislo",0)

//Ulozeni do shared preferences
editor.putInt("nejakeCislo", nejakeCislo)  
editor.commit()
```

getInt, getString, getFloat, getBoolean, getLong

## Zdroje:
Další informace naleznete na adresách: 
[shared-preferences](https://developer.android.com/training/data-storage/shared-preferences)

Novější metoda Datastore je popsána zde: 
[datastore](https://developer.android.com/topic/libraries/architecture/datastore)

A nejjednodušší použití Shared Preferences je např zde:
[android-shared-preferences-example-tutorial](https://www.digitalocean.com/community/tutorials/android-shared-preferences-example-tutorial)