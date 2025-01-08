# HSL, HSB
Hue (odstín), Saturation (sytost), Lightness (světelnost)
Hue (odstín), Saturation (sytost), Brightness/Value (svit)

Bližší k zvyklostem míchání barev
Lépe popisuje osvit
HSL – přidávání L přidává „bílou barvu“
HSV – přidávání V zesiluje barvu

### Konverze z RGB
$$
V = \max(R, G, B)
$$

$$
S = 
\begin{cases} 
0, & \text{pokud } V = 0 \\
\frac{V - \min(R, G, B)}{V}, & \text{jinak}
\end{cases}
$$

$$
H = 
\begin{cases} 
0, & \text{pokud } S = 0 \\
60 \cdot \left( 0 + \frac{G - B}{V - \min(R, G, B)} \right), & \text{pokud } V = R \text{ a } G \geq B \\
60 \cdot \left( 0 + \frac{G - B}{V - \min(R, G, B)} + 6 \right), & \text{pokud } V = R \text{ a } G < B \\
60 \cdot \left( 2 + \frac{B - R}{V - \min(R, G, B)} \right), & \text{pokud } V = G \\
60 \cdot \left( 4 + \frac{R - G}{V - \min(R, G, B)} \right), & \text{pokud } V = B
\end{cases}
$$
