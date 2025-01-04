# Operace s grafy

## Odstranění hrany h:

$G-h = (V,H-\{h\})$

## Odstranění vrcholu:
$G-v = (V-v, H - \{h \in H | v \in h\} )$

Odstraníme všechny hrany incidentní s vrcholem $v$.

## Redukce hrany 
šipka dolu
$G = (V,H)$
$h = \{u,v\} \in H$

Hranu odstraníme a vrcholy spojíme $u,v$ v jeden.
- $V - v$
- $H - {u,v} \u (\{u,v_i\} | \{u,v_i\} \in H \a v_i \neq u)$

## Dělení hrany 
šipka nahoru
$G = (V,H)$
$h = \{u,v\} \in H$

Hranu rozdělíme a vložíme do ní vrchol.
- $V \u w$
- $H - \{u,v\} \u (\{u,w\} \a \{w,v\})$
