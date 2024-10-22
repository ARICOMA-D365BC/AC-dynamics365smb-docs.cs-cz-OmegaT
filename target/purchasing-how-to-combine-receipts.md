---
title: Combine Receipts on a Single Invoice
description: If you want to invoice more than one purchase receipt at a time, you can use the Combine Receipts function.
author: SorenGP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.search.form: 136, 145, 146, 9308
ms.date: 04/01/2021
ms.author: edupont

---
# Combine Receipts on a Single Invoice

If you want to invoice more than one purchase receipt at a time, you can use the **Combine Receipts** function.

Before you can create a combined purchase receipt, more than one receipt from the same vendor in the same currency must be posted. In other words, you must have filled in two or more purchase orders and posted them as received, but not invoiced.

When purchase receipts are combined on an invoice and posted, then a posted purchase invoice is created for the invoiced lines. The **Quantity Invoiced** field on the originating purchase order, or blanket purchase order, is updated based on the invoiced quantity. However, this original purchase document is not deleted, even if it has been fully received and invoiced, and you must therefore delete the purchase document.

> [!NOTE]
> The resulting purchase invoice cannot later be corrected or canceled. If you want to modify a purchase invoice that is created in this way, you must use purchase credit memos. For more information, see [Correct or Cancel Unpaid Purchase Invoices](purchasing-how-correct-cancel-unpaid-purchase-invoices.md).

## To combine receipts

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte Mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Nákupní faktury** a poté vyberte související odkaz.
2. Vyberte akci **Nový**. For more information, see [Record Purchases](purchasing-how-record-purchases.md).
3. On the **Lines** FastTab, choose the **Get Receipt Lines** action.
4. Select multiple receipt lines that you want to include in the invoice.

   If an incorrect receipt line was selected or you want to start over, you can just delete the lines on the purchase invoice and then use the **Get Receipt Lines** function again.
5. To post the invoice, choose the **Post** action.

## To remove open purchase orders after combined receipt posting

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Delete Invoiced Purchase Orders**, and select the related link.
2. Vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)].
3. Zvolte tlačítko **OK**.

Alternatively, delete the individual orders manually.

Repeat steps 1 through 3 for any other affected documents, such as blanket purchase orders.

## Viz také

[Purchasing](purchasing-manage-purchasing.md)  
[Correct or Cancel Unpaid Purchase Invoices](purchasing-how-correct-cancel-unpaid-purchase-invoices.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]