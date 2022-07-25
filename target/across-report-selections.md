---
title: Report Selection in Business Central
description: Learn about how to set up the reports that you use to print various types of documents in Business Central.
author: edupont04
ms.topic: conceptual
ms.search.keywords: setup, reporting
ms.search.form: 306, 307, 347, 385, 524, 865, 5932, 7401, 7355, 99000917
ms.date: 03/11/2022
ms.author: edupont

---
# Výber sestav v Business Central

You can set up default reports to use to print documents for sales and purchases, such as orders, quotes, and invoices. Máte-li například určité rozložení pro prodejní faktury, můžete tuto sestavu zadat na stránce **Výběr sestav - prodej**, aby bylo použito rozložení k odesílání nebo tisku prodejních faktur.

Stránky **Výběry sestav** určují, které sestavy se vytisknou v různých situacích. [!INCLUDE [prod_short](includes/prod_short.md)] provides default configurations, but you can change them if needed. Můžete například přidat sestavy na stránky **Výběry sestav**, pokud chcete, například, vytisknout více než jednu sestavu za každý typ dokladu.

## Dostupné výběry sestav

[!INCLUDE [prod_short](includes/prod_short.md)] obsahuje růžné **Výběry sestav** pro různé oblasti. The following table describes where you can find information about the different pages.

| Oblast nebo úkol | Zjistěte více |
|--------------|----------|
| Příklad, jak fungují Výběry sestav (Prodej) | [Výběry sestav pro prodejní doklady](#example-report-selection-for-sales-documents) |
| Výchozí rozložení e-mailů s prodejními a nákupními doklady | [Nastavení opakovaně použitelných e-mailů a rozvržení pro prodejní a nákupní doklady](admin-how-setup-email.md#set-up-reusable-email-texts-and-layouts) |
| Definice rozvržení šeků | [Výběr rozvržení šeků](finance-how-define-check-layouts.md) |
| Definice sestavy pro vykazování DPH (Německo) | [Nastavení sestav pro DPH a intrastat](LocalFunctionality/Germany/how-to-set-up-reports-for-vat-and-intrastat.md) |

> [!TIP]
> Váš [!INCLUDE [prod_short](includes/prod_short.md)] může zahrovat další stránky **Výběrů sestav** v závislosti na Vaší lokalitě a odvětví. You can always check your setup by choosing the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, entering **Report Selections**, and then choose the relevant link.

Výchozí verze [!INCLUDE [prod_short](includes/prod_short.md)] obsahuje následující stránky **Výběrů sestav**:

* **Výběr sestav - prodej**
* **Výběr sestav - nákup**
* **Výběr sestav - zásoby**
* **Výběr sestav - cash flow**
* **Výběr sestav - sklad**
* **Výběry sestav bankovního účtu**
* **Výběr sestav - upomínka/penále**
* **Report Selection - Job**

## Příklad: Výběr sestavy pro prodejní doklady

Stránka **Výběr sestav - prodej** definuje výchozí sestavy, které se mají použít v různých scénářích pro každý související typ dokladu. Vyberte typ dokladu v poli **Použití** a pak přidejte nebo zkontrolujte výběr sestavy. Můžete nastavit více sestav a pořadí, ve které budou sestavy odeslány nebo vytištěny.

[!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

Some types of documents can be sent as email attachments, and others can't. If a type of document can be sent by email, the **Report Selection** page will contain extra fields.

Například, na stránkách **Výběr sestav - nákup** a **Výběr sestav - nákup** vám následující pole pomohou nastavit e-maily:

| Název pole | Popis |
|-----------|-------------|
| **Použít pro tělo e-mailu** | Insert summarized information, such as invoice number, due date, and payment service link, in an email. |
| **Použití pro přílohu e-mailu** | Attach the related document to the email. |
| **Popis rozvržení těla e-mailu** | Specify the email body layout to use. Typically, the layout is a custom report layout. |

## Viz také

[Set Up Reusable Email Texts and Layouts](admin-how-setup-email.md#set-up-reusable-email-texts-and-layouts)  
[Select a Check Layout](finance-how-define-check-layouts.md)  
[Set Up Reports for VAT and Intrastat (Germany)](LocalFunctionality/Germany/how-to-set-up-reports-for-vat-and-intrastat.md)  
[Managing Report and Document Layouts](ui-manage-report-layouts.md)  
[Define Document Layouts for Customers and Vendors](ui-define-customer-vendor-document-layouts.md)  
[Set Up Printers](ui-specify-printer-selection-reports.md)  
[Financial Reports and Analytics in Business Central](finance-reports.md)  
[Accounts Receivable Reports and Analytics in Business Central](receivables-reports.md)
[Accounts Payable Reports and Analytics in Business Central](payables-reports.md)  
[Fixed Assets Reports and Analytics in Business Central](fa-reports.md)  
[Project Reports and Analytics in Business Central](project-reports.md)  
[Sales Reports and Analytics in Business Central](sales-reports.md)  
[Purchase Reports and Analytics in Business Central](purchase-reports.md)  
[Inventory and Warehouse Reports and Analytics in Business Central](inventory-WMS-reports.md)  
[Assembly Reports and Analytics in Business Central](assembly-reports.md)  
[Production Reports and Analytics in Business Central](production-reports.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]