---
title: Define Granular Permissions  | Microsoft Docs
description: Describes how to give users access to objects by assigning permission sets to them.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: access, right, security
ms.date: 04/01/2021
ms.author: edupont

---
# Přiřazení oprávnění uživatelům a skupinám uživatelů

The [!INCLUDE[prod_short](includes/prod_short.md)] security system allows you to control which objects a user can access within each database or environment. Pro každého uživatele můžete určit, zda je schopen číst, upravovat nebo zadávat data do vybraných databázových objektů. For detailed information, see [Data Security](/dynamics365/business-central/dev-itpro/security/data-security?tabs=object-level) in the Developer and ITPro help for [!INCLUDE[prod_short](includes/prod_short.md)].

Před přiřazením oprávnění uživatelům a skupinám uživatelů je nutné definovat, kdo se může přihlásit  pomocí vytvoření uživatelů podle licence definované v Microsoftu 365 Admin Center. For more information, see [Create Users According to Licenses](ui-how-users-permissions.md).

In [!INCLUDE[prod_short](includes/prod_short.md)], there are two levels of permissions to database objects:

- Celková oprávnění podle licence, také označovaná jako nároková.
- More detailed permissions as assigned from within [!INCLUDE[prod_short](includes/prod_short.md)].

Chcete-li usnadnit správu oprávnění pro více uživatelů, můžete je uspořádat do skupin uživatelů a tím přiřadit nebo změnit jednu sadu oprávnění pro mnoho uživatelů v jednom okamžiku. For more information, see [To manage permissions through user groups](ui-define-granular-permissions.md#to-manage-permissions-through-user-groups).

> [!NOTE]
> An additional method of defining which features a user has access to is by setting the **Experience** field on the **Company Information** page. For more information, see [Change Which Features are Displayed](ui-experiences.md).
>
> Prostřednictvím stránek můžete také definovat, co se uživatelům zobrazí v uživatelském rozhraní a jak pracují s povolenými funkcemi. To provedete prostřednictvím profilů, které přiřadíte různým typům uživatelů podle jejich pracovní role nebo oddělení. For more information, see [Manage Profiles](admin-users-profiles-roles.md) and [Customizing [!INCLUDE[prod_short](includes/prod_short.md)]](ui-customizing-overview.md).

## Přiřazení sad oprávnění uživatelům

Sada oprávnění je kolekce oprávnění pro konkrétní databázové objekty. All users must be assigned one or more permission sets before they can access [!INCLUDE[prod_short](includes/prod_short.md)].

A [!INCLUDE[prod_short](includes/prod_short.md)] solution contains a number of predefined permission sets that are added by Microsoft or by your solution provider. Můžete také přidat nové sady oprávnění přizpůsobené potřebám vaší organizace. For more information, see [To create or edit a permission set](ui-define-granular-permissions.md#to-create-or-modify-a-permission-set).

> [!NOTE]
> Pokud nechcete omezit přístup uživatele více než stanoveno licencí, můžete uživateli přiřadit speciální sadu oprávnění s názvem SUPER. This permission set ensures that the user can access all objects specified in the license.
>
> A user with the Essential license and the SUPER permission set has access to more functionality than users with the Team Member license and the SUPER permission set.

Sady oprávnění můžete uživatelům přiřadit dvěma způsoby:

- From the **User Card** page by selecting permission sets to assign to the user.
- From the **Permission Set by User** page by selecting users that a permission set is assigned to.

### Přiřazení sady oprávnění na kartě uživatele

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. Vyberte uživatele, kterému chcete přiřadit oprávnění.
   Any permission sets that are already assigned to the user are displayed in the **Permission Sets** FactBox.
3. Choose the **Edit** action to open the **User Card** page.
4. On the **User Permission Sets** FastTab, on a new line, fill in the fields as necessary. For more information, see [To create or edit a permission set](ui-define-granular-permissions.md#to-create-or-modify-a-permission-set).

### To assign a permission set on the Permission Set by User page

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. On the **Users** page, select the relevant user, and then choose the **Permission Set by User** action.
3. On the **Permission Set by User** page, select the **[user name]** check box on a line for the relevant permission set to assign the set to the user.
4. Select the **All Users** check box to assign the permission set to all users.

## Získání přehledu oprávnění uživatele

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. Otevřete kartu příslušného uživatele.
3. Choose the **Effective Permissions** action.

   The **Permissions** part lists all the database objects that the user has access to. Tuto sekci nelze upravit.

   The **By Permission Set** part shows the assigned permission sets through which the permissions are granted to the user, the source and type of the permission set, and to which extend the different access types are permitted.

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
> Při úpravě sady oprávnění se změny projeví také u ostatních uživatelů, kterým byla sada oprávnění přiřazena.

## Vytvoření nebo úprava sady oprávnění

Sady oprávnění fungují jako kontejnery oprávnění, takže můžete snadno spravovat více oprávnění v jednom záznamu.

> [!NOTE]  
> A [!INCLUDE[prod_short](includes/prod_short.md)] solution typically contains a number of predefined permission sets that are added by Microsoft or by your software provider. These permission sets are of type **System** or **Extension**. Tyto typy sad oprávnění nelze vytvářet ani upravovat. Můžete je však zkopírovat a definovat vlastní sady oprávnění a oprávnění.
>
> Permission sets that users create, from new or as copies, are of type **User-Defined** and can be edited.

### Vytvoření nové sady oprávnění od nuly

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Permission Sets**, and then choose the related link.
2. To create a new permission set, choose the **New** action.
3. Na novém řádku vyplňte pole dle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
   When you have created a permission set, you must add the actual permissions. For more information, see [To create or modify permissions manually](ui-define-granular-permissions.md#to-create-or-modify-permissions-manually).

### Kopírování sady oprávnění

Funkci kopírování můžete také použít k rychlému přenesení všech oprávnění jiného oprávnění nastaveného na novou sadu oprávnění.

> [!NOTE]  
> Pokud se změní systémová oprávnění, která jste zkopírovali, budete upozorněni (v závislosti na vašem výběru), abyste mohli zvážit, zda jsou změny relevantní pro kopírování nebo zápis do vaší uživatelem definované sady oprávnění.

1. On the **Permission Sets** page, select the line for a permission set that you want to copy, and then choose the **Copy Permission Set** action.
2. On the **Copy Permission Set** page, specify the name of the new permission set, and then choose the **OK** button.
3. Select the **Notify on Changed Permission Set** check box if you want to maintain a link between the original and the copied permission sets. Propojení se potom použije k upozornění, pokud se název nebo obsah původní sady oprávnění změní v budoucí verzi, na kterou bude řešení upgradováno na později.

The new permission set, containing all the permissions of the copied permission set, is added as a new line on the **Permission Sets** page. Nyní mužete začít upravovat opravnění v nové sadě oprávnění. Všimněte si, že řádky jsou seřazeny abecedně v rámci každého typu.

### Export a import sady oprávnění

To quickly set up permissions, you can import permission sets that you have exported from another [!INCLUDE[prod_short](includes/prod_short.md)] tenant.

Ve víceklientských prostředích bude sada oprávnění importována do konkrétního klienta.

1. In tenant 1, on the **Permission Sets** page, select the line or lines for the permission sets to export, and then choose the **Export Permission Sets** action.

   Soubor XML je vytvořen ve složce pro stahování ve vašem počítači. Ve výchozím nastavení se nazývá "Export Permission Sets.xml"

2. In tenant 2, on the **Permission Sets** page, select the **Import Permission Sets** action.
3. On the **Import Permission Sets** dialog page, consider if you want to merge existing permission sets with any new permission sets in the xml file.

   If you select the **Update existing permissions** check box, existing permission sets with the same name as those that exist in the xml file will be merged with the imported permission sets.

   If you do not select the **Update existing permissions** check box, permission sets with the same name as those that exist in the xml file will be skipped during import. V takovém případě budete informováni o přeskočených sadách oprávnění.

4. From the **Import** dialog page, find and select the xml file to be imported, and then choose the **Open** action.

Sady oprávnění jsou importovány.

## Ruční vytvoření nebo úprava oprávnění

Tento postup vysvětluje, jak ručně přidat nebo upravit oprávnění. Můžete také mít oprávnění generována automaticky z vašich akcí v uživatelském rozhraní. For more information, see [To create or modify permissions by recording your actions](ui-define-granular-permissions.md#to-create-or-modify-permissions-by-recording-your-actions).

> [!NOTE]
> Když upravíte oprávnění a tím související sadu oprávnění, změny se budou vztahovat také na ostatní uživatele, kterým je sada oprávnění přiřazena.

1. On the **Permission Sets** page, select the line for a permission set, and then choose the **Permissions** action.
2. On the **Permissions** page, create a new line or edit the fields on an existing line.

In each of the five access type fields, **Read Permission**, **Insert Permission**, **Modify Permission**, **Delete Permission**, and **Execute Permission**, you can select one of the following three permission options:

| Možnost | Popis | Hodnocení |
|------|-----------|-------|
| **Ano** | Uživatel může provést akci s dotyčným objektem. | Nejvyšší |
| **Indirect** | Uživatel může provést akci na dotyčném objektu, ale pouze prostřednictvím jiného souvisejícího objektu, ke kterému má uživatel plný přístup. For more information about indirect permissions, see [Permissions Property](/dynamics365/business-central/dev-itpro/developer/properties/devenv-permissions-property) in Developer and IT-Pro Help | Druhý nejvyšší |
| **Blank** | Uživatel nemůže provést akci s daným objektem. | Nejnižší |

### Příklad - Nepřímé opravnění

Můžete přiřadit nepřímé oprávnění k použití objektu pouze prostřednictvím jiného objektu.
Uživatel může mít například oprávnění ke spuštění Codeunity 80 Sales-Post. Codeunita Sales-Post ykonává mnoho úkolů, včetně úpravy tabulky 37, prodejní řádek. When the user posts a sales document, the Sales-Post codeunit, [!INCLUDE[prod_short](includes/prod_short.md)] checks if the user has permission to modify theSales Line table. Pokud ne, Codeunita nemůže dokončit své úlohy a uživatel obdrží chybovou zprávu. Pokud ano, Codeunita se spustí úspěšně.

Uživatel však nemusí mít úplný přístup k tabulce Prodejní řádek, aby mohl spustit codeunitu. Pokud má uživatel nepřímé oprávnění pro tabulku Prodejní řádek, bude Codeunita Sales-Post úspěšně spuštěna. Pokud má uživatel nepřímé oprávnění, může upravit tabulku Prodejní řádek pouze spuštěním Codeunity Sales-Post nebo jiného objektu, který má oprávnění k úpravě tabulky Prodejní řádek. Uživatel může upravit tabulku Prodejní řádek pouze v případě, že tak činí z podporovaných oblastí aplikace. Uživatel nemůže tuto funkci spustit neúmyslně nebo škodlivě jinými metodami.

## Vytvoření nebo úprava sady oprávnění zaznamenáním vlastní akce

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Permission Sets**, and then choose the related link.
2. Alternatively, on the **Users** page, choose the **Permission Sets** action.
3. On the **Permission Sets** page, choose the **New** Action.
4. Na novém řádku vyplňte pole dle potřeby.
5. Choose the **Permissions** action.
6. On the **Permissions** page, choose the **Record Permissions** action, and then choose the **Start** action.

   Tím se spustí proces nahrávání, který zachytí všechny akce v uživatelském rozhraní.
7. Go to the various pages and activities in [!INCLUDE[prod_short](includes/prod_short.md)] that you want users with this permission set to access. Je nutné provést úkoly, pro které chcete zaznamenat oprávnění.
8. When you want to finish the recording, return to the **Permissions** page, and then choose the **Stop** action.
9. Choose the **Yes** button to add the recorded permissions to the new permission set.
10. U každého objektu v zaznamenaném seznamu určete, zda jsou uživatelé schopni do zaznamenaných tabulek vkládat, upravovat nebo mazat záznamy.

## Filtry zabezpečení - omezení přístupu uživatele k určitým záznamům v tabulce

For record-level security in [!INCLUDE[prod_short](includes/prod_short.md)], you use security filters to limit a user's access to data in a table. Vytvořte filtry zabezpečení na data tabulky. Filtr zabezpečení popisuje sadu záznamů v tabulce, ke kterým má uživatel oprávnění. Můžete například určit, že uživatel může číst pouze záznamy, které obsahují informace o konkrétním zákazníkovi. To znamená, že uživatel nemá přístup k záznamům, které obsahují informace o jiných zákaznících. For more information, see [Using Security Filters](/dynamics365/business-central/dev-itpro/security/security-filters) in Developer and IT-Pro help.

## Správa oprávnění prostřednictvím Skupiny uživatelů

Můžete nastavit skupiny uživatelů, které vám pomohou spravovat sady oprávnění pro skupiny uživatelů ve vaší společnosti.

Začnete vytvořením skupiny uživatelů. Potom skupině přiřadíte sady oprávnění, které definují, ke kterému objektu mají uživatelé skupiny přístup. Když přidáte uživatele do skupiny, budou se na něj vztahovat sady oprávnění definované pro skupinu.

Sady oprávnění přiřazené uživateli prostřednictvím skupiny uživatelů zůstanou synchronizovány tak, aby změna oprávnění skupiny uživatelů byla automaticky rozšířena na uživatele. Pokud odeberete uživatele ze skupiny uživatelů, příslušná oprávnění budou automaticky odebrána.

### Seskupení uživatelů do skupin uživatelů

Následující postup vysvětluje, jak vytvořit skupiny uživatelů ručně. To create user groups automatically, see [To copy a user group and all its permission sets](ui-define-granular-permissions.md#to-copy-a-user-group-and-all-its-permission-sets).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Groups**, and then choose the related link.
2. Alternatively, on the **Users** page, choose the **User Groups** action.
3. On the **User Group** page, choose the **User Group Members** action.
4. On the **User Group Members** page, choose the **Add Users** action.

### Kopírování skupiny uživatelů a všech jejích sad oprávnění

Chcete-li rychle definovat novou skupinu uživatelů, můžete zkopírovat všechny sady oprávnění z existující skupiny uživatelů do nové skupiny uživatelů.

> [!NOTE]
> Členové skupiny uživatelů nejsou zkopírováni do nové skupiny uživatelů. Poté je musíte přidat ručně. For more information, see [To group users in user groups](ui-define-granular-permissions.md#to-group-users-in-user-groups).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Groups**, and then choose the related link.
2. Select the user group that you want to copy, and then choose the **Copy User Group** action.
3. In the **New User Group Code** field, enter a name for the group, and then choose the **OK** button.

The new user group is added to the **User Groups** page. Pokračujte v přidávání uživatelů. For more information, see [To group users in user groups](ui-define-granular-permissions.md#to-group-users-in-user-groups).

### Přiřazení sad oprávnění skupinám uživatelů

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Groups**, and then choose the related link.
2. Vyberte skupinu uživatelů, kterým chcete přiřadit oprávnění.
   Any permission sets that are already assigned to the user are displayed in the **Permission Sets** FactBox.
3. Choose the **User Permission Sets** action to open the **User Permission Sets** page.
4. On the **User Permission Sets** page, on a new line, fill in the fields as necessary.

### To assign a permission set on the **Permission Set by User Group** page

The following procedure explains how to assign permission sets to a user group on the **Permission Set by User Group** page.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. On the **Users** page, select the relevant user, and then choose the **Permission Set by User Group** action.
3. On the **Permission Set by User Group** page, select the **[user group name]** check box on a line for the relevant permission set to assign the set to the user group.
4. Select the **All User Groups** check box to assign the permission set to all user groups.

## Odstranění zastaralých oprávnění ze všech sad oprávnění

1. On the **Permission Sets** page, choose the **Remove Obsolete Permissions** action.

## Nastavení časových omezení uživatele

Správci mohou definovat časové období, během kterého mohou zadaní uživatelé účtovat, a také určit, zda systém zaznamenává dobu, po kterou jsou uživatelé přihlášeni. Administrátoři mohou také uživatelům přiřadit centra odpovědnosti. For more information, see [Work with Responsibility Centers](inventory-responsibility-centers.md).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Setup**, and then choose the related link.
2. On the **User Setup** page opens, choose the **New** action.
3. In the **User ID** field, enter the ID of a user, or choose the field to see all current Windows users in the system.
4. Podle potřeby vyplňte pole.


## Viewing permission changes telemetry

You can set up [!INCLUDE[prod_short](includes/prod_short.md)] to send changes that are done to permission to an Application Insights resource in Microsoft Azure. Then, using Azure Monitor, you create reports and set up alerts on the gathered data. For more information, see the following articles in the [!INCLUDE[prod_short](includes/prod_short.md)] Developer and IT Pro help:

- [Monitoring and Analyzing Telemetry - Enabling Application Insights](/dynamics365/business-central/dev-itpro/administration/telemetry-overview#enable)
- [Analyzing Field Monitoring Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-permission-changes-trace)

## Viz také

[Create Users According to Licenses](ui-how-users-permissions.md)  
[Manage Profiles](admin-users-profiles-roles.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[Customizing [!INCLUDE[prod_short](includes/prod_short.md)]](ui-customizing-overview.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Administration](admin-setup-and-administration.md)  
[Add Users to Microsoft 365 for business](/microsoft-365/admin/add-users/add-users)  
[Security and Protection in Business Central](/dynamics365/business-central/dev-itpro/security/security-and-protection) in Developer and IT-pro Help


[!INCLUDE[footer-include](includes/footer-banner.md)]