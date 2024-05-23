# Návrh filtrů FIR

## Příklad DP:
- $\omega_f = 0.2\pi$
- $\omega_s = 0.3\pi$
- $\delta_p = \delta_s = 0.01$

TODO: přepsat tabulku: Parameters of frequently used windows
### Postup
Koukneme do tabulky:
1) okémko vybereme: Hammingovo
2) $2\pi/L = 0.1\pi$ -> $L = 80+1$
   - některé filtry se sudou délkou nejdou navrhnout.

Matlab:
```matlab
% DP
wp = 0.2*pi;
ws = 0.3*pi;
wc = (ws + wp)/2;
L = 81;
N = L-1;

n = 0:N;
% navrhnutí ideálního filtru
h_id = wc/pi*sinc(wc/pi*(n-N/2)); % magic happens here

% frekvenční charakteristika ideálního filtru
[H, w] = freqz(h_id, 1, 1000);
figure;
plot(w/pi, abs(H));
title('Frekvenční charakteristika ideálního filtru');
xlabel('f/\pi');
ylabel('|H(f)|');


% okénkování
win = hamming(L);
h = h_id .* win';

% frekvenční charakteristika okénkovaného filtru
[H, w] = freqz(h, 1, 1000);
figure;
plot(w/pi, abs(H));
title('Frekvenční charakteristika okénkovaného filtru');
xlabel('f/\pi');
ylabel('|H(f)|');
```

Lze také použít funkci `fir1`:
```matlab
h = fir1(N, wc/pi, 'low', win);
```
- `N` - řád filtru
- `wc/pi` - frekvence
- `low` - typ filtru
- `win` - okénkovací funkce

## Příklad HP:
- $\omega_f = 0.8\pi$
- $\omega_s = 0.7\pi$
- $\delta_p = 0.001$
- $\delta_s = 2*10^{-4}$

### Postup
Vybreme přísnější omezení.
1) vybereme okénko: Blackmanovo
$$
\omega_f - \omega_s = 0.1\pi
$$
$$
12\pi / L = 0.1\pi \Rightarrow L = 120+1
$$
2) Délka filtru bude: $L = 121$

Matlab:
```matlab
% HP
clc;
wp = 0.8*pi;
ws = 0.7*pi;
wc = (ws + wp)/2;
L = 121;
N = L-1;

n = 0:N;
dlta = zeros(L, 1);
dlta(N/2+1) = 1;
% navrhnutí ideálního filtru
h_id = dlta' - wc/pi*sinc(wc/pi*(n-N/2)); % magic happens here

% okénkování
win = hamming(L);
h = h_id .* win';

% frekvenční charakteristika okénkovaného filtru
[H, w] = freqz(h, 1, 1000);
figure;
plot(w/pi, abs(H));
title('Frekvenční charakteristika okénkovaného filtru');
xlabel('f/\pi');
ylabel('|H(f)|');
```