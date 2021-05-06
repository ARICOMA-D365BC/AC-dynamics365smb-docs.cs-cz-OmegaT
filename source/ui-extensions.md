---
title: Installing Extensions to Customize Business Central
description: Learn about adding functionality and customizing Business Central by installing extensions.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: app, add-in, manifest, customize
ms.date: 04/01/2021
ms.author: edupont

---
# Customizing Business Central Online Using Extensions

You can change [!INCLUDE[prod_short](includes/prod_short.md)] online by installing extensions that add functionality, changes behavior, or gives you access to new online services, for example.

> [!NOTE]
> To install extensions from AppSource or add per-tenant extensions, you must have the right permissions. You must either be a member of the D365 EXTENSION MGT user group or you must have the D365 EXTENSION MGT permission set. If you are an administrator, you can assign user groups and permissions to other users in your company.

To use the functionality that is provided by an extension, such as opening pages, running reports, selecting actions, and so on, you must be assigned the permission sets that are installed as part of the extension.

> [!IMPORTANT]  
> The upload of per-tenant extensions and the installation of AppSource extensions is not supported through the **Extension Management** page for on-premise installations. You cannot install AppSource extensions on-premises, including in Docker-based deployments.

When you first launch [!INCLUDE[prod_short](includes/prod_short.md)], some extensions are already installed for you. Over time, more extensions will be made available to you, and you can then choose if you want to use the extension or not.

For example, Microsoft provides an extension that provides integration with PayPal Payments Standard. This extension is installed by default.
But if another extension is made available that offers integration with another payment service, you can install the new extension and then choose which of the two services to use.  

You manage the extensions on the **Extension Management** page. You can access this page from Home. Alternatively, choose the **Search for Page or Report** icon ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") in the top right corner, enter **Extension**, and then choose the related link. For more information, see [Installing and Uninstalling Extensions](ui-extensions-install-uninstall.md).

> [!NOTE]  
> If you think you should have access to an extension but you cannot find its functionality, check the **Extension Management** page - if the extension is not listed there, you can install it as described in the following section.  

> [!NOTE]  
> Sign in to [AppSource.microsoft.com](https://appsource.microsoft.com/) using the email account that you use for [!INCLUDE[prod_short](includes/prod_short.md)] online. Use the same email account for other services and products for a smooth experience.  

You can also get to the marketplace from inside [!INCLUDE[prod_short](includes/prod_short.md)]. On the **Extension Management** page, you can see the extensions that are currently installed, and you can open the **Extension Marketplace** page that shows the [!INCLUDE[prod_short](includes/prod_short.md)] extensions that are currently available in AppSource. If you choose the *More apps* link, you are taken to [AppSource.microsoft.com](https://appsource.microsoft.com/marketplace/apps?product=dynamics-365%3Bdynamics-365-business-central&page=1).  

If you choose an extension, you can read about what the extension does, and you can access Help for the extension to learn more. When you choose to get an extension, you must agree to the terms of use. If you get the extension from the AppSource website, you will be signed in to [!INCLUDE[prod_short](includes/prod_short.md)] to complete the installation.  

When you install an extension, you might have to set it up, such as specifying an account for use with the **PayPal Payments Standard for [!INCLUDE[prod_short](includes/prod_short.md)]** extension.
Other extensions simply add fields to an existing page, or they add a new page, for example.   

If you uninstall an extension, and you then change your mind, you can install it again. When you uninstall an extension that you have been using, the data is preserved so that if you install the extension again, your data is still available. There are some extensions that are required. You are prevented from uninstalling these from the **Extension Management** page. If you try, an error message appears.  

Some extensions are provided by Microsoft, and other extensions are provided by [other companies](ui-extensions-other.md). All extensions are tested before they are made available to you, but we recommend that you access the links that are provided with each extension to learn more about the extension before you choose to install it.  

Microsoft provides the following extensions:  

* [AMC Banking 365 Fundamentals Extension](ui-extensions-amc-banking.md)
* [Ceridian Payroll](ui-extensions-ceridian-payroll.md)
* [Company Hub](ui-extensions-company-hub.md)  
* [Dynamics GP Data Migration](ui-extensions-dynamicsgp-data-migration.md)
* [Envestnet Yodlee Bank Feeds](ui-extensions-yodlee-bank-feeds.md)
* [Essential Business Insights](ui-extensions-essential-business-insights.md)
* [Image Analyzer](ui-extensions-image-analyzer.md)
* [Intelligent Cloud](ui-extensions-data-replication.md)
* [Intelligent Cloud Base](ui-extensions-intelligent-cloud.md)  
* [Late Payment Predictions](ui-extensions-late-payment-prediction.md)
* [Microsoft Pay](ui-extensions-microsoft-pay-payments.md)
* [PayPal Payments Standard](ui-extensions-paypal-payments-standard.md)
* [QuickBooks Data Migration](ui-extensions-quickbooks-data-migration.md)
* [QuickBooks Online Data Migration](ui-extensions-quickbooks-online-data-migration.md)
* [Quickbooks Payroll File Import](ui-extensions-quickbooks-payroll.md)
* [Sales and Inventory Forecast](ui-extensions-sales-forecast.md)
* [VAT Group](ui-extensions-vat-group.md)
* [WorldPay Payments Standard](ui-extensions-worldpay-payments-standard.md)
* [DK - C5 Data Migration](ui-extensions-c5-data-migration.md)
* [DK - Payments and Reconciliations](ui-extensions-payments-reconciliation-formats-dk.md)
* [DK - Tax File Formats](ui-extensions-tax-file-formats-dk.md)
* [The GetAddress.io UK Postcodes Extension](LocalFunctionality/UnitedKingdom/ui-extensions-getaddressio.md)  
* [US/CA/UK/AU/NZ/ZA - Send Remittance Advice](ui-extensions-send-remittance-advice.md)

> [!NOTE]  
> You can keep an eye out for new extensions from Microsoft and other suppliers at [AppSource.microsoft.com](https://appsource.microsoft.com/marketplace/apps?product=dynamics-365%3Bdynamics-365-business-central&page=1).


## Extensions and data transfer

As the following extensions are communicating with other services they may transfer data out of the geography of the [!INCLUDE[prod_short](includes/prod_short.md)] environment:

* AMC Banking 365 Fundamentals Extension
* Image Analyzer
* Late Payment Prediction
* PayPal Payments Standard
* Sales and Inventory Forecast
* WorldPay Payments Standard

This also applies to some functionality in the base application, such as the following capabilities:

* Cash Flow Forecast
* Document Exchange Service
* Dataverse connections
* OCR Service
* Online Map
* EU VAT Reg. No. Service

## See Also

[Customize Business Central](ui-customizing-overview.md)  
[Business Central Extensions by Other Providers](ui-extensions-other.md)  
[Set Up the Envestnet Yodlee Bank Feeds Service](bank-how-setup-bank-statement-service.md)  
[Enable Customer Payment Through PayPal](sales-how-enable-payment-service-extensions.md)  
[Migrating Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Setting Up the GetAddress.io UK Postal Code extension](LocalFunctionality/UnitedKingdom/uk-setup-postal-code-service.md)  
[[!INCLUDE[prod_short](includes/prod_short.md)] Extensions by Other Providers](ui-extensions-other.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]
