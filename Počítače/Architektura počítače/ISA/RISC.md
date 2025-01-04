# RISC
Ze zdejší rodiny se asi do nedávna nejhlasitěji ozýval [ARM](https://www.arm.com). Tato architektura byla vytvořena na [Univerzitě v Cambridge](https://www.geeksforgeeks.org/advanced-risc-machine-arm-processor/) aby učitelé na předmětu Architektura procesorů měli o čem přednášet, jelikož x86/AMD64 je již v dnešní době příliš komplikovaná a o licenci pro návrh se dělí jen pár firem. Jiné jednoduší architektury povětšinou zastarali a pohltil je čas, takže se nehodili pro demonstraci moderních přístupů návrhu procesorů. 
Nevýhoda procesorů ARM je pro nás v tom, že ten kdo je chce vyrábět či navrhovat musí zaplatit tučnou [licenci](https://www.arm.com/products/flexible-access).

Za zmínku též stojí MIPS od [MIPS Technologies](https://www.mips.com/), který byl vznikl na univerzitě ve [Stanfordu](https://www.computerhope.com/jargon/m/mips.htm) jako výukový projekt vedený Johnem Hennessey. Ač jsou i tyto procesory vyráběny, tak se na trhu zdaleka neuchytili natolik jako ARM.

[RISC](https://en.wikipedia.org/wiki/Reduced_instruction_set_computer) dělá věci jinak. Jde o mnohem modernější přístup. Procesor disponuje značným počtem registrů (běžně 32 u 32bitových procesorů), při volání jednodušších funkcí není třeba plnit stack, ale stačí využít k tomu vyhrazených registrů (což je rychlejší). Pro přístup do paměti lze běžně použít pouze instrukce `LOAD` a `STORE`. Jde o menší, lehčí a pružnější návrh, který se snažil začít s čistým štítem a osekat přebytečný křemík, tak aby vznikla vysoká účinnost na watt i za cenu menšího počtu provedených instrukcí na takt ve srovnání architekturou CISC.

Jednou z mladších větví je [RISC-V](https://en.wikipedia.org/wiki/RISC-V), který vznikl na [Univerzitě v Californii, Berkeley](https://riscv.org/about/history/) pod vedením Davidem Pattersonem. Tato architektura je dnes pod open source licencí. Tam kde ARM licencuje svá jádra pro výrobu či modifikaci, tak RISC-V volně nabízí instrukční sady, které můžete použít k vývoji svého procesoru. Této architektuře je věnována stále větší pozornost i na poli velkých hráčů jako jsou: 
[Intel](https://pathfinder.intel.com), 
[AMD](https://circuitcellar.com/newsletter/amd-is-hiring-risc-v-cpu-developers/), 
[NASA](https://www.sifive.com/press/nasa-selects-sifive-and-makes-risc-v-the-go-to-ecosystem). 
A spoustu projektů nově vzniká právě nad touto architekturou: 
[nejrychlejší RISC-V procesor](https://www.cnews.cz/zatim-nejrychlejsi-procesor-risc-v-na-svete-vyrabi-ho-intel-na-4nm-procesu-umi-pcie-5-0-i-ddr5/), 
[první notebook s procesorem RISC-V](https://www.tomshardware.com/news/risc-v-laptop-world-first),
[Raspberry Pi klon](https://www.czc.cz/radxa-rock-4-se-4gb/359880/produkt?gclid=Cj0KCQiAi8KfBhCuARIsADp-A54p9OKqDmKCbrRN9vUVP0A1xcUF1QDlwx-Gjsei9Vh2oUKDrGFNSIcaAoffEALw_wcB).

Právě pro otevřenou licenci a aktuálnost jsem se rozhodl použít pro svůj návrh procesoru architekturu RISC-V. 