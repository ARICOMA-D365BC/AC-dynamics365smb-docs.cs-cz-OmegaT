---
title: Create Incoming Document Records From Docs
description: You can store external business documents by attaching the document files to the related incoming document records.
services: project-madeira
documentationcenter: ''
author: SorenGP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: electronic document, e-invoice, incoming document, OCR, ecommerce, document exchange, import invoice
ms.date: 06/25/2021
ms.author: edupont

---
# Vytváření došlých dokladů přímo z dokladů a položek
You can store external business documents in [!INCLUDE[prod_short](includes/prod_short.md)] by attaching the document files to the related incoming document records. Pokud doklad, například nákupní faktura, nezačíná svou existenci jako záznam došlého dokladu, můžete k němu později vytvořit a připojit záznam příchozího dokladu. You can also attach incoming document files to posted purchase and sales documents and to vendor, customer, and general ledger entries by using the **Incoming Document Files** FactBox in, for example, the **Posted Purchase Invoices** and **Vendor Ledger Entries** pages.

From the **Chart of Accounts** and **General Ledger Entries** pages, you can use a search function to find general ledger entries for posted purchase and sales documents that do not have incoming document records and then centrally link to existing records or create new ones with attached document files. For more information, see [Find Posted Documents without Incoming Document Records](across-how-find-posted-documents-without-income-document-records.md).

Následující postupy ukazují, jak připojit soubor k existující nákupní faktuře, která nebyla vytvořena z došlého dokladu a jak připojit soubor k položce dodavatele. Připojení souboru k zaúčtovaným nákupním nebo prodejním dokladům funguje podobným způsobem.

## Vytvoření a připojení záznamu došlého dokladu k nákupní faktuře
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices**, and then choose the related link.
2. Select the line for a purchase invoice that you want to attach a file to, and then choose the **Create Incoming Document from File** action.
3. Alternatively, select the line for a purchase invoice that you want to attach a file to, and then choose the **Attach File** action.
4. On the **Insert File** page, select the file that represents the incoming document in question, and then choose the **Open** button.

## Vytvoření a připojení záznamu došlého dokladu z položky dodavatele
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendor Ledger Entries**, and then choose the related link.
2. Select a line for a vendor ledger entry that you want to attach a file to, and then choose the **Create Incoming Document from File** action.
3. Alternatively, select a line for a vendor ledger entry that you want to attach a file to, and then choose the **Attach File** action.
4. On the **Insert File** page, select the file that represents the incoming document in question, and then choose the **Open** button.

## Odebrání propojení záznamu došlého dokladu s zaúčtovaným dokladem
Přílohy souborů z nezaúčtovaných dokladů můžete kdykoli odebrat odstraněním souvisejícího záznamu došlého dokladu. Pokud je doklad zaúčtován, musíte nejprve odebrat propojení z souboru došlého dokladu.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Incoming Documents**, and then choose the related link.
2. Select the line for an incoming document record connected to a posted document that you want to remove, and then choose the **Remove Reference to Record** action.

Připojení k zaúčtovanému dokladu bude odebráno. Nyní můžete přistoupit k připojení dalšího souboru došlého dokladu k zaúčtovanému dokladu, tak jak je popsáno v tomto tématu.

## Viz také
[Process Incoming Documents](across-process-income-documents.md)  
[Incoming Documents](across-income-documents.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]