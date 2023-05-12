#CTC 
# Docker

## Linux namespace
Docker využívá Linux oprávnění. Nastaví se aplikacím omezené prostředky.
Izolace prostředků v jádře od verze 2.4 (pouze mnt, 2002). Pro potřeby kontejnerů kompletní od jádra 3.8 (2013).
- mnt - izolace na úrovni mnt pointů 
- net - izolace na úrovni virtuálních síťových vrstev - privátní IP, dns, firewall, sokety - veth pair bridge 
- user - jiné opravnění vně/uvnitř (rootless) 
- cgroup - izolace systémových prostředků (cpu, mem, gpu, …)
- ipc (inter process komunikace), uts (hostname), pid (hierarchie a izolace)

### Docker vs Conteinerd
Docker je komplexní nástroj, který zahrnuje nejen správu kontejnerů, ale také správu sítí, úložišť a dalších funkcí. Na druhé straně Containerd je navržen jako jednoduchý nástroj, který se specializuje na řízení běhu kontejnerů podle standardu Open Container Initiative (OCI).

Docker může být stále používán pro běh kontejnerů, ale v poslední době se častěji používá jako vývojový nástroj pro tvorbu a testování aplikací v kontejnerech, zatímco Containerd se používá pro produkční běh kontejnerů. Containerd také umožňuje využití dalších nástrojů a platform, které podporují standard OCI, což zvyšuje jeho flexibilitu a interoperabilitu.

#### Containerd 
Containerd - runtime (jádro). 
Containerd vzniklo oddělením enginu dockeru jako samostatného open source řešení. Základem byl původní Docker, implementace v Go. Přesunut pod Open Container Initiative (OCI).

#### Open Container Initiative (OCI) 
OCI je standard pro kontejnery, který byl vytvořen jako otevřený a univerzální způsob, jak vytvářet a spouštět kontejnery na různých platformách. Containerd je implementací tohoto standardu a poskytuje základní funkce pro běh kontejnerů, jako jsou spouštění a ukončování kontejnerů, správa jejich konfigurace a další.

## Docker klient 
Docker klient umožňuje uživatelům komunikovat s více než jedním Docker daemonem v infrastruktuře. Ke komunikaci s Docker daemonem poskytuje klient příkazy, které uživatel zapisuje do příkazového řádku (CLI). 

Mezi nejběžnější příkazy patří: 
- `docker run` – Vytvoří a spustí kontejner na pozadí nebo v popředí.
- `docker pull` – Stáhne obraz z registru do Docker daemonu.
- `docker push` – Nahraje obraz z Docker daemonu do registru.
- `docker build` – Sestaví nový obraz kontejneru.
- `docker stats` – Zobrazuje statistiku využití systémových prostředků jednotlivými kontejnery.
- `docker exec` – Spustí příkaz uvnitř kontejneru.
- `docker logs` – Zobrazí protokoly kontejneru.

## Registr 
Registr je služba, která primárně slouží k ukládání a distribuci již sestavených Docker obrazů. Registr je organizován do repositářů, ve kterých jsou uchovávány verze konkrétního obrazu. Stejný obraz může mít více různých verzí identifikovaných podle jejich značek (tags). Registr umožnuje uživatelům vyhledat a stáhnout jakýkoliv obraz z repositáře, nebo naopak do něho nahrát a uložit již sestavený obraz, který je následně možné sdílet s ostatními členy vývojového týmu, nebo různými organizacemi. Repositáře uvnitř registru mohou být nastaveny jako veřejné nebo soukromé. 

- **Soukromý** (Privátní) – V repozitáři jsou uloženy obrazy, které mohou obsahovat citlivé informace, nebo zdrojové kódy a jsou sdíleny pouze v rámci týmu nebo organizace.
	- Harbor
	- Docker Registry
- **Veřejný** (Cloudový) – Obraz z repozitáře je přístupný komukoliv a každý si ho může stáhnout. 
	- [DockerHub](https://hub.docker.com/)
	- Azure Container Registry

Nejběžnější příkazy pro práci s registry jsou `docker pull` a `docker push`. 

Společnost Docker provozuje veřejný registr zvaný Docker Hub, který kromě veřejných a soukromých repozitářů poskytuje také automatické sestavení obrazu. Docker Hub obsahuje desítky tisíc obrazů od různých uživatelů a společností. Docker je ve výchozím nastavení nakonfigurovaný tak, aby primárně vyhledával obrazy z něho. Na trhu existuje několik dalších služeb od společností jako Microsoft, Amazon nebo Google, které nabízejí své placené veřejné registry s vysokou dostupností, jedná se o služby Azure Container Registry, Amazon Elastic Container Registry nebo Google Container Registry. Mimo veřejných registrů, provozovaných v cloudu, je možné provozovat i soukromé registry na vlastní infrastruktuře.

## Docker komponenty 
Pro sestavení a spuštění aplikací v kontejnerech Docker vytváří a používá komponenty, mezi které patří obrazy, kontejnery, služby, dockerfiles a další. Následující kapitoly obsahují stručný přehled těchto komponent.

- Obraz (Image) 
- Registr 
- Kontejner 
	- Jádro (Engine)
	- Běhové prostředí

### Obraz
Základní funkční prvek, “pojmenovaný balíček”, který lze jednoduše kopírovat, sdílet a upravovat.
Skládá se z: 
- **Manifestu** – definice všech komponent které dohromady tvoří image
- **Rozložení** (Layout) – definuje strukturu vrstev souborového systému
- **Vrstvy souborového systému**
- **Index** (volitelný) – index manifestů

Obraz (image) je šablona, ze které lze spustit nové kontejnery. Pro spuštění libovolného počtu kontejnerů lze použít pouze jeden obraz. Obrazy nejsou monolitické bloky, ale skládají se z řady vrstev (layers), které jsou pouze pro čtení. Jednotlivé vrstvy jsou naskládány na sebe a každá vrstva je pouze množinou rozdílů souborového systému od vrstvy před ní. Každý obraz začíná základním obrazem, který tvoří základní vrstvu v obrazu. Typicky je tento základní obraz jedním z oficiálních obrazů, jako je Windows Server Core, Ubuntu nebo CentOS, stažených z veřejných registrů. Je však možné vytvořit obraz zcela od nuly.

#### Vrstvy
Jestliže jsou z obrazu vytvořeny kontejnery, přidá se pro každý kontejner zároveň nová vrstva, do které lze i zapisovat. Tato vrstva se nazývá vrstva kontejneru a jsou v ní uloženy všechny změny provedené ve spuštěném kontejneru (nově vytvořené soubory, změnu existujících souborů, nebo nově smazané soubory). Tyto změny lze uložit do nového obrazu, jinak je možné o změny v kontejneru kdykoliv přijít. Pokud je kontejner odstraněn, smaže se zároveň i vrstva kontejneru a obraz zůstává nezměněn.
Sdílení jednoho obrazu mezi několik kontejnerů má za následek snížení spotřebovaných výpočetních prostředků a dobu spouštění kontejnerů, protože se vytváří pouze tenká vrstva kontejneru a obraz se nemusí znovu vytvářet, nebo stahovat.

Plné jméno:
- docker.io/library/ubuntu:20.04
- REGISTR/SKUPINA/PROJEKT:TAG 
Projekt 
- Slouží k oddělení projektů
- Např. ubuntu nebo nginx
Tag 
- Uživatelský: 1.2.4 
- Hash: e1f5733f050b2488a17b7…
- Speciální: latest

##### Union filesystem 
Skládá se z vrstev: 
- BootFs (přečten při startu) 
- RootFs (např. ubuntu, pouze čtení) 
- Uživatelské vrstvy (pouze čtení) 
- Vrstva běžícího kontejneru (čtení i zápis)

Zápis pomocí metody COW (copy on write). Upravený soubor se nakopíruje do zápisové vrstvy, původní verze v předchozí vrstvě se nezmění.

Union filesystem je typ souborového systému, který umožňuje spojovat více zdrojů dat do jediného virtuálního adresářového stromu. Tento typ souborového systému umožňuje různým procesům pracovat se stejnými soubory a adresáři bez konfliktů a také umožňuje správu většího množství dat bez nutnosti fyzického přesouvání souborů.

Union filesystem funguje tak, že vytváří hierarchický strom, který se skládá z několika vrstev, kde každá vrstva reprezentuje jiný zdroj dat. Tento strom se pak chová jako jeden jediný adresářový strom, ačkoliv se skutečně skládá z různých zdrojů.

Když se v Union filesystemu provádí čtení nebo zápis souboru, systém nejprve hledá soubor nejvyšší vrstvy (nebo vrstev), ve které je soubor k dispozici. Pokud soubor není nalezen, systém postupuje dále a hledá další vrstvy a tak dále, dokud nenajde požadovaný soubor. Pokud je soubor nalezen v některé z vrstev, pak je použit tento soubor a operace je provedena na tomto souboru.

Union filesystem je často používán v kontejnerových technologiích, jako je například Docker, pro umožnění sdílení souborů mezi hostitelským počítačem a kontejnerem, a také mezi kontejnery samotnými. To umožňuje snadnější nasazení aplikací v různých prostředích a umožňuje rychlejší vývoj a testování aplikací v izolovaném prostředí.

##### Copy-on-Write (COW)
V kontextu Union filesystemu se často využívá konceptu Copy-on-Write (COW). COW je technika, která umožňuje vytvářet kopie souborů a adresářů, aniž by byly fyzicky duplikovány. Namísto toho se při vytvoření kopie vytvoří pouze odkaz na původní soubor nebo adresář, a fyzické duplikování se provede pouze tehdy, když jsou soubory nebo adresáře upravovány.

V kontejnerových technologiích jako Docker se COW využívá pro vytváření kontejnerů. Kontejner se skládá z několika vrstev, kde každá vrstva reprezentuje jinou část kontejneru, například operační systém, aplikaci a konfigurační soubory. Když je vytvořen nový kontejner, Docker vytvoří základní vrstvu, která obsahuje operační systém a další potřebné zdroje. Další vrstvy jsou pak přidávány jako COW vrstvy, které obsahují změny v aplikaci a konfiguraci. Tím se dosáhne efektivního využití úložiště a rychlejšího nasazení kontejneru.

Použití COW v kontejnerových technologiích také umožňuje snadnou správu a aktualizaci kontejnerů. Pokud je potřeba aktualizovat kontejner, stačí vytvořit novou COW vrstvu, která obsahuje změny, a vytvořit nový kontejner s touto vrstvou. Pokud je potřeba vrátit se k předchozí verzi kontejneru, stačí jednoduše odstranit vrstvu s aktualizací a kontejner se vrátí ke své předchozí verzi.

### Sestavení obrazu 
Docker obsahuje nástroje, které umožnují sestavit vlastní obrazy podle našich požadavků, nebo lze pouze upravit ty, které vytvořili jiní a publikovali je ve veřejných registrech. Nový obraz je možné sestavit automatizovaným procesem, provedením sady instrukcí obsažených v textovém souboru Dockerfile. Příklad Dockerfilu (Zdrojový kód 3 Dockerfile) má několik řádků, z nichž každý začíná instrukcí jako FROM, RUN nebo CMD. Výsledkem provedení těchto instrukcí je nový obraz, který zahrnuje nakonfigurovaný webový server s aplikací.

```dockerfile
FROM ubuntu:21.04 
COPY . /app 
RUN make /app 
CMD python /app/app.py
EXPOSE 80
```

Následující příklady jsou nejčastěji používanými instrukcemi v souborech Dockerfile: 

- **FROM**
Většina Dockerfilů začíná právě instrukcí FROM a definuje, ze kterého základního obrazu se vytváří náš vlastní obraz. Pokud základní obraz není přítomen v systému, kde proces sestavení běží, Docker se pokusí tento obraz stáhnout z veřejného nebo soukromého registru. 

- **RUN** 
Instrukce RUN provede jakýkoliv platný příkaz a výsledek uloží do nové vrstvy obrazu kontejneru. Tyto příkazy mohou provádět instalaci softwaru, vytváření souborů a adresářů, nebo vytváření konfigurace prostředí. Dlouhé a složité příkazy lze rozdělit zpětným lomítkem na více řádků. Tím je Dockerfile lépe čitelný, srozumitelný a udržovatelný.

- **COPY a ADD** 
Tyto dvě instrukce se používají ke kopírování souborů a složek ze souborového systému hostitele do obrazu, který vytváříme. Instrukce jsou si velmi podobné, s výjimkou toho, že klíčové slovo ADD navíc umožňuje kopírovat sobory ze vzdáleného umístění pomocí URL adresy a kopírovat a rozbalovat TAR soubory. 

- **WORKDIR** 
Nastavuje pracovní adresář pro další Dockerfile instrukce. 

- **CMD a ENTRYPOINT** 
Tyto instrukce jsou odlišné od ostatních. Zatímco všechny ostatní instrukce definované v souboru Dockerfile jsou prováděny v době sestavení obrazu, tyto dvě jsou pouze definicí toho, jak a jaký proces, nebo aplikace, bude spuštěna uvnitř kontejneru, když se kontejner spustí z vytvořeného obrazu.

Instrukce jsou prováděny popořadě a každá z nich vytvoří novou vrstvu v obraze. Změní-li se soubor Dockerfile a znovu dojde k sestavení obrazu, budou znovu sestaveny pouze ty vrstvy, které byly změněny. Toto je důvodem, proč jsou obrazy lehké, malé a rychlé ve srovnání s jinými virtualizačními technologiemi.
Sestavení obrazu lze spustit příkazem `docker build`, který čte instrukce právě ze souboru Dockerfile. Sestavený obraz lze nahrát do registru, nebo rovnou vytvořit nový kontejner s tímto obrazem.

### Kontejner 
Skupina izolovaných procesů běžících na jednom stroji se společnou sadou vlastností

Izolace aplikací: 
- Procesor, paměť, disk, síť, oprávnění, souborový systém
- Vytvoření izolovaného prostředí (sandbox) 

Jednoduchá distribuce:
- Balíček obsahující všechny prostředky potřebné pro běh
- Systémové balíčky a knihovny, konfigurační soubory, skripty

Sjednocený způsob pro práci:
- Spuštění, zastavení, výpis, přístup
- Přístup k výstupu, metrikám

Kontejnery jsou izolovaná prostředí, ve kterých jsou spouštěny aplikace. Kontejner je definován [[Docker#Obraz|obrazem]] a dalšími konfiguračními možnostmi. Pomocí rozhraní, které nabízí Docker, lze kontejner spustit, zastavit, přesunout nebo odstranit. Kontejner lze připojit k jedné nebo více [[Docker#Docker a síť|sítím]], připojit k němu [[Docker#Uložiště|uložiště]], nebo vytvořit úplně nový obraz na základě aktuálního stavu. Pokud je kontejner odstraněn, jsou odstraněny i veškeré změny jeho aktuálního stavu, které předtím nebyly uloženy v připojeném úložišti. Kontejnery mají přístup pouze k prostředkům, které jsou definovány v obrazu, pokud nejsou při vytváření kontejneru definovány další přístupy. Vzhledem k tomu, že kontejnery jsou mnohem menší než virtuální stroje, mohou být během několika sekund restartovány a výsledkem je mnohem lepší hustota serverů.

### Služba 
Služba umožnuje jednoduše škálovat kontejnery se stejnou konfigurací napříč více Docker daemony běžícími na různých hostitelích, které společně fungují jako swarm. Každý člen swarmu je Docker daemon a všichni daemoni spolu úzce spolupracují a komunikují pomocí Docker API. Docker Swarm je více popsán v samostatné kapitole. Často je služba obrazem mikroslužby v rámci nějaké větší aplikace. Příkladem služby může být webový server, databáze nebo jakýkoliv jiný typ aplikace spustitelné v distribuovaném prostředí. Při vytváření služby je nutné definovat požadovaný stav, například jaký obraz se má použít, jaké porty by měla služba používat, kolik replik kontejnerů by mělo běžet v daném okamžiku, nebo jaké příkazy se mají spustit v běžících kontejnerech. Jednou z klíčových výhod mezi službami a samostatnými kontejnery je to, že lze upravit jejich konfiguraci, aniž bychom museli službu jakkoliv ručně restartovat

## Docker a síť
Ovladače: 
- Bridge - Propojení kontejnerů v rámci jednoho stroje 
- Host - Bez izolace 
- Overlay - Propojení kontejnerů v rámci více strojů 
- None - Bez externí konektivity 
- xterní pluginy

### Bridge 
Docker Bridge (také známý jako Docker0) je výchozí síťový adaptér, který je vytvořen při instalaci Dockeru na hostitelském počítači. Bridge je typ sítě, který slouží k propojení kontejnerů s hostitelským počítačem a mezi sebou navzájem. Jedná se o interní síť, která není přístupná zvenčí.

Každý kontejner má svou vlastní síťovou identitu, jako je například IP adresa, ale pokud se kontejnery potřebují navzájem propojit, musí být připojeny k síti Bridge. Bridge umožňuje kontejnerům komunikovat mezi sebou a s hostitelským počítačem pomocí virtuálních rozhraní.

Docker Bridge také poskytuje základní síťovou izolaci mezi kontejnery, což znamená, že kontejnery mohou být spuštěny v izolaci od ostatních aplikací běžících na hostitelském počítači. To umožňuje aplikacím spuštěným v kontejnerech běžet bez interferencí s ostatními aplikacemi a také zvyšuje bezpečnost kontejnerového prostředí.

Docker Bridge je výchozí nastavení sítě pro Docker kontejnery, ale Docker podporuje také vytváření vlastních sítí a připojení kontejnerů k nim. To umožňuje uživatelům vytvářet a spravovat síťové topologie pro své aplikace, což je užitečné pro složitější konfigurace a nasazení aplikací.

### PortMapping
V Dockeru se porty mapují pomocí tzv. "port mapping" neboli "port forwarding". To znamená, že se připojení na určitý port v kontejneru přesměruje na určitý port na hostitelském systému.

Při spouštění kontejneru lze v příkazu použít parametr "-p" nebo "--publish", následovaný dvěma čísly oddělenými dvojtečkou. První číslo určuje port na hostitelském systému a druhé číslo určuje port v kontejneru. 

Například:
```Bash
docker run -p 8080:80 nginx
```

Tento příkaz spustí kontejner s webovým serverem Nginx a mapuje port 80 v kontejneru na port 8080 na hostitelském systému. To znamená, že pokud nyní otevřeme webový prohlížeč a zadáme adresu [http://localhost:8080](http://localhost:8080/), bude požadavek přesměrován na webový server Nginx v kontejneru a zobrazí se odpovídající webová stránka.

Port mapping umožňuje jednoduchou komunikaci mezi kontejnery a hostitelským systémem nebo mezi kontejnery samotnými. Tento mechanismus také umožňuje běh více instancí stejného kontejneru na stejném hostitelském systému s různými porty.

## Uložiště
Docker umožňuje ukládat data v kontejnerech pomocí různých mechanismů, z nichž jeden je použití "volumes" neboli uložišť. Uložiště jsou speciální cesty v souborovém systému kontejneru, které umožňují ukládat data mimo samotný kontejner a uchovávat je i při zastavení a spuštění nové instance kontejneru.

Existují dva typy uložišť v Dockeru: "named volumes" a "host volumes".

### Volume
"Named volumes" jsou vytvářeny pomocí příkazu `docker volume create` a jsou spravovány Dockerem. Tyto uložiště jsou vhodné pro ukládání dat mezi různými instancemi kontejnerů a jejich použití je nezávislé na hostitelském souborovém systému.

### Bind mount
Na druhé straně "host volumes" jsou složky nebo soubory na hostitelském systému, které jsou připojeny do kontejneru jako uložiště pomocí parametru "-v" nebo "--volume" při spuštění kontejneru. Tyto uložiště jsou vhodné pro ukládání dat mimo kontejner, ale na hostitelském systému a jsou přístupné přímo z hostitelského souborového systému.
