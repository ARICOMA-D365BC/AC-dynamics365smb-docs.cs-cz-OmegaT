---
    title: Design Details - Item Tracking Posting Structure
    description: Learn how to use item ledger entries as the primary carrier of item tracking numbers in the Item Tracking Posting Structure.
    author: SorenGP


    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: design, item tracking, posting, inventory
    ms.date: 06/15/2021
    ms.author: edupont

---
# Detaily návrhu: Struktura účtování sledování zboží
Pro sladění s funkcemi kalkulace zásob a pro získání jednoduššího a robustnějšího řešení se jako hlavní nosič používají položky sledování zboží k přenášení informací o číslech sledování zboží.

Item tracking numbers on order network entities and non-order network entities are specified in the **Reservation Entry** table (T337). Čísla sledování zboží, která souvisejí s historickými informacemi, jsou načtena přímo z položek zboží, které souvisejí s danou transakcí. To znamená, že položky zboží odrážejí specifikaci sledování zboží zaúčtovaného řádku objednávky.

The **Item Tracking Lines** page retrieves the information from T337 and the item ledger entries and shows it through the temporary table, **Tracking Specification** (T336). T336 also hold the temporary data in the **Item Tracking Lines page** for item tracking quantities that remain to be invoiced.

## Vztah 1:M
The **Item Entry Relation** table, which is used to link a posted document line with its related item ledger entries, consists of two main parts:

* A pointer to the posted document line, the **Order Line No.** field.
* An entry number pointing to an item ledger entry, the **Item Entry No.** field.

The functionality of the existing **Entry No.** field, which relates an item ledger entry to a posted document line, handles the typical one-to-one relation when no item tracking numbers exist on the posted document line. If item tracking numbers exist, then the **Entry No.** field is left blank, and the one-to-many relation is handled by the **Item Entry Relation** table. If the posted document line carries item tracking numbers but only relates to a single item ledger entry, then the **Entry No.** field handles the relation, and the no record is created in the **Item Entry Relation** table.

## Codeunity 80 a 90
Chcete-li rozdělit položky zboží během účtování, kód v codeunitě 80 a 90, obsahuje smyčky, které prochází globálními dočasnými proměnnými záznamu. Tento kód volá codeunitu 22 s řádkem deníku zboží. Tyto proměnné jsou inicializovány, pokud pro řádek dokladu existují čísla sledování zboží. Aby byl kód jednoduchý, vždy se používá tato struktura opakování. Pokud pro řádek dokladu neexistují žádná čísla sledování zboží, vloží se jeden záznam a smyčka se spustí pouze jednou.

## Účtování deníku zboží
Čísla sledování zboží jsou převedeny prostřednictvím položek rezervace, které se vztahují k položce zboží a opakování prostřednictvím čísel sledování zboží pomocí codeunity 22. Tento koncept funguje stejným způsobem, když se řádek deníku zboží používá nepřímo k zaúčtování prodejní nebo nákupní objednávky, jako když je řádek deníku zboží použit přímo. When the item journal is used directly, the **Source Row ID** field points to the item journal line itself.

## Code unita 22
Codeunity 80 a 90 opakují volání procedury 22 během zaúčtování čísel sledování zboží faktry a při fakturaci existujicích dodávek nebo příjemek.

Během účtování množství čísel sledování zboží načte Codeunita 22 čísla sledování zboží z položek v T337, které se vztahují k účtování. Tyto položky jsou umístěny přímo na řádku deníku zboží.

Codeunit 22 prochází čísly sledování zboží a rozdělí účtování na příslušné položky zboží, které nesou čísla sledování zboží. Informace o tom, které položky zboží jsou vytvořeny, jsou vráceny do  tabulky T337 pomocí dočasného záznamu v tabulce T336, které jsou volány procedurou codeunitě 22. Tento postup se spustí, když codeunita 22 dokončí jeho spuštění, protože v tomto okamžiku codeunita 22 obsahuje informace. When the temporary T336 record is retrieved, codeunits 80 and 90 create records in the **Item Entry Relation** table to link the created item ledger entries to the created shipment or receipt line. Codeunita 80 nebo 90 pak převede dočasné záznamy v T336 na skutečné záznamy v T336, které souvisejí s daným řádkem. K tomuto převodu však dochází, pouze pokud není odstraněn řádek zaúčtovaného dokladu, protože je zaúčtován pouze částečně.

## Viz také
[Design Details: Item Tracking](design-details-item-tracking.md)   
[Design Details: Item Tracking Design](design-details-item-tracking-design.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]