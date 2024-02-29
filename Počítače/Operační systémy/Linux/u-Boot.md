#Linux 
## u-Boot

### Instalace závislostí ze souboru
Překladače pro ubuntu:

Soubor `u-boot_packages.txt` obsahuje následující balíčky:
> [!info] u-boot_packages.txt
```txt
gcc-arm-none-eabi
gcc-arm-linux-gnueabi
gcc-arm-linux-gnueabihf
gcc-aarch64-linux-gnu
qemu-system-arm
```

> [!tip] Instalace balíků
```bash
sudo apt update
xargs sudo apt-get -y install < u-boot_packages.txt 
```

### Stažení u-Boot
Zdrojáky stáhnout ZIP tady: https://github.com/u-boot/u-boot

> [!tip] Rozbalení archivu
```bash
unzip u-boot-master.zip
cd u-boot-master
```

### Příprava
> [!tip] Export proměnné prosředí a sestavení u-boot
```bash
export CROSS_COMPILE=arm-linux-gnueabi-
make qemu_arm_defconfig
make
```

>[!warning] !!! `cc not found`
>Pokud při překladu vidíte `cc not found`, chybí vám překladač, takže doinstalujte tohle:
>```bash
>sudo apt install build-essential
>```

### Boot it!
> [!tip] Bootujeme z našeho image bootloaderu: 
```bash
qemu-system-arm -machine virt -bios u-boot.bin -nographic
```

> [!question] Jak opustit prostředí emulátoru?
>- `ctrl-a, x`

Zahlásí nám kdo naběhl a vypíše HW (emulátoru):
> [!example]
>- RAM
>- CPU
>- Flash

Připojeni vstupu a výstupu:
In, Out, Err

Pak to zle selže, protože nemáme obraz systému, který bychom mohli nabootovat.one

> [!Success] 
`=>` - máme prompt, kde můžeme specifikovat odkud se má bootovat.

> [!example] Spustitelné příkazy:
>- `help` - pro někoho spíše hell.
>- `bdinfo` - adresy do paměti.

### Menu konfig
Spustí TUI, kde můžeme nastavit konfiguraci pro překlad.
```bash
make menuconfig
```

### U-boot podrobněji
```bash
cd u-boot-master
```

#### Adresářová struktura

```bash
tree -L 1
├── api
├── arch
├── board
├── boot
├── cmd
├── common
├── config.mk
├── configs
├── disk
├── doc
├── drivers
├── dts
├── env
├── examples
├── fs
├── generated_defconfig
├── include
├── Kbuild
├── Kconfig
├── lib
├── Licenses
├── MAINTAINERS
├── Makefile
├── net
├── post
├── README
├── scripts
├── System.map
├── test
├── tools
├── u-boot
```

> [!example] Příklady
> - `./cmd/` - obsahuje zdrojové kódy k příkazům v nabootovaném U-bootu.

#### Podporované architektury
Architektur na kterých u-boot zvládne nabootovat:
```bash
tree arch/ -L 1
```