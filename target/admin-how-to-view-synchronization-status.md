---
title: View the Status of Synchronization Jobs (contains video)
description: Use the Coupled Data Synchronization Errors page to view the status of synchronization jobs that have been run for coupled records in integrations.
author: brentholtorf


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: sales, crm, integration, sync, synchronize
ms.search.form: 6250
ms.date: 06/14/2021
ms.author: bholtorf

---

# Zobrazení stavu synchronizace


Use the **Coupled Data Synchronization Errors** page to view the status of synchronization jobs that have been run for coupled records in a Dataverse or [!INCLUDE[crm_md](includes/crm_md.md)] integrations. This includes jobs that were run from the job queue and manual synchronization jobs that ran on records from [!INCLUDE[prod_short](includes/prod_short.md)]. Například zobrazení jejich stavu je užitečné při odstraňování problémů, protože vám poskytuje přístup k podrobnostem o chybách souvisejících s propojenými záznamy. Obvykle jsou tyto typy chyb způsobeny akcemi uživatele, například když:

* Two people made a change to the same data in both business apps.
* Someone deleted data in one of the apps, but not both.

> [!Note]
> The **Coupled Data Synchronization Errors** page shows information about jobs related to coupled records. Pokud vyřešíte všechny chyby, ale záznamy stále nejsou synchronizovány, může to mít něco společného s nastavením integrace. Obvykle správce bude muset vyřešit tyto chyby.

## Příklad
This video shows an example of how to troubleshoot errors that happened while synchronizing with [!INCLUDE[prod_short](includes/cds_long_md.md)]. The process will be the same for all integrations.

> [!VIDEO https://go.microsoft.com/fwlink/?linkid=2097304]


## Zobrazení a řešení chyb synchronizace pro spárované záznamy
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Coupled Data Synchronization Errors**, and then choose the related link.
2. The **Coupled Data Synchronization Errors** page shows issues that occurred when you synchronized coupled records. Následující tabulka obsahuje akce, které můžete použít k řešení problémů jeden po druhém:

| Akce | Popis |
|----|----|
| **Remove Coupling** | Odpojí záznamy a nebudou již synchronizovány. To restart the synchronization you must couple them again. |
| **Retry** and **Retry All** | For each record where an error is found, synchronization is skipped unless you fix the issue. Retry will include the selected record in the next synchronization, and **Retry All** includes all of the records. |
| **Synchronize** | The app will try to resolve a conflict where data was changed in both business apps. You can choose the data to use. |
| **Restore Records** and **Delete Records** | Ty jsou užitečné, když byl záznam odstraněn v jedné z obchodních aplikací. Delete Records deletes the record or row in the app where it still exists. Restore Records recreates the record or row in the business app where it was deleted. |

> [!NOTE]
> To reduce the number of conflicts you need to resolve, you can set up your integration table mappings to apply these actions automatically. For more information, [Mapping Integration Tables](admin-how-to-modify-table-mappings-for-synchronization.md#mapping-integration-tables).

## Zobrazení protokolu synchronizace pro určitý (ručně synchronizovaný) záznam
1. Open, for example, a customer, item or any other record that is synchronizing data between [!INCLUDE[prod_short](includes/prod_short.md)] and Dataverse or [!INCLUDE[crm_md](includes/crm_md.md)].
2. Choose the **Synchronization Log** action to view the synchronization log for a selected record. Například konkrétní zákazník, kterého jste synchronizovali ručně.

## Remove Couplings Between Records
When something goes wrong in your integration and you need to uncouple records to stop synchronizing them, you can do so for one or more records at a time. You can uncouple one or more records from list pages or the **Coupled Data Synchronization Errors** page by choosing one or more lines and choosing **Delete Coupling**. You can also remove all couplings for one or more table mappings on the **Integration Table Mappings** page.

If an entity with a unidirectional coupling is deleted in [!INCLUDE[prod_short](includes/prod_short.md)], you must manually delete the broken coupling. To do that, on the **Coupled Data Synchronization Errors** page, choose the **Find for Deleted** action, and then delete the couplings.

## Viz také
[Setting Up User Accounts for Integrating with Dynamics 365 Sales](admin-setting-up-integration-with-dynamics-sales.md)  
[Use Dynamics 365 Sales from Business Central](marketing-integrate-dynamicscrm.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]