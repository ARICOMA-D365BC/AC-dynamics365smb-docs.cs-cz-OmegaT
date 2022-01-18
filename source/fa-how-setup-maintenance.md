---
title: Set Up FA Maintenance| Microsoft Docs
description: To manage fixed asset repairs and service, you specify general maintenance information, codes for the type of work, and a posting account for costs.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: repair, service
ms.date: 04/01/2021
ms.author: edupont

---
# Set Up Fixed Asset Maintenance
To manage fixed asset maintenance, you must first set up some general maintenance information, a posting account for maintenance costs, and maintenance codes for types of work, such as Routine Service or Repair.

## To set up general maintenance information
If you set up the fields for maintenance, you can post maintenance expenses from the fixed asset journal.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Assets**, and then choose the related link.
2. Select the fixed asset that you to define insurance coverage for, and then choose the **Edit** action.
3. On the **Maintenance** FastTab, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## To set up maintenance codes
When you post maintenance costs from a general journal, you fill in the **Maintenance Code** field to record what kind of maintenance has been performed, such as routine service or repair.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Maintenance**, and then choose the related link.
2. On the **Maintenance** page, set up codes for different types of maintenance work.

## To set up maintenance expense accounts
To post maintenance costs, you must first enter an account number on the **FA Posting Groups** page.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Posting Groups**, and then choose the related link.
2. Fill in the **Maintenance Expense Account** field for each posting group.

> [!NOTE]  
>   To define that maintenance costs are allocated to departments or projects, set up an allocation keys. For more information, see [Set Up General Fixed Assets Features](fa-how-setup-general.md).

## See Also
[Setting Up Fixed Assets](fa-setup.md)  
[Fixed Assets](fa-manage.md)  
[Finance](finance.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]