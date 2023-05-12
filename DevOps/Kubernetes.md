#CTC
# Kubernetes 
Kubernetes (zkráceně k8s) je přenositelná a rozšiřitelná open-source platforma, jejíž hlavním cílem je odstranit složitost správy velkého množství kontejnerů. Nabízí rozhraní API, přes které lze popsat požadovaný stav aplikace a platforma zajistí vše nezbytné pro přizpůsobení infrastruktury. Nasadí skupinu kontejnerů, replikuje je a v případě selhání některých z nich je znovu automaticky obnoví. Kubernetes byl původně navržen společností Google pro masivní škálování. Návrh vychází ze získaných zkušeností s interním nástrojem pro orchestraci kontejnerů Borg. V roce 2014 byl darován organizaci Cloud Native Computing Foundation (CNCF), která spolu s početnou uživatelskou komunitou stojí za popularitou této platformy. Nové funkce jsou vydávány přibližně každé tři měsíce a z toho je většina implementována právě na základě poptávky komunity.

## Architektura Kubernetes 
Jelikož je Kubernetes open source s relativně malými omezeními, může běžet téměř kdekoliv. Na fyzických nebo virtuálních strojích, případně ve veřejném nebo soukromém cloudu, jako je Microsoft Azure, Google Cloud nebo Amazon Web Services. Nejčastěji se používá společně s Dockerem, který poskytuje standard pro vytváření a distribuci kontejnerů. Kubernetes podporuje ale i další kontejnerové technologie, které splňují standardy Open Container Initiative (OCI). Jednou z nevýhod pro začínající uživatele je složitá konfigurace.
Kubernetes tvoří alespoň jeden řídící a více pracovních uzlů. Řídící (master) uzel je vstupní bod pro všechny administrativní úkoly a koordinuje všechny aktivity v clusteru, jakou jsou udržení požadovaného stavu nebo nasazení, škálování a aktualizace kontejnerů. Pro zajištění vysoké dostupnosti může být v clusteru více, než jeden řídící uzel. 

## Pod
Pod je nejmenší jednotka běhu v Kubernetes a reprezentuje běžící instanci jedné nebo více kontejnerů. Pod obsahuje společné prostory pro sdílení zdrojů, jako jsou síťové rozhraní a diskové prostředky, a tyto kontejnery sdílejí tyto prostředky mezi sebou. Pod poskytuje izolaci pro běh kontejnerů v rámci clusteru, ale nelze ho použít k izolaci aplikací od sebe.

## Node
Node je fyzický nebo virtuální stroj, který běží v Kubernetes clusteru a poskytuje prostředky pro běh kontejnerů. Node může hostit jeden nebo více Podů a může mít specifikované množství prostředků, jako jsou CPU, paměť a úložiště, které jsou sdíleny mezi Pody hostovanými na daném Node. Každý Node je připojen do Kubernetes clusteru a poskytuje základní infrastrukturu pro běh aplikací.

## Řídící uzel
Master je hlavní řídící uzel v Kubernetes clusteru a je zodpovědný za řízení celého clusteru. Master spravuje stav všech zdrojů v clusteru, plánuje a řídí běh aplikací a poskytuje API pro komunikaci s ostatními uzly v clusteru. Master se skládá z několika komponent, jako jsou API server, etcd, Scheduler a Controller Manager.

Řídící uzel obsahuje následující základní komponenty:

### Kube-scheduler 
Komponenta je zodpovědná za rozmístění podů (skupina jednoho nebo více kontejnerů) na různé uzle. Rozmístění závisí na řadě faktorů, jako jsou požadavky na systémové prostředky, software nebo umístění dat. Pokud například aplikace vyžaduje 1 GB operační paměti a 2 jádra CPU, budou pody pro tuto aplikaci rozmístěny na uzly, které mají dostatek prostředků.

### Etcd 
Distribuované úložiště klíč-hodnota, které Kubernetes používá k ukládání konfigurace clusteru (jako je počet podů, jejich stav, jmenné prostory atd.). Etcd komunikuje pouze přímo s kube-apiserver, který slouží jako zprostředkovatel a validátor pro jakékoliv operace s datovým úložištěm. Všechny ostatní komponenty, které potřebují získat informace o aktuálním stavu clusteru, musí komunikovat skrze kube-apiserver.

### Kube-apiserver 
Kubernetes API je centrální řídící komponenta, která přijímá všechny REST požadavky a slouží jako frontend do clusteru. Z toho důvodu slouží jako rozhraní pro veškerou komunikaci v clusteru. Uživatelé mohou komunikovat se serverem API přes příkazový řádek, prostřednictvím nástroje `kubectl`. Pomocí příkazu `kubectl` lze vytvářet, editovat a mazat jednotlivé prostředky, zobrazovat přehled o aktuálně běžících prostředcích a mnoho dalšího.

### Kube-controller-manager 
Spouští na pozadí řadu různých procesů, které sledují aktuální stav clusteru a provádí různé operace, aby zajistily požadovaný stav. V případě, že nastane změna konfigurace (například změna obrazu, ze kterého jsou pody spuštěny nebo změna parametrů v konfiguračním souboru yaml), controller zaznamená změnu a aktualizuje všechny prostředky, aby odpovídala novému požadovanému stavu.

### Cloud-controller-manager 
Komponenta je integrována do každého veřejného cloudu pro optimální podporu zón dostupnosti, virtuálních strojů, síťových služeb, úložiště, směrování a load balancingu.

## Pracovní uzel
Pracovní uzel je virtuální nebo fyzický stroj, který spouští kontejnery a je spravován řídícím uzlem. Každý uzel musí mít nainstalovaný nástroj pro správu a provoz kontejnerů, například Docker nebo Rkt. Původně bylo možné pracovní uzly konfigurovat pouze v systému Linux, ale od verze 1.14 je přidána podpora i pro Windows Server 2019. V produkčním prostředí by měl mít cluster minimálně tři uzly. 

Pracovní, jinak také "agent" je uzel, na kterých běží kontejnery. Agent je registrován u Mastera a řídí běh kontejnerů. Agent poskytuje prostředky pro běh kontejnerů, jako jsou CPU, paměť a úložiště. Agent také umožňuje Masteru ovládat kontejnery, které běží na tomto uzlu, a poskytuje Masterovi informace o stavu kontejnerů a uzlu jako celku.

Níže jsou popsány hlavní komponenty v pracovním uzlu:

### Kubelet 
Hlavní služba v uzlu, která pravidelně přijímá nové nebo upravené specifikace podů a zajišťuje, že pody a jejich kontejnery jsou bez chyb a běží v požadovaném stavu. Specifikace podu jsou soubory psané v YAML nebo JSON. Tato komponenta také zasílá informace řídícímu uzlu o stavu hostitele, na kterém služba běží.

### Kube-proxy 
Komponenta, která běží na každém pracovním uzlu za účelem řešení jednotlivých podsítí hostitele a vystavení služeb vnějšímu světu. Předává požadavky správným kontejnerům napříč různými izolovanými sítěmi v clusteru.

## Resources 
Pro seznámení se základní architekturou Kubernetes je důležité znát a pochopit i další prostředky, které umožňují v clusteru provozovat kontejnery tím nejlepším možným způsobem. Mezi nejpoužívanější prostředky (tzv. resources) patří Pods, Services, Deployments, Namespaces, Secrets, ConfigMaps atd. Pod je nejzákladnějším prostředkem v Kubernetes, který lze vytvořit nebo spravovat. Každý pod představuje jednu instanci dané aplikace nebo spuštěného procesu v Kubernetes. Skládá se z jednoho nebo více na sobě závislých kontejnerů, které sdílejí stejné síťové zdroje, úložiště, jedinečnou síťovou IP adresu a další konfiguraci, jak tyto kontejnery budou spuštěny. Kontejnery uvnitř podu mezi sebou komunikují pomocí portů a je možné do nich připojit datové úložiště s daty. Pody jsou vytvářeny a ničeny na uzlech podle potřeby, aby odpovídaly požadovanému stavu určeného uživatelem ve specifikaci podu. V případě selhání nebo nedostatku prostředků na uzlu je běžící pod na tomto uzlu zničen. Z toho důvodu je mnohem běžnější spravovat pody pomocí controllerů, které umožňují vytvářet a spravovat více podů, škálovat je, aktualizovat, nebo je automaticky obnovit po selhání na jiném uzlu. Mezi příklady controllerů, které obsahují jeden nebo více podů patří:

### ReplicaSet 
Zajišťuje spuštění zadaného počtu podů. Využívá se k zajištění vysoké dostupnosti a odolnosti proti chybám.

### Deployment 
Deployment spravuje controller ReplicaSet, který řídí počet podů, které by měly být spuštěny na základě požadovaného stavu. Navíc spravuje několik dalších věcí, jako jsou aktualizace podů a vrácení změn do původního stavu v případě, že aktualizace selže.

### StatefulSet 
Je přizpůsoben pro správu podů, které vyžadují perzistentní úložiště. Využívají se pro stavové aplikace jako je MySQL, Elasticsearch nebo MongoDB.

### DaemonSet 
Je způsob, jak zajistit, aby na každém uzlu v clusteru běžela jedna instance podu. Používá se pro služby, které zajišťují monitorování, protokolování a skenování virů.

### Job a CronJob 
Spouštějí naplánovanou úlohu, která může pravidelně spouštět nějaké zálohovací operace nebo import dat z jiného systému

## Services
Jelikož pody v clusteru jsou vytvářeny podle potřeby a mohou kdykoliv zaniknout, není zaručeno, že jejich IP adresa zůstane stejná. Proto nemá smysl používat jejich IP adresu. Služby (services) v Kubernetes seskupují pody a zajišťují mezi nimi komunikaci uvnitř clusteru, zároveň je umožňuje zpřístupnit mimo cluster do veřejné sítě. Služby poskytují stabilní IP adresu, která trvá po celou dobu existence služby, i když se změní IP adresy členských podů. Klienti zasílají požadavky na jednu stabilní IP adresu a jejich požadavky jsou přesměrovány na jeden z podů v rámci služby. Služba identifikuje své pody pomocí štítků a selektorů. Aby mohl být pod členem služby, musí mít všechny své štítky uvedené v selektoru služby. Štítek tvoří pár klíč-hodnota, který slouží k popisu a propojení objektů. Existuje několik typů služeb, které určují, jak je služba vystavena do sítě a odkud je služba přístupná.

### ClusterIP 
Výchozí typ služby, který vystavuje službu na interní IP adrese clusteru. Služba je dostupná pouze v rámci clusteru. 

### NodePort 
Vystavuje službu na IP adrese každého uzlu na konkrétním portu. Služba může zpracovávat požadavky, které přicházejí z vnějšku clusteru. 

### LoadBalancer 
Služba je přístupná z vnějšku clusteru prostřednictvím loadbalanceru od poskytovatele cloudu. Poskytovatel cloudu zajistí vytvoření loadbalanceru, který pak automaticky směruje požadavky na službu v Kubernetes. 

### ExternalName 
Mapují službu na název DNS. Není stanoveno žádné proxy jakéhokoliv druhu. Toto se běžně používá k vytvoření služby v Kubernetes, která představuje externí datové uložiště, jako je databáze, která běží mimo Kubernetes.

## Ingress
S přibývajícími službami se správa může stát velmi složitá. Kubernetes proto podporuje prostředek Ingress, který funguje jako vstupní bod do clusteru. Umožňuje sloučit směrovací pravidla do jednoho zdroje, proto může vystavit více služeb pod stejnou IP adresou. Navíc podporuje loadbalancing, TLS akceleraci a řízení certifikátů. Typickou implementací Ingress je Treafik, Ambassador nebo NGINX. Doposud byly popsány hlavní prostředky, bez kterých by provoz kontejnerů v Kubernetes nebyl možný. Mezi další podpůrné prostředky, se kterými je možné se v této práci setkat jsou:

### Namespace 
Jeden fyzický cluster může spouštět více virtuálních clusterů. Virtuální cluster je určený pro prostředí s mnoha uživateli rozloženými do více týmů nebo projektů. Využívá se pro oddělení produkčního a vývojového prostředí. 

### Volume 
Datový svazek se vztahuje na celý pod a je připojen do všech kontejnerů v podu. Kubernetes zaručuje, že data jsou zachována i po restartu kontejnerů. Jeden pod může mít připojeno více svazků různých typů. 

### Secret 
Obsahuje citlivé informace, jako jsou hesla, certifikáty TLS, tokeny OAuth a klíče ssh. 

### ConfigMap 
Je mechanismus, jak do kontejnerů připojit konfigurační soubory.

## Manifest
Tyto prostředky jsou definovány pomocí konfiguračních souborů (tzv. manifestů) ve formátu YAML nebo JSON. Kubernetes nepodporuje konfigurační soubory napsané pro Docker Compose nebo Swarm, jelikož mají zcela odlišné objekty a strukturu. 

## Kubectl
Kubectl je příkazový řádekový nástroj, který umožňuje administrátorům spravovat Kubernetes cluster pomocí příkazů. Kubectl komunikuje s API serverem v Kubernetes clusteru a umožňuje administrátorům vytvářet, měnit a odstraňovat zdroje v Kubernetes clusteru. Kubectl také umožňuje spravovat kontejnery a aplikace, které běží v clusteru.

Příklady příkazů v Kubectl jsou:

-  `kubectl create` - vytvoří nový objekt v Kubernetes clusteru na základě konfiguračního souboru.
- `kubectl get` - získá informace o zdrojích v Kubernetes clusteru, například seznam kontejnerů, služeb nebo uzlů.
- `kubectl describe` - zobrazí podrobné informace o zdroji v Kubernetes clusteru, jako jsou například konfigurace a stav.
- `kubectl apply` - aktualizuje nebo vytváří zdroje v Kubernetes clusteru na základě konfiguračního souboru.
- `kubectl delete` - odstraní zdroj v Kubernetes clusteru na základě jeho jména a typu.
- `kubectl logs` - zobrazí logy z kontejneru běžícího v Kubernetes clusteru.
- `kubectl exec` - spustí příkaz uvnitř běžícího kontejneru v Kubernetes clusteru.

Tyto a další příkazy v Kubectl umožňují administrátorům účinně spravovat Kubernetes cluster a aplikace běžící v něm.