# Yocto
Stojí nad BitBake.

```mermaid
graph TD;

	subgraph package
		make_pkg["make/Cmake/ninja"]
		src_pkg["src"]
		config_pkg["config"]
	end
	
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
	OpenEmbedded --> Yocto

	subgraph Image
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
	end
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

## Další

![YP flow diagram](https://docs.yoctoproject.org/2.5/overview-manual/figures/YP-flow-diagram.png)

recepty:
`.class` - dědíme přes INHERIT
`.bb` - bitbake recept
`.bbappend` - najdi stejnojmenný recept a tohle přidej
`.conf` - konfigurace

VisualStudio Code rozšíření

BitBake
- Fatcher - stahování zdrojáků