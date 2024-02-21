# Práce s vlákny
Android poskytuje standardní Java mechanismy pro vytváření, běh a správu vláken. Lze taktéž využívat ThreadPool, Executor + novější třídy z balíčku `java.util.concurrent`.

## AsyncTask
AsyncTask je třída, která umožňuje provádět operace na pozadí a zároveň poskytuje mechanismus pro publikování výsledků do hlavního vlákna. AsyncTask je určen pro jednorázové použití. Vytvoří se instance třídy a spustí se pomocí metody `execute()`. Výsledky jsou publikovány pomocí metody `publishProgress()`, která vyvolá metodu `onProgressUpdate()` v hlavním vlákně. Po dokončení se vyvolá metoda `onPostExecute()` v hlavním vlákně.

Spuštění:
``` Kotlin
class MyAsyncTask : AsyncTask<String, Int, String>() {
    override fun doInBackground(vararg params: String?): String {
        // zpracování dat na pozadí
        return "výsledek"
    }

    override fun onProgressUpdate(vararg values: Int?) {
        // zpracování výsledků v hlavním vlákně
    }

    override fun onPostExecute(result: String?) {
        // zpracování výsledků v hlavním vlákně
    }
}

MyAsyncTask().execute("parametr1", "parametr2")
```