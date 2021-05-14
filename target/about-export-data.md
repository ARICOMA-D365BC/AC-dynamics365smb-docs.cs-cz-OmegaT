---
title: Export Your Business Central Data to Excel| Microsoft Docs
description: You can export your financial reports and business intelligence data from Business Central  to Excel, or open your data in Excel.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: analysis, reporting, financial report, business intelligence, BI, Excel
ms.date: 04/01/2021
ms.author: edupont

---
# Export vašich obchodních dat do Excelu
If you want to work with your data from [!INCLUDE[prod_short](includes/prod_short.md)] in Excel, you can open all lists in Excel and work with it there. Similarly, if you want to cancel your subscription for [!INCLUDE[prod_short](includes/prod_short.md)], you can export your data to Excel so that you can take it with you.

## Otevření seznamů v aplikaci Excel
Data můžete otevírat v Excelu z libovolného deníku, seznamu nebo sešitu. You just open the page that you want, and then choose **Open in Excel**. For example, open the list of customers (search for **Customers**), and then choose **Open in Excel**. Váš prohlížeč vás vyzve k otevření nebo uložení vygenerovaného sešitu aplikace Excel.

> [!NOTE]
> Use this option when you do not want to make changes and publish those changes back to [!INCLUDE[prod_short](includes/prod_short.md)].

Každý seznam obsahuje několik sloupců a export do Excelu bude zahrnovat všechny sloupce, které jsou v aktuálním zobrazení. Chcete-li přidat nebo odebrat sloupce před otevřením seznamu v aplikaci Excel, stačí otevřít místní nabídku pro libovolný sloupec a určit, které sloupce chcete zobrazit. Tento seznam sloupců se u většiny seznamů liší a odráží strukturu databáze, ve které jsou data uložena. Pokud si nejste jisti, jaký typ dat určitý sloupec obsahuje, můžete je přidat do svého zobrazení a pak se rozhodnout, zda je chcete znovu odebrat.

### Úpravy dat v Excelu
Your [!INCLUDE[prod_short](includes/prod_short.md)] experience includes an add-in for Excel so you can edit data in Excel. For more information, see [Analyzing Financial Statements in Microsoft Excel](finance-analyze-excel.md).

## Export dat do jiných finančních systémů
If you decide to cancel your subscription for [!INCLUDE[prod_short](includes/prod_short.md)], you can export your data to Excel and take it with you to your next finance system.

Samozřejmě můžete exportovat všechny stránky, ale to může být více, než skutečně potřebujete. Zvažte export následujících základních tabulek a nezapomeňte přidat všechny sloupce, jak je popsáno výše:

* Účetní osnova
* Zákazníci
* Dodavatelé
* Banky
* Zboží

Pokud chcete také všechny své finanční transakce, jedná se o velké množství dat, takže export bude často trvat déle než několik minut. The financial transactions are shown on the **General Ledger Entries** page.

Doporučujeme také zvážit export dat z následujících stránek:

* Položky zákazníka
* Položky dodavatele
* Položky bankovního účtu
* Položky zboží
* Nastavení obecného účtování
* Účto skupiny zákazníků
* Účto skupiny dodavatele
* Účto skupiny zboží
* Účto skupiny bankovního účtu
* Finanční rozpočty
* Položky finančního rozpočtu
* Prodejní nabídky
* Prodejní faktury
* Nákupní faktury
* Kontakty
* Prodejci

> [!NOTE]  
> If you have set up more than one company in [!INCLUDE[prod_short](includes/prod_short.md)], you must export the relevant data from each company.

> [!NOTE]
> You must have at least one of the following permissions to open or edit data in Excel:
> - Permission set *D365 Excel Export Action*
> - System permission 6110 *Allow Action Export To Excel*.

For more information, see [To get an overview of a user's permissions](ui-define-granular-permissions.md#to-get-an-overview-of-a-users-permissions).

## Zobrazit související školení na webu [Microsoft Learn](/learn/modules/configure-powerbi-excel-dynamics-365-business-central/index)

## Viz také
[Canceling Your Subscription for [!INCLUDE[prod_short](includes/prod_short.md)]](admin-cancel.md)  
[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Analyzing Financial Statements in Microsoft Excel](finance-analyze-excel.md)  
[Finance](finance.md)  
[General Business Functionality](ui-across-business-areas.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]