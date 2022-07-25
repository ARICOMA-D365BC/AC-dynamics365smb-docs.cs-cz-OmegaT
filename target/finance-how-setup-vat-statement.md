---
title: Set Up a VAT Statement
description: This topic tells you how to set Up a VAT Statement Template and VAT Statement Names to meet changing tax authority requirements.
author: brentholtorf

ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: VAT, posting, tax, value-added tax
ms.search.form: 317, 318, 320, 474
ms.date: 06/16/2021
ms.author: bholtorf

---
# Set Up VAT Statement Templates and VAT Statement Names

Finanční úřady mohou změnit své požadavky na účtování DPH. Šablony výkazu DPH a názvy výkazu DPH vám mohou pomoci připravit se na nadcházející změny a zajistit hladký přechod na nové požadavky. Šablony výkazu DPH můžete použít k nastavení různých sestav při výběru tisku výkazu. Each VAT Statement Template can have multiple Vat Statement names which in turn define the calculations, and you can create a new VAT statement name when requirements change. Jeden název může například vypočítávat DPH pro tento rok na základě aktuálních požadavků a jiný může počítat DPH na základě požadavků pro příští rok. Názvy jsou také způsob, jak si například udržet historii formátů výkazů DPH, tím je možno nahlédnout zpět, jak jste vypočítali DPH v předchozích letech.

## To define a VAT statement

Výkazy DPH umožňují vypočítat částku vyrovnání DPH za určité období, například kvartálně.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Statements**, and then choose the related link.
2. Choose the **Name** field, and then choose **New** on the **VAT Statement Names** page.
3. Vyplňte požadovaná pole. Obvykle chcete mít nastavení pro každou DPH účto skupinu nebo  DPH účto skupinu zboží a jejich kombinace. For Row numbers it does make sense to use equvalent numbers or codes as in your official VAT Statement [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!Tip]
> You can filter the information that the statement will include, depending on what you choose in the **Type** field. **Account Totaling** is useful when you want the VAT from a specific account.
> **VAT Entry Totaling** gets VAT from the accounts assigned to the selections in the **Gen. Posting Type**, **VAT Bus. Posting Group**, and/or the **VAT Prod. Posting Group** fields. **Row Totaling** lets you enter a value or quick filter criteria in the **Row Totaling** field. For more information, see [Searching, filtering, and Sorting Data](ui-enter-criteria-filters.md). **Description** is often used to add a note to the statement. Můžete jej například použít jako nadpis, když jste použili součet řádků.

## Náhled výkazu DPH

Po definování výkazu DPH můžete zobrazit jeho náhled a ujistit se, že vyhovuje vašim potřebám.
> [!Tip]
> It is best practice to have one section in the VAT Statement using **Type** **Vat Entry Totaling** and another section below using **Type** **Account Totaling** to reconcile the amounts based on the **VAT Entry** table compared to the amount on the **G/L Accounts**. You can also use the **G/L - VAT Reconciliation** Report for this purpose.

1. Choose **Preview**.
2. Zadáním filtru data omezíte výpis na konkrétní období. For more information about how to customize the page to show the date filter, see [Searching, filtering, and Sorting Data](ui-enter-criteria-filters.md).
3. Můžete vybrat různé možnosti a určit typ položek DPH, které mají být zahrnuty do výkazu.
4. On the lines where the **Type** field contains **VAT Entry Totaling** you can see a list of VAT entries by choosing the amount in the **Column Amount** field.
5. Pomocí personalizace můžete zobrazit další pole v řádcích. Například nerealizovaná základní částka a nerealizovaná částka DPH, pokud používáte nerealizovanou DPH.

## Viz také

[Set Up Value-Added Tax](finance-setup-vat.md)  
[Setting Up Unrealized Value Added Tax](finance-setup-unrealized-vat.md)      
[Report VAT to a Tax Authority](finance-how-report-vat.md)  
[Work with VAT on Sales and Purchases](finance-work-with-vat.md)  
[Local functionality in Business Central](about-localization.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]