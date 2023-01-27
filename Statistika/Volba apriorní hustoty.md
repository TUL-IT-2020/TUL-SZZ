# Volba apriorní hustoty
Aposteriorní hustota pravděpodobnosti má tvar:
$$
p(\theta|x) = \frac
	{p(x,\theta)p(\theta)}
	{p(x)}
= \frac
	{p(x,\theta)p(\theta)}
	{\int p(x, \theta)p(\theta) d\theta}
$$
Kde hustota $p(\theta)$ je apriorní hustota pravděpodobnosti.
Nejběžnější volby pro $p(\theta)$ jsou [[Uniformní (rovnoměrné) rozdělení|uniformní]] a [[Gaussovo (normální) rozdělení|normální]] pdf.
1. Pokud $p(x|\theta)$ modelujeme jako hustotu rovnoměrného rozdělení, pak díky volbě $\theta \sim U(a,b)$ nebo $\theta \sim N(\mu_{\theta}, \sigma^2_\theta)$ bude i aposteriorní hustota $p(\theta|x)$ normální.
2. Tomuto odpovídá např. model dat $x = \theta + w$, kde $w\sim N(\mu, \sigma^2)$. Pro odhady $\theta$ se dá ukázat, že:
	1. pokud $\theta \sim N(\mu_\theta, \sigma^2_\theta)$
$$
\hat \theta_{MSE} = \frac
	{\frac
		{N}
		{\sigma^2} \bar x
	+ \frac
		{\mu_\theta}
		{\sigma^2_\theta}
	}
	{\frac
		{N}
		{\sigma^2}
	+ \frac
		{1}
		{\sigma^2_\theta}
	}
$$
	2. Aposteriorní rozptyl je dán jako: $var(\theta|x) \sigma^2_{\theta|x} = \frac{1}{\frac{N}{\sigma^2}  + \frac{1}{\theta^2_\theta}}$
	3. $BMSE(\hat\theta) < \frac{\sigma^2}{N}$
