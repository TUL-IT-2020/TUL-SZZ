# Fragmenty
Fragment je vrstva, která je vložena mezi Activity a View. Reprezentuje část UI rozhraní včetně příslušných metod. Fragment je možno vložit do příslušných Activity nebo dalších fragmentů. Výhodou je flexibilita znovupoužitelnost jako jednotky UI. Bez duplikace kódu lze programovat optimalizovaná UI pro různé varianty displejů. Jejich vývoj je podobný jako u Activity.

`void onAttach(Activity a)` – volaná ve chvíli, kdy 
je fragment asociován s aktivitou.

`View onCreateView(inflater, vgroup, state)`
– vytváří a vrací UI související s fragmentem. Zde je 
vhodné asociovat Fragment s layoutem.

`void onActivityCreated()` – volána v okamžiku, 
kdy byla ukončena metoda `onCreate()` související aktivity.

`void onDestroyView()` – volána v okamžiku, kdy je 
“zničeno“ View připojené k fragmentu.

`void onDestroy()` – opak `onAttach()`, fragment ztrácí 
asociaci s aktivitou.
