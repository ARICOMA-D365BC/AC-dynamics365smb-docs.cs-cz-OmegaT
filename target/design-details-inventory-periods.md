---
    title: Design Details - Inventory Periods
    description: Inventory Periods helps avoid problems with balances and stock valuations by opening or closing inventory periods to limit posting in a set period of time.
    author: SorenGP

    
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/15/2021
    ms.author: edupont

---
# Detaily návrhu: Inventory Periods
Zpětné transakce nebo úpravy nákladů často ovlivňují zůstatky a ocenění zásob za účetní období, která lze považovat za uzavřená. To může nepříznivě ovlivnit jinak přesné vykazování, zejména v rámci globálních korporací. Funkci Období zásob lze použít k zabránění těmto problémům otevřením nebo uzavřením skladových období, aby se omezilo účtování v nastaveném časovém období.

Skladové období je časové období definované koncovým datem, ve kterém účtujete skladové transakce. Když uzavřete skladové období, nelze v uzavřeném období zaúčtovat žádné změny hodnoty. To zahrnuje účtování nové hodnoty, očekávané nebo fakturované účtování, změny existujících hodnot a úpravy nákladů. Stále však můžete vyrovnat otevřenou položku zboží, která spadá do uzavřeného období. Pro více informací navštivte [Detaily návrhu: Vyrovnání zboží](design-details-item-application.md).

Chcete-li zajistit, aby všechny položky transakcí v uzavřeném období byly konečné, musí být před uzavřením skladového období splněny následující podmínky:

- Všechny výstupní položky zboží v období musí být uzavřeny (bez záporných zásob).
- Všechny položky zboží v období musí být adjustovány.
- Všechny vydané a dokončené výrobní zakázky v období musí adjstované náklady.

Když uzavřete skladové období, vytvoří se položka skladového období pomocí čísla poslední položky žurnálu zboží, který spadá do období inventury. Čas, datum a kód uživatele, který období uzavírá, se navíc zaznamenává do položky období zásob. Pomocí těchto informací s poslední položkou žurnálu zboží za předchozí období můžete zjistit, které skladové transakce byly zaúčtovány v období zásob. Je také možné znovu otevřít období zásob, pokud potřebujete zaúčtovat v uzavřeném období. Při opětovném otevření období zásob je vytvořena položka období zásob.

## Viz také

[Design Details: Inventory Costing](design-details-inventory-costing.md)  
[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Finance](finance.md)  
[Working with Business Central](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]