# Operace s grafy

## Odstranění hrany $h$:

$G-h = (V,H-\{h\})$

## Odstranění vrcholu $v$:
$G-v = (V-v, H - \{h \in H | v \in h\} )$

Odstraníme všechny hrany incidentní s vrcholem $v$.

## Redukce hrany 
$G\downarrow h$

$G = (V,H)$
$h = \{u,v\} \in H$

> [!tip]
Hranu odstraníme a vrcholy spojíme $u,v$ v jeden.

- $V - v$
- $H - {u,v} \u (\{u,v_i\} | \{u,v_i\} \in H \land v_i \neq u)$

## Dělení hrany $h$

$G\uparrow h$

$G = (V,H)$
$h = \{u,v\} \in H$

> [!tip]
Hranu rozdělíme a vložíme do ní vrchol.

- $V \cup \{w\}$
- $\{H - \{u,v\}\} \cup (\{u,w\} \land \{w,v\})$
