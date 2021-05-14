---
title: Work with Incoming Documents| Microsoft Docs
description: You can manage incoming external business documents, such as payment receipts or PDFs, manage OCR tasks, and convert files to electronic documents and records.
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
# Došlé doklady

Some business transactions are not recorded in [!INCLUDE[prod_short](includes/prod_short.md)] from the outset. Místo toho se do vaší společnosti dostane externí obchodní doklad jako příloha e-mailu nebo papírová kopie, kterou naskenujete. To je typické pro nákupy, kde takové soubory příchozích dokladů představují potvrzení o platbách za výdaje nebo malé nákupy.

From PDF or image files representing incoming documents, you can have an external OCR service (Optical Character Recognition) generate electronic documents that can then be converted to document records inside [!INCLUDE[prod_short](includes/prod_short.md)]. Choose a service package that is appropriate for your organization and/or country/region. Alternatively, you can create entries manually to represent the external documents.

On the **Incoming Documents** page, you can use different functions to review expense receipts, manage OCR tasks, and convert incoming document files, manually or automatically, to the relevant documents or journal lines. Externí soubory lze připojit v libovolné fázi procesu, včetně zaúčtovaných dokladů a výsledných položek dodavatele, zákazníka a financí.

Proces došlých dokladů se může skládat z následujících hlavních činností:

* Record the external documents inside [!INCLUDE[prod_short](includes/prod_short.md)] by creating lines on the **Incoming Documents** page in either of the following ways:
   * Ručně pomocí jednoduchých funkcí, buď z počítače nebo z mobilního zařízení, jedním z následujících způsobů:
      * Use the **Create from File** button, and then fill relevant fields on the **Incoming Document** page. Soubor je automaticky připojen.
      * Use the **New** button, and then fill relevant fields on the **Incoming Document** page and manually attach the related file.
      * From a tablet or phone, use the **Create from Camera** button to create a new incoming document record, and then send the image to the OCR service, for example.
   * Automaticky přijetím dokladu ze služby OCR jako elektronického dokladu poté, co jste odeslali e-mailem související soubor PDF nebo obrázek službě OCR. The **Financial Information** FastTab is automatically filled on the **Incoming Document** page.
* Use the OCR service to have PDF or image files turned into electronic documents that can be converted to document records in [!INCLUDE[prod_short](includes/prod_short.md)].
* Vytvořte nové dokumenty nebo řádky finančního deníku pro záznamy příchozích dokladů zadáním informací při jejich čtení z příchozích souborů.
* Připojte příchozí soubory k nákupním a prodejním dokladům v jakémkoli stavu, včetně položek dodavatele, zákazníka a financí, které vyplývají z účtování.
* View incoming document records and their attachments from any purchase and sales document or entry, or find all general ledger entries without incoming document records from the **Chart of Accounts** page.

| Viz | Také |
| --- | --- |
| Nastavení funkce Došlých dokladů a nastavení služby OCR | [Set Up Incoming Documents](across-how-setup-income-documents.md) |
| Vytváření záznamů došlých dokladů, připojování souborů, použití služby OCR k přeměně PDF souborů na elektronické doklady, převedení elektronických dokladů na evidenci dokladů, kontrola záznamů došlých dokladů z zaúčtovaných prodejních a nákupních dokladů. | [Processing Incoming Documents](across-process-income-documents.md) |

## Zobrazit související školení na webu [Microsoft Learn](/learn/modules/incoming-documents-dynamics-365-business-central/index)

## Viz také

[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]