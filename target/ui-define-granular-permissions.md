---
title: Define Granular Permissions
description: This article describes how to define granular permissions and assign each user the permission sets that they need to do their jobs.
author: SorenGP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: access, right, security
ms.search.form: 1, 119, 8930, 9800, 9807, 9808, 9830, 9831
ms.date: 05/09/2022
ms.author: edupont

---
# Přiřazení oprávnění uživatelům a skupinám uživatelů

The [!INCLUDE[prod_short](includes/prod_short.md)] security system controls which objects a user can access within each database or environment, in combination with the user's license. You can specify for each user whether they're able to read, modify, or enter data in the selected database objects. For detailed information, see [Data Security](/dynamics365/business-central/dev-itpro/security/data-security?tabs=object-level) in the developer and administration content for [!INCLUDE[prod_short](includes/prod_short.md)].

Before you assign permissions to users and user groups, you must define who can sign in by creating users according to their license. For more information, see [Create Users According to Licenses](ui-how-users-permissions.md).

In [!INCLUDE[prod_short](includes/prod_short.md)], there are two levels of permissions to database objects:

- Celková oprávnění podle licence, také označovaná jako nároková.

   The licenses include default permission sets. Starting in 2022 release wave 1, admins can customize these default permissions for the relevant license types. For more information, see [Configure permissions based on licenses](ui-how-users-permissions.md#licensespermissions).

- More detailed permissions that are assigned from within [!INCLUDE[prod_short](includes/prod_short.md)].

   This article describes how you can define, use, and apply permissions inside [!INCLUDE [prod_short](includes/prod_short.md)] to change the default configuration.

[!INCLUDE [admin-gdap-users](includes/admin-gdap-users.md)]  
For more information, see [Delegated administrator access to Business Central Online](/dynamics365/business-central/dev-itpro/administration/delegated-admin).

[!INCLUDE [prod_short](includes/prod_short.md)] online includes default user groups that are assigned to users automatically based on their license. You can change the default configuration by modifying or adding users groups, permission sets, and permissions. The following table outlines key scenarios for modifying the default permissions.

| Viz | Také |
|---------|---------|
| To make it easier to manage permissions for multiple users, you can organize them in user groups and then assign or change one permission set for many users in one action. | [To manage permissions through user groups](#to-manage-permissions-through-user-groups) |
| To manage permission sets for specific users | [To assign permission sets to users](#to-assign-permission-sets-to-users) |
| To learn how to define permission set | [To create or modify a permission set](#to-create-or-modify-a-permission-set) |
| To manage specific permissions | [To create or modify permissions manually](#to-create-or-modify-permissions-manually) |
| To view or troubleshoot a user's permissions | [To get an overview of a user's permissions](#to-get-an-overview-of-a-users-permissions) |
| To learn about record-level security | [Security filters limit a user's access to specific records in a table](#security-filters-limit-a-users-access-to-specific-records-in-a-table) |

> [!NOTE]
> An additional method of defining which features users have access to is by setting the **Experience** field on the **Company Information** page. For more information, see [Change Which Features are Displayed](ui-experiences.md).
>
> Prostřednictvím stránek můžete také definovat, co se uživatelům zobrazí v uživatelském rozhraní a jak pracují s povolenými funkcemi. To provedete prostřednictvím profilů, které přiřadíte různým typům uživatelů podle jejich pracovní role nebo oddělení. For more information, see [Manage Profiles](admin-users-profiles-roles.md) and [Customizing [!INCLUDE[prod_short](includes/prod_short.md)]](ui-customizing-overview.md).

## Správa oprávnění prostřednictvím Skupiny uživatelů

User groups help you manage permission sets across the company. [!INCLUDE [prod_short](includes/prod_short.md)] online includes default user groups that are assigned to users automatically based on their license. You can add users manually to a user group, and you can create new user groups as copies of existing ones.

Začnete vytvořením skupiny uživatelů. Potom skupině přiřadíte sady oprávnění, které definují, ke kterému objektu mají uživatelé skupiny přístup. Když přidáte uživatele do skupiny, budou se na něj vztahovat sady oprávnění definované pro skupinu.

Permission sets assigned to a user through a user group stay synchronized. A change to the user group permissions is automatically propagated to the users. Pokud odeberete uživatele ze skupiny uživatelů, příslušná oprávnění budou automaticky odebrána.

### To add users to a user group

Následující postup vysvětluje, jak vytvořit skupiny uživatelů ručně. To create user groups automatically, see [To copy a user group and all its permission sets](#to-copy-a-user-group-and-all-its-permission-sets).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Groups**, and then choose the related link.

   1. Alternatively, on the **Users** page, choose the **User Groups** action.
2. On the **User Group** page, choose the **User Group Members** action.
3. On the **User Group Members** page, choose the **Add Users** action.

### Kopírování skupiny uživatelů a všech jejích sad oprávnění

Chcete-li rychle definovat novou skupinu uživatelů, můžete zkopírovat všechny sady oprávnění z existující skupiny uživatelů do nové skupiny uživatelů.

> [!NOTE]
> The user group members are not copied to the new user group. Poté je musíte přidat ručně. For more information, see the [To add users to a user group](#to-add-users-to-a-user-group) section.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Groups**, and then choose the related link.
2. Select the user group that you want to copy, and then choose the **Copy User Group** action.
3. In the **New User Group Code** field, enter a name for the group, and then choose the **OK** button.

The new user group is added to the **User Groups** page. Pokračujte v přidávání uživatelů. For more information, see the [To add users to a user group](#to-add-users-to-a-user-group) section.

### Přiřazení sad oprávnění skupinám uživatelů

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Groups**, and then choose the related link.
2. Vyberte skupinu uživatelů, kterým chcete přiřadit oprávnění.

   Any permission sets that are already assigned to the user are displayed in the **Permission Sets** FactBox.
3. Choose the **User Permission Sets** action to open the **User Permission Sets** page.
4. On the **User Permission Sets** page, on a new line, fill in the fields as necessary.

### To assign a permission set on the **Permission Set by User Group** page

The following procedure explains how to assign permission sets to a user group on the **Permission Set by User Group** page.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. On the **Users** page, select the relevant user, and then choose the **Permission Set by User Group** action.
3. On the **Permission Set by User Group** page, select the **[user group name]** field on a line for the relevant permission set to assign the set to the user group.
4. Select the **All User Groups** check box to assign the permission set to all user groups.

You can also assign permissions sets directly to a user.

## Přiřazení sad oprávnění uživatelům

Sada oprávnění je kolekce oprávnění pro konkrétní databázové objekty. All users must be assigned one or more permission sets before they can access [!INCLUDE[prod_short](includes/prod_short.md)].

A [!INCLUDE[prod_short](includes/prod_short.md)] solution contains predefined permission sets that are added by Microsoft or by your solution provider. Můžete také přidat nové sady oprávnění přizpůsobené potřebám vaší organizace. For more information, see the [To create or edit a permission set](#to-create-or-modify-a-permission-set) section.

> [!NOTE]
> If you do not want to restrict a user's access more than already defined by the license, you can assign a special permission set called SUPER to the user. This permission set ensures that the user can access all objects specified in the license.
>
> A user with the Essential license and the SUPER permission set has access to more functionality than users with the Team Member license and the SUPER permission set.

Sady oprávnění můžete uživatelům přiřadit dvěma způsoby:

- From the **User Card** page by selecting permission sets to assign to the user.
- From the **Permission Set by User** page by selecting users that a permission set is assigned to.

### Přiřazení sady oprávnění na kartě uživatele

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. Vyberte uživatele, kterému chcete přiřadit oprávnění.
   Any permission sets that are already assigned to the user are displayed in the **Permission Sets** FactBox.
3. Choose the **Edit** action to open the **User Card** page.
4. On the **User Permission Sets** FastTab, on a new line, fill in the fields as necessary. For more information, see [To create or edit a permission set](ui-define-granular-permissions.md#to-create-or-modify-a-permission-set).

### To assign a permission set on the Permission Set by User page

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. On the **Users** page, choose the **Permission Set by User** action.
3. On the **Permission Set by User** page, select the **[user name]** check box on a line for the relevant permission set to assign the set to the user.

   Select the **All Users** check box to assign the permission set to all users.

## Získání přehledu oprávnění uživatele

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. Otevřete kartu příslušného uživatele.
3. Choose the **Effective Permissions** action.

   The **Permissions** part lists all the database objects that the user has access to. You can't edit this section.

   The **By Permission Set** part shows the assigned permission sets through which the permissions are granted to the user, the source and type of the permission set, and to which extent the different access types are permitted.

   For each row that you select in the **Permissions** section, the **By Permission Set** section shows which permission set or sets that the permission is granted through. In this section, you can edit the value in each of the five access type fields, **Read Permission**, **Insert Permission**, **Modify Permission**, **Delete Permission**, **Execute Permission**.

   > [!NOTE]  
   > Only permission sets of type **User-Defined** can be edited.
   >
   > Rows of source Entitlement originate from the subscription license. Hodnoty oprávnění hodnot oprávnění nadřazují hodnoty v jiných sadách oprávnění, pokud mají vyšší hodnocení. A value in a non-entitlement permission set that has a higher ranking than the related value in the entitlement will be surrounded by brackets to indicate that it is not effective as it is overruled by the entitlement.
   >
   > For an explanation of ranking, see [To create or edit permissions manually](ui-define-granular-permissions.md#to-create-or-modify-permissions-manually).

4. To edit a permission set, in the **By Permission Set** part, on the line for a relevant permission set of type **User-Defined**, choose one of the five access type fields and select a different value.

5. To edit individual permissions within the permission set, choose the value in the **Permission Set** field to open the **Permissions** page. Follow the steps described in [To create or edit permissions](ui-define-granular-permissions.md#to-create-or-modify-permissions-manually).

> [!NOTE]  
> When you edit a permission set, the changes will also apply to other users that have the permission set assigned.

### Security filters limit a user's access to specific records in a table

For record-level security in [!INCLUDE[prod_short](includes/prod_short.md)], you use security filters to limit a user's access to data in a table. Vytvořte filtry zabezpečení na data tabulky. Filtr zabezpečení popisuje sadu záznamů v tabulce, ke kterým má uživatel oprávnění. Můžete například určit, že uživatel může číst pouze záznamy, které obsahují informace o konkrétním zákazníkovi. In this way, the user can't access the records that contain information about other customers. For more information, see [Using Security Filters](/dynamics365/business-central/dev-itpro/security/security-filters) in the administration content.


## Vytvoření nebo úprava sady oprávnění

Sady oprávnění fungují jako kontejnery oprávnění, takže můžete snadno spravovat více oprávnění v jednom záznamu.

> [!NOTE]  
> A [!INCLUDE[prod_short](includes/prod_short.md)] solution typically contains a number of predefined permission sets that are added by Microsoft or by your software provider. These permission sets are of type **System** or **Extension**. Tyto typy sad oprávnění nelze vytvářet ani upravovat. Můžete je však zkopírovat a definovat vlastní sady oprávnění a oprávnění.
>
> Permission sets that users create, from new or as copies, are of type **User-Defined** and can be edited.

### Vytvoření nové sady oprávnění od nuly

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Permission Sets**, and then choose the related link.
2. To create a new permission set, choose the **New** action.
3. Na novém řádku vyplňte pole dle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
   When you have created a permission set, you must add the actual permissions. For more information, see [To create or modify permissions manually](ui-define-granular-permissions.md#to-create-or-modify-permissions-manually).

### Kopírování sady oprávnění

Funkci kopírování můžete také použít k rychlému přenesení všech oprávnění jiného oprávnění nastaveného na novou sadu oprávnění.

> [!NOTE]  
> If a System permission set that you have copied is changed, you will be notified (depending on your selection), so that you can consider if the changes are relevant to copy or write into your user-defined permission set.

1. On the **Permission Sets** page, select the line for a permission set that you want to copy, and then choose the **Copy Permission Set** action.
2. On the **Copy Permission Set** page, specify the name of the new permission set, and then choose the **OK** button.
3. Select the **Notify on Changed Permission Set** check box if you want to maintain a link between the original and the copied permission sets. This way, you'll be notified if the name or content of the original permission set changes in a future version.

The new permission set, containing all the permissions of the copied permission set, is added as a new line on the **Permission Sets** page. Nyní mužete začít upravovat opravnění v nové sadě oprávnění.

> [!TIP]
> The lines are sorted alphabetically within each type.

### Export a import sady oprávnění

To quickly set up permissions, you can import permission sets that you exported from another [!INCLUDE[prod_short](includes/prod_short.md)] tenant.

In multitenant environments, a permission set will be imported into a specific tenant. In other words, the scope of the import is *Tenant*.

1. In tenant 1, on the **Permission Sets** page, select the line or lines for the permission sets to export, and then choose the **Export Permission Sets** action.

   An XML file is created in the download folder on your machine. By default, the name is *Export Permission Sets.xml*.

2. In tenant 2, on the **Permission Sets** page, select the **Import Permission Sets** action.
3. On the **Import Permission Sets** dialog page, consider if you want to merge existing permission sets with any new permission sets in the XML file.

   If you select the **Update existing permissions** check box, existing permission sets that match names in the XML file will be merged with the imported permission sets.

   If you don't select the **Update existing permissions** check box, permission sets that match names in the XML file will be skipped during import. In that case, you'll be notified about permission sets that are skipped.

4. From the **Import** dialog page, find and select the XML file to be imported, and then choose the **Open** action.

Sady oprávnění jsou importovány.

## Ruční vytvoření nebo úprava oprávnění

Tento postup vysvětluje, jak ručně přidat nebo upravit oprávnění. You can also have permissions generated automatically from your actions in the UI. For more information, see [To create or modify permissions by recording your actions](ui-define-granular-permissions.md#to-create-or-modify-permissions-by-recording-your-actions).

> [!NOTE]
> When you edit a permission and thereby the related permission set, the changes will also apply to other users that have the permission set assigned.

1. On the **Permission Sets** page, select the line for a permission set, and then choose the **Permissions** action.
2. On the **Permissions** page, create a new line or edit the fields on an existing line.

In each of the five access type fields, **Read Permission**, **Insert Permission**, **Modify Permission**, **Delete Permission**, and **Execute Permission**, you can select one of the following three permission options:

| Možnost | Popis | Hodnocení |
|------|-----------|-------|
| **Ano** | Uživatel může provést akci s dotyčným objektem. | Nejvyšší |
| **Indirect** | Uživatel může provést akci na dotyčném objektu, ale pouze prostřednictvím jiného souvisejícího objektu, ke kterému má uživatel plný přístup. For more information about indirect permissions, see [Permissions Property](/dynamics365/business-central/dev-itpro/developer/properties/devenv-permissions-property) in Developer and IT-Pro Help | Druhý nejvyšší |
| **Blank** | The user can't perform the action on the object in question. | Nejnižší |

> [!IMPORTANT]
> Use caution when assigning **Insert Permission** or **Modify Permission** to the **9001 User Group Member** or **9003 User Group Permission Set** table. Any users assigned to the permission set could potentially assign themselves to other user groups, which in turn, may give them unintended permissions.

### Příklad - Nepřímé opravnění

Můžete přiřadit nepřímé oprávnění k použití objektu pouze prostřednictvím jiného objektu.
Uživatel může mít například oprávnění ke spuštění Codeunity 80 Sales-Post. Codeunita Sales-Post ykonává mnoho úkolů, včetně úpravy tabulky 37, prodejní řádek. When the user posts a sales document, the Sales-Post codeunit, [!INCLUDE[prod_short](includes/prod_short.md)] checks if the user has permission to modify theSales Line table. If not, the codeunit can't complete its tasks, and the user receives an error message. Pokud ano, Codeunita se spustí úspěšně.

However, the user doesn't need to have full access to the Sales Line table to run the codeunit. Pokud má uživatel nepřímé oprávnění pro tabulku Prodejní řádek, bude Codeunita Sales-Post úspěšně spuštěna. Pokud má uživatel nepřímé oprávnění, může upravit tabulku Prodejní řádek pouze spuštěním Codeunity Sales-Post nebo jiného objektu, který má oprávnění k úpravě tabulky Prodejní řádek. Uživatel může upravit tabulku Prodejní řádek pouze v případě, že tak činí z podporovaných oblastí aplikace. The user can't run the feature inadvertently or maliciously by other methods.

## Vytvoření nebo úprava sady oprávnění zaznamenáním vlastní akce

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Permission Sets**, and then choose the related link.

   Alternatively, on the **Users** page, choose the **Permission Sets** action.
2. On the **Permission Sets** page, choose the **New** Action.
3. Na novém řádku vyplňte pole dle potřeby.
4. Choose the **Permissions** action.
5. On the **Permissions** page, choose the **Record Permissions** action, and then choose the **Start** action.

   A recording process starts and captures all your action in the user interface.
6. Go to the various pages and activities in [!INCLUDE[prod_short](includes/prod_short.md)] that you want users with this permission set to access. Je nutné provést úkoly, pro které chcete zaznamenat oprávnění.
7. When you want to finish the recording, return to the **Permissions** page, and then choose the **Stop** action.
8. Choose the **Yes** button to add the recorded permissions to the new permission set.
9. U každého objektu v zaznamenaném seznamu určete, zda jsou uživatelé schopni do zaznamenaných tabulek vkládat, upravovat nebo mazat záznamy.

## Odstranění zastaralých oprávnění ze všech sad oprávnění

1. On the **Permission Sets** page, choose the **Remove Obsolete Permissions** action.

## Nastavení časových omezení uživatele

Administrators can define periods of time during which specified users are able to post. Administrators can also specify if the system logs how much time users are signed in. Similarly, administrators can assign responsibility centers to users. For more information, see [Work with Responsibility Centers](inventory-responsibility-centers.md).

1. Vyberte ikonu ![Žárovky, která otevře ikonu Řekněte mi](media/ui-search/search_small.png "Řeknete mi, co chcete dělat"), zadejte **Nastavení uživatelů** a poté vyberte související odkaz.
2. On the **User Setup** page opens, choose the **New** action.
3. In the **User ID** field, enter the ID of a user, or choose the field to see all current Windows users in the system.
4. Vyplňte pole podle potřeby.

## Viewing permission changes telemetry

You can set up [!INCLUDE[prod_short](includes/prod_short.md)] to send changes that are done to permission to an Application Insights resource in Microsoft Azure. Then, using Azure Monitor, you create reports and set up alerts on the gathered data. For more information, see the following articles in the [!INCLUDE[prod_short](includes/prod_short.md)] Developer and admin help:

- [Monitoring and Analyzing Telemetry - Enabling Application Insights](/dynamics365/business-central/dev-itpro/administration/telemetry-overview#enable)
- [Analyzing Field Monitoring Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-permission-changes-trace)

## Delegated admin users

[!INCLUDE [admin-gdap-users](includes/admin-gdap-users.md)]

## Viz také

[Create Users According to Licenses](ui-how-users-permissions.md)  
[Manage Profiles](admin-users-profiles-roles.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[Customizing [!INCLUDE[prod_short](includes/prod_short.md)]](ui-customizing-overview.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Administration](admin-setup-and-administration.md)  
[Add Users to Microsoft 365 for business](/microsoft-365/admin/add-users/add-users)  
[Security and Protection in Business Central](/dynamics365/business-central/dev-itpro/security/security-and-protection) in Developer and IT-pro Help  
[Assign a telemetry ID to users](/dynamics365/business-central/dev-itpro/administration/telemetry-enable-application-insights#assign-a-telemetry-id-to-users)


[!INCLUDE[footer-include](includes/footer-banner.md)]