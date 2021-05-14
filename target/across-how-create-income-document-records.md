---
title: Create Records of Incoming Documents| Microsoft Docs
description: You can create records of incoming documents, such as e-invoices, and manage OCR tasks, eCommerce, and document exchange.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: electronic document, e-invoice, incoming document, OCR, ecommerce, document exchange, import invoice
ms.date: 04/01/2021
ms.author: edupont

---
# Vytvoření záznamu došlého dokladu
On the **Incoming Documents** page, you can use different functions to review expense receipts, manage OCR tasks, and convert incoming document files, manually or automatically, to the relevant documents or journal lines. Externí soubory lze připojit v libovolné fázi procesu, včetně zaúčtovaných dokladů a výsledných položek dodavatele, zákazníka a financí.

To record an external document in [!INCLUDE[prod_short](includes/prod_short.md)], you must first create or complete an incoming document record. Můžete to udělat ručně, nebo můžete vyfotografovat externí doklad a pak vytvořit záznam došlého dokladu s připojeným obrázkovým souborem.

Předtím než můžete použít funkce Došlých dokladů, musíte provést požadované nastavení. For more information, see [Set Up Incoming Documents](across-how-setup-income-documents.md).

## Schválení nebo odmítnutí došlých dokladů
Pokud chcete povolit uživatelům vytvářet faktury nebo řádky finančního deníku ze záznamů došlého dokladu, dokud nejsou schváleny, můžete nastavit toho, kdo musí schválit záznamy předtím, než budou zpracovány.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Incoming Documents**, and then choose the related link.
2. Select the line with the document that you want to approve or reject, and then choose the **Approve** or **Reject** actions.

If you approve the incoming document record, the **Released** check box on the incoming document line is selected. Uživatel, který je pověřen tvorbou například nákupních faktur, může zpracovat záznam.

## Vytvoření záznamu došlého dokladu pořízením fotografie
> [!NOTE]  
> The following procedure only applies to the [!INCLUDE[prod_short](includes/prod_short.md)] Tablet and Phone clients.

1. On the app bar, choose the **Create Incoming Document from Camera** tile, and then go to step 4.
2. Alternatively, on the app bar, choose the options button, choose **Incoming Documents**, and then choose **All**.
3. On the **Incoming Documents** page, choose the ellipsis button, and then choose **Create from Camera**. Fotoaparát na tabletu nebo telefonu je aktivován.
4. Take a photo of a document, such as a purchase receipt, that you want to process as an incoming document, and then choose the **OK** button.

   Vytvoří se nový záznam došlého dokladu s připojeným obrázkem.

## Připojení obrázku k záznamu došléh dokladu pomocí fotografie
> [!NOTE]  
> The following procedure only applies to the [!INCLUDE[prod_short](includes/prod_short.md)] Tablet and Phone clients.

1. On the app bar, choose the options button, choose **Incoming Documents**, and then choose **All**.
2. Otevře se karta pro existující záznam došlého dokladu.
3. On the **Incoming Document** page, choose the ellipsis button, and then choose **Attach Image from Camera**. Fotoaparát na tabletu nebo telefonu je aktivován.
4. Take a photo of a document, such as a purchase receipt, that you want to process as an incoming document, and then choose the **OK** button.

   Obrázek je připojen k záznamu došlého dokladu.

## Vytvoření záznamu došlého dokladu ručně
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Incoming Documents**, and then choose the related link.
2. Choose the **Create from File** action.
3. On the **Insert File** page, select a file, and then choose **Open**. Soubor je automaticky připojen.
4. Alternatively, choose the **New** action.
5. To attach a file, choose the **Attach File** action.
6. On the **Insert File** page, select the file that represents the incoming document in question, and then choose the **Open** button.
7. On the **Incoming Document** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## Viz také
[Process Incoming Documents](across-process-income-documents.md)  
[Incoming Documents](across-income-documents.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]