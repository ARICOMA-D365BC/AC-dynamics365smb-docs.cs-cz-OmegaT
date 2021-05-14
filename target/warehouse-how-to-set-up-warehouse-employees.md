---
    title: How to Set Up Warehouse Employees | Microsoft Docs
    description: Each user who performs warehouse activities must be set up as a warehouse employee assigned to one default location and potentially more non-default locations.
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
# Nastavení zaměstnanců skladu
Každý uživatel, který provádí aktivity skladu, musí být nastaven jako zaměstnanec skladu a přiřazený k jedné výchozí lokaci, potenciálně více nevýchozím lokacím. Toto uživatelské nastavení filtruje všechny aktivity skladu v databázi do místa zaměstnance, takže zaměstnanec může provádět pouze aktivity skladu ve výchozím umístění. Uživatele lze přiřadit k dalším nevýchozím lokacím, pro které může zaměstnanec zobrazit řádky aktivit, ale neprovádět aktivity.

## Nastavení zaměstnanců skladu
1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Zaměstnanci skladu** a poté vyberte související odkaz.
2. Vyberte akci **Nový**.
3. Select the **User ID** field, and then select the user to be added as a warehouse employee. Choose the **OK** button.
6. In the **Location Code** field, enter the code of the location where the user will be working.
7. Select the **Default** check box to define the location as the only location where the employee can perform warehouse activities.
8. Tyto kroky opakujte pro přiřazení dalších zaměstnanců k umístěním nebo přiřazení jiných než výchozích umístění k existujícím zaměstnancům skladu.

## Viz také
[Správa skladu](warehouse-manage-warehouse.md)    
[Zásoby](inventory-manage-inventory.md)    
[Nastavení správy skladu](warehouse-setup-warehouse.md)       
[Správa montáže](assembly-assemble-items.md)      
[Detaily návrhu: Správa skladu](design-details-warehouse-management.md)    
[Práce s [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]