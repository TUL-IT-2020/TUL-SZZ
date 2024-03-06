#Linux 
# Tar Command

## Úvod
> [!tldr] 
> Příkaz **tar** v [[Linux]] je jedním z nejdůležitějších příkazů pro správu souborů. Je zkratkou pro Tape Archive a slouží k vytváření a extrahování archivních souborů. 

> [!info] Archivní soubor 
> je komprimovaný soubor, který obsahuje jeden nebo více souborů seskupených pro snazší uložení a přenositelnost. 

V tomto průvodci ukážeme, prostřednictvím příkladů, jak vytvářet, vypisovat, upravovat a extrahovat archivní soubory tar a pokrýt některé z nejčastěji používaných možností příkazu tar.

## Syntaxe příkazu tar

Příkaz **tar** přijímá následující syntaxi −
```bash
$ tar [možnosti][archivní-soubor] [soubor nebo adresář, který má být archivován]
```

Podívejme se na některé z možností poskytovaných příkazem **tar**.

### Možnosti příkazu tar

> [!example] Příkaz **tar** poskytuje následující možnosti −
> - -c − Toto vytváří archivní soubor.
> - -x − Možnost extrahuje archivní soubor.
> - -f − Určuje název souboru archivu.
> - -v − Tiskne podrobné informace o jakékoli operaci tar na terminálu.
> - -t − Toto vypisuje všechny soubory uvnitř archivního souboru.
> - -u − Toto archivuje soubor a pak jej přidá k existujícímu archivnímu souboru.
> - -r − Toto aktualizuje soubor nebo adresář umístěný uvnitř .tar souboru
> - -z − Vytvoří soubor tar pomocí komprese gzip
> - -j − Vytvoří archivní soubor pomocí komprese bzip2
> - -W − Možnost -w ověřuje archivní soubor.
> - -C − Toto mění adresář před vytvořením nebo extrahováním souborů.
> - --delete − Toto odstraní soubor ze souboru tar.

## Vytvoření archivního souboru

Nástroj **tar** vám umožňuje vytvářet archivní soubory pomocí různých algoritmů komprese, jako jsou **xz**, **gzip** a **bzip2**. Přijatým konvenčním zvykem je přidat příponu komprese k komprimovanému souboru.

Například při použití komprese **gzip** (pomocí možnosti **-z**) musí mít soubor příponu `.tar.gz`.
```bash
$ tar -czvf sales.tar.gz  sales1.pdf sales2.pdf sales3.pdf
```

V tomto příkladu příkaz vytváří soubor s názvem `sales.tar.gz` ze tří PDF souborů.

Stejně tak při použití komprese **bzip2** (pomocí možnosti **-j**) musí mít archivní soubor příponu `.tar.bz2` jako příponu.
```bash
$ tar -cjvf sales.tar.bz2 sales1.pdf sales2.pdf sales3.pdf
```

Kromě archivace souborů můžete také komprimovat adresáře. Například následující příkaz vytváří jednoduchý tarball domovského adresáře.
```bash
$ tar -cvf home.tar /home/james
```

### Výpis obsahu archivního souboru

Možnost **-t** lze použít k výpisu obsahu archivního souboru bez jeho extrakce.
```bash
$ tar -tf sales.tar.gz
```

Tento příkaz vypisuje všechny soubory v archivu `sales.tar.gz`.

## Extrahování archivního souboru

Existuje několik způsobů, jak extrahovat komprimovaný soubor pomocí příkazu **tar**.

### Extrahování do aktuálního adresáře

Pro extrahování archivu do aktuálního pracovního adresáře použijte možnost **-x**.
```bash
$ tar -xvf documents.tar.gz
```

V tomto příkladu jsme rozbalili nebo extrahovali soubor `documents.tar.gz`, který obsahuje tři textové soubory.

### Extrahování do samostatného adresáře

Pro extrahování archivu do jiného adresáře se používá možnost **-C** následovaná cílovou cestou, jak je ukázáno v následujícím příkladu.
```bash
$ tar -xvf documents.tar.gz -C /tmp/files
```

Tento příkaz extrahuje obsah archivu `documents.tar.gz` do adresáře `/tmp/files`.

### Extrahování konkrétních souborů z archivu

Můžete extrahovat určité soubory tím, že je budete vypisovat jeden po druhém na příkazovém řádku.
```bash
$ tar -xvf documents.tar.gz file1.txt file2.txt
```

V tomto příkladu jsme extrahovali soubory `file1.txt` a `file2.txt` z archivu `documents.tar.gz`.

## Přidání souboru do .tar archivu

Pro přidání nebo připojení souboru k `.tar` archivu použijte možnost **-r**.
```bash
$ tar -rvf files.tar file3.txt
```

V tomto příkladu přidáváme soubor `file3.txt` do souboru `archives.tar`.

## Odstranění souboru z .tar souboru

Pro odstranění souboru z `.tar` archivu použijte možnost **--delete**.
```bash
$ tar --delete -f archives.tar file3.txt
```

V tomto příkladu odstraňujeme soubor `file3.txt` ze souboru `archives.tar`.

### Komprese archivu

Příkaz **tar** lze také použít k vytvoření komprimovaného archivu pomocí komprese **gzip** nebo **bzip2**. Pro vytvoření komprimovaného souboru lze možnost **-z** nebo **-j** použít ve spojení s možností **-c**.
```bash
$ tar -zcvf archive.tar.gz files_to_compress
```

Tento příkaz vytváří archiv `.tar.gz` z určených souborů.
```bash
$ tar -jcvf archive.tar.bz2 files_to_compress
```

Tento příkaz vytváří archiv `.tar.bz2` z určených souborů.

### Rozbalení archivu

Pro dekomprimaci souboru `.tar.gz` −
```bash
$ tar -zxvf archive.tar.gz
```

Pro dekomprimaci souboru `.tar.bz2` −
```bash
$ tar -jxvf archive.tar.bz2
```

## Závěr

Příkaz **tar** je velmi užitečný nástroj pro správu archivních souborů v [[Linux]] a může být použit k vytvoření, výpisu, úpravě a extrakci archivních souborů. Tento průvodce poskytuje několik příkladů, jak používat příkaz **tar** k vytvoření, výpisu, úpravě a extrakci archivních souborů.

## Zdroje:
- https://www.tutorialspoint.com/linux-tar-command