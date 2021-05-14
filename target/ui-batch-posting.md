---
title: How to Post Multiple Documents at the Same Time | Microsoft Docs
description: Instead of posting individual documents one by one, you can select multiple non-posted documents in a list for batch posting, either for immediate posting or scheduled to, for example, the end of the day.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.reviewer: edupont
ms.date: 04/01/2021
ms.author: edupont

---
# Dávkové zaúčtování dokladů

Namísto účtování jednotlivých dokladů jeden po druhém můžete vybrat více nezaúčtovaných dokladů v seznamu pro okamžité zaúčtování nebo pro dávkové zaúčtování podle plánu, například na konci dne. To může být užitečné, pokud může pouze nadřízený zaúčtovat doklady vytvořené jinými uživateli nebo, aby se zabránilo problémům s výkonem systému z účtování během pracovní doby.

## Okamžité hmoradné zaúčtování nákupních objednávek

Následující postup vysvětluje, jak okamžitě zaúčtovat více nákupních objednávek. Postup je podobný pro všechny nákupní a prodejní doklady.

1. Vyberte ![Žárovku, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete delat"), zadejte **Nákupní objednávky**a pak zvolte související odkaz.
2. On the **Purchase Orders** page, proceed to select all orders to be posted:
3. In the **No.** field, choose the three vertical dots to open the context menu, and then choose the **Select More** action.
4. Zaškrtněte políčko u všech řádků představujících objednávky, které chcete zaúčtovat současně.
5. Choose the **Posting** action, and then choose the **Post** action.
6. Choose the **Yes** button on the confirmation message.

## Dávkově zaúčtování více nákupních objednávek

Následující postup vysvětluje, jak dávkově zaúčtovat nákupní objednávky. The steps are similar for all purchase and sales documents where the **Batch Post** action is available.

1. Vyberte ![Žárovku, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete delat"), zadejte **Nákupní objednávky**a pak zvolte související odkaz.
2. On the **Purchase Orders** page, proceed to select all orders to be posted:
3. In the **No.** field, choose the three vertical dots to open the context menu, and then choose the **Select More** action.
4. Zaškrtněte políčko u všech řádků představujících objednávky, které chcete zaúčtovat současně.
5. Choose the **Posting** action, and then choose the **Post Batch** action.
6. On the **Batch Post Purchase Order** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
7. Zvolte tlačítko **OK**.
8. To view potential issues that occurred during batch posting of documents, open the **Error Message Register** page.

> [!NOTE]
> Posting of multiple documents might take some time and block other users. Consider enabling background posting. For more information, see [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).

## Nastavení účtování na pozadí pomocí fronty úloh
Fronta úloh je účinným nástrojem pro plánování chodu obchodních procesů na pozadí, například když se více uživatelů pokouší zaúčtovat prodejní objednávky, ale současně lze zpracovat pouze jednu objednávku.

Následující postup vysvětluje, jak nastavit účtování prodejních objednávek na pozadí. The steps are similar for purchasing.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Nastavení prodeje a pohledávek** a poté vyberte související odkaz.
2. On the **Sales & Receivables Setup** page, choose the **Post with Job Queue** check box.
3. Choose the **Job Queue Category Code** field, and then specify the **SALESPOST** code.

   > [!NOTE]
   > Některé úlohy mění stejná data a neměly by se spouštět současně, protože to může způsobit konflikty. Například úlohy na pozadí pro prodejní doklady se pokusí upravit stejná data současně. Kategorie fronty úloh pomáhají předcházet těmto konfliktům tím, že zajišťují, že při spuštění jedné úlohy se další úloha, která patří do stejné kategorie front úloh nespustí, dokud nedokončí. Například úloha, která patří do kategorie fronty prodejních úloh, bude čekat, dokud nebudou provedeny všechny ostatní úlohy související s prodejem. You specify a job queue category on the **Background Posting** FastTab on the **Sales & Receivables Setup** page.
   >
   > [!INCLUDE[prod_short](includes/prod_short.md)] provides job queue categories for sales, purchase, and general ledger posting. Doporučujeme, abyste vždy určili jeden z nich nebo ten, který vytvoříte. Pokud dojde k selhání v důsledku konfliktů, zvažte nastavení kategorie pro všechno účtování prodeje, nákupu a hlavní knihy na pozadí.

   If you also want sales documents to be printed when they are posted, select the **Post & Print with Job Queue** check box on the **Sales & Receivables Setup** page.  
   If you select **PDF** in the **Report Output Type** field, successfully posted purchase orders will be available in the **Report Inbox** part on your Role Center.

   > [!IMPORTANT]  
   > Pokud nastavíte úlohu, která bude účtovat a tisknout dokumenty a tiskárna zobrazí dialogové okno, například žádost o přihlašovací údaje nebo upozornění na nedostatek inkoustu v tiskárně, bude váš dokument zaúčtován, ale nevytisknut. The corresponding job queue entry eventually times out and the **Status** field is set to **Error**. Proto doporučujeme nepoužívat nastavení tiskárny, které vyžaduje interakci se zobrazením dialogových oken tiskárny ve spojení s odesíláním na pozadí.

   Next time that you post sales documents, [!INCLUDE [prod_short](includes/prod_short.md)] automatically creates a job queue entry for each document and run the jobs in the background, one by one.

4. Chcete-li ověřit, zda fronta úloh funguje podle očekávání, zaúčtujte prodejní objednávku. Více informací viz [Prodávání produktů](sales-how-sell-products.md).
   The sales order will now be added to a dedicated job queue entry, which defines when the documents are posted.

### Zobrazení stavu z prodejního nebo nákupního dokladu
If the job queue cannot post the sales order, the status is changed to **Error** and the sales order is added to the list of sales orders that the user must handle manually.
1. From the document that you have tried to post with background posting, choose the **Job Queue Status** field, which will contain **Error**.
2. Zkontrolujte chybovou zprávu a problém vyřešte.

Alternativelly you can review on the **Job Queue Log Entries** page if the sales order was posted successfully. For more information, see [To view status or errors in the job queue](admin-job-queues-schedule-tasks.md#to-view-status-or-errors-in-the-job-queue).

## Vytvoření položky fronty úlohy pro dávkové účtování prodejních objednávek

Alternatively, you can postpone postings for when it is convenient for your organization. For example, in your business it might make sense to run certain routines when most of the data entry for the day has concluded. You can achieve this by setting the job queue up to run various batch-posting reports, such as the **Batch Post Sales Orders**, **Batch Post Sales Invoices**, and similar reports. [!INCLUDE[prod_short](includes/prod_short.md)] supports background posting for all sales, purchasing, and service documents.

The following procedure shows how to set the **Batch Post Sales Orders** report up to automatically post sales orders at 4 PM on week days.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Queue Entries**, and then choose the related link.
2. Vyberte akci **Nový**.
3. In the **Object Type to Run** field, select **Report**.
4. In the **Object ID to Run** field, select 296, **Batch Post Sales Orders**.

   You can also use following reports:

   * 900 **Batch Post Assembly Orders**
   * 497 **Batch Post Purchase Invoices**
   * 496 **Batch Post Purchase Orders**
   * 498 **Batch Post Purch. Credit Memos**
   * 6665 **Batch Post Purch. Ret. Orders**
   * 298 **Batch Post Sales Credit Memos**
   * 297 **Batch Post Sales Invoices**
   * 296 **Batch Post Sales Orders**
   * 6655 **Batch Post Sales Return Orders**
   * 6005 **Batch Post Service Cr. Memos**
   * 6004 **Batch Post Service Invoices**
   * 6001 **Batch Post Service Orders**

5. Select the **Report Request Page** check box.
6. In the **Batch Post Sales Orders** request page, define what is included during automatic posting of sales orders, and then choose the **OK** button.

   > [!IMPORTANT]
   > Remember to set strict filters; otherwise, [!INCLUDE [prod_short](includes/prod_short.md)] will post all documents, even if they are not ready. Consider setting a filter on the **Status** field for the value *Released*, and a filter on the **Posting Date** field for the value *..today*. For more information, see [Sorting, Searching, and Filtering](ui-enter-criteria-filters.md).
7. Select all check boxes from **Run on Mondays** through **Run on Fridays**.
8. In the **Starting Time** field, enter 4 PM.
9. Choose the **Set Status to Ready** action.

Sales orders that are within defined filters will now be posted every week day at 4 PM.


## Viz také

[Posting Documents and Journals](ui-post-documents-journals.md)  
[Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md)  
[Edit Posted Documents](across-edit-posted-document.md)  
[Correct or Cancel Unpaid Purchase Invoices](purchasing-how-correct-cancel-unpaid-purchase-invoices.md)  
[Finding Pages and Information with Tell Me](ui-search.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]