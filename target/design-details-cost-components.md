---
    title: Design Details - Cost Components | Microsoft Docs
    description: Cost components are different types of costs that make up the value of an inventory increase or decrease.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/08/2021
    ms.author: edupont

---
# Detaily Návrhu: Komponenty nákladů
Komponenty nákladů se skládájí z různých typy nákladů, které tvoří hodnotu zvýšení nebo snížení zásob.

V následující tabulce jsou uvedeny různé komponenty nákladů a všechny podřízené nákladové komponenty, z nichž se skládají.

| Komponenty nákladů | Podřízené komponenty nákladů | Popis |
|--------------------|--------------------------------|---------------------------------------|  
| Přímé náklady | Jednotková cena (přímá nákupní cena) | Náklady, které lze vysledovat k nákladovému objektu. |
| Přímé náklady | Náklady na dopravu (poplatky za zboží) | Náklady, které lze vysledovat k nákladovému objektu. |
| Přímé náklady | Náklady na pojištění (poplatky za zboží) | Náklady, které lze vysledovat k nákladovému objektu. |
| Nepřímé náklady | Náklady, které nelze vysledovat k nákladovému objektu. |
| Odchylka | Odchylka nákupu | The difference between actual and standard costs, which is only posted for items using the **Standard** costing method. |
| Odchylka | Odchylka materiálu | The difference between actual and standard costs, which is only posted for items using the **Standard** costing method. |
| Odchylka | Odchylka kapacity | The difference between actual and standard costs, which is only posted for items using the **Standard** costing method. |
| Odchylka | Subdodavatelská odchylka | The difference between actual and standard costs, which is only posted for items using the **Standard** costing method. |
| Odchylka | Odchylka režijních kapacit | The difference between actual and standard costs, which is only posted for items using the **Standard** costing method. |
| Odchylka | Odchylka režijních nákladů výroby | The difference between actual and standard costs, which is only posted for items using the **Standard** costing method. |
| Přecenění | Odpis nebo zhodnocení aktuální hodnoty zásob. |
| Zaokrouhlení | zbytky způsobené způsobem výpočtu snížení hodnoty zásob. |

> [!NOTE]  
> Freight and insurance costs are item charges that can be added to an item’s cost at any time. When you run the **Adjust Cost - Item Entries** batch job, the value of any related inventory decreases are updated accordingly.

## Viz také
[Design Details: Inventory Costing](design-details-inventory-costing.md)   
[Design Details: Variance](design-details-variance.md)
[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Finance](finance.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]