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
# Report Selection in Business Central

You can set up default reports to use to print documents for sales and purchases, such as orders, quotes, and invoices. For example, if you have a specific layout for sales invoices, you can specify that report in the **Report Selections - Sales** page so that it will be used to send or print sales invoices.  

The **Report Selections** pages specify which report will be printed in different situations. [!INCLUDE [prod_short](includes/prod_short.md)] provides default configurations, but you can change them if needed. You can also add reports to the **Report Selection** pages if you want to print more than one report per document type, for example.  

## Available report selections

[!INCLUDE [prod_short](includes/prod_short.md)] includes different **Report Selection** pages for different areas. The following table describes where you can find information about the different pages.  

|Area or task  |Learn more|
|--------------|----------|
|Example of how report selection works (Sales)|[Report selection for sales documents](#example-report-selection-for-sales-documents)|
|Default layout for emails with sales and purchase documents  |[Set Up Reusable Email Texts and Layouts for Sales and Purchase Documents](admin-how-setup-email.md#set-up-reusable-email-texts-and-layouts) |
|Define check layouts     |[Select a Check Layout](finance-how-define-check-layouts.md) |
|Define reports for VAT reporting (Germany)|[Set Up Reports for VAT and Intrastat](LocalFunctionality/Germany/how-to-set-up-reports-for-vat-and-intrastat.md) |

> [!TIP]
> Your [!INCLUDE [prod_short](includes/prod_short.md)] can include additional **Report Selection** pages, depending on your location and industry, for example. You can always check your setup by choosing the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, entering **Report Selections**, and then choose the relevant link.

The default version of [!INCLUDE [prod_short](includes/prod_short.md)] includes the following **Report Section** pages:

* **Report Selection - Sales**  
* **Report Selection - Purchase**  
* **Report Selection - Inventory**  
* **Report Selection - Cash Flow**  
* **Report Selection - Warehouse**  
* **Report Selection - Bank Account**  
* **Report Selections Reminder/Finance Charge**  
* **Report Selection - Job**  

## Example: Report selection for sales documents

The **Report Selection - Sales** page defines the default reports to use in different scenarios for each related document type. Choose a document type in the **Usage** field, and then add or review the report selection. You can set up more than one report and the order of sequence that the reports must be sent or printed in.  

[!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

Some types of documents can be sent as email attachments, and others can't. If a type of document can be sent by email, the **Report Selection** page will contain extra fields.  

For example, in the **Report Selection - Sales** and **Report Selection - Purchase** pages, the following fields help you set up emailing:

|Field name |Description  |
|-----------|-------------|
|**Use for Email Body**| Insert summarized information, such as invoice number, due date, and payment service link, in an email.        |
|**Use for Email Attachment**| Attach the related document to the email.|
|**Email Body Layout Description**|Specify the email body layout to use. Typically, the layout is a custom report layout. |

## See also

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