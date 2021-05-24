---
title: Use Excel to import data into Business Central
description: Use the default configuration package to add customer data in Excel and import the data back into Business Central.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: migration, Excel
ms.date: 04/01/2021
ms.author: edupont

---
# Import obchodních dat z jiných finančních systémů.

When you sign up for [!INCLUDE[prod_short](includes/prod_short.md)], you can choose to create an empty company so that you can upload your own data and to test your new [!INCLUDE[prod_short](includes/prod_short.md)] company. V závislosti na finančním řešení, které vaše firma používá dnes, můžete přenášet informace o zákaznících, dodavatelích, zásobách a bankovních účtech.

V Centru rolí můžete spustit průvodce nastavením, který vám pomůže přenášet obchodní data ze souboru Excel nebo z jiných formátů. Typ souborů, které můžete nahrát, závisí na dostupných příponách. For example, you can migrate data from QuickBooks because [!INCLUDE[prod_short](includes/prod_short.md)] includes an extension that handles the conversion from QuickBooks. Pokud chcete migrovat data z jiných finančních programů, musíte buď zkontrolovat, zda je pro toto řešení k dispozici rozšíření, nebo importovat z aplikace Excel.

[!INCLUDE[prod_short](includes/prod_short.md)] includes templates for accounts, customers, vendors, and inventory items that you can choose to apply when you import your data.

You can import master data and some transactional data from other finance systems based on the default configuration package in [!INCLUDE[prod_short](includes/prod_short.md)]. On the **Configuration Packages** page, you can work with the package to import and validate the data before you apply the package.

> [!TIP]  
> We recommend that you use data migration wizards to import data from Dynamics GP, Dynamics NAV, or QuickBooks. For more information, see [Migrating On-Premises Data to Business Central Online](/dynamics365/business-central/dev-itpro/administration/migrate-data) in the administration content, or [QuickBooks Data Migration](ui-extensions-quickbooks-data-migration.md).

> [!NOTE]  
> For larger implementation work, you can use RapidStart Services for [!INCLUDE[prod_short](includes/prod_short.md)], which is an extensive toolkit for setting up new solutions based on customers' business requirements and setup data. RapidStart Services také nabízí funkce pro import obchodních dat. For more information, see [Setting Up a Company With RapidStart Services](admin-set-up-a-company-with-rapidstart.md).

To import item pictures, you can use a dedicated function on the **Inventory Setup** page. For more information, see [Import Multiple Item Pictures](inventory-how-import-item-pictures.md).

## Import dat z konfiguračních balíčků
[!INCLUDE[prod_short](includes/prod_short.md)] includes a configuration package that you can export to Excel and set up your data there. Potom můžete data importovat znovu z aplikace Excel. Balíček se skládá z 27 tabulek, včetně hlavních dat, jako jsou zákazníci, dodavatelé, zboží a obchodní vztahy, dalších základních tabulek nastavení, jako jsou způsoby expedice a tabulek transakcí, jako je prodejní hlavička a řádky.

> [!NOTE]  
> Working with configuration packages is advanced functionality, and we recommend that you contact your administrator. For more information, see [Importing Data from Legacy Accounting Software using a Configuration Package](across-import-data-configuration-packages.md).

## Práce s daty v Excelu
Při exportu výchozího konfiguračního balíčku do Excelu vygenerovaný sešit obsahuje list pro každou tabulku v balíčku. Pro zjednodušení vašich úkolů můžete využít mapovací nástroje XML, které jsou zabudovány do Excelu. Můžete také použít vestavěné funkce aplikace Excel, které vám pomohou s formátováním dat a vložením dat do správné buňky. Například, přidání prázdného listu a zkopírování starších dat. Potom vytvořte vzorec aplikace Excel pro mapování dat v transformačním listu mezi poli v exportovaném listu a staršími daty zákazníků. Po namapování všech dat zkopírujte oblast dat do listu tabulky.

> [!IMPORTANT]  
> Do not change the columns in the worksheets. If they are moved, changed, or deleted, the worksheet cannot be imported into [!INCLUDE[prod_short](includes/prod_short.md)].

> [!NOTE]
> Fields of type Blob cannot be exported/imported using Excel.

## Tabulky ve Výchozím konfiguračním balíčku
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
[Setting Up a Company With RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Migrating On-Premises Data to Business Central Online](/dynamics365/business-central/dev-itpro/administration/migrate-data)  
[QuickBooks Data Migration](ui-extensions-quickbooks-data-migration.md)  
[Import Multiple Item Pictures](inventory-how-import-item-pictures.md)

## [!INCLUDE[prod_short](includes/free_trial_md.md)]


[!INCLUDE[footer-include](includes/footer-banner.md)]