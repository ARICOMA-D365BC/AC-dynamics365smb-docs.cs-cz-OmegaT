---
title: Install and Uninstall Extensions
description: Learn about installing and uninstalling extensions in Business Central.
author: SusanneWindfeldPedersen

ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: app, add-in, manifest, customize, install, uninstall
ms.search.form: 2500
ms.date: 05/24/2022
ms.author: solsen
---

# Install and Uninstall Extensions in Business Central

Můžete změnit [!INCLUDE[prod_short](includes/prod_short.md)] instalací rozšíření, která například přidají funkčnost, změní chování nebo vám poskytnou přístup k novým online službám. Další informace naleznete v tématu [Přizpůsobení Business Central pomocí rozšíření](ui-extensions.md).

> [!NOTE]
> To install or uninstall extensions from AppSource or add per-tenant extensions, you must have the right permissions. You must either be a member of the EXTEND. MGT. - ADMIN user group or you must have the EXTEND. MGT. - ADMIN permission set. Pokud jste správce, můžete přiřadit skupiny uživatelů a oprávnění ostatním uživatelům ve vaší společnosti.
>
> Chcete-li použít funkce poskytované rozšířením, jako je otevírání stránek, spouštění sestav, výběr akcí a další, musíte mít přiřazené sady oprávnění, které jsou nainstalovány jako součást rozšíření.

> [!NOTE]  
> The **EXTEND. MGT. - ADMIN** permission set was introduced in Business Central 2021 release wave 1 as a replacement for the **D365 EXTENSION MGT** permission set in earlier versions.

## <a name="install"></a>Install an Extension

Rozšíření spravujete na stránce **Správa rozšíření** Na tuto stránku se dostanete z Domovské stránky. Alternatively, choose the **Search for Page or Report** icon ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") in the top right corner, enter **Extension**, and then choose the related link.

Nová rozšíření můžete získat na [AppSource.microsoft.com](https://go.microsoft.com/fwlink/?linkid=2081646). Zde si můžete pro zobrazit všechna dostupná rozšíření pro [!INCLUDE[prod_short](includes/prod_short.md)] a můžete získat aplikace, rozšíření a balíčky obsahu pro další produkty společnosti Microsoft. Nastavte příslušné filtry, podívejte se na informace o každém rozšíření a získejte rozšíření pro Váš [!INCLUDE[prod_short](includes/prod_short.md)].

> [!NOTE]  
> Přihlaste se na [AppSource.microsoft.com](https://appsource.microsoft.com/) pomocí e-mailového účtu, který používáte pro [!INCLUDE[prod_short](includes/prod_short.md)]. Pro bezproblémové používání prostředí používejte stejný e-mailový účet.

Na marketplace se můžete také dostat z [!INCLUDE[prod_short](includes/prod_short.md)]. Na stránce **Správa rozšíření** uvidíte rozšíření, která jsou aktuálně nainstalována, a můžete otevřít stránku **Tržiště rozšíření**, která zobrazuje [!INCLUDE[prod_short](includes/prod_short.md)] rozšíření, která jsou aktuálně dostupná v AppSource. If you choose the *More apps* link, you're taken to [AppSource.microsoft.com](https://go.microsoft.com/fwlink/?linkid=2081646).

Pokud vyberete rozšíření, můžete si přečíst, co rozšíření dělá, a můžete získat přístup k nápovědě k rozšíření a dozvědět se více. Pokud se rozhodnete získat rozšíření, musíte souhlasit s podmínkami použití. If you get the extension from the AppSource website, you'll be signed in to [!INCLUDE[prod_short](includes/prod_short.md)] to complete the installation.

Když nainstalujete rozšíření, budete jej možná muset nastavit, například zadat účet pro použití s rozšířením **Platební standard PayPal pro [!INCLUDE[prod_short](includes/prod_short.md)]**.
Jiná rozšíření jednoduše přidají pole na existující stránku nebo například přidají novou stránku.

Pokud odinstalujete rozšíření a poté změníte názor, můžete ji nainstalovat znovu. Pokud odinstalujete rozšíření, které používáte, data se zachotá, takže pokud rozšíření znovu nainstalujete, budou data stále k dispozici. Jsou požadována některá rozšíření. You're prevented from uninstalling these extensions from the **Extension Management** page. Pokud to zkusíte, zobrazí se chybová zpráva.

Některá rozšíření poskytuje společnost Microsoft a jiná rozšíření poskytují [jiné společnosti](ui-extensions-other.md). All extensions are tested before they're made available to you, but we recommend that you access the links that are provided with each extension to learn more about the extension before you choose to install it.

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

## Upload a Per-Tenant Extension (PTE)

You upload a PTE by using the **Extension Management** page. On the **Extension Management** page, go to **Manage**, then choose **Upload Extension**. On the **Upload and Deploy Extension** page, specify the .app file to upload. To proceed, choose the **Accept** button, and then the **Deploy** button, which will start the process of deploying the PTE.

If the PTE contains breaking schema changes, it's possible to *force* an upload of it. To do that, in the **Schema Sync Mode** choose the **Force** option. You'll get a confirmation dialog to accept before proceeding.

## Uninstall an Extension

You uninstall an extension by using the **Extension Management** page. To uninstall an extension, select it on the page, then select the **Uninstall** action. Pokud rozšíření odinstalujete a pak si to rozmyslíte, můžete rozšíření nainstalovat znovu.

When you uninstall an extension that you've been using, data is by default preserved in case you install the extension again. Můžete toho namísto smazat data zároveň s rozšířením. This operation is controlled by the **Delete Extension Data** switch. By default, this switch is **off**. When you try to turn on the **Delete Extension Data** switch for the extension, you'll get a confirmation dialog, and you must choose **Yes** to turn it on. After the **Delete Extension Data** switch is turned on, you can uninstall the extension, and you'll be asked to reconfirm that you want to uninstall the extension and delete the data.

> [!IMPORTANT]
> - There may be other extensions that require or depend on the extension that you want to uninstall in order to work. These other extensions are referred to as *dependents*. You can't uninstall an extension unless its dependents are also uninstalled.
> - When you choose to uninstall an extension that has one or more dependents, you'll get a confirmation dialog that lists the dependents and asks whether you want to uninstall the extension and all its dependents. You'll have to select **Yes** to continue.
> - If you turn on the **Delete Extension Data** switch, uninstalling the extension will delete all data for the extension **plus** data for all dependent extensions. Akci nelze vrátit zpět.
> - Některá rozšíření jsou nutná. Nelze je odinstalovat ze stránky **Správa rozšíření**. Pokud to zkusíte, zobrazí se chybová zpráva.

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