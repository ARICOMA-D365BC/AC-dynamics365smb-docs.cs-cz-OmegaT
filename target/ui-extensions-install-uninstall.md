---
title: Installing and Uninstalling Extensions in Business Central  | Microsoft Docs
description: Learn about installing and uninstalling extensions in Business Central.
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: app, add-in, manifest, customize, install, uninstall
ms.date: 06/03/2021
ms.author: solsen
---

# Instalace a odinstalování rozšíření v Business Central

Můžete změnit [!INCLUDE[prod_short](includes/prod_short.md)] instalací rozšíření, která například přidají funkčnost, změní chování nebo vám poskytnou přístup k novým online službám. Další informace naleznete v tématu [Přizpůsobení Business Central pomocí rozšíření](ui-extensions.md).

> [!NOTE]
> To install or uninstall extensions from AppSource or add per-tenant extensions, you must have the right permissions. You must either be a member of the EXTEND. MGT. - ADMIN user group or you must have the EXTEND. MGT. - ADMIN permission set. Pokud jste správce, můžete přiřadit skupiny uživatelů a oprávnění ostatním uživatelům ve vaší společnosti.
>
> Chcete-li použít funkce poskytované rozšířením, jako je otevírání stránek, spouštění sestav, výběr akcí a další, musíte mít přiřazené sady oprávnění, které jsou nainstalovány jako součást rozšíření.

> [!NOTE]  
> The **EXTEND. MGT. - ADMIN** permission set was introduced in Business Central 2021 release wave 1 as a replacement for the **D365 EXTENSION MGT** permission set in earlier versions.

## Instalace rozšíření

Rozšíření spravujete na stránce **Správa rozšíření** Na tuto stránku se dostanete z Domovské stránky. Alternatively, choose the **Search for Page or Report** icon ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") in the top right corner, enter **Extension**, and then choose the related link.

Nová rozšíření můžete získat na [AppSource.microsoft.com](https://go.microsoft.com/fwlink/?linkid=2081646). Zde si můžete pro zobrazit všechna dostupná rozšíření pro [!INCLUDE[prod_short](includes/prod_short.md)] a můžete získat aplikace, rozšíření a balíčky obsahu pro další produkty společnosti Microsoft. Nastavte příslušné filtry, podívejte se na informace o každém rozšíření a získejte rozšíření pro Váš [!INCLUDE[prod_short](includes/prod_short.md)].

> [!NOTE]  
> Přihlaste se na [AppSource.microsoft.com](https://appsource.microsoft.com/) pomocí e-mailového účtu, který používáte pro [!INCLUDE[prod_short](includes/prod_short.md)]. Pro bezproblémové používání prostředí používejte stejný e-mailový účet.

Na marketplace se můžete také dostat z [!INCLUDE[prod_short](includes/prod_short.md)]. Na stránce **Správa rozšíření** uvidíte rozšíření, která jsou aktuálně nainstalována, a můžete otevřít stránku **Tržiště rozšíření**, která zobrazuje [!INCLUDE[prod_short](includes/prod_short.md)] rozšíření, která jsou aktuálně dostupná v AppSource. Pokud zvolíte odkaz *Více aplikací* budete přesměrováni na [AppSource.microsoft.com](https://go.microsoft.com/fwlink/?linkid=2081646).

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


## Uploading a Per-Tenant Extension (PTE)

You upload a PTE by using the **Extension Management** page. On the **Extension Management** page, go to **Manage**, then choose **Upload Extension**. On the **Upload and Deploy Extension** page, specify the .app file to upload. To proceed, choose the **Accept** button, and then the **Deploy** button, this will start the process of deploying the PTE.

If the PTE contains breaking schema changes, it is possible to *force* an upload of it. To do that, in the **Schema Sync Mode** choose the **Force** option. You will get a confirmation dialog to accept before proceeding.

## Odinstalace rozšíření

You uninstall an extension by using the **Extension Management** page. Pokud rozšíření odinstalujete a pak si to rozmyslíte, můžete rozšíření nainstalovat znovu. Odinstalujete-li rozšíření, které používáte, data jsou ve výchozím nastavení zachována, takže pokud rozšíření znovu nainstalujete. Můžete toho namísto smazat data zároveň s rozšířením. Ovládá se to zaškrtávacím políčkem **Odstranit data rozšíření**. Ve výchozím nastavení není toto políčko *povoleno*.

> [!IMPORTANT]  
> Pokud zaškrtnete políčko **Odstranit data rozšíření**, zobrazí se potvrzovací dialogové okno a musíte zvolit **OK**. Je-li zaškrtnuto políčko **Odstranit data rozšíření**, můžete nyní rozšíření odinstalovat a budete požádáni o opětovné potvrzení, že chcete rozšíření odinstalovat, a data smazat. Akci nelze vrátit zpět.
> Některá rozšíření jsou nutná. Nelze je odinstalovat ze stránky **Správa rozšíření**. Pokud to zkusíte, zobrazí se chybová zpráva.

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