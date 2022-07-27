---
title: About Unit Cost Calculation
description: Learn how the costing method and other factors influence the Unit Cost field on the Item card.
author: rubenseishima

ms.service: dynamics365-business-central
ms.topic: article
ms.date: 03/06/2022
ms.author: a-reishima
---
# About Unit Cost Calculation

Each item has a unit cost that is calculated based on the company's costing method and other factors. As a rule, with the *Standard* costing method, the **Unit Cost** field value is based on the standard cost for the item. For all other costing methods (*FIFO*, *LIFO*, *Specific*, and *Average*), the unit cost is calculated based on the average unit cost across a period of time.

For more information, see [Managing Inventory Costs](finance-manage-inventory-costs.md).

## When is the unit cost field updated

The chosen costing method influences when the **Unit Cost** field is updated.

When the costing method is set as *Standard*, the **Unit Cost** field is updated whenever the standard cost is changed, and users can't edit the **Unit Cost** field. For more information, see [Updating Standard Costs](finance-how-to-update-standard-costs.md).

If the costing method is *FIFO*, *LIFO*, *Specific*, or *Average*, then the **Unit Cost** is updated in the following cases:

* When the item is cost-adjusted, automatically or by an [Adjust Cost](inventory-how-adjust-item-costs.md#to-adjust-item-costs-manually) task.
* During the posting of purchase invoices, output, or positive adjustment if one of the following conditions is true:
   * The net invoiced quantity of the item changes from negative or zero to positive.
   * The current unit cost is zero.

If one of these conditions is true, then the **Unit Cost** field is updated with the value in the **Last Direct Cost** field on the item card.

> [!NOTE]
> The **Unit Cost** field is not updated if the current unit cost is higher than zero and the new unit cost is zero. A unit cost of zero is considered an exception from regular business. Therefore, the current unit cost is retained to provide the last known, relevant value. This exception applies even if the existing inventory has been revalued to zero.

In the **Unit Cost** field on the item card, you can drill down to view the history of transactions that the average cost of units on hand is calculated from in the **Average Cost Calc. Overview** window.

## Unit cost calculation for purchases

When you purchase items, the value in the **Last Direct Cost** field on the item card is copied to the **Direct Unit Cost** field on a purchase line or to the **Unit Amount** line on an item journal line.

To, co vyberete v poli **Metoda ocenění**, ovlivňuje jak [!INCLUDE[prod_short](includes/prod_short.md)] vypočítá obsah pole **Pořizovací cena** na řádcích.

### Costing method FIFO, LIFO, Specific, or Average

[!INCLUDE[prod_short](includes/prod_short.md)] vypočítá obsah pole **Pořizovací cena (LM)** na nákupním řádku nebo obsah pole **Pořizovací cena** na řádku deníku zboží podle následujícího vzorce:

*Unit Cost (LCY) = (Direct Unit Cost – (Discount Amount / Quantity)) x (1 + Indirect Cost % / 100) + Overhead Rate*

### Costing method Standard

Pole **Pořizovací cena (LM)** na nákupním řádku nebo pole **Pořizovací ceny** je vyplněno na řádku deníku zboží zkopírováním hodnoty do pole **Pořizovací ceny** na kartě zboží. By using costing method set as *Standard*, this value is always based on the standard cost.

When you post the purchase, [!INCLUDE[prod_short](includes/prod_short.md)] uses the unit cost from the purchase line or item journal line to the purchase item invoice entry. You can see it on the entry list for the item.

### All costing methods

Pořizovací cena z řádku zdrojového dokladu se používá k výpočtu obsahu pole **Částka nákladů (skutečná)** nebo případně pole **Částka nákladů (očekávaná)**, která se vztahuje k této položce zboží, bez ohledu na způsob ocenění zboží.

## Unit cost calculation for sales

When you sell items, the unit cost is copied from the **Unit Cost** field on the item card to the sales line or the item journal line.

Když zaúčtujete, pořizovací cena z řádku nákupu nebo řádku deníku zboží se zkopíruje do položky nákupní faktury za zboží a lze ji zobrazit v seznamu položek zboží. [!INCLUDE[prod_short](includes/prod_short.md)] používá Pořizovací cenu z řádku zdrojového dokladu k výpočtu obsahu pole **Částka nákladů (skutečná)** nebo případně pole **Částka nákladů (očekávaná)** v položce ocenění vztahující se k této položce zboží.

## Viz také

[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Registering New Items](inventory-how-register-new-items.md)  
[About Inventory Costing](finance-learn-about-costing.md)  
[Inventory](inventory-manage-inventory.md)  
[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Setup Best Practices: Costing Method](setup-best-practices-costing-method.md)  
[Design Details: Costing Methods](design-details-costing-methods.md)  
[Design Details: Cost Adjustment](design-details-cost-adjustment.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]