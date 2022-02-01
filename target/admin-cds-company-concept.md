---
title: Company and Business Unit Mapping | Microsoft Docs
description: Companies are both a legal and business constructs, and they are used to secure and visualize business data.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: CDS, Dataverse, integration, sync
ms.date: 04/01/2021
ms.author: bholtorf

---

# Modely vlastnictví dat
[!INCLUDE[prod_short](includes/cc_data_platform_banner.md)]

[!INCLUDE[prod_short](includes/cds_long_md.md)] requires that you specify an owner for the data you store. For more information, see [Types of tables](/powerapps/maker/data-platform/types-of-entities) in the Power Apps documentation. When you set up integration between [!INCLUDE[prod_short](includes/cds_long_md.md)] and [!INCLUDE[prod_short](includes/prod_short.md)] you must choose the **User or team** ownership for records that are synchronized. Akce, které lze u těchto záznamů provádět, lze řídit na úrovni uživatele. <!--We recommend the Team ownership model because it makes it easier to manage ownership for multiple people.NO LONGER TRUE IN DATAVERSE-->

## Vlastnictví týmu
In [!INCLUDE[prod_short](includes/prod_short.md)], a company is a legal and business table that offers ways to secure and visualize business data. Uživatelé vždy pracují v kontextu společnosti. The closest that [!INCLUDE[prod_short](includes/cds_long_md.md)] comes to this concept is the business unit table, which does not have legal or business implications.

Vzhledem k tomu, že organizační jednotky postrádají právní a obchodní důsledky, nelze vynutit mapování 1:1 (1:1) k synchronizaci dat mezi společností a organizační jednotkou, a to buď jednosměrnou, nebo obousměrnou. To make synchronization possible, when you enable synchronization for a company in [!INCLUDE[prod_short](includes/prod_short.md)], the following happens in [!INCLUDE[prod_short](includes/cds_long_md.md)]:

* We create a company table that is equivalent to the company table in [!INCLUDE[prod_short](includes/prod_short.md)]. Název společnosti je doplněn "BC Company ID." Například Společnost Cronus International Ltd. (93555b1a-af3e-ea11-bb35-000d3a492db1).
* Vytvoříme výchozí organizační jednotku, která má stejný název jako společnost. Například Společnost Cronus International Ltd. (93555b1a-af3e-ea11-bb35-000d3a492db1).
* Vytvoříme samostatný tým vlastníků se stejným názvem jako společnost a přidružíme jej k organizační jednotce. Název týmu je předponou "BCI -." Například BCI - Cronus International Ltd. (93555b1a-af3e-ea11-bb35-000d3a492db1).
* Records that are created and synchronized to [!INCLUDE[prod_short](includes/cds_long_md.md)] are assigned to the "BCI Owner" team that is linked to the business unit.

> [!NOTE]
> If you rename a company in [!INCLUDE[prod_short](includes/prod_short.md)], the names of the company, business, and team that we create automatically in [!INCLUDE[prod_short](includes/cds_long_md.md)] are not updated. Vzhledem k tomu, že pro integraci se používá pouze ID společnosti, nemá to vliv na synchronizaci. If you want the names to match you must update the company, business unit, and team in [!INCLUDE[prod_short](includes/cds_long_md.md)].

The following image shows an example of this data setup in [!INCLUDE[prod_short](includes/cds_long_md.md)].

![Kořenová organizační jednotka je nahoře, týmy jsou uprostřed a pak jsou společnosti dole.](media/cds_bu_team_company.png)

In this configuration, records that are related to the Cronus US company will be owned by a team that is linked to the Cronus US business unit in [!INCLUDE[prod_short](includes/cds_long_md.md)]. Users who can access that business unit through a security role that is set to business unit–level visibility in [!INCLUDE[prod_short](includes/cds_long_md.md)] can now see those records. Následující příklad ukazuje, jak pomocí týmů poskytnout přístup k těmto záznamům.

* Role Manažera prodeje je přiřazena členům amerického prodejního týmu Cronus.
* Uživatelé, kteří mají roli Správce prodeje, mají přístup k záznamům účtů pro členy stejné organizační jednotky.
* Tým prodeje společnosti Cronus v USA je propojen s obchodní jednotkou Cronus v USA, která byla zmíněna výše. Members of the Cronus US Sales team can see any account that is owned by the Cronus US user, which would have come from the Cronus US company table in [!INCLUDE[prod_short](includes/prod_short.md)].

Mapování 1:1 mezi organizační jednotkou, společností a týmem je však pouze výchozím bodem, jak je znázorněno na následujícím obrázku.

![Role zabezpečení řídí viditelnost dat.](media/cds_bu_team_company_2.png)

In this example, a new EUR (Europe) root business unit is created in [!INCLUDE[prod_short](includes/cds_long_md.md)] as the parent for both Cronus DE (Gernamy) and Cronus ES (Spain). Obchodní jednotka EUR nesouvisí se synchronizací. However, it can give members of the EUR Sales team access to account data in both Cronus DE and Cronus ES by setting the data visibility to **Parent/Child BU** on the associated security role in [!INCLUDE[prod_short](includes/cds_long_md.md)].

Synchronizace určuje, který tým má vlastnit záznamy. This is controlled by the **Default owning team** field on the BCI row. When a BCI record is enabled for synchronization we automatically create the associated business unit and owner team (if it doesn't already exist), and set the **Default owning team** field. When synchronization is enabled for an table, administrators can change the owning team, but a team must always be assigned.

> [!NOTE]
> Records become read-only after a company is added and saved, so be sure to choose the correct company.

## Výběr jiné obchodní jednotky
Výběr obchodní jednotky můžete změnit, pokud používáte model vlastnictví Týmů. Pokud používáte model vlastnictví osoby, je vždy vybrána výchozí obchodní jednotka.

If you choose another business unit, for example, one that you created earlier in [!INCLUDE[prod_short](includes/cds_long_md.md)], it will keep its original name. To znamená, že nebude příponou s ID společnosti. Vytvoříme tým, který používá konvenci pojmenování.

Při změně obchodní jednotky si můžete vybrat pouze obchodní jednotky, které jsou o jednu úroveň pod kořenovou obchodní jednotkou.

## Vlastnictví osoby
Pokud zvolíte model vlastnictví osoby, musíte zadat každého prodejce, který bude vlastnit nové záznamy. The business unit and team are created as described in the [Team Ownership](admin-cds-company-concept.md#team-ownership) section.

Výchozí organizační jednotka se používá, když je vybrán model vlastnictví osoby, a nemůžete zvolit jinou organizační jednotku. The team that is associated with the default business unit will own records for common tables, such as the Product table, that are not related to specific salespersons.

When you couple salespersons in [!INCLUDE[prod_short](includes/prod_short.md)] to users in [!INCLUDE[prod_short](includes/cds_long_md.md)], [!INCLUDE[prod_short](includes/prod_short.md)] will add the user to the default team in [!INCLUDE[prod_short](includes/cds_long_md.md)]. You can verify that users are added by looking at the **Default Team Member** column on the **Users - Common Data Service** page. If the user is not added, you can add them manually by using the **Add Coupled Users to Team** action. For more information, see [Synchronizing Data in Business Central with Dataverse](admin-synchronizing-business-central-and-sales.md).

## Viz také
[About [!INCLUDE[prod_short](includes/cds_long_md.md)]](admin-common-data-service.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]