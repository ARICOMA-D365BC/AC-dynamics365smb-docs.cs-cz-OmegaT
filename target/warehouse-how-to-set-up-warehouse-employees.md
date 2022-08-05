---
title: Set Up Warehouse Employees
description: Each user who performs warehouse activities must be set up as a warehouse employee assigned to one default location and potentially more non-default locations.
author: SorenGP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 7328, 7348
ms.date: 04/01/2021
ms.author: edupont

---
# Nastavení zaměstnanců skladu

Každý uživatel, který provádí aktivity skladu, musí být nastaven jako zaměstnanec skladu a přiřazený k jedné výchozí lokaci, potenciálně více nevýchozím lokacím. Toto uživatelské nastavení filtruje všechny aktivity skladu v databázi do místa zaměstnance, takže zaměstnanec může provádět pouze aktivity skladu ve výchozím umístění. Uživatele lze přiřadit k dalším nevýchozím lokacím, pro které může zaměstnanec zobrazit řádky aktivit, ale neprovádět aktivity.

## Nastavení zaměstnanců skladu

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Employees**, and then choose the related link.
2. Vyberte **Nový** Akce.
3. Select the **User ID** field, and then select the user to be added as a warehouse employee. Choose the **OK** button.
4. In the **Location Code** field, enter the code of the location where the user will be working.
5. Select the **Default** check box to define the location as the only location where the employee can perform warehouse activities.
6. Tyto kroky opakujte pro přiřazení dalších zaměstnanců k umístěním nebo přiřazení jiných než výchozích umístění k existujícím zaměstnancům skladu.

## Viz také

[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)
[Assembly Management](assembly-assemble-items.md)
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]