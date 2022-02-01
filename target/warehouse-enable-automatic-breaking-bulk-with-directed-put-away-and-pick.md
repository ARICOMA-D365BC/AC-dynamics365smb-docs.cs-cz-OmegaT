---
    title: Breaking Bulk with Directed Put-away and Pick
    description: Learn how to enable automatic breaking bulk with directed put-away and pick, as well as breakbulking in picks, putaways, movements, and more.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/25/2021
    ms.author: edupont

---
# Povolení automatického rozdělení zboží s řízeným zaskladněním a vyskladněním
For locations that use directed put-away and pick, [!INCLUDE[prod_short](includes/prod_short.md)] can, in various situations, automatically breakbulk, that is, break a larger unit of measure into smaller units of measure, when it creates warehouse instructions that fulfill the needs of source documents, production orders, or internal picks and put-aways. Rozbalení také znamená shromáždění menších měrných jednotek, je-li to nutné, k uspokojení odchozích požadavků, a to tak, že se větší měrná jednotka ve zdrojovém dokladu nebo výrobní zakázce rozdělí na menší měrné jednotky, které jsou ve skladu k dispozici.

## Rozbalení ve vyskladnění
If you want to store items in several different units of measure and allow them to be automatically combined as needed in the picking process, select the **Allow Breakbulk** field on the location card.

To fulfill a task, application automatically looks for an item in the same unit of measure. But if it cannot find this form of the item, and this field is selected, application will suggest that you break a larger unit of measure into the unit of measure that is needed.

Pokud systém může najít pouze menší měrné jednotky, navrhne vám, abyste shromáždili zboží ke splnění množství v dodávce nebo výrobní zakázce. Ve skutečnosti rozdělí větší měrnou jednotku zdrojového dokumentu na menší jednotky pro výdej.

## Rozbalení v zaskladnění
In the warehouse put-away, application automatically suggests Place action lines in the put-away unit of measure, for example, pieces, even though the items arrive in a different unit of measure.

## Rozbalení v přesunech
The application also breakbulks automatically in replenishment movements, if the **Allow Breakbulk** field is selected on the **Option** FastTab on the **Calculate Bin Replenishment** page.

Výsledky procesu převodu lze zobrazit z jedné měrné jednotky do jiné jako přechodné řádky rozbalení v pokynech pro zaskladnění, vyskladnění nebo přesun.

> [!NOTE]  
> If you select the **Set Breakbulk Filter** field on the warehouse instruction header, application will hide the breakbulk lines whenever the larger unit of measure is going to be completely used. Pokud je například je na paletě 12 kusů a vy použijete všech 12 kusů, vyskladnění bude brát jednu paletu a umístí 12 kusů. However, if you have to pick only 9 pieces, then the breakbulk lines will not be hidden, even if you have selected the **Breakbulk Filter** field, because you have to place the remaining three pieces somewhere in the warehouse.

> [!NOTE]  
> If you want your units of measure to perform optimally in the warehouse, also in connection with the breakbulk functionality, you should wherever possible try to:
>
> - Nastavte základní měrnou jednotku pro zboží jako nejmenší měrnou jednotku, kterou očekáváte ve vašich skladových procesech.
> - Nastavte alternativní měrné jednotky pro zboží jako násobky základní měrné jednotky.

## Viz také
[Správa skladu](warehouse-manage-warehouse.md)    
[Zásoby](inventory-manage-inventory.md)    
[Nastavení správy skladu](warehouse-setup-warehouse.md)       
[Správa montáže](assembly-assemble-items.md)      
[Detaily návrhu: Správa skladu](design-details-warehouse-management.md)    
[Práce s [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]