---
title: Importing Many Item Pictures from a ZIP File
description: To import multiple item pictures give picture files names corresponding to item numbers, compress them to a ZIP file, and use the Import Item Pictures page.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: product, image
ms.search.form: 30, 461
ms.date: 06/16/2021
ms.author: edupont

---
# Hromadný import obrázků zboží
Můžete hromadně importovat obrázky zboží. Simply name your picture files with names corresponding to your item numbers, compress them to a zip file, and then use the Import Item Pictures page to manage which item pictures to import.

Podporovány jsou všechny běžné formáty souborů.

## Pojmenování souborů obrázků podle názvů zboží a příprava ZIP souboru
1. V místě, kde jsou obrázky zboží uloženy, pojmenujte každý soubor podle čísla souvisejícího zboží. Například:

   |Číslo zboží|Název souboru|
   |-|-|
   |1000|1000.bmp|
   |1001|1001.bmp|
   |1002|1002.bmp|

2. Seskupte všechny soubory do jednoho souboru ZIP. For example, in Windows Explorer, select the files, and then choose **Send to**, **Compressed (zipped) folder**.

## Import obrázků zboží
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Setup**, and then choose the related link.
2. Choose the **Import Item Pictures** action.
3. In the **Select a ZIP file** field, select the relevant ZIP folder, and then choose the **Open** button.

   A line for each item and picture is created on the **Import Item Pictures** page.

   > [!NOTE]
   > For item cards that already have a picture, the **Picture Already Exists** check box is selected. If you do not want any existing pictures to be replaced, deselect the **Replace Pictures** check box. Pokud nechcete, aby byly jednotlivé existující obrázky nahrazeny, odstraňte dotyčné řádky.

3. Choose the **Import Pictures** action.

The **Import Status** field is updated to show if the picture import was skipped or completed.

## Viz také
[Register New Items](inventory-how-register-new-items.md)  
[Create Number Series](ui-create-number-series.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]