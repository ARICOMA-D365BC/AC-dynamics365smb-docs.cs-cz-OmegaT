---
    title: Design Details - Item Tracking Availability
    description: The Item Tracking Lines and Item Tracking Summary pages provide dynamic availability information for serial or lot numbers, increasing transparency for users.
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
# Detaily návrhu: Dostupnost sledování zboží
The **Item Tracking Lines** and **Item Tracking Summary** pages provide dynamic availability information for serial or lot numbers. Účelem je zvýšit transparentnost pro uživatele na odchozích dokladech, jako jsou prodejní objednávky, tím, že jim ukážete, která sériová čísla nebo kolik jednotek čísel šarže je aktuálně přiřazeno na jiných otevřených dokladech. To snižuje nejistotu způsobenou dvojitým přidělením a dává zpracovatelům objednávek důvěru, že sledování zboží a data, která slibují na nezaúčtovaných prodejních objednávkách, mohou být splněny. For more information, see [Design Details: Item Tracking Lines Page](design-details-item-tracking-lines-window.md).

When you open the **Item Tracking Lines** page, availability data is retrieved from the **Item Ledger Entry** table and the **Reservation Entry** table, with no date filter. When you choose the **Serial No.** field or the **Lot No.** field, the **Item Tracking Summary** page opens and shows a summary of the item tracking information in the **Reservation Entry** table. Souhrn obsahuje následující informace o každém sériovém čísle nebo čísle šarže na řádku sledování zboží:

| Pole | Popis |
|---------------------------------|---------------------------------------|  
| **Total Quantity** | Celkové množství sériových čísel nebo čísla šarže, které jsou aktuálně na skladě. |
| **Total Requested Quantity** | Celkové množství sériových čísel nebo čísla šarže, které jsou aktuálně požadovány ve všech dokladech. |
| **Current Pending Quantity** | The quantity that is entered in the current instance of the **Item Tracking Lines** page but is not yet committed to the database. |
| **Total Available Quantity** | Množství sériových čísel nebo čísel šarží, které má uživatel k dispozici.<br /><br /> Toto množství se počítá z ostatních polí na stránce následujícím způsobem:<br /><br /> Celkové množství – (Celkové požadované množství + Aktuální množství ke zpracování). |

> [!NOTE]  
> You can also see the information in the preceding table by using the **Select Entries** function on the **Item Tracking Lines** page.

To preserve database performance, availability data is only retrieved once from the database when you open the **Item Tracking Lines** page and when you use the **Refresh Availability** function on the page.

## Vzorec výpočtu
Jak je popsáno v předchozí tabulce, dostupnost daného sériového čísla nebo čísla šarže se počítá následujícím způsobem.

Celkové množství k dispozici = Množství ve skladu  – (všechny požadavky + množství dosud nezapsáno v databázi)

> [!IMPORTANT]  
> This formula implies that the serial or lot number availability calculation considers only inventory and ignores projected receipts. Proto dodávka, která ještě není zaúčtována do zásob, nemá vliv na dostupnost sledování zboží, na rozdíl od běžné dostupnosti zboží, kde jsou zahrnuty předpokládané příjmy.

## Viz také
[Detaily návrhu: Sledování zboží](design-details-item-tracking.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]