---
title: Make Drop Shipments (contains video)
description: Describes how to create a sales order linked to a purchase order to enable shipment directly from the vendor to the customer.
author: SorenGP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: direct shipment
ms.date: 04/01/2021
ms.author: edupont

---
# Vytvoření přímých dodávek

Přímá dodávka je dodávka zboží od jednoho z vašich dodavatelů přímo jednomu z vašich zákazníků.

Je-li prodejní objednávka označena jako „přímá dodávka“ a vytvoříte nákupní objednávku s uvedením zákazníka v poli **Příjemce**, **Adresa zákazníka**, můžete tyto dva doklady propojit pro poučení dodavatele, aby odeslal zboží přímo zákazníkovi.
<br><br>

> [!Video https://www.microsoft.com/en-us/videoplayer/embed/RE4mOyM?rel=0]

## Chcete-li vytvořit prodejní objednávku pro přímou dodávku

Chcete-li připravit přímou dodávku, vytvořte prodejní objednávku pro zboží a na prodejním řádku označte, že prodej vyžaduje přímou dodávku.

1. Vytvoření prodejní objednávky pro zboží. Více informací viz [Prodávání produktů](sales-how-sell-products.md).
2. Na řádku prodejní objednávky pro přímou dodávku zaškrtněte políčko **Přímá dodávka**.

> [!TIP]
> By default, the Drop Shipment check box isn't available on the lines. If it isn't, you can add it by personalizing the section of page that contains the lines. For more information, see [Personalize Your Workspace](ui-personalization-user.md).

## Chcete-li vytvořit nákupní objednávku pro přímou dodávku

To prepare a drop shipment, you indicate on the purchase order that it must be shipped to your customer, not to yourself.

1. Create a purchase order. Don't fill any fields on the lines. Pro více informací navštivte [Evidence nákupu](purchasing-how-record-purchases.md)
2. In the **Ship-to** field, select **Customer Address**.
3. In the **Customer** field, select the customer that you're selling to.
4. Choose the **Drop Shipments** action, and then choose the **Get Sales Order** action.
5. On the **Sales List** page, select the sales order that you prepared in [To create a sales order for drop shipment](#to-create-a-sales-order-for-drop-shipment).
6. Zvolte tlačítko **OK**.

The line information from the sales order is inserted on the purchase order line(s).

You can now tell your vendor to ship the items directly to the customer. For example, you might send them the order by email.

If your vendor provides a tracking number or similar information, you can add that information in a purchase order line of type *Comment*.

## To create multiple purchase orders for drop shipments

You can also use the requisition worksheet to create the purchase order for the vendor.

The advantage of using the requisition worksheet is that it can create purchase orders for all outstanding drop shipments. That means you won't have to create each one individually.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Requisition Worksheets**, and then choose the related link.
2. Choose the **Drop Shipments** action, and then choose the **Get Sales Order** action.
3. Zvolte tlačítko **OK**.
4. Review the purchase order lines, and in the **Vendor No.** field, select vendor that supplies required goods.
5. Choose the **Carry Out Action Message** action to convert reviewed lines to a purchase order.

## To view the linked purchase order from the sales order

* Select the drop-shipment sales order line, choose the **Order** action, choose the **Drop Shipment** action, and then choose the **Purchase Order** action.

## To post a drop shipment

After the vendor ships the items, you can post the sales order as shipped. You can also post the purchase order, but only with the **Receive** option until the sales order has been invoiced.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Prodejní objednávky** a poté zvolte související odkaz.
2. Open the sales order that you created in [To create a sales order for drop shipment](#to-create-a-sales-order-for-drop-shipment).
3. V poli **Množ. to Ship** field, specify how many of the order quantity to ship, the full or a partial order quantity.
4. Choose the **Post** or **Post and Send** action.
5. Choose either the **Ship** option to invoice later, or the **Ship and Invoice** option to invoice immediately.

## Viz také

[Create Special Orders](sales-how-to-create-special-orders.md)  
[Purchase Items for a Sale](purchasing-how-purchase-products-sale.md)  
[Sell Products](sales-how-sell-products.md)  
[Record Purchases](purchasing-how-record-purchases.md)  
[Sales](sales-manage-sales.md)  
[Inventory](inventory-manage-inventory.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]