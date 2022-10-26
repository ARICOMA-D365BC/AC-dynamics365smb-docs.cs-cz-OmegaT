---
title: Process Returns or Cancellations
description: Explains how to create and post a purchase credit memo when you want to return items to a vendor or cancel purchased services.
author: SorenGP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: cancel, undo, correct
ms.search.form: 6640, 6643, 9307, 9309, 9308, 6652, 145, 147
ms.date: 04/01/2021
ms.author: edupont

---
# Process Purchase Returns or Cancellations

If you want to return items to your vendor or cancel services that you have purchased, then you can create and post a purchase credit memo that specifies the requested change with regard to the original purchase invoice. To include the correct purchase invoice information, you can create the purchase credit memo directly from the posted purchase invoice or you can create a new purchase credit memo with copied invoice information.

If you need more control of the purchase return process, such as warehouse documents for the item handling or better overview when shipping back items from multiple purchase documents with one purchase return, then you can create purchase return orders. A purchase return order automatically issues the related purchase credit memo. For more information, see [To create a purchase return order based on one or more a posted purchase documents](purchasing-how-process-purchase-returns-cancellations.md#to-create-a-purchase-credit-memo-from-a-posted-purchase-invoice).

> [!NOTE]  
> If a posted purchase invoice has not yet been paid, then you can use the **Correct** or **Cancel** functions on the posted purchase invoice to automatically reverse the involved transactions. These functions only work for unpaid invoices, and they do not support partial returns or cancellations. You can also not correct or cancel purchase invoices that were posted with with receipts from more than one purchase order. For more information, see [Correct or Cancel Unpaid Purchase Invoices](purchasing-how-correct-cancel-unpaid-purchase-invoices.md).

Typically, you create a purchase credit memo or purchase return order in reaction to a credit memo sent to you by a vendor. The purchase credit memo or purchase return order functions as your internal documentation of the credit memo process for accounting purposes or to control the shipping of the involved items.

The change may relate to all the products on the original purchase invoice or only to some of the products. Accordingly, you can partially return received items or demand partial reimbursement of received services. In that case, you must edit the information on the purchase credit memo or purchase return order.

In addition to the original posted purchase invoice, you can apply the purchase credit memo or purchase return order to other purchase documents, for example another posted purchase invoice because you are also returning items delivered with that invoice.

The credit memo posting will also revert any item charges that were assigned to the posted document, so that the item's value entries are the same as before the item charge was assigned.

## Inventory Costing
To preserve correct inventory valuation, you typically want to pick return items from inventory at the unit cost that they were purchased at, not at their current unit cost. This is referred to as exact cost reversing.

Two functions exist to assign exact cost reversing automatically.

| Function | Popis |
|------------------|---------------------------------------|  
| **Get Posted Document Lines to Reverse** function on the **Purchase Return Order** page | Copies lines of one or more posted documents to be reversed into the purchase return order. For more information, see [To create a purchase return order based on one or more posted purchase documents](purchasing-how-process-purchase-returns-cancellations.md#to-create-a-purchase-return-order-based-on-one-or-more-posted-purchase-documents). |
| **Copy from Document** function in the **Purchase Credit Memo** and **Purchase Return Order** pages | Copies both the header and lines of one posted document to be reversed.<br /><br /> Requires that the **Exact Cost Reversing Mandatory** check box is selected on the **Purchases & Payables Setup** page. |

To assign exact cost reversing manually, you must choose the **Appl.-from Item Entry** field on any type of return document line, and then select the number of the original purchase entry. This links the purchase credit memo or purchase return order to the original purchase sales entry and ensures that the item is valued at the original unit cost.

For more information, see [Design Details: Inventory Costing](design-details-inventory-costing.md).

## To create a purchase credit memo from a posted purchase invoice

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Purchase Invoices**, and then choose the related link.
2. On the **Posted Purchase Invoices** page, select the posted purchase invoice that you want to reverse, and then choose the **Create Corrective Credit Memo** action.

   Most fields on the purchase credit memo header are filled with the information from the posted purchase invoice. You can edit all the fields, for example with new information that reflects the return agreement.
3. Edit information on the lines according to the agreement, such as the number of items returned or the amount to be reimbursement.
4. Vyberte akci **Vyrovnat položky**.
5. On the **Apply Vendor Entries** page, select the line with the posted purchase document that you want to apply the purchase credit memo to, and then choose the **Applies-to ID** action. The number of the purchase credit memo is inserted in the **Applies-to ID** field.
6. In the **Amount to Apply** field, enter the amount that you want to apply if smaller than the original amount.

   At the bottom of the **Apply Vendor Entries** page, you can see the total amount to apply to reverse all involved entries, namely when the value in the **Balance** field is zero.
7. Zvolte tlačítko **OK**. When you post the purchase credit memo, it will be applied to the specified posted purchase documents.

   When you have created or edited the needed purchase credit memo lines and the single or multiple applications are specified, you can proceed to post the purchase credit memo.
8. Vyberte tlačítko **Zaúčtovat**.

The posted purchase invoices that you apply the credit memo to are now reversed. If you have already paid the original invoice, the vendor should now refund the payment to you. If the credit memo is only for part of the product on the original invoice, you may only pay the remaining amount on the original purchase invoice to close it.

The purchase credit memo is removed and replaced with a new document in the list of posted purchase credit memos.

## To create a purchase credit memo by copying a posted purchase invoice

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Credit Memos**, and then choose the related link.
2. Choose the **New** action to open a new empty purchase credit memo.
3. Do pole **Dodavatel** zadejte název existujícího dodavatele.
4. Choose the **Copy from Document** action.
5. On the **Copy Purchase Document** page, in the **Document Type** field, select **Posted Invoice**.
6. Choose the **Document No.** field to open the **Posted Purchase Invoices** page, and then select the posted purchase invoice that contains lines that you want to reverse.
7. Select the **Recalculate Lines** check box if you want the copied posted purchase invoice lines to be updated with any changes in item price and unit cost since the invoice was posted.
8. Zvolte tlačítko **OK**. The copied invoice lines are inserted in the purchase credit memo.
9. Complete the purchase credit memo as explained in [To create a purchase credit memo from a posted purchase invoice](purchasing-how-process-purchase-returns-cancellations.md#to-create-a-purchase-credit-memo-from-a-posted-purchase-invoice).

## To create a purchase return order based on one or more posted purchase documents

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Return Orders**, and then choose the related link.
2. Vyberte akci **Nový**.
3. Vyplňte pole na pevné záložce **Obecné** podle potřeby.
4. Na pevné záložce **Řádky** vyplňte řádky ručně nebo zkopírujte informace z jiných dokumentů, abyste řádky vyplnili automaticky:

   - Pomocí funkce **Získat řádky zaúčtovaného dokladu k obrácení** zkopírujte jeden nebo více řádků zaúčtovaného dokladu z jednoho nebo více zaúčtovaných dokladů. Tato funkce vždy přesně obrátí náklady z řádku zaúčtovaného dokladu. Tato funkce je popsána v následujících krocích.
   - Pomocí funkce **Kopírovat z dokumentu** zkopírujte existující dokument k vrácení objednávky. Tato funkce slouží ke zkopírování celého dokumentu. Může to být buď zaúčtovaný dokument, nebo dokument, který ještě není zaúčtován. Tato funkce umožňuje přesné obrácení nákladů pouze v případě, že je zaškrtnuto políčko **Povinné přesné vrácení nákladů** na stránce **Nastavení prodeje a pohledávek**.  

5. Choose the **Get Posted Document Lines to Reverse** action.
6. At the top of the **Posted Purchase Document Lines** page, select the **Show Reversible Lines Only** check box if you want to see only lines that have quantities that have not yet been returned. For example, if a posted purchase invoice quantity has already been returned, you may not want to include that quantity on a new purchase return document.

   > [!NOTE]  
   > This field only works for posted receipts and posted invoice lines, not for posted return or posted credit memo lines.

   Na levé straně stránky jsou uvedeny různé typy dokumentů a číslo v závorkách ukazuje počet dokumentů dostupných pro každý typ dokumentu.

7. V poli **Filtr typu dokumentu** vyberte typ řádků zaúčtovaného dokladu, který chcete použít.
8. Vyberte řádky, které chcete zkopírovat do nového dokumentu.

   > [!NOTE]  
   > Pokud použijete Ctrl+A k výběru všech řádků, zkopírují se všechny řádky v rámci filtru, který jste nastavili, ale filtr **Zobrazit pouze reverzibilní množství** bude ignorován. Předpokládejme například, že jste filtrovali řádky na konkrétní číslo dokumentu se dvěma řádky, z nichž jeden již byl vrácen. I když je vybráno pole **Zobrazit pouze reverzibilní množství**, pokud stisknete Ctrl+A pro zkopírování všech řádků, zkopírují se oba řádky, namísto pouze jednoho, který ještě nebyl obrácen.

9. Kliknutím na tlačítko **OK** zkopírujte řádky do nového dokumentu.

   Dochází k následujícím procesům:

   - Pro řádky zaúčtovaného dokladu typu **Zboží** je vytvořen nový řádek dokladu, který je kopií řádku zaúčtovaného dokladu s množstvím, které ještě nebylo obráceno. The **Appl.-to Item Entry** field is filled in as appropriate with the number of the item ledger entry of the posted document line.

   - Pro řádky zaúčtovaného dokladu, které nejsou typu **Zboží**, například náklady na zboží, je vytvořen nový řádek dokladu, který je kopií původního řádku zaúčtovaného dokladu.

   - Vypočítá pole **Jednotkové náklady (LCY)** na novém řádku z nákladů na odpovídajících záznamech knihy zboží.

   - Pokud je zkopírovaným dokladem zaúčtovaná zásilka, zaúčtovaná účtenka, zaúčtovaná vratka nebo zaúčtovaná zpětná zásilka, jednotková cena se vypočítá automaticky z karty zboží.

   - Pokud je zkopírovaný doklad zaúčtovaná faktura nebo dobropis, zkopíruje se jednotková cena, fakturační slevy a řádkové slevy z řádku zaúčtovaného dokladu.

   - If the posted document line contains item tracking lines, the **Appl.-to Item Entry** field on the item tracking lines is filled with the appropriate item ledger entry numbers from the posted item tracking lines.

   Když kopírujete ze zaúčtované faktury nebo zaúčtované dobropisy, aplikace zkopíruje všechny relevantní fakturační slevy a řádkové slevy jako platné v době zaúčtování tohoto dokladu z řádku zaúčtovaného dokladu do nového řádku dokladu. Uvědomte si však, že pokud možnost **Calc. Nák. Discount** option is activated on the **Purchases & Payables Setup** page, then the invoice discount will be newly calculated when you post the new document line. Částka řádku pro nový řádek se tedy může lišit od částky řádku pro řádek zaúčtovaného dokladu v závislosti na novém výpočtu slevy faktury.

   > [!NOTE]  
   > Pokud již byla část množství řádku účtovaného dokladu stornována nebo prodána nebo spotřebována, vytvoří se řádek pouze pro množství, které zůstalo na skladě nebo které nebylo vráceno. Pokud již bylo stornováno celé množství řádku zaúčtovaného dokladu, nový řádek dokladu se nevytvoří.
   >
   > Pokud je tok zboží v zaúčtovaném dokladu stejný jako tok zboží v novém dokladu, vytvoří se kopie řádku původního zaúčtovaného dokladu v novém dokladu. Pole **Aplikační formulář pro zadání zboží** není vyplněno, protože v tomto případě není možné přesné vrácení nákladů. For example, if you use the **Get Posted Document Lines to Reverse** function to get a posted purchase credit memo line for a new purchase credit memo, only the original posted credit memo line is copied to the new credit memo.

10. On the **Purchase Return Order** page, in the **Return Reason Code** field on each line, select the reason for the return.
11. Vyberte tlačítko **Zaúčtovat**.

## To create a replacement purchase order from a purchase return order

You may agree with your vendor that they compensate you for a purchased item by replacing the item. The replacement item can be the same or it can be different. This situation could occur if the vendor mistakenly shipped the wrong item.

1. On the **Purchase Return Order** page for an active return process, on an empty line, make a negative entry for the replacement item by inserting a negative amount in the **Quantity** field.
2. Vyberte akci **Přesunout záporné čáry**.
3. On the **Move Negative Purchase Lines** page, fill in the fields as necessary.
4. Zvolte tlačítko **OK**. The negative line is deleted from the purchase return order, and a new purchase order is created. For more information, see [Record Purchases](purchasing-how-record-purchases.md).

## To create a purchase allowance

If you receive items from your vendor that are not what you wanted, for example, if they are slightly damaged, the wrong color or the wrong size, the vendor may offer you a purchase allowance.

You can post this reduced purchase cost as an item charge on a credit memo or return order and link it to the posted receipt. The following describes it for a purchase return order, but the same steps apply to a purchase credit memo.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Credit Memos**, and then choose the related link.
2. Choose the **New** action to open a new empty purchase credit memo.
3. Fill in the credit memo header with information about the vendor who sent you the purchase allowance.
4. On the **Lines** FastTab, in the **Type** field, select **Charge (Item)**.
5. In the **No.** field, select the appropriate item charge value.

   You may want to create a special item charge number to cover purchase allowances.
6. In the **Quantity** field, enter **1**.
7. In the **Direct Unit Cost** field, enter the amount of the purchase allowance.
8. Assign the purchase allowance as an item charge to the items in the posted receipt. Další informace [naleznete v tématu Použití poplatků za položku k účtování dodatečných obchodních nákladů](payables-how-assign-item-charges.md). When you have assigned the allowance, return to the **Purchase Credit Memo** page.

When you post the purchase return order, the purchase allowance is added to the relevant purchase entry amount. Tímto způsobem můžete udržovat přesné ocenění zásob.

## To combine return shipments

If you want to return items covered by different purchase return orders to the same vendor, then you can use the **Combine Return Shipments** function.

When you ship the items, you post the related purchase return orders as shipped and this creates posted purchase return shipments.

When you are ready to invoice these items, instead of invoicing each purchase return order separately, you can create a purchase credit memo and automatically copy the posted purchase return shipment lines to this document. Then you can post the purchase credit memo and conveniently invoice all the open purchase return orders at the same time.

When return shipments are combined on a credit memo and posted, then a posted purchase credit memo is created for the invoiced lines. The **Quantity Invoiced** field on the originating purchase return order is updated based on the invoiced quantity. However, this original purchase return order is not deleted, even if it has been fully received and invoiced, and you must therefore delete the purchase return order manually.

> [!NOTE]  
> The following procedure assumes that there are several purchase return orders for the vendor, and that they have been posted as shipped.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Credit Memos**, and then choose the related link.
2. Vyberte akci **Nový**.
3. On the **General** FastTab, fill in the fields as necessary.
4. Choose the **Get Return Shipment Lines** action.
5. Select multiple return shipment lines that you want to include in the invoice.

   If an incorrect return shipment line was selected or you want to start over, you can just delete the lines on the purchase credit memo and then use the **Get Return Shipment Lines** function again.
6. Vyberte tlačítko **Zaúčtovat**.

### To remove open purchase return orders after combined return shipment posting

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Delete Invoiced Purchase Return Orders**, and then choose the related link.
2. Fill in the fields as necessary, and then choose the **OK** button.
3. Alternatively, delete the individual purchase return orders manually.

## Podívejte se na související školení na webu [Microsoft Learn](/learn/paths/return-items-dynamics-365-business-central/)

## Viz také
[Purchasing](purchasing-manage-purchasing.md)  
[Record Purchases](purchasing-how-record-purchases.md)  
[Correct or Cancel Unpaid Purchase Invoices](purchasing-how-correct-cancel-unpaid-purchase-invoices.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Process Sales Returns or Cancellations](sales-how-process-sales-returns-cancellations.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]