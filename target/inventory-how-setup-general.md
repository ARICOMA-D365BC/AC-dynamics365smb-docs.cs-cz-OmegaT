---
title: Set Up General Inventory Information
description: Describes how to define the general inventory setup so that you can manage your warehouse and stock.
author: brentholtorf


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: warehouse, stock
ms.search.form: 30, 456, 461
ms.date: 07/28/2021
ms.author: edupont

---
# Nastavení obecných informací o zásobách

Obecné nastavení zásob nastavíte na stránce **Nastavení zásob**.

## Nastavení obecných informací o zásobách

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Setup**, and then choose the related link.
2. Na stránce **Nastavení zásob** vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

Pro podrobné informace o polích ocenění, **Automatické účtování nákladů**, **Účtování oček.nákladů do fin.** a **Výchozí metoda ocenění** navštivte [Odsouhlasení nákladů na zboží s financemi](finance-how-to-post-inventory-costs-to-the-general-ledger.md), [Detaily návrhu: Ocenění zásob](design-details-inventory-costing.md) a [Detaily návrhu: Účtování očekávaných nákladů](design-details-expected-cost-posting.md). Pro více informací navštivte [Správa nákladů zásob](finance-manage-inventory-costs.md).

Pokud chcete zahrnout dobu zpracování ve skladu do kalkulace nadějné zakázky na nákupní řádek, můžete jej nastavit jako výchozí pro zásoby, na stránce **Nastavení zásob** a pro vaši lokaci. Pro více informací navštivte [Výpočet data přislíbení objednávky](sales-how-to-calculate-order-promising-dates.md).

> [!NOTE]
> The **Automatic Cost Adjustment** field is set to *Always* by default to ensure that inventory values are always correct in the general ledger, which in turn keeps your sales and profit statistics up to date. Změny nákladů z příchozích položek, například pro nákupy nebo výstup výroby, jsou přiřazeny k souvisejícím výstupním položkám, jako jsou prodeje nebo převody. To je užitečné pro nové zákazníky [!INCLUDE[prod_short](includes/prod_short.md)] a malé firmy s relativně nízkou úrovní skladových transakcí.
>
> S růstem firmy a zvyšováním úrovně zásob to však může zpomalit výkon systému. Chcete-li minimalizovat snížený výkon během účtování, vyberte možnost času, která definuje, jak daleko v čase od pracovního data může dojít k příchozí transakci, aby se potenciálně spustila úprava souvisejících položek výstupních hodnot.
>
> Případně můžete ručně upravit náklady v pravidelných intervalech pomocí dávkové úlohy Adjustace nákladů položek zboží. You can also turn off automatic cost posting or set the **Automatic Cost Adjustment** field to *Never*. In both cases, a notification displays from which you can start an assisted setup guide to help you schedule tasks for the job queue. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

## Viz také

[Set Up Inventory](inventory-setup-inventory.md)  
[Design Details: Costing Methods](design-details-costing-methods.md)  
[Manage Inventory](inventory-manage-inventory.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[General Business Functionality](ui-across-business-areas.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]