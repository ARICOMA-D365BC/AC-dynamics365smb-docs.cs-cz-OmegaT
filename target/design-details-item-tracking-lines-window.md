---
    title: Design Details - Item Tracking Lines Page
    description: Read about how to manage the flow of serial and lot numbers in your inventory using the Item Tracking Lines page.
    author: SorenGP

    
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: design, inventory, item, tracking, serial number, lot number
    ms.date: 06/15/2021
    ms.author: edupont

---
# Detaily návrhu: Stránka Řádky sledování zboží
Záznamy sledování zboží a záznamy rezervací jsou vytvářeny v rezervačním systému a jejich dostupnost se vypočítává dynamicky. Data that is entered on the **Item Tracking Lines** page is managed in a temporary version of the **Tracking Specification** table. When the page is closed, the active data is committed to the **Reservation Entry** table and the historic data is committed to the **Tracking Specification** table. For more information, see [Design Details: Active versus Historic Item Tracking Entries](design-details-active-versus-historic-item-tracking-entries.md).

Lookups from the **Serial No.** and **Lot No.** fields show availability based on both the **Item Ledger Entry** table and the **Reservation Entry** table, with no date filter. The matrix of quantity fields on the header of the **Item Tracking Lines** page dynamically displays the quantities and sums of item tracking numbers that are being entered on the lines of the page. The quantities must correspond to those of the document line, which is indicated by **0** in the **Undefined** fields in the header of the page.

To coordinate the flow of serial and lot numbers through inventory, the following rules exist for entering data on the **Item Tracking Lines** page:

* For both inbound and outbound item tracking lines, you cannot enter a serial number, with or without a lot number, more than once in the same instance of the **Item Tracking Lines** page. Pokud se pokusíte zadat libovolnou kombinaci sériových čísel nebo čísel šarží, která jsou již na stránce, chybová hláška zablokuje zadávání dat.
* Pro vstupní řádky sledování zboží, nelze zaúčtovat související doklad, pokud je zboží stejné varianty a se stejným sériovým číslem již na skladě. Pokud se pokusíte zaúčtovat kladný řádek pro skladové zboží se stejnou variantou a sériovým číslem, chybová hláška zablokuje účtování. However, for both inbound and outbound item tracking lines on open documents, you can have the same combination of serial or lot numbers that relate to different source document lines, that is, existing in different instances of the **Item Tracking Lines** page until the related document is posted.
* Pokud je zboží nastaveno pro sledování specifického sériového čísla nebo sledování specifického číslo šarže, nelze zaúčtovat řádek výstupního dokladu, pokud ve skladu neexistuje zboží s definovaným sériovým číslem nebo číslem šarže. Pokud se pokusíte zaúčtovat řádek výstupního dokladu se zbožím se sériovým číslem nebo číslem šarže, které není ve skladu, chybová zpráva zablokuje účtování.

The rules for entering data on the **Item Tracking Lines** page also support the coupling principles that govern order tracking, planning, and reservation. For more information, see [Design Details: Item Tracking and Planning](design-details-item-tracking-and-planning.md).

## Viz také
[Detaily návrhu: Sledování zboží](design-details-item-tracking.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]