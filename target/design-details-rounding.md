---
    title: Design Details - Rounding
    description: Rounding residuals can occur when you value the cost of an inventory decrease measured in a different quantity than the corresponding inventory increase.
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
# Detaily návrhu: Zaokrouhlení
K zaokrouhlení zbytků může dojít, když oceníte náklady na snížení zásob, které se měří v jiném množství než odpovídající zvýšení zásob. Rounding residuals are calculated for all costing methods when you run the **Adjust Cost - Item Entries** batch job.

Použijete-li metodu průměrných nákladů, zaokrouhlení se vypočítá a zaznamená na kumulativním základě položky.

Když použijete jinou metodu kalkulace než Průměr, zbytkové zaokrouhlování se vypočítá, když se zvýšení zásob plně vyrovná, tedy když se zbývající množství pro zvýšení zásob rovná nule. Poté se vytvoří samostatná položka pro zbytkové zaokrouhlování a datum zaúčtování u tohoto zaokrouhlovacího záznamu je datem zaúčtování posledního záznamu fakturované hodnoty zvýšení zásob.

## Příklad
Následující příklad ukazuje, jak jsou zpracovány různé zbytky zaokrouhlení pro metodu průměrného výpočtu nákladů a  metodu neprůměrných nákladů. In both cases, the **Adjust Cost - Item Entries** batch job has been run.

V následující tabulce jsou uvedeny položky zboží, na kterých je příklad založen.

| Zúčtovací datum | Množství | Číslo položky |
|------------------|--------------|---------------|  
| 01.01.20 | 3 | 1 |
| 01.02.20 | -1 | 2 |
| 01.03.20 | -1 | 3 |
| 01.04.20 | -1 | 4 |

U položky používající metodu průměrných nákladů se zaokrouhlení zbytku (1/300) vypočítá s prvním snížením (číslo položky 2) a přenese se do položky číslo 3. Proto má položka číslo 3 hodnotu –3,34.

Následující tabulka ukazuje výsledné hodnoty.

| Zúčtovací datum | Množství | Částka nákladů (skutečná) | Číslo položky zboží | Číslo položky |
|------------------|--------------|----------------------------|---------------------------|---------------|  
| 01.01.20 | 3 | 10 | 1 | 1 |
| 01.02.20 | -1 | -3.33 | 2 | 2 |
| 01.03.20 | -1 | -3.34 | 3 | 3 |
| 01.04.20 | -1 | -3.33 | 4 | 4 |

U zboží, které používá jinou metodu ocenění než Průměr, se zaokrouhlení zbytkové hodnoty (0,01) vypočítá, pokud je zbývající množství pro zvýšení zásob nulové. Zbytek zaokrouhlování má samostatný záznam (číslo 5).

Následující tabulka ukazuje výsledné hodnoty.

| Zúčtovací datum | Množství | Částka nákladů (skutečná) | Číslo položky zboží | Číslo položky |
|------------------|--------------|----------------------------|---------------------------|---------------|  
| 01.01.20 | 3 | 10 | 1 | 1 |
| 01.02.20 | -1 | -3.33 | 2 | 2 |
| 01.03.20 | -1 | -3.33 | 3 | 3 |
| 01.04.20 | -1 | -3.33 | 4 | 4 |
| 01.01.20 | 0 | -0.01 | 1 | 5 |

## Viz také
[Design Details: Inventory Costing](design-details-inventory-costing.md)   
[Design Details: Cost Adjustment](design-details-cost-adjustment.md)   
[Design Details: Costing Methods](design-details-costing-methods.md)
[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Finance](finance.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]