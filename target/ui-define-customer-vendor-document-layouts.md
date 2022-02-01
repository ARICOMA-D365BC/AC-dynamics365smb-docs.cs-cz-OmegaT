---
title: Assign Customers or Vendors Document Layouts
description: When custom report layouts are defined, you can select them from customer and vendor cards to specify they aer used for the customer or vendor in question.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customized report, document layout, logo, personalize
ms.date: 06/24/2021
ms.author: edupont

---
# Definování rozložení sestav pro zákaníky a dodavatele
When custom report layouts are defined, you can select them from customer and vendor cards to specify which layouts will be used for different types of documents that you create for the customer or vendor in question. The value in the **Usage** field, defines which process the document layout will be used for, such as **Reminder**, **Shipment**, and **Confirmation**.

Kromě nastavení rozvržení, která se mají použít pro vybraný doklad, můžete ušetřit čas při odesílání dokladů různým zákazníkům nebo dodavatelům nastavením e-mailových adres konkrétních kontaktů pro použití s ​​konkrétními dokumenty. Například výkazy zákazníků budou odeslány kontaktům účetních, prodejní objednávky odběratelům a nákupní objednávky prodejcům nebo účetím.

ři definování rozložení dokladu pro zákazníka nebo dodavatele můžete také zadat e-mailovou adresu kontaktní osoby, která musí dokument obdržet. You can quickly do this with the **Select Email from Contacts** function, which automatically filters to contact email addresses registered for the customer or vendor in question.

Before you can define which document layout to use for which processes, and which contact to send the document to, you must load all the available reports (documents) from the **Report Selections** page. You can quickly do this with the **Copy from Report Selection** function.

Následující text popisuje, jak definovat rozložení prodejních dokladů z karty zákazníka. Postup je stejný pro rozložení nákupních dokladů z karty dodavatele.

## Povolení všech dostupných prodejních dokladů pro zákazníka
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Otevřete kartu zákazníka, pro kterou chcete definovat rozvržení dokladu v rámci jednoho obchodního procesu.
3. On the **Customer Card** page, choose the **Document Layouts** page.
4. On the **Document Layouts** page, choose the **Copy from Report Selection** action.

The **Document Layouts** page for the customer in question is filled with all the report layouts for sales that exist in the system. For more information about they were created, see [Create and Modify Custom Report Layouts](ui-how-create-custom-report-layout.md).

Nyní můžete pokračovat v úpravě seznamu pomocí vlastních rozložení sestav nebo e-mailových adres pro kontakty, kterým musí být doklady odeslány.

## Výběr vlastního rozvržení sestavy, které se použije pro prodejní doklad
If one or more of the report layouts that are defined in the **Document Layouts** page for the customer do not have a custom report layout defined, then you can quickly do that.

1. On the **Document Layouts** page, on the line for a report layout that you want to use a custom layout for, choose the **Custom Layout Description** field. Toto pole je vyplněno, pokud je rozložení zákazníka již vybráno, nebo prázdné.
2. On the **Custom Report Layouts** page, select the special document layout that you want to use for the sales document type in question. For more information, see [Create and Modify Custom Report Layouts](ui-how-create-custom-report-layout.md).

## Nastavení, který kontakt obdrží rozložení dokladu pro zákazníka
You can save time when sending documents to different customers or vendor contacts by specifying contact email addresses on the different lines on the **Document Layouts** page. Například výkazy zákazníků budou odeslány kontaktům účetních, prodejní objednávky odběratelům a nákupní objednávky prodejcům nebo účetím.

1. On the **Document Layouts** page, on the line for a report layout that you want to send to a specific contact for the customer, choose the **Select Email from Contacts** action.
2. On the **Contacts** page, select the line for the relevant contact, and then choose the **OK** button.

E-mailová adresa kontaktu je nyní vložena na řádku rozvržení dokladu, takže dotyčný prodejní doklad, například upomínka, je vždy zaslán tomuto kontaktu ve společnosti zákazníka.

## Viz také
[Update Custom Report Layouts](ui-update-report-layouts.md)  
[Create and Modify Custom Report Layouts](ui-how-create-custom-report-layout.md)  
[Import and Export a Custom Report or Document Layout](ui-how-import-and-export-report-layout.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Managing Report Layouts](ui-manage-report-layouts.md)  
[Working with Reports, Batch Jobs, and XMLports](ui-work-report.md)  
[Working with Reports, Batch Jobs, and XMLports](ui-work-report.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]