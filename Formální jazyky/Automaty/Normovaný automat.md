## Normovaný automat
Normovaný automat je deterministický konečný automat bez nedosažitelných stavů, jehož stavy jsou označeny jednoznačně (jednoznačným postupem). O dvou ekvivalentních automatech, které nejsou normované, můžeme říci, že jsou stejné až na označení stavů. Normováním si jednodušíme porovnávání automatů, protože dva ekvivalentní normované automaty jsou shodné i včetně označení stavů).

### Postup normování KA 
Stavy $i$ automatu uspořádáme podle nejkratších slov z jazyků $L_i$ (budeme indexovat sestupně, „největší“ slovo dostane nejmenší index). Porovnáváme podle délky slova, stejně dlouhá slova podle abecedy. 
- u každého stavu i automatu zjistíme nejkratší slovo příslušného jazyka $L_i$ (je možné, že budeme potřebovat více takových slov), 
- seřadíme slova podle délky sestupně, 
- pokud vyjdou dvě stejně dlouhá slova u více stavů, porovnáme je podle abecedy, 
- pokud vyjdou stejná slova u více stavů, použijeme u každého druhé nejkratší slovo (atd. dokud nenajdeme rozdíl, ten najdeme určitě – jsou to různé jazyky), 
- Seřazené stavy pojmenujeme (oindedexujeme) od 1.