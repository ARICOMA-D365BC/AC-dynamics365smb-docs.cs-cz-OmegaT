---
    title: How to Enable Picking by FEFO | Microsoft Docs
    description: First-Expired-First-Out (FEFO) is a sorting method that ensures that the oldest items, those with the earliest expiration dates, are picked first.
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
# Povolení vyskladnění pomocí FEFO
First-Expired-First-Out (FEFO - První expiruje, první ven) je metoda třídění, která zajišťuje, že se nejdříve vyberou nejstarší položky, které mají nejstarší data vypršení platnosti.

Tato funkce funguje, pouze pokud jsou splněna následující kritéria:

- Zboží musí mít sériové číslo/číslo šarže.
- On the item’s item tracking code setup, the **SN Warehouse Tracking** field or the **Lot Warehouse Tracking** field must be selected.
- Zboží musí být zaúčtováno do skladu s datem expirace.
- On the location, the **Require Pick**, **Pick According to FEFO**, and **Bin Mandatory** toggles must be turned on.

Když jsou splněna všechna kritéria, jsou položky, které mají sériové číslo nebo šarži řazeny od nejstarších ve všech vyskladněních a přesunech zboží,  s výjimkou zboží, které používají sledování specifické pro SN nebo šarže.

> [!NOTE]  
> If some serial or lot-numbered items use specific tracking, then those are respected first and under them, the remaining, non-specific, serial/lot numbers are listed according to FEFO.
> <br /><br />
> If two serial or lot-numbered items have the same expiration date, then the application selects the item with the lowest serial or lot number.
> <br /><br />
> When picking serial or lot-numbered items in locations set up for directed put-away and pick, only quantities on bins of type *Pick* are picked according to FEFO.  
> <br /><br />
> To enable movements according to FEFO, leave the **From Bin** field empty on the **Inventory Movement** page or the **Movement Worksheet** pages.  
> <br /><br />
> If the **Strict Expiration Posting** field is selected on the **Item Tracking Code Card**, only items that are not expired will be included in the pick, and the lines are sorted according to the FEFO principle.

## Viz také
[Picking Items](warehouse-pick-items.md)   
[Pick Items for Warehouse Shipment](warehouse-how-to-pick-items-for-warehouse-shipment.md)   
[Pick Items with Inventory Picks](warehouse-how-to-pick-items-with-inventory-picks.md)   
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Inventory](inventory-manage-inventory.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]