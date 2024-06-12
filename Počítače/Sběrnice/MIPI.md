# MIPI
![[MIPI.png]]
Mobile Industry Processor Interface
organizace (ARM, Intel, Nokia, Samsung, ST, TI) zajišťující standradizaci různých rozhraní

Sdružuje různé specifikace standardů
- Display Serial Interface – MIPI DSI
- Camera Serial Interface – MIPI CSI (1,2,3)

Není otevřený standard
Přístup k dokumentaci mají pouze členové aliance

## MIPI – C-PHY, D- PHY, M-PHY
Sériové rozhraní pro připojení kamer u mobilních zařízení. Specifikuje fyzickou vrstvu C-PHY / D-PHY. Sériová komunikace s vysokou rychlostí a nízkou spotřebou.

D-PHY 
4 vodiče – hodiny a data, SLVS (Scalable Low Voltage Signaling. Nekompatibilní s LVDS), až 1 GHz

C-PHY 
3 vodiče – pouze data, 3fázové kódování symbolů.
3 vodiče, 6 stavů vodičů, 5 přechodů (změna). Kódování 16:7 – 2,2857 bit/symbol ~ log2(5).
Až 875 MHz.

## MIPI – CSI-2
CSI-2
1-4 sériové linky
Diferenciální PCM (posílá se rozdíl dvou vzorků, nebo vzorku a modelu)
Podpora RGB888, RAW6-20, YUVXXX,…
Camera Control Interface (~IIC, I3C)
řízení kamery – Camera Command Set

Z pohledu integrátora – důležitý endpoint a jeho schopnosti
Převádí CSI na nějaký rozumný HW standard uvnitř SoC (DVP)
Nutno ověřit schopnosti oproti připojované kameře