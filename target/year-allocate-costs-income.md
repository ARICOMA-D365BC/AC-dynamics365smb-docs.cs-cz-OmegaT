---
title: Overview of Tasks to Allocate Costs and Income
description: Outlines the tasks to allocate an entry in a general journal to several different accounts when you post the journal.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 283
ms.date: 04/01/2021
ms.author: edupont

---
# Přidělení nákladů a výnosů

Při účtování deníku můžete přiřadit položku ve finančním deníku několika různým účtům. Přidělení lze provést třemi různými metodami:

* Množství
* Procento (%)
* Částka

Funkce přidělení lze použít opakovaně pomocí finančních deníků a deníků dlouhodobého majetku.
<!--You can also distribute the cost or revenue of a line to an intercompany partner when you post a sales or purchase document. When you post the document, a line will be posted in your general journal, and a corresponding line will be created in the intercompany outbox.-->

Následující postupy popisují, jak připravit přidělení nákladů v periodickém finanční deníku pomocí definování alokačních klíčů Když jsou definovány alokační klíče, tak poté dokončíte a zaúčtujete deník jako jakýkoli jiný periodický finanční deník. For more information, see [Working with General Journals](ui-work-general-journals.md).

## Nastavení alokačních klíčů

Položku v periodickém finančním deníku můžete při účtování přidělit několika různým účtům. Přidělení lze vytvořit podle množství, procenta nebo částky.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Recurring General Journal**, and then choose the related link.
2. Choose the **Batch Name** field to open the **General Journal Batches** page.
3. Můžete buď upravit již existující přidělení v listech děníku, nebo vytvořit nový deník s patřičným přidělením.
   * To create a new batch, choose the **New** action, and go to the next step.
   * Chcete-li změnit přidělení existujícího deníku, vyberte deník a přejděte ke kroku 7.
4. In the **Name** field, enter a name for the batch, such as CLEANING. In the **Description** field, enter a description, such as Cleaning Expenses Journal.
5. Až budete hotovi, zavřete stránku. Otevře se nový, prázdný periodický deník.
6. Vyplňte pole v hlavičce.
7. Choose the **Allocations** action.
8. Přidejte řádek pro každé přidělení. You must fill in either the **Allocation %**, **Allocation Quantity**, or **Amount** field. You must also fill in the **Account No.** field and, if you are allocating the transaction among global dimensions, the global dimension fields.
9. If you enter a percentage on a line, the amount in the **Amount** field is calculated automatically. These amounts have the opposite sign from the total amount in the **Amount** field in the recurring journal.
10. After entering the allocations lines, choose **OK** to return to the **Recurring General Journal** page. The **Allocated Amt. (USD)** field is filled in and matches the **Amount** field.
11. Zaúčtujte deník.

## Změna již nastaveného alokačního klíče
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Recurring General Journal**, and then choose the related link.
2. On the **Recurring General Journal** page, select the journal with the allocation.
3. Choose the line with the allocation, and then choose **Allocations** action.
4. Change the relevant fields, and then choose the **OK** button.

## Viz také
[Closing Years and Periods](year-close-years-periods.md)  
[Working with General Journals](ui-work-general-journals.md)    
[Posting Documents and Journals](ui-post-documents-journals.md)    
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]