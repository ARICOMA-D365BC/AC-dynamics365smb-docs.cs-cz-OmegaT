---
title: Create a Customer Sales Order and Sell Products
description: Describes how to create a sales order to record your agreement with a customer to sell or trade products under specific terms.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: trade, partial deliveries, customer sales order
ms.search.form: 42, 48, 9305
ms.date: 09/24/2021
ms.author: edupont

---
# Sell Products with a Customer Sales Order

This article provides guidance to users on when to use a customer sales order rather than just an invoice. If your sales process requires that you can only ship parts of an order quantity, for example, because the full quantity is not available at once, then sell those products by making a customer sales order.

If you sell items by delivering directly from your vendor to your customer, as a drop shipment, then you must also use sales orders. For more information, see [Make Drop Shipments](sales-how-drop-shipment.md). In all other aspects, sales orders work the same way as sales invoices. For more information, see [Invoice Sales](sales-how-invoice-sales.md).

When you deliver the products, either fully or partially, you post the sales order as shipped or as shipped and invoiced to create the related item and customer ledger entries in your system. When you post the sales order, you can also email the document as a PDF attachment. You can have the email body prefilled with a summary of the order and payment information, such as a link to PayPal. For more information, see [Send Documents by Email](ui-how-send-documents-email.md).

In business environments where the customer pays immediately, for example by PayPal or cash, payment is recorded immediately when you post the sales order as invoiced, that is, the posted sales invoice is closed as fully applied. You select the relevant method in the **Payment Method Code** field on the sales order. See under step 8. For electronic payments, such as PayPal, you must also fill in the **Payment Service** field. For more information, see [Enable Customer Payments Through Payment Services](sales-how-enable-payment-service-extensions.md).

You can even create directly-paid orders for non-registered customers by first setting up a "cash customer" card, which you point to on the sales order. For more information, see [Set Up Cash Customers](finance-how-to-set-up-cash-customers.md).

## Vytvoření prodejní objednávky

> [!NOTE]  
> The following procedure assumes that the customer is already set up. For instructions on how to do this, please see [Register New Customers](sales-how-register-new-customers.md).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.
2. Vyberte **Nový** a vytvořte nový záznam.
3. Do pole **Zákazník** zadejte jméno existujícího zákazníka.

   Ostatní pole na stránce **Prodejní objednávka** se sama vyplní standardními informacemi o vybraném zákazníkovi.

4. Podle potřeby vyplňte další zbývající pole na stránce **Prodejní objednávka**. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

   > [!NOTE]  
   > If you allow the customer to pay immediately, for example, by credit card or PayPal, then fill in the **Payment Method Code** field. The payment is then recorded as soon as you post the sales order as invoiced. If you select CASH, then the payment is recorded in a specified balancing account.

   You are now ready to fill in the sales order lines with inventory items or services that you want to sell to the customer.

   If you have set up recurring sales lines for the customer, such as a monthly replenishment order, then you can insert these lines on the order by choosing the **Get Recurring Sales Lines** action.
5. V záložce **Řádky** v poli **Typ** vyberte typ zboží, poplatek nebo transakce, které budete účtovat zákazníkovi s řádkem prodeje.

6. Do pole **Číslo** zadejte číslo zboží nebo služby.

   You leave the **No.** field empty in the following cases:

   * If the line is for a comment. Write the comment in the **Description** field.
   * If the line is for a catalog item. Choose the **Select Catalog Items** action. For more information, see [Work With Catalog Items](inventory-how-work-nonstock-items.md).
7. Do pole **Množství** zadejte počet položek, které mají být prodány.

   > [!NOTE]  
   > For items of type *Resource* or *Service*, the quantity is a time unit, such as hours, as indicated in the **Unit of Measure Code** field on the line. For more information, see [Set Up Item Units of Measure](inventory-how-setup-units-of-measure.md).

   The **Line Amount** field is updated to show the value in the **Unit Price** field multiplied by the value in the **Quantity** field.

   The price and line amounts are shown with or without sales tax depending on what you selected in the **Prices Including Tax** field on the customer card.
8. Do pole **Řádková sleva** zadejte procentuální hodnotu, pokud chcete odběrateli poskytnout slevu na produkt. The value in the **Line Amount** field is updated accordingly.

   If you have set up special item prices on the **Sales Prices and Sales Line Discounts** FastTab on the customer or item card, then the price and amount on the quote line are automatically updated if the agreed price criteria are met. For more information, see [Record Sales Price, Discount, and Payment Agreements](sales-how-record-sales-price-discount-payment-agreements.md).
9. Chcete-li přidat komentář k řádku objednávky, který zákazník může vidět na vytištěné prodejní objednávce, napište komentář do pole **Popis** na prázdném řádku.
10. Opakujte kroky 5 až 9 pro každou položku, kterou chcete prodat zákazníkovi.

   The totals fields under the lines are automatically updated as you create or modify lines to display the amounts that will be posted to the ledgers.

   > [!NOTE]
   > In very rare cases, the posted amounts may deviate from what is displayed in the totals fields. This is typically due to rounding calculations in relation to VAT or sales tax.
   >
   > To check the amounts that will actually be posted, use the **Statistics** page, which takes into account the rounding calculations. Also, if you choose the **Release** action, the totals fields will be updated to include rounding calculations.

11. Optionally, in the **Invoice Discount Amount** field, enter an amount that should be deducted from the value shown in the **Total Incl. DPH**.

   If you have set up invoice discounts for the customer, then the specified percentage value is automatically inserted in the **Invoice Discount %** field if the criteria are met, and the related amount is inserted in the **Inv. Discount Amount Excl. DPH**. For more information, see [Record Sales Price, Discount, and Payment Agreements](sales-how-record-sales-price-discount-payment-agreements.md).
12. Chcete-li odeslat pouze část objednaného množství, zadejte toto množství do pole **K dodání**. Hodnota se zkopíruje do pole **K. fakturaci**.
13. Chcete-li fakturovat pouze část dodaného množství, zadejte toto množství do pole **K fakturaci**. Množství musí být nižší než hodnota v poli **K dodání**.
14. Po dokončení řádků prodejní objednávky vyberte akci **Účtovat a Odeslat**.

The **Post and Send Confirmation** dialog box displays the customer's preferred method of receiving documents. You can change the sending method by choosing the lookup button for the **Send Document to** field. For more information, see [Set Up Document Sending Profiles](sales-how-setup-document-send-profiles.md).

The related item and customer ledger entries are now created in your system, and the sales order is output as a PDF document. When the sales order is fully posted, it is removed from the list of sales orders and replaced with new documents in the list of posted sales invoices and the list of posted sales shipments.

## External document number

[!INCLUDE [ext-doc-no-sales](includes/ext-doc-no-sales.md)]

## Viz také

[Sales](sales-manage-sales.md)  
[Setting Up Sales](sales-setup-sales.md)  
[Print the Picking List](sales-how-print-picking-list.md)  
[Inventory](inventory-manage-inventory.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]