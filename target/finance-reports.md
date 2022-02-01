---
title: Financial Reports and Analytics
description: See which financial reports and analytics are available in the standard version of Business Central so that you can keep track of your business.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: reporting
ms.date: 04/12/2021
ms.author: edupont

---
# Financial Reports and Analytics in Business Central

Finanční výkaznictví v [!INCLUDE [prod_short](includes/prod_short.md)] umožňuje finančním a obchodním odborníkům vytvářet, udržovat a prohlížet finanční výkazy. Překračuje tradiční omezení sestav a pomáhá efektivně navrhovat různé typy sestavy. [!INCLUDE [prod_short](includes/prod_short.md)] obsahuje několik sestav, sledovacích funkcí a nástrojů, které pomáhají auditorům nebo kontrolorům, kteří jsou odpovědní za reporting finančnímu oddělení. Finanční výkaznictví zahrnuje podporu dimenzí, takže segmenty účtu nebo dimenze jsou okamžitě k dispozici. No other tools or configuration steps are required.

## Sestavy

Následující tabulka popisuje některé klíčové sestavy ve finančním výkaznictví.

| Report | Object ID | Description |
|--|--|--|
| **Trial Balance** | 6 | Shows the chart of accounts with balances and net changes. Můžete zvolit, zda chcete zobrazit předvahu pro vybrané dimenze. Sestavu můžete použít na konci účetního období nebo fiskálního roku. |
| **Trial Balance by Period** | 38 | Shows the opening balance by general ledger account, the movements in the selected period of month, quarter, or year, and the resulting closing balance. |
| **Trial Balance/Budget** | 9 | Shows a trial balance in comparison to a budget. Můžete zvolit, zda chcete zobrazit předvahu pro vybrané dimenze. Sestavu můžete použít na konci účetního období nebo fiskálního roku. |
| **Detailed Trial Balance** | 4 | Shows a detail trial balance for selected general ledger accounts. Sestavu můžete použít na konci účetního období nebo fiskálního roku. Nastavením filtrů můžete určit, které účty budou zahrnuty do přehledu. |
| **Trial Balance/Previous Year** | 7 | Shows a trial balance in comparison to the previous year's figures. Můžete zvolit, zda chcete zobrazit předvahu pro vybrané dimenze. Sestavu můžete použít na konci účetního období nebo fiskálního roku. *The previous year* means the same period one calendar year earlier. |
| **Account Schedule** | 25 | Account schedules can be used to display the general ledger accounts in a different way than in the chart of accounts. Účetní schémata lze například použít pro sestavy klíčových údajů. |
<!-- | **Balance Sheet** (Acc.Schedule or Excel) or **Trial Balance** |  |  |
| **Statement of Cash Flow** (Account Schedule) |  |  |
| **Trial Balance Summary/Detail** |  |  |
| **Income Statement** (Acc.Schedule or Excel) |  |  |
| **Budget** |  |  | -->

## Úlohy

Následující články popisují některé klíčové úlohy pro analýzu stavu vaší firmy:

* [Analáza skutečných částek proti rozpočtovým částkám](bi-how-analyze-actual-versus-budget.md)
* [Příprava finančního výkaznictví s účetními schématy a kategoriemi účtů](bi-how-work-account-schedule.md)
* [Nastavení a publikování webových služeb klíčových ukazatelů výkonu na základě účetních plánů](bi-how-to-set-up-and-publish-kpi-web-services-based-on-account-schedules.md)
* [Analýza dat podle dimenzí](bi-how-analyze-data-dimension.md)
* [Vytváření sestav analýz](bi-how-create-analysis-views-reports.md)
* [Vytváření sestav pomocí XBRL](bi-create-reports-with-xbrl.md)
* [Správa přístupu databáze](admin-data-access-intent.md)

## Viz také

[Creating Cost Budgets](finance-create-cost-budgets.md)  
[Report VAT to Tax Authorities](finance-how-report-vat.md)  
[Closing Years and Periods](year-close-years-periods.md)  
[Using Pre-Closing Reports](year-prepare-preclose-reports.md)  
[Preparing Closing Statements](year-prepare-close-statement.md)  
[Analyzing Financial Statements in Microsoft Excel](finance-analyze-excel.md)  
[Working with Dimensions](finance-dimensions.md)  
[Accounts Receivable Reports and Analytics](receivables-reports.md)  
[Accounts Payable Reports and Analytics](payables-reports.md)  
[Fixed Assets Reports and Analytics](fa-reports.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Finance](finance.md)  
[Local Functionality Overview](about-localization.md)  
[Accountant Experiences in [!INCLUDE[prod_long](includes/prod_long.md)]](finance-accounting.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
