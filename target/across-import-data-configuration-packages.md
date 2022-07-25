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

When you sign up for [!INCLUDE[prod_short](includes/prod_short.md)], you can choose to create an empty company so that you can upload your own data and to test your new [!INCLUDE[prod_short](includes/prod_short.md)] company. V závislosti na finančním řešení, které vaše firma používá dnes, můžete přenášet informace o zákaznících, dodavatelích, zásobách a bankovních účtech.

V Centru rolí můžete spustit průvodce nastavením, který vám pomůže přenášet obchodní data ze souboru Excel nebo z jiných formátů. Typ souborů, které můžete nahrát, závisí na dostupných příponách. For example, you can migrate data from QuickBooks because [!INCLUDE[prod_short](includes/prod_short.md)] includes an extension that handles the conversion from QuickBooks. Pokud chcete migrovat data z jiných finančních programů, musíte buď zkontrolovat, zda je pro toto řešení k dispozici rozšíření, nebo importovat z aplikace Excel.

[!INCLUDE[prod_short](includes/prod_short.md)] includes templates for accounts, customers, vendors, and inventory items that you can choose to apply when you import your data. To import item pictures, you can use a dedicated function on the **Inventory Setup** page. For more information, see [Import Multiple Item Pictures](inventory-how-import-item-pictures.md).

> [!TIP]  
> We recommend that you use data migration wizards to import data from Dynamics GP, Dynamics NAV, or QuickBooks. For more information, see [Migrate On-Premises Data to Business Central Online](/dynamics365/business-central/dev-itpro/administration/migrate-data) in the administration content, or [QuickBooks Data Migration](ui-extensions-quickbooks-data-migration.md).

## Work with Data in Excel

You can use the Excel add-in to prepare existing content for use in [!INCLUDE [prod_short](includes/prod_short.md)]. For more information, see [Viewing and Editing in Excel From Business Central](across-work-with-excel.md).

## Import Data from Configuration Packages

For larger implementation work, you can set up solution-specific configuration packages. For more information, see [Set Up Company Configuration Packages](/dynamics365/business-central/dev-itpro/administration/set-up-standard-company-configuration-packages) (in English only) in the administration content.

> [!NOTE]  
> Working with configuration packages is advanced functionality, and we recommend that you contact your reselling partner. For more information, see [Set Up Company Configuration Packages](/dynamics365/business-central/dev-itpro/administration/set-up-standard-company-configuration-packages) (in English only).

You can import master data and some transactional data from other finance systems based on the default configuration package in [!INCLUDE[prod_short](includes/prod_short.md)]. On the **Configuration Packages** page, you can work with the package to import and validate the data before you apply the package. For example, you can export the configuration package to Excel and set up your data there. Potom můžete data importovat znovu z aplikace Excel. Balíček se skládá z 27 tabulek, včetně hlavních dat, jako jsou zákazníci, dodavatelé, zboží a obchodní vztahy, dalších základních tabulek nastavení, jako jsou způsoby expedice a tabulek transakcí, jako je prodejní hlavička a řádky.

Při exportu výchozího konfiguračního balíčku do Excelu vygenerovaný sešit obsahuje list pro každou tabulku v balíčku. Pro zjednodušení vašich úkolů můžete využít mapovací nástroje XML, které jsou zabudovány do Excelu. Můžete také použít vestavěné funkce aplikace Excel, které vám pomohou s formátováním dat a vložením dat do správné buňky. Například, přidání prázdného listu a zkopírování starších dat. Potom vytvořte vzorec aplikace Excel pro mapování dat v transformačním listu mezi poli v exportovaném listu a staršími daty zákazníků. Po namapování všech dat zkopírujte oblast dat do listu tabulky.

> [!IMPORTANT]  
> Do not change the columns in the worksheets. If they are moved, changed, or deleted, the worksheet cannot be imported into [!INCLUDE[prod_short](includes/prod_short.md)].

> [!NOTE]
> Fields of type Blob cannot be exported/imported using Excel.

### Tabulky ve Výchozím konfiguračním balíčku

Výchozí konfigurační balíček podporuje následující tabulky:

- Platební podmínky
- Cenová skupina zákazníka
- Způsob dodávky
- Prodejci/Nákupčí
- Lokace
- Účet hlavní knihy
- Zákazník
- Dodavatele
- Zboží
- Prodejní hlavička
- Prodejní řádek
- Nákupní hlavička
- Nákupní řádek
- Obecné finančího deníku
- Řádek deníku zboží
- Účto skupiny zákazníků
- Účto skupiny dodavatele
- Účto skupiny zboží
- Měrné jednotky
- Obecné obchodní účto skupiny
- Obecné účto skupiny zboží
- Nastavení obecného účtování
- Teritoria
- Kategorie zboží
- Prodejní ceny
- Nákupní ceny

## Viz také

[Migrating On-Premises Data to Business Central Online (in English only)](/dynamics365/business-central/dev-itpro/administration/migrate-data)  
[Set Up Company Configuration Packages](/dynamics365/business-central/dev-itpro/administration/set-up-standard-company-configuration-packages)  
[QuickBooks Data Migration](ui-extensions-quickbooks-data-migration.md)  
[Import Multiple Item Pictures](inventory-how-import-item-pictures.md)

## [!INCLUDE[prod_short](includes/free_trial_md.md)]


[!INCLUDE[footer-include](includes/footer-banner.md)]