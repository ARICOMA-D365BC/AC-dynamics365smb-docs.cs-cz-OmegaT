---
    title: Design Details - Item Tracking in the Warehouse
    description: Inbound and outbound warehouse documents have standard functionality for assigning and selecting item tracking numbers.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: design, item, tracking, serial number, lot number, outbound documents
    ms.date: 06/15/2021
    ms.author: edupont

---
# Detaily návrhu: Sledování zboží ve skladu
Zpracování sériových čísel a čísel šarží je především úlohou skladu a proto mají všechny vstupní a výstupní skladové doklady standardní funkce pro přiřazování a výběr čísel sledování zboží.

Protože je však rezervační systém založen na položkách zboží, doklady aktivit skladu, které evidují pouze položky skladu, nejsou plně podporovány. Because reservations and item tracking numbers can be handled only at the location level, not at the bin and zone level, the **Item Tracking Lines** page cannot be opened from warehouse activity documents. The same applies to the **Reservation** page.

Poté, co bylo ke zboží ve skladu přidáno sériové číslo nebo číslo šarže, lze ji volně přesunout a přeradit ve skladu pomocí nezávislé struktury sledování položky, která nesouvisí s rezervačním systémem. **Serial No.** and **Lot No.** fields are accessed directly on warehouse document lines. Když je sériové číslo nebo číslo šarže později účtováno, je synchronizováno s rezervačním systémem jako součást běžné úpravy přihrádky For more information, see [Design Details: Integration with Inventory](design-details-integration-with-inventory.md).

Rezervační systém však při výpočtu dostupnosti bere v úvahu aktivity skladu. Například zboží, které je přiděleno vyskladnění nebo zapsané, tedy vyskladněné, nelze rezervovat. For more information, see [Design Details: Warehouse Availability](design-details-availability-in-the-warehouse.md).

## Viz také
[Design Details: Item Tracking](design-details-item-tracking.md)  
[Design Details: Integration with Inventory](design-details-integration-with-inventory.md)  
[Design Details: Warehouse Availability](design-details-availability-in-the-warehouse.md)  
[Design Details: Item Tracking Design](design-details-item-tracking-design.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]