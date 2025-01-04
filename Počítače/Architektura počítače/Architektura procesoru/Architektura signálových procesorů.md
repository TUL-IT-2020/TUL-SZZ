# Architektura signálových procesorů
Digitální signálový procesor nebo také digitální signální procesor (zkratka **DSP**) je mikroprocesor, jehož návrh je optimalizován pro algoritmy používané při zpracování digitálně reprezentovaných signálů. Hlavním nárokem na systém bývá průběžné zpracování velkého množství dat „protékajících“ procesorem. Často slouží jako hardwarová implementace různých číslicových filtrů.

**Hlavní součásti:**
- *Hlavní aritmetická jednotka* (jednotlivé části nezávislé):
	- jednotka **MAC** (Multiplier and Accumulator) – paralelní násobička a sčítačka (na 1 strojový cyklus) – velikost střadače je dána součtem velikostí operandů + 8 bitů
	- jednotka ALU
	- jednotka podporující paralelní posuny (barell-shifter).
- *Generátory adres DAG* (Data Address Generator) - správa adres pro čtená data a konstanty, nejčastěji dva (pro konstanty a pro data) – podporují různé druhy adresování (inkrementace, dekrementace, reverzně bitové adresování, adresování v kruhovém zásobníku apod.).
- *Čítač instrukcí* – může opakovat jednu či více instrukcí.


DSP má většinou (**super)harvardskou architekturu** (zejména proto, že kód i data mají zvláštní sběrnice, možnost uchovávat data i v paměti programu).
Z pohledu instrukčního cyklu jsou architektury založeny většinou na vnitřním paralelismu (**superskalární**, speciální typy LIM a VLIM), někdy se využívají architektury paralelních systémů, příp. shlukování DSP do výpoč. sítí.

**Hlavní účelem je co nejrychleji zpracovat velké množství dat ideálně paralelně. (rychlá sčítačka a násobička, zdvojení výpočetní jednotek dle SIMD, zřetězení instrukcí, atd)**

![Typické blokové schéma dsp](TUL-SZZ/assets/počítače/26_dsp.png)
*Typické blokové schéma dsp*

**Nejčastější algoritmy číslicového zpracování signálů:**
- [[Konvoluce v obraze|konvoluce]]
- číslicová filtrace IIR, - diskrétní transformace
- korelace
- práce s maticemi