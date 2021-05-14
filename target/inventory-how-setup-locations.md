---
title: Set Up a Location Card and Define Transfer Routes| Microsoft Docs
description: You create a location card for each place you store inventory items, for example, a warehouse or distribution center, and set up routes to transfer items between locations.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: warehouse, distribution center
ms.date: 04/01/2021
ms.author: edupont

---
# Set Up Locations
If you buy, store, or sell items at more than one place or warehouse, you must set each location up with a location card and define transfer routes.

You can then create document lines for a specific location, view availability by location, and transfer inventory between locations. For more information, see [Manage Inventory](inventory-manage-inventory.md).
<br><br>

> [!Video https://www.microsoft.com/videoplayer/embed/RE4aQvq?rel=0]

## To create a location card
1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Lokace** a poté vyberte související odkaz.
2. Vyberte akci **Nový**.
3. On the **Location Card** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Repeat steps 2 and 3 for every location where you want to keep inventory.

> [!NOTE]  
> Many fields on the location card refer to the handling of items in inbound and outbound warehouse processes. For more information, see [Setting Up Warehouse Management](warehouse-setup-warehouse.md).

## To create a transfer route
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transfer Routes**, and then choose the related link.
2. Alternatively, from any **Location Card** page, choose the **Transfer Routes** action.
3. Vyberte akci **Nový**.
4. On the **Location Card** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

You can now transfer inventory items between two locations. Pro více informací navštivte [Převádění zásob mezi lokacemi](inventory-how-transfer-between-locations.md).

## Viz také
[Manage Inventory](inventory-manage-inventory.md)  
[Transfer Inventory Between Locations](inventory-how-transfer-between-locations.md)    
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[General Business Functionality](ui-across-business-areas.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]