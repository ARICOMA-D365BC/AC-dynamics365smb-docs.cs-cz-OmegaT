---
title: Manage database access intent in Business Central | Microsoft Docs
description: Change the database access intent for reports, API pages, and queries.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 04/01/2021
ms.author: jswymer
---
# Správa přístupu databáze

Jako super uživatel nebo správce můžete změnit přístup k databázi například, k sestavám, stránkám typu API a databázovým dotazům, abyste zlepšili výkon služby.

## Přehled

[!INCLUDE[prod_short](includes/prod_short.md)] can be set up to use read-only replicas of the primary (read-write) database. Použití replikování databáze snižujete zatížení primární databáze. V některých případech to také zlepší výkon při prohlížení dat v klientovi. Repliky jsou výhodné pro objekty, jako jsou sestavy, dotazy a stránky rozhraní API, které se používají pouze pro zobrazení dat, nikoli pro úpravu dat.

Při spuštění objektů určuje záměr přístupu k databázi, zda se použije replika pouze pro čtení, pokud je k dispozici, nebo se použije primární databáze. Reports, API pages, and queries are developed with a predefined database access intent (see [DatabaseAccessIntent property](/dynamics365/business-central/dev-itpro/developer/properties/devenv-dataaccessintent-property)).

The **Database Access Intent List** page lets you override the predefined database access intent for objects when they're run.

In database terms, this feature is commonly known as *read scale-out*. For more information about read-scale out and data access intent in [!INCLUDE[prod_short](includes/prod_short.md)], see [Utilizing Read Scale-Out for Better Performance](/dynamics365/business-central/dev-itpro/administration/database-read-scale-out-overview) in the [!INCLUDE[prod_short](includes/prod_short.md)] Developer and Administration help.

## Změna přístupu k databázi

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Database Access Intent List**, and then choose the related link.

   Na stránce jsou uvedeny všechny sestavy, stránky a dotazy. The **Access Intent** column includes one of the following values:

   | **Setting** | **Popis** |
   |------------|-------------|  
   | **Default** | Označuje, že objekt používá předdefinovaný záměr přístupu k databázi. |
   | **Allow Write** | Nastaví objekt pro použití primární databáze, což umožňuje uživateli upravovat data. |
   | **Read Only** | Nastaví objekt pro použití repliky databáze, což znamená, že uživatel může pouze zobrazit data, nikoli změnit data. |

2. Choose the **Edit List** action.

3. On the **Edit - Database Access Intent List** page, change the **Access Intent** field for the objects.

   > [!NOTE]
   > If an object that is editable, like the Customer Card, is set to **Read Only**, the primary database will still be used, regardless of the access intent, allowing users to make changes as normal.

## Zobrazit související školení na webu [Microsoft Learn](/learn/paths/deploy-configure-dynamics-365-business-central/)

## Viz také
[Business Functionality](across-business-functionality.md)  
[General Business Functionality](ui-across-business-areas.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)

## [!INCLUDE[prod_short](includes/free_trial_md.md)]


[!INCLUDE[footer-include](includes/footer-banner.md)]