# CSMA/CD
- stanice vysílají pouze pokud nevysílá nikdo jiný
- pokud začnou vysílat dvě stanice naráz vznikne kolize (zjistí tak že přijme signál)
- pak se všechny vysílající stanice odmlčí a zkusí vysílat znovu
- čeká náhodnou dobu, doba čekání se prodlužuje s každým pokusem
- evektivita klesá s rostoucí zátěží/rychlostí

Carrier Sense Multiple Access with Collision Detection CSMA/CD) je protokol pro přístup k přenosovému médiu v počítačových sítích. Patří do třídy CSMA, tedy metod s vícenásobným kolizním přístupem a nasloucháním nosné. 

Na rozdíl od čistého CSMA u CSMA/CD stanice při svém vysílání současně kontroluje přenosové médium, zda nezachytí jiné vysílání, které koliduje s jejím. Z této vlastnosti je odvozena přípona „s detekcí kolizí“ (with Collision Detection) v názvu metody. Pokud stanice zjistí kolizi, zastaví vysílání, počká náhodnou dobu a opakuje svůj pokus znovu. CSMA/CD je proto efektivnější než samotné CSMA či CSMA/CA − v nich se kolize nezjišťují a dojde-li k nim, zbytečně se odvysílá celý datový rámec, který bude beztak nutno opakovat.

## CSMA/CD v Ethernetu
Nejrozšířenějším představitelem CSMA/CD je klasický Ethernet. Ten byl postaven na sběrnicové topologii a algoritmus CSMA/CD v něm řídí přístup stanic ke sdílené sběrnici představované koaxiálním kabelem. Stanice, která chce odeslat datový rámec, se podle jeho pravidel chová následovně:
1. Naslouchá, zda je médium volné. Dokud není, čeká na jeho uvolnění.
2. Zahájí vysílání. Současně s odesíláním rámce naslouchá, zda nepřichází signál od jiné stanice. Pokud ano, došlo ke kolizi. Stanice ukončí vysílání, odešle signál umožňující rozpoznat kolizi také ostatním (jam signal) a přejde k opakování pokusu podle bodu 3.
3. Stanice vybere náhodné číslo z intervalu od 0 do 2k - 1, kde k je pořadové číslo pokusu (od 10. pokusu se interval již nezvětšuje a horní hranice zůstává 210 - 1, tedy 1023). Náhodné číslo určuje délku čekací doby, po jejímž uplynutí stanice opakuje pokus o odeslání od bodu 1. Maximální počet pokusů je 16, poté je pokus o odeslání považován za neúspěšný.

Modernější varianty Ethernetu však opouštějí sdílené přenosové médium, používají přepínače s plně duplexním režimem provozu a metoda CSMA/CD u nich není nadále uplatňována.

