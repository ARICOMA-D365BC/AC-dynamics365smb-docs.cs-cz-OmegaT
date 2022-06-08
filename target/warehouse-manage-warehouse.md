---
title: Manage Warehouse Activities
description: After goods are received and before goods are shipped, a series of internal warehouse activities take place to ensure an effective flow through the warehouse.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 5774, 5776, 5777, 5785, 5793, 5797, 7318, 7364, 7401, 8909, 9000, 9008, 9009, 9050, 9053, 9056
ms.date: 06/25/2021
ms.author: edupont

---
# Warehouse Management

After goods are received and before goods are shipped, a series of internal warehouse activities take place to ensure an effective flow through the warehouse and to organize and maintain company inventories.

Typical warehouse activities include putting items away, moving items inside or between warehouses, and picking items for assembly, production, or shipment. Assembling items for sale or inventory may also be considered warehouse activities, but these are covered elsewhere. Pro více informací navštivte [Správa montáže](assembly-assemble-items.md).

In large warehouses, these different handling tasks can be separated by departments and the integration managed by a directed workflow. In simpler installations, the flow is less formalized and the warehouse activities are performed with so-called inventory put-aways and inventory picks. For more information about basic versus advanced warehouse configurations, see [Design Details: Warehouse Overview](design-details-warehouse-overview.md).

Before you can perform warehouse activities, you must set the system up for the relevant complexity of warehouse processing. Pro více informací navštivte [Nastavení správy skladu](warehouse-setup-warehouse.md).

Úkoly inventury, úpravy a přeřazení zboží související se skladem mohou zahrnovat skladové úkoly, které musí být provedeny u položek skladu před jejich synchronizací se souvisejícími položkami zboží. For more information, see [Count, Adjust, and Reclassify Inventory](inventory-how-count-adjust-reclassify.md).

Následující tabulka popisuje sekvenci úloh s odkazy na témata, které je popisují.

| **Viz** | **také** |
|------------|-------------|  
| Record the receipt (including over-receipt) of items at warehouse locations, either with a purchase order only, in simple location setups, or with a warehouse receipt, in case of semi or fully automated warehouse processing at the location. | [Příjem zboží](warehouse-how-receive-items.md) |
| Bypass the put-away and pick processes to expedite an item straight from receiving or production to shipping. | [Cross-Dock Items](warehouse-how-to-cross-dock-items.md) |
| Put away items received from purchases, sales returns, transfers, or production output according to the configured warehouse process. | [Putting Items Away](warehouse-put-away-items.md) |
| Move items between bins in the warehouse. | [Moving Items](warehouse-move-items.md) |
| Pick items to be shipped, transferred, or consumed in assembly or production, according to the configured warehouse process. | [Picking Items](warehouse-pick-items.md) |
| Record the shipment of items from warehouse locations, either with a sales order only, in simple location setups, or with a warehouse shipment, in case of semi or fully automated warehouse processes at the location. | [Dodání zboží](warehouse-how-ship-items.md) |

## Viz také

[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)
[Assembly Management](assembly-assemble-items.md)
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

## [!INCLUDE[prod_short](includes/free_trial_md.md)]


[!INCLUDE[footer-include](includes/footer-banner.md)]