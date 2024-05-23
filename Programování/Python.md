# Python

## Instalace Pythonu
```Bash
sudo apt install python3-full
```

### Instalace modulů pro Python
```Bash
python3 -m pip install -r requirements.txt
```

## Config
Zobrazení kde máme soubory `pip.conf`:
```python
python3 -m pip config debug
```
Pokud soubor neexistuje, tak jej vytvoříme v `~/.config/pip/pip.conf`

### error: externally-managed-environment
Přidáme do souboru: `~/.config/pip/pip.conf`
```ini
[global]
break-system-packages = true
```

## Jupiter notebook
- https://linux.how2shout.com/how-to-install-jupyter-notebook-in-ubuntu-vscode/

```Bash
pip install notebook
```

You can use Python's `venv` like described [here](https://stackoverflow.com/a/75696359/10626495).

However if you really want to install packages that way, then there are a couple of solutions:

- use `pip`'s argument `--break-system-packages`,
- add following lines to `~/.config/pip/pip.conf`:

```ini
[global]
break-system-packages = true
```

### Jak nainstalovat bez condy

```
python3.10 -m pip install ipykernel --break-system-packages
```