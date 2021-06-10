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
> Chcete-li nainstalovat rozšíření z AppSource nebo přidat rozšíření na tenanta, musíte mít správná oprávnění. Musíte být buď členem skupiny uživatelů D365 EXTENSION MGT, nebo musíte mít sadu oprávnění D365 EXTENSION MGT. Pokud jste správce, můžete přiřadit skupiny uživatelů a oprávnění ostatním uživatelům ve vaší společnosti.

Chcete-li použít funkce poskytované rozšířením, jako je otevírání stránek, spouštění sestav, výběr akcí a další, musíte mít přiřazené sady oprávnění, které jsou nainstalovány jako součást rozšíření.

> [!IMPORTANT]  
> The upload of per-tenant extensions and the installation of AppSource extensions is not supported through the **Extension Management** page for on-premise installations. You cannot install AppSource extensions on-premises, including in Docker-based deployments.

When you first launch [!INCLUDE[prod_short](includes/prod_short.md)], some extensions are already installed for you. Over time, more extensions will be made available to you, and you can then choose if you want to use the extension or not.

Společnost Microsoft například poskytuje rozšíření, které zajišťuje integraci s PayPal Payments Standard. This extension is installed by default.
But if another extension is made available that offers integration with another payment service, you can install the new extension and then choose which of the two services to use.

You manage the extensions on the **Extension Management** page. Na tuto stránku se dostanete z Domovské stránky. Případně vyberte ikonu **Hledat stránku nebo sestavu** Žárovku, která otevře funkci Řekněte mi ![](media/ui-search/search_small.png "Řekněte mi, co chcete udělat") v pravém horním rohu zadejte **Rozšíření** a poté vyberte související odkaz. For more information, see [Installing and Uninstalling Extensions](ui-extensions-install-uninstall.md).

> [!NOTE]  
> If you think you should have access to an extension but you cannot find its functionality, check the **Extension Management** page - if the extension is not listed there, you can install it as described in the following section.

> [!NOTE]  
> Sign in to [AppSource.microsoft.com](https://appsource.microsoft.com/) using the email account that you use for [!INCLUDE[prod_short](includes/prod_short.md)] online. Pro bezproblémové používání prostředí používejte stejný e-mailový účet.

Na marketplace se můžete také dostat z [!INCLUDE[prod_short](includes/prod_short.md)]. Na stránce **Správa rozšíření** uvidíte rozšíření, která jsou aktuálně nainstalována, a můžete otevřít stránku **Tržiště rozšíření**, která zobrazuje [!INCLUDE[prod_short](includes/prod_short.md)] rozšíření, která jsou aktuálně dostupná v AppSource. Pokud zvolíte odkaz *Více aplikací* budete přesměrováni na [AppSource.microsoft.com](https://appsource.microsoft.com/marketplace/apps?product=dynamics-365%3Bdynamics-365-business-central&page=1).

Pokud vyberete rozšíření, můžete si přečíst, co rozšíření dělá, a můžete získat přístup k nápovědě k rozšíření a dozvědět se více. Pokud se rozhodnete získat rozšíření, musíte souhlasit s podmínkami použití. Pokud získáte rozšíření z webu AppSource, budete pro dokončení instalace přihlášeni k [!INCLUDE[prod_short](includes/prod_short.md)].

Když nainstalujete rozšíření, budete jej možná muset nastavit, například zadat účet pro použití s rozšířením **Platební standard PayPal pro [!INCLUDE[prod_short](includes/prod_short.md)]**.
Jiná rozšíření jednoduše přidají pole na existující stránku nebo například přidají novou stránku.

Pokud odinstalujete rozšíření a poté změníte názor, můžete ji nainstalovat znovu. Pokud odinstalujete rozšíření, které používáte, data se zachotá, takže pokud rozšíření znovu nainstalujete, budou data stále k dispozici. Jsou požadována některá rozšíření. Nelze je odinstalovat ze stránky **Správa rozšíření**. Pokud to zkusíte, zobrazí se chybová zpráva.

Některá rozšíření poskytuje společnost Microsoft a jiná rozšíření poskytují [jiné společnosti](ui-extensions-other.md). Všechna rozšíření jsou testována před tím, než jsou k dispozici, ale doporučujeme abyste před instalací prošli odkazy, které jsou k dispozici, abyste se o rozšíření dozvěděli více, než se rozhodnete jej nainstalovat.

Společnost Microsoft poskytuje následující rozšíření:

* [Rozšíření AMC Banking 365 Fundamentals](ui-extensions-amc-banking.md)
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
* EU VAT Reg. Ne.  Service

## Viz také

[Přizpůsobení Business Central](ui-customizing-overview.md)  
[Rozšíření Business Central od ostatních poskytovatelů](ui-extensions-other.md)  
[Nastavení služby Envestnet Yodlee Bank Feeds](bank-how-setup-bank-statement-service.md)  
[Povolit platbu zákazníka prostřednictvím služby PayPal](sales-how-enable-payment-service-extensions.md)  
[Migrace obchodních dat z jiných finančních systémů](across-import-data-configuration-packages.md)  
[Nastavení rozšíření GetAddress.io UK Postal Code extension](LocalFunctionality/UnitedKingdom/uk-setup-postal-code-service.md)  
[[!INCLUDE[prod_short](includes/prod_short.md)] Rozšíření od jiných poskytovatelů](ui-extensions-other.md)  
[Příprava na podnikání](ui-get-ready-business.md)

## [!INCLUDE[prod_short](includes/free_trial_md.md)]


[!INCLUDE[footer-include](includes/footer-banner.md)]
