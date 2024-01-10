# Architektura grafických procesorů
**GPU** (graphic processing unit) je v informačních technologiích specializovaný mikroprocesor uvnitř počítače, telefonu a podobně. GPU zajišťuje rychlé grafické výpočty a změny obsahu videopaměti, které jsou posléze zobrazovány na monitoru. Moderní grafické procesory mohou být využívány i k jiným výpočtům, než pro zobrazování dat (například kryptoanalýza, nebo trénování neuronových sítí).

- podobnost s DSP (více univerzální)
    - [[Architektura signálových procesorů|DSP]] spíše audio hw realizovaný filtr v mp3 přehrávači
    - GPU univerzální pomocník procesoru na paralelní výpočty (SIMD)
- velmi vysoký výkon na paralelní výpočty
- masivní paralelizace (používá se ke kryptoanalýze například pro lámání [[Hashovací funkce|hashe]])
- specializovaná architektura na vektorové a maticové operace (filtry, konvoluce, transformace)
- GPU obvykle disponují paměťovou sběrnicí s mnohem vyšší propustností, než CPU. GPU totiž pracuje s větším množstvím dat najednou.

![[GPU diagram.png]]

[CPU vs GPU](https://www.youtube.com/watch?v=-P28LKWTzrI)