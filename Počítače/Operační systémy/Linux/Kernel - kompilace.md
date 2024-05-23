#Linux 
# Kompilace Linuxového jádra
## Stažení Kernelu
1. Z hlavní linie kernelu stáhneme poslední zdrojáky: [www.kernel.org](https://www.kernel.org/)
2. Rozbalte někam na vašem disku [[tar command|tar]]: 
```bash
tar -xvf linux-*.*.*.tar.xz
```
3. Vejděte do adresáře.
## Překlad pro ARM
1. !!! Klíčová proměnná je nyní `ARCH=??`, my ji nastavíme na `ARCH=arm`. Buď pomocí: 
```bash
export ARCH=arm
``` 
Pro aktuální relaci terminálu, nebo pomocí nastavení v každém volání příkazů.
2. Zadejte:
```bash
make ARCH=arm help
``` 
- uvidíme mj. list připravených **defconfigs**.
3. Budeme dál používat qemu, to umí emulovat některé desky NXP (freescale) pro procesory arm, proto uděláme:make
```bash
ARCH=arm 
CROSS_COMPILE=arm-linux-gnueabihf- 
make imx_v6_v7_defconfig
```
4. Poté spustíme vlastní make, uvádím s proměnnými: 
```bash
ARCH=arm 
CROSS_COMPILE=arm-linux-gnueabihf- 
make -j 12
``` 
- -j určuje počet jader, v tomto případě funguje jen tehdy, máteli 12 a více CPU.
## Start jádra v qemu
Nyní ve stejném adresáři, kde jsme překládali (kvůli cestám) můžeme zkusit spustit nový kernel (moc toho ale neuvidíme): 
```bash
qemu-system-arm -M mcimx6ul-evk -cpu cortex-a7 -m 512M -kernel arch/arm/boot/zImage -dtb arch/arm/boot/dts/nxp/imx/imx6ul-14x14-evk.dtb -append ="console=ttymxc0 loglevel=8 earlycon printk" -nographic
```
