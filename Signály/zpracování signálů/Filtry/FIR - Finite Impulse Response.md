# FIR
filtr s končenou impulsní odezvou

- Filtry FIR jsou jednodušší pro návrh a realizaci, jejich průběhy jsou však vzdálené ideálním filtrům.
## Příklady filtrů FIR
1. Zesilovač 
  $$
    y[n] = k x[n]
  $$   
  $$
    h(n) = k\delta[n] \quad \text{impulsní odezva}
  $$

2. Zpožďovač
   $$
   y[n] = x[n-k]
   $$
  $$
    h(n) = \delta[n-k] \quad \text{impulsní odezva}
    $$
3. Derivátor (diferenciátor)
   $$
   y[n] = x[n] - x[n-1]
   $$
  $$
    h(n) = \delta[n] - \delta[n-1] \quad \text{impulsní odezva}
 $$
4. [[Klouzavý průměr|Průměrovací]] filtr kauzální
   $$
   y[n] = \frac{1}{N} \sum_{k=0}^{N-1} x[n-k]
   $$
$$
    h(n) = \frac{1}{N} \sum_{k=0}^{N-1} \delta[n-k] \quad \text{impulsní odezva}
    $$