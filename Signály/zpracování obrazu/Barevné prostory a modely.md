# Barevné prostory a modely
## RGB model
Barva určena souřadnicemi Red, Green, Blue .
Rozsah v CIEXYZ určuje trojúhelník prostoru

Nejčastější u snímačů
Foveon snímač (závislost intenzity tvorby e-d párů na hloubce) – výsledek je implicitní RGB
CFA – nutné dopočítat

> [!tip] Jas != G; 
> $$Y = 0.3R + 0.59G + 0.11B$$

> [!note] Bitové hloubky:
>- 8-8-8, 
>- 5-6-5, 
>- 10bit+ HDR

RGB888 vs RGB888P

## YUV, Y’UV, YIQ
Vhodný pro přenos barevné informace. Analogové (TV).

> [!example] YUV
>- Y – jas, 
>- U – modrá projekce, 
>- V – červená projekce

> [!example] Y’UV
>- Y’ – luma (vážený jas po gamma korekci), 
>- U, 
>- V – chroma modré a červené projekce (-/+)

Převod záleží na standardu YUV

## YCrCb, YPrPb
Digitální reprezentace
- Y’ – luma (vážený jas po gamma korekci), 
- Cr, Cb – chroma modré a červené projekce

V počítačích často označováno jako YUV

> [!note] Formáty a pořadí ukládání:
>- YUV444 – 3 byte / pix
>- YUV422 – 4 byte / 2 pix
>- YUV411 – 6 byte / 4 pix
>- YUV420p – 6 byte / 4 pix

RGB888 → YUV444

## HSL, HSB
Hue (odstín), Saturation (sytost), Lightness (světelnost)
Hue (odstín), Saturation (sytost), Brightness/Value (svit)

Bližší k zvyklostem míchání barev
Lépe popisuje osvit
HSL – přídávání L přidává „bílou barvu“
HSV – přidávání V zesiluje barvu

## CMYK
Substraktivní model u tiskáren. Technologické problémy reprodukce.

> [!tip] 
> Kombinace CMY netvoří černou => Key (Černá)

Mísení vs dithering
Přesnost sítotisku