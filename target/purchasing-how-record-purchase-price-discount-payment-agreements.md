---
title: Record Special Purchase Prices and Discounts
description: You can define different or alternate prices and discount agreements and apply them to purchase documents for vendors.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: special price, alternate price, pricing
ms.search.form: 26, 1346, 7012, 7014, 7017, 7018, 7189, 7190
ms.date: 04/01/2021
ms.author: bholtorf

---
# Record Special Purchase Prices and Discounts
> [!NOTE]
> In 2020 release wave 2 we released streamlined processes for setting up and managing prices and discounts. Pokud jste nový zákazník a používáte tuto verzi, používáte nové prostředí. If you're an existing customer, whether you are using the new experience depends on whether your administrator has enabled the **New sales pricing experience** feature update in **Feature Management**. Další informace naleznete v tématu [Povolení nadcházejících funkcí s předstihem](/dynamics365/business-central/dev-itpro/administration/feature-management).

The different price and discount agreements that apply when you buy from different vendors must be defined so that the agreed rules and values are applied to purchase documents that you create for the vendors.

When you have recorded special prices and line discounts for sales and purchases, [!INCLUDE[prod_short](includes/prod_short.md)] ensures that your profit on item trade is always optimal by automatically calculating the best price on sales and purchase documents and on job and item journal lines. Pro více informací navštivte [Výpočet nejlepší ceny](purchasing-how-record-purchase-price-discount-payment-agreements.md#best-price-calculation).

Concerning prices, you can have a special purchase price inserted on purchase lines if a certain combination of vendor, item, minimum quantity, unit of measure, or starting/ending date exists.

Concerning discounts, you can set up and use two types of purchase discounts:

| Typ slevy | Popis |
| --- | --- |
| **Purchase Line Discount** | An amount discount that is inserted on purchase lines if a certain combination of vendor, item, minimum quantity, unit of measure, or starting/ending date exists. This works in the same way as for purchase prices. |
| **Fakturační sleva** | A percentage discount that is subtracted from the document total if the value amount of all lines on a purchase document exceeds a certain minimum. |

Because purchase line discounts and purchase prices are based on a combination of item and vendor, you can also enter this configuration from the item card, where the rules and values are defined. For more information, see [Register New Items](inventory-how-register-new-items.md).

## To set up a special purchase price for a vendor

#### [Aktuální zkušenosti](#tab/current-experience)

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.
2. Open the relevant vendor card, and then choose the **Prices** action.
3. Vyplňte pole na řádku podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Fill a line for each combination for which the vendor grants you a purchase line discount.

#### [Po novu](#tab/new-experience)
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.
2. Choose the vendor, and then choose the **Sales Price Lists** action.
3. Choose **New** to create a new purchase price list.
4. Na záložkáck **Obecné** a **Daň** vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
5. Chcete-li přidat zboží do seznamu, proveďte jednu z následujících akcí:
   * Chcete-li přidat více položek, vyberte možnost **Navrhnout řádky** a poté zadejte kritéria filtru, abyste určili typy položek, které chcete přidat. Volitelně můžete také zadat některá další nastavení položek, která jsou specifická pro daný ceník. V případě potřeby je můžete později změnit.
   * Chcete-li zkopírovat položky z jiného ceníku, zvolte **Kopírovat řádky** a poté vyberte ceník, který chcete zkopírovat.
   * To add items manually, in the grid, in the **Product Type** field, choose the type of product that the price list is for. V závislosti na výběru vyplňte zbývající pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
6. Chcete-li ceník začít používat, vyberte v poli **Stav** možnost **Aktivní**.

---

## To set up a line discount for a vendor
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.
2. Open the relevant vendor card, and then choose the **Line Discounts** action.

   The **Purchase Type** field is prefilled with **Vendor**, and the **Purchase Code** field is prefilled with the vendor number.
3. Vyplňte pole na řádku podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Fill a line for each combination for which the vendor grants you a purchase line discount.

## To set up an invoice discount for a vendor
When your vendors have informed you which invoice discounts they grant, enter the invoice discount code on the vendor cards and set up the terms for each code.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.
2. Open the vendor card for a vendor that will be eligible for invoice discounts.
3. Do pole **Kód fakturační Code** field, select a code for the relevant invoice discount terms to use to calculate invoice discounts for the vendor.

   > [!NOTE]  
   > Invoice discount codes are represented by existing vendor cards. This enables you to quickly assign invoice discount terms to vendors by picking the name of another vendors who will have the same terms.

   Proceed to set up new the purchase invoice discount terms.
4. On the **Vendor Card** page, choose the **Invoice Discounts** action. The **Vend. slevy zákazníka** se otevře.
5. Do pole **Kód měny** zadejte kód měny, na kterou se vztahují podmínky slevy na faktuře na řádku. Chcete-li nastavit podmínky fakturační slevy v USD, ponechte pole prázdné.
6. Do pole **Minimální částka** zadejte minimální částku, kterou musí mít faktura nárok na slevu.
7. Do pole **Procento slevy** zadejte fakturační slevu jako procento částky faktury.
8. Repeat steps 5 through 7 for each currency that the vendor will receive a different invoice discount for.

The invoice discount is now set up and assigned to the vendor in question. When you select the vendor code in the **Invoice Disc. Code** field on other vendor cards, the same invoice discount is assigned to those vendor.

## To choose a principle for posting purchase discounts
When you post a purchase invoice that includes one or more discounts, you can choose between two principles for posting discount amounts. You can post discounts separately or you can subtract discounts from invoice discounts.

Before you can do this, you must have already set up the necessary accounts for posting discount amounts in the chart of accounts. You must also check that you have entered the correct account numbers in the general posting setup in the **Purch. Line Disc. Account** and **Purch. Zásoby skonta Account** fields.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchases & Payables Setup**, and then choose the related link.
2. In the **Discount Posting** field, choose one of the following principles for posting discounts.

| **Discount Posting Principle** | **Fakturační sleva** | **Řádková sleva** |
|------------------------------------|--------------------------|-----------------------|  
| **All Discounts** | Posted separately | Posted separately |
| **Invoice Discounts** | Posted separately | Subtracted |
| **Line Discounts** | Subtracted | Posted separately |
| **No Discounts** | Subtracted | Subtracted |

## Purchase Invoice Discounts and Service Charges
If you have fixed terms for invoice discounts with any vendors, you can enter them for those vendors. Then the discount will be calculated when you fill in a purchase invoice.

Before you can use invoice discounts with purchases, you must specify the vendors that offer you the discounts.

You link discount percentages to specific invoice amounts in **Vend. Invoice Discounts** pages. You can enter any number of percentages in each page. Each vendor can have its own page, or you can link several vendors to the same page.

In addition to a discount percentage, you can link a service charge amount to a specific invoice amount.

You can define the terms of the invoice discount in LCY for domestic vendors and in foreign currency for foreign vendors.

You can choose to have [!INCLUDE[prod_short](includes/prod_short.md)] automatically calculate the invoice discounts for quotes, blanket orders, orders, invoices, or credit memos.

> [!TIP]  
> Before you enter this information, it is a good idea to prepare an outline of the discount structure that you want to use. This makes it easier to see which vendors can be linked to the same invoice discount page. The fewer pages that you have to set up, the faster that you can enter the basic information.

## Best Price Calculation
When you have recorded special prices and line discounts for sales and purchases, [!INCLUDE[prod_short](includes/prod_short.md)] ensures that your profit on item trade is always optimal by automatically calculating the best price on sales and purchase documents and on job and item journal lines.

The best price is the lowest permissible price with the highest permissible line discount on a given date. [!INCLUDE[prod_short](includes/prod_short.md)] automatically calculates this when it inserts the unit price and the line discount percentage for items on new document and journal lines.

> [!NOTE]  
> The following describes how the best price is calculated for sales. The calculation is the same for purchases.

1. [!INCLUDE[prod_short](includes/prod_short.md)] checks the combination of the bill-to customer and the item and then calculates the applicable unit price and line discount percentage, using the following criteria:

   - Does the customer have a price/discount agreement, or does the customer belong to a group that does?
   - Is the item or the item discount group on the line included in any of these price/discount agreements?
   - Is the order date (or the posting date for the invoice and credit memo) within the starting and ending date of the price/discount agreement?
   - Is a unit of measure code specified? If so, [!INCLUDE[prod_short](includes/prod_short.md)] checks for prices/discounts with the same unit of measure code, and prices/discounts with no unit of measure code.

2. [!INCLUDE[prod_short](includes/prod_short.md)] checks if any price/discount agreements apply to information on the document or journal line, and then inserts the applicable unit price and line discount percentage, using the following criteria:

   - Is there a minimum quantity requirement in the price/discount agreement that is fulfilled?
   - Is there a currency requirement in the price/discount agreement that is fulfilled? If so, the lowest price and the highest line discount for that currency are inserted, even if LCY would provide a better price. If there is no price/discount agreement for the specified currency code, [!INCLUDE[prod_short](includes/prod_short.md)] inserts the lowest price and the highest line discount in LCY.

If no special price can be calculated for the item on the line, then either the last direct cost or the unit price from the item card is inserted.

## Zobrazit související školení na webu [Microsoft Learn](/learn/modules/set-up-prices-discounts-dynamics-365-business-central/index)

## Viz také
[Setting Up Purchasing](purchasing-setup-purchasing.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]