# Termíny periferií 
- Arbiter
- Master
- Slave

![[Bus.png]]

Master
- Může iniciovat transakci
Slave
- Může odpovědět na transakci
Arbiter
- Průběžně monitoruje sběrnici a přiděluje ji master podle priority:
- Pevná priorita, round robin, dynamická
Transakce
- Požadavek master
- Arbitrace
- Přenos

## Parametry
Datová šířka – počet bitů přenesených v jednom cyklu
Adresní šířka – 2adresní šířka - počet unikátních adresovatelných slov v systémů
Frekvence sběrnice Fs
Teoretická propustnost – maximální počet bajtů přenesených za vteřinu $= Fs*D$
Reálná propustnost – počet bajtů přenesených za vteřinu včetně režie

## Topologie
- Peer to peer
- Sběrnice
- Crossbar