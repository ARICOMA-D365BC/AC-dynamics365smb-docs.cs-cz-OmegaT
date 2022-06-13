---
title: Assign Document Layouts to Customers or Vendors
description: Use document layouts to control the appearance and format of documents such as invoices and orders that you send to customers and vendors.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customized report, document layout, logo, personalize
ms.search.form: 21, 9650
ms.date: 04/07/2022
ms.author: edupont

---
# Define Document Layouts for Customers and Vendors
Document layouts use report layouts to define the look and feel of documents that you send to customers and vendors. Business Central provides standard layouts, but you can also tailor custom layouts for each of your business partners. For more information, see [Create and Modify Custom Report Layouts](ui-how-create-custom-report-layout.md). You select standard and custom document layouts from customer and vendor cards by choosing the **Document Layouts** action. The value in the **Usage** field defines the process for which the document layout is used. For example, for customers, you might use **Reminder**, **Shipment**, and **Confirmation** types of document layouts.

Document layouts can also save you time when you send documents to customer or vendor contacts by email. For each layout that you assign to the customer or contact, you can by specify one or more contact email addresses. For example, you can send an invoice to the customer's purchasing and warehouse contacts. Adding contact email addresses is easy. On the **Document Layouts** page, the **Select Email from Contacts** action let's you choose from a list of the contact email addresses that you've registered for the customer or vendor. You can also add email addresses manually. If you enter multiple addresses, separate them with a semi-colon, and don't add spaces between the addresses.

Before you can define which document layout to use for which processes, and which contact to send the document to, you must load all the available reports (documents) from the **Report Selections** page. You can quickly load the documents by using the **Copy from Report Selection** action on the **Document Layouts** page.

The steps in the following sections describe how to define sales document layouts from the **Customer Card** page. For vendors, the steps are the same from the **Vendor Card** page.

## To load the standard document layouts for sales documents for a customer
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Open the **Customer Card** page for the customer, and then choose the **Document Layouts** action.
3. On the **Document Layouts** page, choose the **Copy from Report Selection** action.

The **Document Layouts** page displays all layouts that are available for sales documents. 

## To select a custom report layout to use for the sales document layout
If you haven't already created a custom report layout for the type of document, you'll need to do that first. For more information, see [Create and Modify Custom Report Layouts](ui-how-create-custom-report-layout.md).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Open the **Customer Card** page for the customer, and then choose the **Document Layouts** action.
3. On the **Document Layouts** page, on the line for a report layout that you want to use a custom layout for, choose the **Custom Layout Description** field.
4. On the **Custom Report Layouts** page, select the document layout that you want to use for the type of sales document. For more information, see [Create and Modify Custom Report Layouts](ui-how-create-custom-report-layout.md).

## To specify which contact will receive which document layout for a customer
To save time when you send documents to customer and vendor contacts by email, specify their email addresses on document layouts. For example, you can always send customer statements to their accountant contacts and sales orders to their purchasers, or purchase orders to vendor salespeople.

1. On the **Document Layouts** page, on the line for a report layout that you want to send to a specific contact for the customer, choose the **Select Email from Contacts** action.
2. On the **Contacts** page, select one or more contacts, and then choose **OK**.

## See Also  
[Update Custom Report Layouts](ui-update-report-layouts.md)  
[Create and Modify Custom Report Layouts](ui-how-create-custom-report-layout.md)  
[Import and Export a Custom Report or Document Layout](ui-how-import-and-export-report-layout.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Managing Report Layouts](ui-manage-report-layouts.md)  
[Work with Reports, Batch Jobs, and XMLports](ui-work-report.md)  
[Work with Reports, Batch Jobs, and XMLports](ui-work-report.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]