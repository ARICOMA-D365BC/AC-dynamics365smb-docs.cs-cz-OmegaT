---
    title: Setting Up and Using a Purchase Approval Workflow | Microsoft Docs
    description: You can automate the process of approving new or changed records, such as documents, journal lines, and customer cards, by creating workflows with steps for the approvals in question. Before you create approval workflows, you must set up an approver and substitute approver for each approval user. You can also set approvers' amount limits to define which sales and purchase records they are qualified to approve. Approval requests and other notifications can be sent as email or internal note. For each approval user setup, you can also set up when they receive notifications.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2021
    ms.author: edupont

---
# Návod: Nastavení a použití workflow schvalování nákupu

Můžete automatizovat proces schvalování nových nebo změněných záznamů, jako jsou doklady, řádky deníku a karty zákazníků, vytvořením workflow s kroky pro příslušné schvalování. Před vytvořením schvalovacího workflow je nutné nastavit schvalovatele a nahradit schvalovatele pro každého uživatele schvalování. You can also set approvers' amount limits to define which sales and purchase records they are qualified to approve. Žádosti o schválení a další oznámení lze odeslat jako e-mail nebo interní oznámení. Pro každé nastavení uživatele schvalování můžete také nastavit, když obdrží oznámení.

> [!NOTE]
> In addition to the Workflow functionality within [!INCLUDE[prod_short](includes/prod_short.md)], you can use Power Automate to define workflows for events in [!INCLUDE[prod_short](includes/prod_short.md)]. Note that although they are two separate workflow systems, any flow template that you create with Power Automate is added to the list of workflow templates within [!INCLUDE[prod_short](includes/prod_short.md)]. For more information, see [Using Business Central in an Automated Workflow](across-how-use-financials-data-source-flow.md).

Můžete nastavovat a používat workflow, které spojují úlohy podnikových procesů prováděné různými uživateli. Systémové úlohy, jako je například automatické účtování, lze zahrnout jako kroky do workflow, které předchází nebo následují úkoly uživatele. Vyžádání a udělení souhlasu k vytvoření nových záznamů jsou typické kroky workflow. For more information, see [Workflow](across-workflow.md).

## O tomto návodu

Tento návod ilustruje následující úkoly:

- Nastavení uživatelů schvalování
- Nastavení oznámení pro uživatele schvalování.
- Úprava a povolení schvalovacího workflow.
- Jako Alicia budeme žádet o schválení objednávky.
- Jako Sean obdržíme oznámení a žádost o schválení.

## Příběh

Sean je super uživatel ve společnosti CRONUS. Vytvořil dva uživatele schvalování. Jedním z nich je Alicia, která zastupuje nákupčího. The other is himself representing Alicia's approver. Sean si poté udělí neomezená práva ke schválení nákupu a stanoví, že obdrží interní notifikaci, jakmile nastane příslušná událost. Nakonec Sean vytvoří požadované workflow schvalování jako kopii existující šablony workflow schvalování objednávky, ponechá všechny stávající podmínky události a možnosti odpovědí nezměněné a poté povolí workflow.

To test the approval workflow, Sean first signs in to [!INCLUDE[prod_short](includes/prod_short.md)] as Alicia, and then requests approval of a purchase order. Sean se poté přihlásí sám za sebe, uvidí oznámení ve svém Centru rolí, poté rozkline odkaz na žádost o schválení objednávky a žádost schválí.

## Users

Before you can set up approval users and their notification method, you must make sure that two users exist in [!INCLUDE[prod_short](includes/prod_short.md)]: One user will represent Alicia. Druhý uživatel, vy, reporezentujete Seana. For more information, see [Create Users According to Licenses](ui-how-users-permissions.md).

### Nastavení uživatelů schvalování

Pokud jste přihlášeni jako vy, nastavte Alicii jako uživatele schválení, jehož schvalovatelem jste sami. Nastavte oprávnění ke schválení a určete, jak a kdy budete o žádostech o schválení informováni.

#### Nastavení Vašeho účtu a Alicie jako uživatelů schvalování

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Approval User Setup**, and then choose the related link.
2. On the **Approval User Setup** page, choose the **New** action.

   > [!NOTE]  
   > Nejdříve musíte nastavit schvalovatele, než nastavíte uživatele schvalování, který potřebuje svého schvalovatele. Proto musíte nejdříve nastavut sebe před nastavením Alicie.

3. Nastavte dva uživatele schvalování tak, že vyplníte pole podle popisu v následující tabulce.

   | ID uživatele | ID schvalovatele | Neomezené schvalování nákupu |
   |-------------|-----------------|---------------------------------|  
   | VY | Vybraný |
   | ALICIA | VY |

### Nastavení oznámení

V tomto návodu je uživatel upozorněn interním oznámením o požadavcích na schvalování. Approval notification can also be by email, and you can add a workflow response step that notifies the sender when a request is approved or rejected. For more information, see [Specify When and How to Receive Notifications](across-how-to-specify-when-and-how-to-receive-notifications.md).

#### Nastavení způsobu jak a kdy budete upozorněni

1. On the **Approval User Setup** page, select the line for yourself, and then choose the **Notification Setup** action.
2. On the **Notification Setup** page, in the **Notification Type** field, choose **Approval**.
3. In the **Notification Method** field, choose **Note**.
4. On the **Notification Setup** page, choose the **Notification Schedule** action.
5. On the **Notification Schedule** page, in the **Recurrence** field, select **Instantly**.

## Vytvoření Workflow

Create the purchase order approval workflow by copying the steps from the **Purchase Order Approval Workflow** workflow template. Ponechejte existující kroky workflow beze změny a povolte ho.

> [!TIP]
> Optionally, add a workflow response step to notify the sender when their request is approved or rejected. For more information, see [Specify When and How to Receive Notifications](across-how-to-specify-when-and-how-to-receive-notifications.md).

### Vytvoření a povolení workflow schvalování nákupní objednávky

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Workflows**, and then choose the related link.
2. On the **Workflows** page, choose the **New Workflow from Template** action.
3. On the **Workflow Templates** page, select the workflow template named **Purchase Order Approval Workflow**, and then choose the **OK** button.

   The **Workflow** page opens for a new workflow containing all the information of the selected template. The value in the **Code** field is extended with *-01* to indicate that this is the first workflow that is created from the **Purchase Order Approval Workflow** workflow template.
4. On the header of the **Workflow** page, select the **Enabled** check box.

## Použití schovalování workflow

Use the new Purchase Order Approval Workflow workflow by first signing in to [!INCLUDE[prod_short](includes/prod_short.md)] as Alicia to request approval of a purchase order. Potom se přihlaste sami, zobrazte upozornění v Centru rolí, kliknetě na odkaz žádosti o schválení a pak žádost schvalte.

### Žádost o schválení objednávky jako Alicia.

1. Přihlaste se jako Alicia.
2. Vyberte ![Žárovku, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete delat"), zadejte **Nákupní objednávky**a pak zvolte související odkaz.
3. Select the line for open purchase order 106001, and then choose the **Edit** action.
4. On the **Purchase Order** page, choose the **Send Approval Request** action.

Notice that the value in the **Status** field has changed to **Pending Approval**.

### Schválení objednávky jako Sean

1. Přihlaste se jako Sean.
2. On the Role Center, in the **Self Service** area, choose the **Requests to Approve** tile.
3. On the **Requests to Approve** page, select the line about the purchase order by Alicia, and then choose the **Approve** action.

The value in the **Status** field on Alicia's purchase order changes to **Released**.

Nyní jste nastavili a testovali jednoduché workflow na základě prvních dvou kroků Workflow schvalování nákupní objednávky. You can easily extend this workflow to automatically post Alicia's purchase order when Sean approves it. Chcete-li to provést, musíte povolit Worklflow nákupní faktury ve Workflow, ve kterém je odpověď na vydanou nákupní fakturu k zaúčtování. First you must change the event condition on the first workflow step from (purchase) **Invoice** to **Order**.

The generic version of [!INCLUDE[prod_short](includes/prod_short.md)] includes a number of workflow templates for scenarios that are supported by the application code. Většina z nich je určena pro schvalování.

Varianty workflow definujete vyplněním polí na řádcích workflow z pevných seznamů hodnot událostí a odpovědí představujících scénáře podporované kódem aplikace. For more information, see [Create Workflows](across-how-to-create-workflows.md).

If a business scenario requires a workflow event or response that is not supported, a Microsoft partner must implement them through code, or you can set up a workflow using Power Automate. For more information, see [Using [!INCLUDE[prod_short](includes/prod_short.md)] in an Automated Workflow](across-how-use-financials-data-source-flow.md) or [Events in AL](/dynamics365/business-central/dev-itpro/developer/devenv-events-in-al) in the developer help, respectively.

## Viz také

[Set Up Approval Users](across-how-to-set-up-approval-users.md)  
[Setting Up Workflow Notifications](across-setting-up-workflow-notifications.md)  
[Create Workflows](across-how-to-create-workflows.md)  
[Use Approval Workflows](across-how-use-approval-workflows.md)  
[Workflow](across-workflow.md)  
[Using Business Central in an Automated Workflow](across-how-use-financials-data-source-flow.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]