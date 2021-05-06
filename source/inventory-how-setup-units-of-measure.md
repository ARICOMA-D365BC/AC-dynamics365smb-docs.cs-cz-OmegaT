---
title: How to Set Up Item Units of Measure| Microsoft Docs
description: You can set up multiple units of measure for an item so that you can assign units of measure to the item.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: UOM
ms.date: 04/01/2021
ms.author: edupont

---
# Set Up Units of Measure

As part of setting up your [!INCLUDE [prod_short](includes/prod_short.md)], you set up general units of measure in the **Units of Measure** page. Then, when you register new items, you specify the base unit of measure on the **Item Card**. But you can also add units of measure later.  

You can set up multiple units of measure for an item so that you can assign units of measure to the item for the following purposes:

- Assign a base unit of measure on the item's item card to define how it is stored in inventory and to serve as the conversion basis for alternate units of measure.
- Assign alternate units of measure to purchase, production, or sales documents to specify how many units of the base unit of measure you handle at a time in those processes. For example, you may buy the item on pallets and only use single pieces in your production.

If an item is stocked in one unit of measure but produced in another, a production order is created that uses a manufacturing batch unit of measure to calculate the correct quantity of the components during the **Refresh Production Order** batch job. An example of a manufacturing batch unit of measure calculation is when a manufactured item is stocked in pieces but produced in tons. For more information, see [Work with Manufacturing Batch Units of Measure](production-how-to-use-the-manufacturing-batch-unit-of-measure.md).  

## To set up units of measure

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Units of Measure**, and then choose the related link.  
2. Choose the **New** action. A new empty line is inserted.  
3. Fill in the fields. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  
4. If you know that your organization will sell items with this unit of measure to customers in other countries, you can add translations.  
    1. Select the code for which you want to set up translations, and then choose the **Translations** action.
    2. In the **Language Code** field, select the drop-down arrow to see a list of available language codes. Select the language code for which you want to enter a translation, and then choose the OK button to copy the code to the field.
    3. In the **Description** field, enter the appropriate text.
5. Repeat the previous steps for any additional units of measure that you want to add.  

When you register a new item, you can choose the base unit of measure from the list of units of measure that you have now set up. You can also set up multiple units of measure for an item.  

## To set up multiple item units of measure

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.
2. Open the card of the item for which you want to set up alternate units of measure.
3. Choose the **Units of Measure** action. The **Item Units of Measure** page opens.
4. If the **Base Unit of Measure** field on the item card is filled, then that unit of measure is already set up.
5. Choose the **New** action. A new empty line is inserted.
6. In the **Code** field, enter the name of the unit of measure. Alternatively, choose the field to select from the unit of measure codes that are in the database.
7. In the **Qty. per Unit of Measure** field, enter how many units of the base unit of measure the new unit of measure contains.
8. Optionally, in the **Height**, **Width**, **Length**, and **Weight** fields, specify precise information about the size of one unit of measure so that the [!INCLUDE [prod_short](includes/prod_short.md)] can calculate how many of each item unit can be placed in any given bin. The **Cubage** field is calculated automatically based on **Height**, **Width**, and **Length**.

    If any of these fields contain a value other than 0, then that measure is used during all processes that involve placing items in a bin: put-away, movements, receipts, shipments, picks, and adjustments. [!INCLUDE [prod_short](includes/prod_short.md)] checks the sum of each physical measure of the items being put away and the items already in the bin against the maximum size or other measure that can fit into a bin, according to the bin capacity policy on the location card for this item. In other words, you must use the same unit measure for each dimension across all item units of measure - use kilograms or pounds for weight, for example, but be consistent.
9. Repeat steps 5 through 7 to set up all the alternate units of measure that you want to use in different processes for this item.

    In the **Base Unit of Measure** field at the bottom of the window, you can view or change the item's base unit of measure. You can also change the base unit of measure in the **Base Unit of Measure** field on the item card. In the **Item Units of Measure** page, the base unit of measure must have the value **1** in the **Qty. per Unit of Measure** field.

You can now use the alternate units of measure on purchase, production, and sales documents as described in the [To enter a default unit of measure code for sales and purchasing transactions](#to-enter-a-default-unit-of-measure-code-for-sales-and-purchasing-transactions) section.  

## To set up unit of measure translations

When you sell items to foreign customers, you may want to specify the unit of measure in the customer's language. You can do this after you have set up the necessary unit of measure translations.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Units of Measure**, and then choose the related link.
2. Select the code for which you want to set up translations, and then choose the **Translations** action.
3. In the **Language Code** field, select the drop-down arrow to see a list of available language codes. Select the language code for which you want to enter a translation, and then choose the OK button to copy the code to the field.
4. In the **Description** field, enter the appropriate text.
5. Repeat steps 2 through 4 for the unit of measure codes and the languages for which you want to enter translations.

## To enter a default unit of measure code for sales and purchasing transactions

If you usually buy or sell in units different from the base unit of measure, you can specify separate units of measure for purchases and sales. To do this, the units of measure must be set up on the **Item Units of Measure** page.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.
2. Open the relevant item card for which you want to specify a default sales or purchase unit of measure code.
3. For sales, on the **Invoicing** FastTab, in the **Sales Unit of Measure** field, open the **Item Units of Measure** page.
4. For purchasing, on the **Replenishment** FastTab, in the **Purch. Unit of Measure** field, open the **Item Units of Measure** page.
5. Select the code you want to set up as the default unit of measure for sales or purchasing respectively, and then choose the **OK** button.

## See Also

[Work with Manufacturing Batch Units of Measure](production-how-to-use-the-manufacturing-batch-unit-of-measure.md)  
[Register New Items](inventory-how-register-new-items.md)  
[Managing Inventory](inventory-manage-inventory.md)  
[Managing Purchasing](purchasing-manage-purchasing.md)  
[Managing Sales](sales-manage-sales.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]