---
title: Custom and Built-In Layouts for Reports and Documents | Microsoft Docs
description: Use report layouts to customize documents, for example, to personalize the font, logo, or page settings of PDF files you send to customers.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customized report, document layout, logo, personalize
ms.date: 04/01/2021
ms.author: edupont

---
# Správa rozvržení sestav a dokladů
Rozložení sestavy řídí obsah a formát sestavy, včetně těch datových polí datové sady sestavy, které se zobrazují v sestavě, jejich uspořádání, stylu textu, obrázků a dalších prvků. From [!INCLUDE[prod_short](includes/prod_short.md)], you can change which layout is used on a report, create new layout, or modify the existing layouts.

> [!NOTE]  
> In [!INCLUDE[prod_short](includes/prod_short.md)], the term "report" also covers externally-facing documents, such as sales invoices and order confirmations that you send to customers as PDF files.

Rozložení sestavy nastavuje zejména následující:

* The label and data fields to include from the dataset of the [!INCLUDE[prod_short](includes/prod_short.md)] report.
* Textový formát, například typ písma, velikost a barva.
* Logo společnosti a jeho pozice.
* Obecné nastavení stránky, například okraje a obrázky na pozadí.

Sestavu lze nastavit ve více rozloženích sestav, mezi kterými lze přepínat podle potřeby. Můžete použít jedno z vestavěných rozvržení přehledů nebo si můžete vytvořit vlastní rozvržení sestav a podle potřeby je přiřadit k vašim přehledům. For more information, see [Create a Custom Report or Document Layout](ui-how-create-custom-report-layout.md).

Existují dva typy rozvržení sestav, které můžete použít v sestavách - Word a RDLC.

## Přehled rozvržení sestavy aplikace Word
Rozložení sestavy aplikace Word je založeno na dokumentu aplikace Word (typ souboru DOCX). Rozložení sestav aplikace Word umožňují navrhovat rozložení sestav pomocí aplikace Microsoft Word 2013 nebo novější. Rozložení sestavy aplikace Word určuje obsah zprávy - určuje, jak jsou tyto prvky obsahu uspořádány a jak vypadají. Dokument rozložení sestavy aplikace Word obvykle používá tabulky k uspořádání obsahu, kde mohou buňky obsahovat datová pole, text nebo obrázky.

![Example of a word report layout document for NAV.](media/nav_wordreportlayout_edit_in_word_example.png "NAV_WordReportLayout_Edit_In_Word_Example")

## Přehled rozvržení RDLC
Rozložení RDLC je založeno na rozložení definic klientských sestav (typy souborů .rdlc nebo .rdl). Tato rozvržení jsou vytvářena a upravována pomocí SQL Server Report Builder. Koncepce návrhu rozvržení RDLC je podobná rozvržení aplikace Word, kde rozvržení definuje obecný formát sestavy a určuje pole z datové sady, která má být zahrnuta. Navrhování rozložení RDLC je pokročilejší než rozložení aplikace Word. For more information, see [Designing RDLC Report Layouts](/dynamics-nav/Designing-RDLC-Report-Layouts).

## Vestavěné a vlastní rozvržení sestavy
[!INCLUDE[prod_short](includes/prod_short.md)] includes several built-in layouts. Vestavěná rozvržení jsou předdefinovaná rozvržení, která jsou navržena pro konkrétní sestavy. [!INCLUDE[prod_short](includes/prod_short.md)] reports will have a built-in layout as either an RDLC report layout, Word report layout, or in some cases both. You cannot modify a built-in report layout from [!INCLUDE[prod_short](includes/prod_short.md)] but you use them as a starting point for building your own custom report layouts.

Vlastní rozvržení jsou rozvržení sestavy, která navrhujete tak, aby změnila vzhled sestavy. Obvykle vytvoříte vlastní rozvržení na základě vestavěného rozvržení, ale můžete je vytvořit od nuly nebo jako kopie z existujícího vlastního rozvržení. Vlastní rozvržení vám umožní mít více rozvržení pro stejnou sestavu, mezi nimiž podle potřeby přepínáte. For example, you can have different layouts for each [!INCLUDE[prod_short](includes/prod_short.md)] company, or you can have different layouts for the same company for specific occasions or events, like a special campaign or holiday season.

## Rozhodnutí, zda použít rozvržení sestavy Word nebo RDLC
Rozložení sestavy může být založeno buď na dokumentu aplikace Word, nebo na souboru RDLC. Rozhodování o tom, zda použít rozvržení sestavy aplikace Word nebo typ rozvržení sestavy RDLC, bude záviset na tom, jak chcete, aby generovaná sestava vypadala, a na vašich znalostech aplikace Word a SQL Server Report Builder.

Obecné koncepční koncepce rozvržení Word a RDLC jsou velmi podobné. However each type has certain design features that affect how the generated report appears in [!INCLUDE[prod_short](includes/prod_short.md)]. To znamená, že stejná sestava může vypadat odlišně při použití rozvržení sestavy aplikace Word ve srovnání s rozvržením sestavy RDLC.

Proces nastavení rozvržení sestav aplikace Word a rozvržení sestav RDLC v sestavách je stejný. Hlavní rozdíl spočívá ve způsobu úpravy rozvržení. Rozložení sestav aplikace Word je obvykle snazší vytvořit a upravit než rozvržení sestav RDLC, protože můžete použít aplikaci Word. Rozložení sestav RDLC je upraveno pomocí nástroje SQL Server Report Builder, který cílí na pokročilejší uživatele.

For information on how to change which layout to use, see [Change the Current Report Layout](ui-how-change-layout-currently-used-report.md).

## Zobrazit související školení na webu [Microsoft Learn](/learn/modules/change-documents-dynamics-365-business-central/index)

## Viz také
[Update Custom Report Layouts](ui-update-report-layouts.md)  
[Create and Modify Custom Report Layouts](ui-how-create-custom-report-layout.md)  
[Import and Export a Custom Report or Document Layout](ui-how-import-and-export-report-layout.md)  
[Define Special Document Layouts for Customers and Vendors](ui-define-customer-vendor-document-layouts.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Working with Reports, Batch Jobs, and XMLports](ui-work-report.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]