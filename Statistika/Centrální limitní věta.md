# Centrální limitní věta
Často nás zajímá jaké má rozdělení náhodná veličina, která vznikne součtem nebo [[Zákon velkých čísel#Průměr|průměrem]] náhodných veličin. To ale obecně vůbec není snadné. CLT nám říká, za jakých podmínek lze toto rozdělení aproximovat [[Gaussovo (normální) rozdělení|normálním rozdělením]].

## CLT:
Nechť $(X_n)^{\infty}_{n=1}$ je posloupnost [[Statistická závislost a nezávislost#I.I.D. (independent identically distributed)|i.i.d.]] náhodných veličin se společnou [[Střední hodnota a rozptyl#Střední hodnota|střední hodnotou]] $\mu$ a konečným [[Střední hodnota a rozptyl#Rozptyl|rozptylem]] $\sigma^2$. Potom platí:
$$
\lim_{n \rightarrow \infty} \frac{\sum^{n}_{i=1} X_i - n\mu}{\sqrt{n}\sigma} \sim N(0,1)
$$
