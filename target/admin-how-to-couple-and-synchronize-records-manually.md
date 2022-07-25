---
title: Coupling and Synchronizing (contains video)
description: Synchronizing an integration table mapping enables data syncing in all records in a table in Business Central and Dynamics 365 Sales table that are coupled.
author: brentholtorf


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: crm, sales, couple, decouple, synchronize
ms.search.form: 6250
ms.date: 10/01/2021
ms.author: bholtorf

---

# Coupling and Synchronizing Records between Dataverse and Business Central

This topic describes how to couple one or more records in [!INCLUDE[prod_short](includes/prod_short.md)] with records in Dataverse or [!INCLUDE[crm_md](includes/crm_md.md)]. Coupling records lets you view Dataverse information from [!INCLUDE[prod_short](includes/prod_short.md)], and vice versa. Spojení také umožňuje synchronizovat data mezi záznamy. Můžete spárovat existující záznamy nebo vytvářet a spárovat nové záznamy.

> [!Note]
> Coupling and synchronizing data is available only if your system administrator has created a connection between [!INCLUDE[prod_short](includes/prod_short.md)] and Dataverse or [!INCLUDE[crm_md](includes/crm_md.md)]. A quick way to check is to open the **Customer** card and look for the **Set Up Coupling** action. Pokud je akce k dispozici, aplikace jsou připojené.

## Video příklad
This video shows coupling and synchronizing data in the context of an integration with [!INCLUDE[crm_md](includes/crm_md.md)].

> [!VIDEO https://go.microsoft.com/fwlink/?linkid=2098376]

## Párování záznamů
1. In [!INCLUDE[prod_short](includes/prod_short.md)], open the card for the record you want to couple. Například, karta zákazníka nebo kontaktu.

   Můžete také otevřít stránku se seznamem a vybrat záznam, který chcete spárovat.

2. Choose the **Set Up Coupling** action.
3. Fill in the fields, and then choose **OK**.

## Synchronizace jednoho záznamu
1. In [!INCLUDE[prod_short](includes/prod_short.md)], open the card for the record you want to couple. Například, karta zákazníka nebo kontaktu.
2. Choose the **Synchronize Now** action.
3. If a record can be synchronized in one direction, select the option that specifies the direction of data update, and then choose **OK**.

## To synchronize a single record from [!INCLUDE[crm_md](includes/crm_md.md)]
1. In [!INCLUDE[crm_md](includes/crm_md.md)], open the form for the record you want to couple. Například, karta účtu nebo karta kontaktu.
2. Choose the **[!INCLUDE[prod_short](includes/prod_short.md)]** action in the ribbon to open and couple record automatically.

> [!Note]
> You can synchronize a single record from [!INCLUDE[crm_md](includes/crm_md.md)] automatically only when **Sync. Only Coupled Records** is disabled and the synchronization direction is set to Bidirectional or From Integration Table on the **Integration Table Mapping** page for the record. For more information, see [Mapping the Tables and Fields to Synchronize](admin-how-to-modify-table-mappings-for-synchronization.md#creating-new-records).

## To couple multiple records using match-based coupling

You can specify the data to synchronize for an entity, such as a customer or contact, by coupling records based on matches. You can refine the matches by making the search case sensitive, and assigning a priority for each match. If no match is found, you can also specify that you want to create the entity in Dataverse. For more information, see [Customize the Match-Based Coupling](admin-how-to-set-up-a-dynamics-crm-connection.md#customize-the-match-based-coupling).

1. In [!INCLUDE[prod_short](includes/prod_short.md)], open the list page for the record, such as the Customers or Contacts list pages.
2. Choose the **Match-Based Coupling** action.
3. Podle potřeby vyplňte pole. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## Synchronizace více záznamů
1. In [!INCLUDE[prod_short](includes/prod_short.md)], open the list page for the record, such as the Customers or Contacts list pages.
2. Select the records that you want to synchronize, and then choose the **Synchronize Now** action.
3. If records can be synchronized in one direction, select the option that specifies the direction, and then choose **OK**.

## Uncoupling Records
You can uncouple one or more records from list pages or the **Coupled Data Synchronization Errors** page by choosing one or more lines and choosing **Delete Coupling**. You can also remove all couplings for one or more table mappings on the **Integration Table Mappings** page.

## Viz také
[Use Dynamics 365 Sales from Business Central](marketing-integrate-dynamicscrm.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]