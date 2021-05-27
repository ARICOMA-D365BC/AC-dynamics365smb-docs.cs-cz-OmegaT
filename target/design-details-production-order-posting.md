---
    title: Design Details - Production Order Posting | Microsoft Docs
    description: Similar to assembly order posting, the consumed components and the used machine time are converted and output as the produced item when the production order is finished.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2021
    ms.author: edupont

---
# Podrobnosti návrhu: Účtování výrobní zakázky
Podobně jako při zaúčtování montážní zakázky jsou spotřebované komponenty a použitý čas stroje převedeny a výstupem je vyrobené zboží po dokončení výrobní zakázky. Pro více informací navštivte [Podrobnosti návrhu: Účtování montážní zakázky](design-details-assembly-order-posting.md). Tok nákladů pro montážní zakázky je však méně složitý, zejména proto, že účtování nákladů na montáž probíhá pouze jednou a nevytváří zásoby v procesu práce.


Transakce, ke kterým dochází během výrobního procesu, lze sledovat v následujících fázích:

1. Nákup materiálů a dalších výrobních vstupů.
2. Přeměna na nedokončenou výrobu.
3. Přeměna na zásoby hotových výrobků.
4. Prodej hotových výrobků.

Proto kromě běžných skladových účtů musí výrobní společnost zřídit tři samostatné skladové účty pro evidování transakcí v různých fázích výroby.

| Skladový účet | Popis |
|-----------------------|---------------------------------------|  
| **Raw Materials account** | Zahrnuje náklady na suroviny, které jsou zakoupeny, ale dosud nebyly převedeny do výroby. Zůstatek na účtu Surovin označuje náklady na suroviny, které jsou k dodaní.<br /><br /> Když se suroviny přesunou do výroby, náklady na materiál se převedou z účtu Surovin na účet nedokončené výroby. |
| **Work in Process (WIP) account** | Kumulace nákladů vzniklých během výroby v účetním období. Účet nedokončené výroby je odepisován z nákladů na suroviny, které jsou převedeny ze skladu surovin, nákladů na přímou práci a vzniklých výrobních režijních nákladů.<br /><br /> Účet nedokončené výroby se připisuje k celkovým výrobním nákladům jednotek, které jsou dokončeny ve výrobním závodě a převedeny do skladu hotových výrobků. |
| **Finished Goods account** | Tento účet zahrnuje celkové výrobní náklady jednotky, které jsou dokončeny, ale ještě nebyly prodány. V době prodeje se náklady na prodané jednotky převádí z účtu Hotových výrobků na účet Nákladů na prodané zboží. |

Hodnota zásob se vypočítá sledováním nákladů na všechna zvýšení a snížení vyjádřená následující rovnicí:

* hodnota zásob = počáteční zůstatek zásob + hodnota všech zvýšení - hodnota všech snížení

V závislosti na typu zásob jsou zvýšení a snížení reprezentovány různými transakcemi.

||Increases|Decreases|  
|-|---------------|---------------|  
|**Raw material inventory**|-   Net purchases of material<br />-   Output of subassemblies<br />-   Negative consumption|Material consumption|  
|**WIP inventory**|-   Material consumption<br />-   Capacity consumption<br />-   Manufacturing overhead|Output of end items (cost of goods manufactured)|  
|**Finished goods inventory**|Output of end items (cost of goods manufactured)|-   Sales (cost of goods sold)<br />-   Negative output|  
|**Raw material inventory**|-   Net purchases of material<br />-   Output of subassemblies<br />-   Negative consumption|Material consumption|

Hodnoty zvýšení a snížení se zaznamenávají v různých typech vyrobených zásob stejným způsobem jako u nakoupených zásob. Pokaždé, když se transakce zvýšení nebo snížení zásob uskuteční, vytvoří se pro tuto částku položka zboží a odpovídající věcná položka. Pro více informací navštivte [Detaily návrhu: Účtování zásob](design-details-inventory-posting.md).

Přestože hodnoty transakcí, které souvisejí s nakoupeným zbožím, jsou zaúčtovány pouze jako položky zboží se souvisejícími položkami ocenění, transakce, které souvisejí s vyrobeným zbožím, jsou kromě položek zboží zaúčtovány jako položky kapacity se souvisejícími položkami ocenění.

## Struktura účtování
Zaúčtování výrobních objednávek do Nedokončené výroby zahrnuje výstup, spotřebu a kapacity.

Následující diagram znázorňuje princip účtování v codeunitě 22.

![Postupy účtování výrobní zakázky](media/design_details_inventory_costing_14_production_posting_1.png "Postupy účtování výrobní zakázky")

Následující diagram znázorňuje spojení mezi výslednými položkami a nositeli nákladů.

![Vstupní tok výroby](media/design_details_inventory_costing_14_production_posting_2.png "Vstupní tok výroby")

Položka kapacity popisuje spotřebu kapacity z hlediska časových jednotek, zatímco související položka ocenění popisuje hodnotu specifické spotřeby kapacity.

Položka zboží popisuje spotřebu materiálu nebo výstup z hlediska množství, zatímco související položka ocenění popisuje hodnotu této specifické spotřeby nebo výstupu materiálu.

Položku hodnoty, která popisuje hodnotu zásob nedokončené výroby, lze přidružit k jedné z následujících kombinací objektů nákladů:

- Řádek výrobní zakázky, pracovního nebo strojního centra a položky kapacity.
- Řádek výrobní zakázky, zboží a položka zboží.
- Pouze řádek výrobní zakázky

For more information about how costs from production and assembly are posted to the general ledger, see [Design Details: Inventory Posting](design-details-inventory-posting.md).

## Účtování kapacit
Zaúčtování výstupu z posledního řádku TNG postupu výrobní zakázky má za následek kromě zvýšení zásob také položku kapacity pro koncové zboží.

Položka kapacity je záznam času stráveného k výrobě zboží. Související položka hodnoty popisuje zvýšení hodnoty zásob nedokončené výroby, což je hodnota převodních nákladů. For more information, see “From the Capacity Ledger” in [Design Details: Accounts in the General Ledger](design-details-accounts-in-the-general-ledger.md).

## Náklady výrobní zakázky
K řízení zásob a výrobních nákladů musí výrobní společnost měřit náklady výrobních zakázek, protože předem stanovené standardní náklady na každou vyrobenou položku jsou kapitalizovány v rozvaze. For information about why produced items use the Standard costing method, see [Design Details: Costing Methods](design-details-costing-methods.md).

> [!NOTE]  
> In environments that do not use the Standard costing method, the actual rather than the standard cost of produced items is capitalized on the balance sheet.

Skutečné náklady výrobní zakázky se skládají z následujících nákladových složek:

- Skutečné náklady na materiál
- Skutečné náklady na kapacitu nebo náklady na subdodavatele
- Výrobní režie

Tyto skutečné náklady jsou zaúčtovány do výrobní zakázky a porovnány se standardními náklady pro výpočet odchylek. Odchylky se počítají pro každou složku nákladů na zboží: suroviny, kapacitu, subdodavatele, režijní náklady na kapacitu a výrobní režii. Odchylky lze analyzovat, aby se zjistily problémy, jako je nadměrný odpad při výrobě.

V prostředí se standardními náklady je nákladování výrobní zakázky založeno na následujícím mechanismu:

1. Při zaúčtování poslední operace TNG postupu jsou náklady výrobní zakázky zaúčtovány do položek zboží a nastaveny na očekávané náklady.

   Tyto náklady se rovnají výstupnímu množství, které je zaúčtováno do deníku výstupu vynásobené standardními náklady, které jsou zkopírovány z karty zboží. Náklady jsou považovány za očekávané náklady, dokud není výrobní zakázka dokončena. For more information, see [Design Details: Expected Cost Posting](design-details-expected-cost-posting.md).

   > [!NOTE]  
   > This differs from assembly order posting, which always posts actual costs. For more information, see [Design Details: Assembly Order Posting](design-details-assembly-order-posting.md).
2. When the production order is set to **Finished**, the order is invoiced by running the **Adjust Cost-Item Entries** batch job. V důsledku toho se celkové náklady objednávky počítají na základě standardních nákladů spotřebovaných materiálů a kapacity. Rozdíly mezi vypočtenými standardními náklady a skutečnými výrobními náklady se počítají a zaúčtují.

## Viz také
[Design Details: Inventory Costing](design-details-inventory-costing.md)   
[Design Details: Assembly Order Posting](design-details-assembly-order-posting.md)  
[Managing Inventory Costs](finance-manage-inventory-costs.md)
[Finance](finance.md)  
[Working with Business Central](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]