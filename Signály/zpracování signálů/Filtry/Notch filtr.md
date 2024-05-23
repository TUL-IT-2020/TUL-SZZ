# Notch filtr
- Velmi úzký pásmový filtr (zadří jednu frekvenci)

## Postup
- $F_s = 500 Hz$
- $F_0 = 50 Hz$

Výpočet digitální frekvence:
$$
\omega = 2\pi\frac{F_0}{F_s} = 2\pi\frac{50}{500} = \frac{1}{5} \pi
$$

$$
H(z) = (1 -e^{-j\pi/5}z^{-1})(1 -e^{j\pi/5}z^{-1})
$$
Co nemsím dát za $z$ aby tam nebylo $\infty$?
- $|z| > 0$

```matlab
%notch filter FIR

f0 = 50;
fs = 500;
w0 = (2*pi*f0)/fs;
beta = [exp(1i*pi/5) exp(-1i*pi/5)];
b = poly(beta);
a = 1;

[H, w_ax] = freqz(b, a, 1000, fs);
figure;
plot(w_ax/pi, abs(H));
```

IIR:
Přiblížíme póly velmi blízko k nulám. Umístíme je na kružnici o menším poloměru. Protože jsou póly blízko nulám, tak se zvýší specifita filtru.

```matlab
%notch filter IIR

f0 = 50;
fs = 500;
w0 = (2*pi*f0)/fs;
R = 1;    % poloměr kružnice pro nuly
K = 0.99; % poloměr kružnice pro póly

beta = R*[exp(1i*pi/5) exp(-1i*pi/5)];
alpha = K*beta;
b = poly(beta);
a = poly(alpha);

% normalizace zesílení na 1
C = sum(b)/sum(a);  % zesilení filtru

[H, w_ax] = freqz(b/C, a, 1000, fs);
figure;
plot(w_ax/pi, abs(H));
figure;
zplane(b/C, a);
```
