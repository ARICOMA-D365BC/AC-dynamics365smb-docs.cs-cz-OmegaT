---
title: Assign Default Bins to Items
description: If you are using bins at a location, assigning default bins to your items can make the process of shipping, receiving, and moving your items much easier.
author: SorenGP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.search.form: 7371, 7374, 7379
ms.date: 06/25/2021
ms.author: edupont

---
# Přiřazení výchozí přihrádky ke zboží
Pokud používáte přihrádky v lokaci, přiřazení výchozích přihrádek k vašemu zboží může proces expedice, příjmu a přesunu podstatně zjednodušit. Pokud je ke zboží přiřazena výchozí přihrádka, je tato přihrádka navržena pokaždé, když zahájíte transakci pro toto zboží. Default bins are defined on the **Bin Content** page.

## Přiřazení výchozí přihrádky ke zboží
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bin Content Creation Worksheet**, and choose the related link.
2. Vyplňte kód přihrádky a informace o zboží pro každou přihrádku, kterou chcete nastavit pro zboží jako výchozí. Make sure to select the **Default** field.
3. Choose the **Create Bin Content** action. Pro zboží jsou nyní přiřazeny výchozí přihrádky.

> [!NOTE]  
> When an item is put away, if the item does not have a default bin assigned, the bin where the item is put away is assigned as the default.

## Změna výchozí přihrádky zboží
Pravděpodobně bude nutné změnit přiřazení výchozí přihrádky pro zboží nebo přiřadit výchozí přihrádku novému zboží.
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bin Contents**, and then choose the related link.
2. In the **Location Filter** field, select the appropriate location code.
3. Find the current default bin content entry for the item and clear the **Default Bin** check box.
4. Najděte řádek s obsahem přihrádky, pro který chcete novou výchozí přihrádku. Select the **Default Bin** check box.

> [!NOTE]  
> When an item is put away for the first time, and the item does not have a default bin assigned, the system will assign the bin where the item is put away as the default bin for the item.

## Viz také
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)
[Assembly Management](assembly-assemble-items.md)
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]