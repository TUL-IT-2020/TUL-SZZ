# FFT - Fast Fourier Transform
Fast Fourier Transform je rychlý algoritmus pro výpočet DFT. Poskytuje úplně stejné hodnoty jako DFT, ale mnohem rychlejším způsobem. Vysoké rychlosti je dosaženo optimalizovaným výpočtem, ten bere v úvahu např. symetričnost exponenciálních členů $e^{-j k n \frac{2 \pi}{N}}$, dále podobnost mezi lichými a sudými koeficienty, atd.

>[!tip] 
>Nejrychleji funguje v případech, že **N je mocninou 2**.

## Složitost:
$O(N*log(N))$

$W_N^{kn} = e^{-j2\pi}$