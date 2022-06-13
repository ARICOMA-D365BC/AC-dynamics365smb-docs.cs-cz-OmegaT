---
title: Use Excel to import data into Business Central
description: Use the default configuration package to add customer data in Excel and import the data back into Business Central.
author: edupont04

ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: migration, Excel
ms.date: 05/10/2022
ms.author: edupont

---
# Import Business Data from Other Finance Systems

When you sign up for [!INCLUDE[prod_short](includes/prod_short.md)], you can choose to create an empty company so that you can upload your own data and to test your new [!INCLUDE[prod_short](includes/prod_short.md)] company. Depending on the finance solution that your business uses today, you can transfer information about customers, vendors, inventory, and bank accounts.  

From the Role Center, you can start an assisted setup guide that helps you transfer the business data from an Excel file or from other formats. The type of files you can upload depends on the extensions that are available. For example, you can migrate data from QuickBooks because [!INCLUDE[prod_short](includes/prod_short.md)] includes an extension that handles the conversion from QuickBooks. If you want to migrate data from other finance solutions, you must either check if an extension is available for that solution or import from Excel.  

[!INCLUDE[prod_short](includes/prod_short.md)] includes templates for accounts, customers, vendors, and inventory items that you can choose to apply when you import your data. To import item pictures, you can use a dedicated function on the **Inventory Setup** page. For more information, see [Import Multiple Item Pictures](inventory-how-import-item-pictures.md).

> [!TIP]  
> We recommend that you use data migration wizards to import data from Dynamics GP, Dynamics NAV, or QuickBooks. For more information, see [Migrate On-Premises Data to Business Central Online](/dynamics365/business-central/dev-itpro/administration/migrate-data) in the administration content, or [QuickBooks Data Migration](ui-extensions-quickbooks-data-migration.md).

## Work with Data in Excel

You can use the Excel add-in to prepare existing content for use in [!INCLUDE [prod_short](includes/prod_short.md)]. For more information, see [Viewing and Editing in Excel From Business Central](across-work-with-excel.md).  

## Import Data from Configuration Packages

For larger implementation work, you can set up solution-specific configuration packages. For more information, see [Set Up Company Configuration Packages](/dynamics365/business-central/dev-itpro/administration/set-up-standard-company-configuration-packages) (in English only) in the administration content.  

> [!NOTE]  
> Working with configuration packages is advanced functionality, and we recommend that you contact your reselling partner. For more information, see [Set Up Company Configuration Packages](/dynamics365/business-central/dev-itpro/administration/set-up-standard-company-configuration-packages) (in English only).

You can import master data and some transactional data from other finance systems based on the default configuration package in [!INCLUDE[prod_short](includes/prod_short.md)]. On the **Configuration Packages** page, you can work with the package to import and validate the data before you apply the package. For example, you can export the configuration package to Excel and set up your data there. Then, you can import the data from Excel again. The package consists of 27 tables, including master data such as customers, vendors, items, and accounts, other basic setup tables such as shipping methods, and transactions tables such as sales header and lines.  

When you export the default configuration package to Excel, the generated workbook contains a worksheet for each table in the package. To simplify your tasks, you can take advantage of the XML manipulation tools that are built into Excel. You can also use Excel built-in functions to help with data formatting and to put data in the correct cell. For example, add a blank worksheet and copy the legacy data to it. Then make an Excel formula to map data in the transformation worksheet between the fields in the exported worksheet and customer legacy data. After you have mapped all of the data, copy the range of data onto the table worksheet.  

> [!IMPORTANT]  
> Do not change the columns in the worksheets. If they are moved, changed, or deleted, the worksheet cannot be imported into [!INCLUDE[prod_short](includes/prod_short.md)].

> [!NOTE]
> Fields of type Blob cannot be exported/imported using Excel.

### Tables in the Default Configuration Package

The default configuration package supports the following tables:

- Payment Terms
- Customer Price Group
- Shipment Method
- Salesperson/Purchaser
- Location
- GL Account
- Customer
- Vendor
- Item
- Sales Header
- Sales Line
- Purchase Header
- Purchase Line
- Gen. Journal Line
- Item Journal Line
- Customer Posting Group
- Vendor Posting Group
- Inventory Posting Group
- Unit of Measure
- Gen. Business Posting Group
- Gen. Product Posting Group
- General Posting Setup
- Territory
- Item Category
- Sales Price
- Purchase Price

## See Also

[Migrating On-Premises Data to Business Central Online (in English only)](/dynamics365/business-central/dev-itpro/administration/migrate-data)  
[Set Up Company Configuration Packages](/dynamics365/business-central/dev-itpro/administration/set-up-standard-company-configuration-packages)  
[QuickBooks Data Migration](ui-extensions-quickbooks-data-migration.md)  
[Import Multiple Item Pictures](inventory-how-import-item-pictures.md)

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]