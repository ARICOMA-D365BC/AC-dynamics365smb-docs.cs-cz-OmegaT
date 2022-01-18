---
title: Add Extended Text
description: You can add extra lines to extend the standard text that describes an item, a G/L account, and other data.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/24/2021
ms.author: edupont

---
# Add Extended Text

You can extend the description for items, stock-keeping units, general ledger accounts, and resources by adding extra lines as extended text. You can also set up conditions for use of the extra lines.  

The following section describes how to add extended text to a description of an item. But the same steps apply to stock-keeping units, general ledger accounts, and resources.  

## To define extended text for an description

1. Open the card for an item that you want to add extended text to, and then choose the **Extended Text** action.
2. Fill in the **Code** and **Description** fields.
3. Choose the **New**.
4. Fill in the **Language Code** field or select the **All Language Codes** check box if you use language codes.
5. Fill in the **Starting Date** and **Ending Date** fields if you want to limit the dates on which the extended text is used.
6. In the **Text** field, write the extended text.
7. Select relevant check boxes for the document types where you want the extended text printed.
8. Close the page.

You can now add this extended text to documents. The following procedure explains how to add extended text to a sales order, but the same steps apply to any other document that you specified for the extended text.  

## To add an extended item text on a sales order line

1. Open a sales order with a sales line for an item that has extended text defined. For more information, see [Sell Products](sales-how-sell-products.md).
2. Select the line in question, and then choose the **Insert Ext. Text** action.

## See Also

[Setting Up Inventory](inventory-setup-inventory.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]