#CTC 
# GO
> [!example] Stránky: 
>- [golang](https://golang.org/)
>- [go.dev](https://go.dev/)
>- [geting started](https://go.dev/doc/tutorial/getting-started)
>- [naming conventions](https://betterprogramming.pub/naming-conventions-in-go-short-but-descriptive-1fa7c6d2f32a)
>- https://go.dev/tour/moretypes/26
>- https://go.dev/doc/tutorial/create-module
## Go Tour na vašem počítači
```Bash
go tool tour
```

## go.mod  
Soubor go.mod je soubor, který obsahuje informace o modulu, který se nachází v aktuálním adresáři a jeho závislostech na jiných modulech. Tento soubor je vytvořen příkazem `go mod init`.  

## Datové typy
Veřejný vs privátní datový typ:
- Veřejný: začíná Velkým písmenem
- Privátní: začíná malým písmenem

Deklarace proměnné:
- U implicitní deklarace je typ proměnné určen na základě hodnoty.

```go
// privátní deklarace
// explicitní
var x int 

// implicitní
y := 1 

// public deklarace
var Z int
```

### Uint64  
Uint64 je nezáporný celočíselný typ, který může představovat čísla od 0 do 2^64-1. "Uint" znamená "unsigned integer" (nezáporné celé číslo). 

### struct{}  
Struktura je základní datový typ v Go, který umožňuje seskupit proměnné různých typů. "struct{}" je prázdná struktura, která neobsahuje žádné pole. Tento typ se často používá v situacích, kde potřebujete něco signalizovat, ale samotná hodnota není důležitá. Například prázdná struktura se často používá s kanály pro signalizaci, že nějaký proces je hotov, aniž byste museli posílat konkrétní hodnotu.

## Funkce
```go
// bez návratové hodnoty
func print(x int) {
    fmt.Println(x)
}

// s jednou návratovou hodnotou
func add(x int, y int) int {
    return x + y
}   

// více návratových hodnot
func swap(x, y string) (string, string) {
    return y, x
}
```

### Defer  
> [!tldr] zpožděné vykonání

Klíčové slovo defer v jazyce Go se používá k odložení vykonání funkce až do konce obsahující funkce. To je užitečné pro úklid, jako je zavírání souborů nebo odemykání mutexů, bez ohledu na to, jak se funkce ukončí.  

## Kanál  
Kanál v jazyce Go je nástroj pro komunikaci mezi gorutinami. Pomocí kanálů můžete odesílat hodnoty z jedné gorutiny do druhé. Jsou navrženy tak, aby podporovaly posílání zpráv, což je výhodné pro vytváření synchronizovaných procesů.  

### chan bool  
Tento typ je kanál, který přenáší hodnoty boolean (pravdivostní hodnoty).  

### <- chan bool  
Tento zápis se používá pro přijímání hodnot z kanálu booleanů. Symbol "<-" je operátor přijetí a "chan bool" je kanál booleanů.  

## Gorutina  
Gorutiny jsou lehké vlákna pro výkonnost v jazyce Go. Zatímco tradiční vlákno v operačním systému může obsahovat až megabajty paměti, gorutina obvykle potřebuje jen několik kilobajtů. To umožňuje snadno vytvořit tisíce nebo dokonce miliony gorutin v jednom programu.  

## Synchronizace
### Mutex  
Mutex je nástroj pro synchronizaci v jazyce Go, který se používá k ochraně sdílených dat před současným přístupem. Používá se v situacích, kdy potřebujete zajistit, že pouze jedna gorutina může přistupovat k určitému kódu nebo datům v daný moment.  

### wait.Group  
WaitGroup je struktura z balíčku "sync" v Go, která se používá k synchronizaci výkonu skupiny gorutin. Pomocí metod **Add**, **Done** a **Wait** můžete ovládat, kdy se skupina gorutin spustí a dokončí. Je to nástroj pro synchronizaci v jazyce Go, který umožňuje čekat na dokončení několika gorutin. To je užitečné, pokud potřebujete spustit několik gorutin a chcete počkat, až všechny skončí.  

