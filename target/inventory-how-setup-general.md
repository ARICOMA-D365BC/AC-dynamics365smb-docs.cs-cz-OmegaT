---
title: Define the General Inventory Setup
description: Describes how to define the general inventory setup so that you can manage your warehouse and stock.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: warehouse, stock
ms.date: 04/01/2021
ms.author: edupont

---
# Nastavení obecných informací o zásobách

Obecné nastavení zásob nastavíte na stránce **Nastavení zásob**.

## Nastavení obecných informací o zásobách

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Nastavení zásob** a poté vyberte související odkaz.
2. Na stránce **Nastavení zásob** vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

Pro podrobné informace o polích ocenění, **Automatické účtování nákladů**, **Účtování oček.nákladů do fin.** a **Výchozí metoda ocenění** navštivte [Odsouhlasení nákladů na zboží s financemi](finance-how-to-post-inventory-costs-to-the-general-ledger.md), [Detaily návrhu: Ocenění zásob](design-details-inventory-costing.md) a [Detaily návrhu: Účtování očekávaných nákladů](design-details-expected-cost-posting.md). Pro více informací navštivte [Správa nákladů zásob](finance-manage-inventory-costs.md).

Pokud chcete zahrnout dobu zpracování ve skladu do kalkulace nadějné zakázky na nákupní řádek, můžete jej nastavit jako výchozí pro zásoby, na stránce **Nastavení zásob** a pro vaši lokaci. Pro více informací navštivte [Výpočet data přislíbení objednávky](sales-how-to-calculate-order-promising-dates.md).

> [!NOTE]
> The **Automatic Cost Adjustment** toggle is turned on by default to ensure that inventory values are always correct in the general ledger, which in turn keeps your sales and profit statistics up to date. Změny nákladů z příchozích položek, například pro nákupy nebo výstup výroby, jsou přiřazeny k souvisejícím výstupním položkám, jako jsou prodeje nebo převody. This is helpful for new [!INCLUDE[prod_short](includes/prod_short.md)] customers and small businesses with relatively low inventory transaction levels. S růstem firmy a zvyšováním úrovně zásob to však může zpomalit výkon systému. Chcete-li minimalizovat snížený výkon během účtování, vyberte možnost času, která definuje, jak daleko v čase od pracovního data může dojít k příchozí transakci, aby se potenciálně spustila úprava souvisejících položek výstupních hodnot. Případně můžete ručně upravit náklady v pravidelných intervalech pomocí dávkové úlohy Adjustace nákladů položek zboží.

## Viz také
[Nastavení zásob](inventory-setup-inventory.md)    
[Detaily návrhu: Metody ocenění](design-details-costing-methods.md)      
[Zásoby](inventory-manage-inventory.md)    
[Práce s [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    
[Změňte, které funkce se zobrazí](ui-experiences.md)    
[Přehled obchodních funkcionalit](ui-across-business-areas.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]