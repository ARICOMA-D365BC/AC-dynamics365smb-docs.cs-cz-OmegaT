---
    title: Design Details - Item Tracking and Reservations
    description: This topic talks about item tracking and reservations, and describes the concepts behind the two options.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/15/2021
    ms.author: edupont

---
# Detaily návrhu: Sledování zboží a Rezervace

Současné použití rezervace a sledování konkrétního zboží je neobvyklé, protože oba vytvářejí spojení mezi nabídkou a poptávkou. S výjimkou situací, kdy zákazník nebo plánovač výroby požaduje určitou šarži, kdy má zřídka smysl rezervovat skladové položky, které nesou čísla sledování zboží pro konkrétní výběr. I když je možné rezervovat zboží, které vyžaduje konkrétní sledování zboží, je zapotřebí speciálních funkcí, aby se zabránilo konfliktům dostupnosti mezi zpracovateli objednávek, kteří požadují stejné zboží sledované položkou.

Koncept "Pozdní vazby" zajišťuje, že nespecifická rezervace sériového čísla nebo čísla šarže zůstane volně spojena až do zaúčtování. V době zaúčtování může rezervační systém přemístil nespecifické rezervace, aby bylo zajištěno, že vyrovnání možné proti sériovému číslu nebo číslu šarže, které je skutečně vybráno. Mezitím je sériové číslo nebo číslo šarže k dispozici pro konkrétní rezervaci v jiných dokladech, které požadují toto konkrétní sériové číslo nebo číslo šarže.

Nespecifická rezervace je rezervace, ve které se uživatel nestará o to, která konkrétní položka je vybrána, a konkrétní rezervace je rezervace, ve které se uživatel ví, kterou chce.

> [!NOTE]  
> The Late Binding functionality relates only to items that are set up with specific item tracking, and it applies only to reservations against inventory, not against inbound supply orders.

Rezervace čísel sledování zboží spadá do dvou kategorií, jak je znázorněno v následující tabulce.

| Rezervace | Popis |
|-----------------|---------------------------------------|  
| Specifikcé | Určité sériové číslo nebo číslo šarže vyberete při rezervaci skladové položky z poptávky, například v prodejní objednávce.<br /><br /> Jedná se o běžnou rezervace. Jedná se o pevnou vazbu mezi nabídkou a poptávkou, která nese sériová čísla i čísla šarží. **Note:**  The demand carries serial or lot numbers. <br /><br /> For example, you want to reserve a can of blue paint from Lot A, because the customer requests it. Zákazníkovi je tedy dodána plechovka modré barvy ze šarže A. |
| Nespecifické | Při rezervaci skladového zboží z poptávky, například v prodejní objednávce, nebudete muset vybírat určité sériové číslo nebo číslo šarže.<br /><br /> Jedná se o stav, který je uložen u položky rezervace pro sériová čísla nebo čísla šarží, která nejsou vybrána specificky. **Note:**  The demand does not carry serial or lot numbers. <br /><br /> For example, you want to reserve a can of blue paint from any lot for your sales order. Zákazníkovi je odeslána plechovka modré barvy s náhodným sériovým číselem nebo číslem šarže. |

Hlavní rozdíl mezi specifickou a nespecifickou rezervací je definován existencí sériových čísel nebo čísel šarží na straně poptávky, jak je znázorněno v následující tabulce.

| Typ | Dodávka | Poptávka |
|-----------------|-----------------------|--------------------------|
| **Specific** | Sériové číslo nebo číslo šarže. | Sériové číslo nebo číslo šarže. |
| **Nonspecific** | Sériové číslo nebo číslo šarže. | Žádné sériové číslo nebo číslo šarže. |

When you reserve inventory quantities from an outbound document line for an item that has item tracking numbers assigned and is set up for specific item tracking, the **Reservation** page leads you through different workflows depending on your need for the serial or lot numbers.

## Specifická rezervace
When you choose **Reserve** from the outbound document line, a dialog box appears that asks you if you want to reserve specific serial or lot numbers. If you choose **Yes**, then a list is displayed with all the serial or lot numbers that are assigned to the document line. The **Reservation** page opens after you select one of the serial or lot numbers, and you can then reserve among the selected serial or lot numbers in a typical fashion.

If some of the specific item tracking numbers that you are trying to reserve are held in nonspecific reservations, then a message at the bottom of the **Reservation** page informs you how many of the total reserved quantity are held in nonspecific reservations and whether they are still available.

## Nespecifická rezervace
If you choose **No** in the dialog box that appears, the **Reservation** page opens and allows you to reserve among all serial or lot numbers in inventory.

Vzhledem ke struktuře rezervačního systému musí systém při umistování nespecifické rezervace zboží sledovaného zboží vybrat konkrétní položky zboží, proti které má být rezervováno. Protože položky zboží nesou i sledovací čísla zboží, rezervace si nepřímo vyhrazuje konkrétní sériová čísla nebo čísla šarží, i když jste to neměli v úmyslu. Aby se tato situace vyřešila, rezervační systém se před účtováním pokusí přesunout nespecifické položky rezervace.

Systém ve skutečnosti stále rezervuje proti konkrétním položkám, ale pak používá mechanismus přessunutí, kdykoli je v nespecifické rezervaci specifická poptávka po šarži nebo sériovém čísle. To může být případ, kdy účtujete transakci poptávky, například prodejní objednávku, deník spotřeby nebo objednávku transferu pro sériové číslo nebo číslo šarže nebo při pokusu o konkrétní rezervaci sériového čísla nebo čísla šarže. Systém přesunuje rezervace tak, aby byla šarže nebo sériové číslo k dispozici poptávce nebo konkrétní rezervaci, čímž se do nespecifické rezervace umístí jiné číslo šarže nebo sériové číslo. Pokud zásoby mají nedostatečné množství, systém provede co největší přesunutí a zobrazí se chyba dostupnosti, pokud v době zaúčtování stále není dostatečné množství.

> [!NOTE]  
> On a nonspecific reservation the lot number or serial number field is blank in the reservation entry that points at the demand, such as the sale.

## Přesunutí
Když uživatel zaúčtuje odchozí doklad po výběru nesprávného sériového čísla nebo čísla šarže, ostatní nespecifické rezervace se přesunou tak, aby odrážely skutečné sériové číslo nebo číslo šarže, které je vyskladněno. To uspokojí účtovací modul pevným vyrovnání mezi nabídkou a poptávkou.

U všech podporovaných obchodních scénářů je přemístíní možné pouze proti kladným položkám zboží, které nesou čísla rezervací, sériová čísla nebo šarže, ale bez definovaných sériových čísel nebo čísel šarží na straně poptávky.

## Podporované obchodní scénáře
Funkce Pozdní vazba podporuje následující obchodní scénáře:

* Zadání určitého sériového čísla nebo čísla šarže do výstupního dokladu s nespecifickou rezervací nesprávného sériového čísla nebo čísla šarže.
* Rezervace konkrétního sériového čísla nebo čísla šarže.
* Účtování výstupního dokladu s nespecifickou rezervací sériového čísla nebo čísla šarže

### Zadání sériových čísel nebo čísel šarží do výstupního dokladu se špatnou nespecifickou rezervací
To je nejběžnější ze tří podporovaných scénářů. V tomto případě funkce Pozdní vazba zajišťuje, že uživatel může zadat sériové číslo nebo číslo šarže, které je skutečně vyskladněné do výstupního dokladu, který má nespecifické sledování jiného sériového čísla nebo čísla šarže.

Potřeba nastává například v případě, že zpracovatel objednávky poprvé provedl nespecifickou rezervaci libovolného sériového čísla nebo čísla šarže. Později, když je zboží skutečně vyskladněné ze skladu, musí být vyskladněné sériové číslo nebo číslo šarže zadáno do objednávky před jeho účtováním. Nespecifická rezervace je v době zaúčtování přesunuta, aby bylo zajištěno, že vyskladněné sériové číslo nebo číslo šarže lze zadat bez ztráty rezervace a aby bylo zajištěno, že vyskladěné sériové číslo nebo číslo šarže může být plně použito a zaúčtováno.

### Rezervace konkrétního sériových čísel nebo čísel šarže.
V tomto obchodním scénáři funkce Pozdní vazba zajišťuje, že uživatel pokoušející se rezervovat určité sériové číslo nebo číslo šarže, které je aktuálně nespecificky rezervováno, tak může učinit. Nespecifická rezervace je v době rezervace přesunuta, aby se pro konkrétní požadavek uvolnilo sériové číslo nebo číslo šarže.

The reshuffle happens automatically, but embedded Help is displayed at the bottom of the **Reservation** page and shows the following text:

**XX of the Total Reserved Quantity are nonspecific and may be available.**

In addition, the **Nonspecific Reserved Qty.** field shows how many reservation entries are nonspecific. Ve výchozím nastavení toto pole není viditelné pro uživatele.

### Účtování výstupních dokladů s nespecifickou rezervací sériových čísel nebo čísel šarží
Tento obchodní scénář je podporován funkcí Pozdní vazba, která umožňuje pevné vyrovnání a odchozí účtování toho, co je skutečně vyskladněno pomocí přesunutí na jinou nespecifickou rezervaci sériového čísla nebo čísla šarže. Pokud přesunutí není možné, zobrazí se při pokusu účtování dodávky následující standardní chybová zpráva:

**Item XX cannot be fully applied.**

## Viz také
[Detaily návrhu: Sledování zboží](design-details-item-tracking.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]