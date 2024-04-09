# Yocto
Stojí nad BitBake.

```mermaid
flowchart TD;
	
	subgraph OpenEmbedded
		Toolchain
		subgraph Executable_metadata
			conf
			src
			make/Cmake
		end
		src --> Toolchain
		conf --> Toolchain
		make/Cmake --> Toolchain
		Executable_metadata --> recipes --> BitBake
		recipe --> BitBake
	end

	subgraph Yocto
		vrstvy
		tools["nástroje"]
		distro["referenční distro (Poky)"]
	end
	BitBake --> Yocto

	subgraph Image
        direction LR
		subgraph Bootloader
			make_btldr["make"]
			src_btldr["src"]
			config_btldr["config"]
		end
		subgraph DTC
			src_dtc["src"]
			config_dtc["config"]
		end
		subgraph Kernel
			make_ker["make"]
			src_ker["src"]
			config_ker["config"]
		end
		subgraph Rootfs
			file_system
			packages
		end
		Bootloader === DTC === Kernel === Rootfs
	end
    Bootloader -- "recipe" --> BitBake
    DTC -- "recipe" --> BitBake
    Kernel -- "recipe" --> BitBake
    Rootfs -- "recipe" --> BitBake

	subgraph package
        direction TB
		make_pkg["make/Cmake/ninja"]
		src_pkg["src"]
		config_pkg["config"]
	end

	package --> packages
    Toolchain --> Image
```
## Dokumentace

Černá dokumentace je aktuální.
### Struktura dokumentace

What I wish to know about Yocto
Overview and concepts
- Kde začít

Board Support Package
- Jak to rozchodit na naší desce

Development tasks manual
BitBake Documentation

Toaster -> grafických náhled přes web na buildovací server

## Konfigurace
See the [local.conf.sample](https://git.yoctoproject.org/poky/tree/meta-poky/conf/templates/default/local.conf.sample) in the `meta-poky` layer:
- _Target Machine Selection:_ Controlled by the [MACHINE](https://docs.yoctoproject.org/ref-manual/variables.html#term-MACHINE) variable.
- _Download Directory:_ Controlled by the [DL_DIR](https://docs.yoctoproject.org/ref-manual/variables.html#term-DL_DIR) variable.
- _Shared State Directory:_ Controlled by the [SSTATE_DIR](https://docs.yoctoproject.org/ref-manual/variables.html#term-SSTATE_DIR) variable.
- _Build Output:_ Controlled by the [TMPDIR](https://docs.yoctoproject.org/ref-manual/variables.html#term-TMPDIR) variable.
- _Distribution Policy:_ Controlled by the [DISTRO](https://docs.yoctoproject.org/ref-manual/variables.html#term-DISTRO) variable.
- _Packaging Format:_ Controlled by the [PACKAGE_CLASSES](https://docs.yoctoproject.org/ref-manual/variables.html#term-PACKAGE_CLASSES) variable.
- _SDK Target Architecture:_ Controlled by the [SDKMACHINE](https://docs.yoctoproject.org/ref-manual/variables.html#term-SDKMACHINE) variable.
- _Extra Image Packages:_ Controlled by the [EXTRA_IMAGE_FEATURES](https://docs.yoctoproject.org/ref-manual/variables.html#term-EXTRA_IMAGE_FEATURES) variable.
## Layers
- [Managing Layers](https://docs.yoctoproject.org/dev-manual/layers.html#managing-layers)

### Recepts
recepty:
`.class` - dědíme přes INHERIT
`.bb` - bitbake recept
`.bbappend` - najdi stejnojmenný recept a tohle přidej
`.conf` - konfigurace

### OpenEmbedded Build System Concepts
![YP flow diagram](https://docs.yoctoproject.org/2.5/overview-manual/figures/YP-flow-diagram.png)
## Další

VisualStudio Code rozšíření

BitBake
- Fatcher - stahování zdrojáků

