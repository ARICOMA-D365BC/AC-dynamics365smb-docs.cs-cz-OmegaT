---
title: Set Up Incoming Documents| Microsoft Docs
description: Use the Incoming Documents feature to create electronic documents, manage OCR tasks, import invoices, and convert image files.
author: SorenGP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: electronic document, e-invoice, incoming document, OCR, ecommerce, document exchange, import invoice
ms.date: 04/01/2021
ms.author: edupont

---
# Nastavení došlých dokladů

If you create general journal lines from incoming document records, you must specify on the **Incoming Documents Setup** page which journal template and batch to use.

If you do not want users to create invoices or general journal lines from incoming document records unless the documents are first approved, you must set up workflow approvers.

To turn PDF and image files into electronic documents that you can convert to, for example, purchase invoices inside [!INCLUDE[prod_short](includes/prod_short.md)], you must first set up the OCR feature and enable the service. Choose a service package that is appropriate for your organization and/or country/region. Alternatively, you can create entries manually to represent the external documents.

When the Incoming Documents feature is set up, you can use different functions to review expense receipts, manage OCR tasks, and convert incoming document files, manually or automatically, to the relevant documents or journal lines. Externí soubory lze připojit v libovolné fázi procesu, včetně zaúčtovaných dokladů a výsledných položek dodavatele, zákazníka a financí. For more information, see [Processing Incoming Documents](across-process-income-documents.md).

## To set up the Incoming Documents feature

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Incoming Document Setup**, and then choose the related link.
2. Vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

As part of the setup, you must decide if you want to require approval of incoming documents. To require approval, you must set up approvers and approval workflows. If your organization does not intend to require approval, you can skip the next section.

Finally, you if you use a service to convert PDF or image files representing incoming documents, you must it set up. Otherwise, you can also skip that section.

## To set up approvers of incoming document records

Optionally, set up an approval process for the incoming documents. Approvers of incoming documents must be set up as approval workflow users.

Before you can create workflows that involve approval steps, you must set up the workflow users who are involved in approval processes. On the **Approval User Setup** page, you also set amount limits for specific types of requests and define substitute approvers to whom approval requests are delegated when the original approver is absent. For more information, see [Set Up Approval Users](across-how-to-set-up-approval-users.md).

## To set up an OCR service

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **OCR Service Setup**, and then choose the related link.
2. Vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]  
> You login data is automatically encrypted.

For more information, see [Use OCR to Turn PDF and Image Files into Electronic Documents](across-how-use-ocr-pdf-images-files.md).

## Viz také

[Zpracování došlých dokladů](across-process-income-documents.md)    
[Došlé doklady](across-income-documents.md)    
[Nákup](purchasing-manage-purchasing.md)    
[Práce s [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]