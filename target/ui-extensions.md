---
title: Customizing Business Central Online Using Extensions
description: Learn all about adding functionality and customizing Business Central by installing extensions here.
author: edupont04


ms.topic: conceptual
ms.search.keywords: app, add-in, manifest, customize
ms.search.form: 2500, 2502
ms.date: 03/22/2022
ms.author: edupont

---
# Customizing Business Central Online Using Extensions

You can change [!INCLUDE[prod_short](includes/prod_short.md)] online by installing extensions that add functionality, changes behavior, or gives you access to new online services, for example.

> [!NOTE]
> To install or uninstall extensions from AppSource or add per-tenant extensions, you must have the right permissions. You must either be a member of the **D365 Extension Mgt.** user group, or you must have the **EXTEN. MGT. - ADMIN** permission set explicitly. Pokud jste správce, můžete přiřadit skupiny uživatelů a oprávnění ostatním uživatelům ve vaší společnosti. For more information, see [Create Users According to Licenses](ui-how-users-permissions.md).
>
> Chcete-li použít funkce poskytované rozšířením, jako je otevírání stránek, spouštění sestav, výběr akcí a další, musíte mít přiřazené sady oprávnění, které jsou nainstalovány jako součást rozšíření.

<!-- [!NOTE]  
> The **EXTEN. MGT. - ADMIN** permission set was introduced in 2021 release wave 1 as a replacement for the **D365 EXTENSION MGT** permission set in earlier versions.-->

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

> [!NOTE]  
> You can keep an eye out for new extensions from Microsoft and other suppliers at [AppSource.microsoft.com](https://appsource.microsoft.com/marketplace/apps?product=dynamics-365%3Bdynamics-365-business-central&page=1).


## Extensions and data transfer

Because the following extensions communicate with other services, they might transfer data out of the geography of the [!INCLUDE[prod_short](includes/prod_short.md)] environment:

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
* EU VAT Reg. Č.. Služba

## Recommended Apps
Microsoft partners and resellers can create an extensions that they can use to compile lists of apps that they often recommend to their customers. If they do, and have deployed the extension to your tenant, the apps will be available on the **Recommended Apps** page. There you can read about each app and decide whether to install them.

> [!NOTE]
> If you are a Microsoft partner or reseller, and you're interested in providing a list of recommended apps, see [Recommend Apps from AppSource](/dynamics365/business-central/dev-itpro/administration/recommend-apps).

## Viz také

[Install and Uninstall Extensions](ui-extensions-install-uninstall.md)  
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
