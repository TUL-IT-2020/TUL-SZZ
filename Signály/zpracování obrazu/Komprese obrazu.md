# Komprese obrazu
## Kompresní poměr
Podíl velikostí komprimovaného ku nekomprimovanému.
Zmenšení v procentech – kompresní zisk.
Odlišnost – Rozdíl, kvadratická odchylka.

## RLE
![[RLE - run length encoding]]

## Huffmanovo kódování
![[Huffmanovo kódování]]
## Aritmetické kódování
![[Aritmetické kódování]]
## Slovníkové metody komprese
![[Slovníkové metody - LZ]]

## Delta komprese
Kódujeme rozdíl mezi dvojicí sousedních vzorků, nebo rozdíl mezi vzorkem a nějakým modelem (akumulátor).

(Adaptive) Differential Pulse Code Modulation (losless JPEG)

Příklad 1
100*<0,255>=100B
100*<-8,8> = 63B

Příklad 2
100*<0,255>=100B
100*<-200,233>=113B

Vhodné:
- setříděné posloupnosti, “plynulá data“

Nevhodné:
- náhodná data (obraz?)

## FELICS
FELICS - Fast and Effective Lossless Image Compression Scheme

Vychází ze statistické analýzy souboru „běžných“ fotografií.
H=max(N1,N2), 
L=min(N1,N2)
Δ=H-L
leží-li P v Δ kódujeme zkráceným binárním kódem
leží-li mimo, pak Rice code (00← nebo 01→)

Novější varianty využívat AC. Nízká latence výpočtu, nízké HW nároky.

HiRISE MRO