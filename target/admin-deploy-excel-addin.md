---
title: Getting the Business Central Add-in for Excel
description: Learn about how to get users the Business Central add-in for Excel.
author: jswymer

ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: Excel, add-in, centralized deployment, M365 admin center, individual acquisition, appsource
ms.date: 10/07/2021
ms.author: jswymer

---
# Získejte doplněk Business Central pro Excel

[! INCLUDE[prod_short](includes/prod_short.md)] obsahuje doplněk pro excel, který umožňuje uživatelům vybrat akci **Upravit v excelu** na určitých stránkách a otevřít tak data v excelovém listu. Tato akce se liší od akce **Otevřít v aplikaci Excel**, protože umožňuje uživatelům provádět změny v aplikaci Excel a poté publikovat změny zpět do [! ZAHRNOUT[prod_short](includes/prod_short.md)]

## Přehled

### O doplňku

Doplněk se nazývá **Doplněk Microsoft Dynamics Office** a je k dispozici pro instalaci z [Office Store (AppSource).](https://appsource.microsoft.com/) S nainstalovaným doplňkem je akce **Upravit v Excelu** dostupná na většině stránek seznamu a částí seznamu pomocí ikony **Sdílet** ![Sdílet stránku v jiné aplikaci. ](media/share-icon.png). Další informace o použití doplňku naleznete v tématu [Zobrazení a úpravy v aplikaci Excel z Business Central](across-work-with-excel.md).

> [!NOTE]
> Doplněk funguje pouze v systému Windows; ne na MacOS.

### O nasazení jako správce

S [!INCLUDE[prod_short](includes/prod_short.md)] online existuje několik možností nasazení, jak dostat doplněk k uživatelům. Jednou z možností je *individuální pořízení*, kdy necháte uživatele instalovat doplněk sami. Při použití této možnosti musí mít uživatelé přístup ke stahování souborů z Office Store. Další možností je nastavit *centralizované nasazení* v Admin Centru pro správu Microsoft 365 tak, aby se doplněk automaticky nasadil do celé organizace, skupin nebo konkrétních uživatelů. Centralizované nasazení poskytuje způsob, jak získat doplněk pro uživatele, pokud vaše organizace neposkytuje uživatelům přístup k Office Store.

Pro koncového uživatele se prostředí instalace liší pro dva scénáře nasazení:

- Při individuální akvizici se při prvním výběru akce **Upravit v aplikaci Excel** otevře podokno **Nový doplněk Office** v aplikaci Excel. K instalaci doplňku uživatel zvolí **Důvěřovat tomuto doplňku**, čímž se doplněk nainstaluje přímo z Office Store. Uživatelé se pak přihlásí do [!INCLUDE[prod_short](includes/prod_short.md)] pomocí svého uživatelského jména a hesla.

- Při centralizovaném nasazení se doplněk při prvním výběru akce **Upravit v aplikaci Excel** automaticky nainstaluje do aplikace Excel z centralizovaného nasazení; ne z Office Store. Jediné, co uživatelé musí udělat, je přihlásit se k [!INCLUDE[prod_short](includes/prod_short.md)]

S oběma těmito možnostmi nasazení je doplněk automaticky nakonfigurován pro připojení k [!INCLUDE[prod_short](includes/prod_short.md)]. Třetí možností nasazení je ruční instalace doplňku přímo z aplikace Excel. Pomocí této možnosti budou uživatelé muset nakonfigurovat doplněk pro připojení k [!INCLUDE[prod_short](includes/prod_short.md)]

### <a name="switch"></a>Přechod z individuální akvizice na centralizované nasazení nebo naopak

Když přejdete z individuálního pořízení doplňku na centralizované nasazení nebo naopak, budou ovlivněny soubory aplikace Excel, které uživatelé vytvořili před přechodem. Po přechodu mohou uživatelé stále otevírat všechny listy aplikace Excel, které byly dříve vytvořeny pomocí akce **Upravit v aplikaci Excel** nebo vytvořeny ručně konfigurací doplňku aplikace Excel. Nemohou však aktualizovat data v souboru z Business Central nebo odesílat aktualizace do Business Central

Tento stav je způsoben skutečností, že každému souboru aplikace Excel je přiřazen identifikátor "doplňku". Při přechodu do centralizovaného nasazení nebo z centralizovaného nasazení je přiřazeno jiné ID, takže dřívější ID se zablokuje.

## Příprava (pouze on-premise)

[! INCLUDE[prod_short](includes/prod_short.md)] v místním prostředí vyžaduje, aby vaše prostředí bylo nakonfigurované pro doplněk. Pokud ne, akce **Upravit v Excelu** nebude uživatelům k dispozici. Další informace naleznete v části [Nastavení doplňku aplikace Excel pro úpravu dat Business Central](/dynamics365/business-central/dev-itpro/administration/configuring-excel-addin) v nápovědě pro vývojáře a IT profesionály.

## Deploy the add-in by using Centralized Deployment

Centralized Deployment is a feature in Microsoft 365 admin center that you use to automatically install add-ins in users' Office apps, like Excel. To help you with Centralized Deployment, [!INCLUDE[prod_short](includes/prod_short.md)] includes the **Excel Add-in Centralized Deployment** assisted setup.

### Before you begin

- To learn about preventing users from downloading from the Office store, see [Manage add-ins in the admin center](/microsoft-365/admin/manage/manage-addins-in-the-admin-center).
- Verify that Centralized Deployment will work for your organization. For more information, see [Determine if Centralized Deployment of add-ins works for your organization](/microsoft-365/admin/manage/centralized-deployment-of-add-ins)
- If you're transitioning from individual acquisition, see [Switching from individual acquisition to Centralized Deployment](#switch)

> [!NOTE]
> Enabling Centralized Deployment affects features that use the Excel add-in, such as the **Edit in Excel** action. It has no effect on other Excel-related features and or permissions assigned to users in [!INCLUDE[prod_short](includes/prod_short.md)]

### Set up Centralized Deployment of the add-in

You'll work in both [!INCLUDE[prod_short](includes/prod_short.md)] and the Microsoft 365 admin center.

1. In [!INCLUDE[prod_short](includes/prod_short.md)], choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Excel Add-in Centralized Deployment**, then choose the related link.
2. Read the information on the **Business Central Excel add-in setup** page and choose **Next**.
3. Sign in to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/?linkid=2163967) and go to **Integrated Apps**<!--**Add-ins**-->.

   Complete the following steps to configure the add-in to deploy from the Office Store:
   1. Choose **Get apps** to open Office Store (AppSource). <!--**Deploy Add-in** 5. In the **Deploy a new add-in**, select **Choose from the store**.-->
   2. Search for **Microsoft Dynamics Office Add-in**, then select **Get it now**. <!--On the **Select add-in** page, search for and select **Microsoft Dynamics Office Add-in** > **Add** > **Continue**.-->
   3. On the **Add Users** page, specify the users that you want to deploy the add-in for, then choose **Next**.<!--On the **Configure add-in**, specify the users that you want to deploy the add-in for.-->
   4. Review the **Accept permissions requests**, then choose **Next** > **Finish Deployment**.
   5. Wait for the green check mark next to **Deployed** appears for the add-in, then choose **Done**. <!--Select **Deploy** and wait til successful, then **Next** > **Continue**.-->

      The add-in appears on the **Add-ins** page. For more information about deploying add-ins in the Microsoft 365 admin center, see [Deploy add-ins in the admin center](/power-platform/admin/use-service-admin-role-manage-tenant?azure-portal=true).
4. Go back to **Excel Add-in Centralized Deployment** assisted setup in [!INCLUDE[prod_short](includes/prod_short.md)], and choose **Next**.
5. Turn on **Use Centralized Deployment**, and choose **Finish**.

   If you don't turn on this switch, [!INCLUDE[prod_short](includes/prod_short.md)] will get the add-in directly from the Office Store.

When finished, you can always change the deployment in Microsoft 365 admin center, like assigning more users. For more information about deploying add-ins in the admin center, see [Deploy add-ins in the admin center](/power-platform/admin/use-service-admin-role-manage-tenant?azure-portal=true).

> [!IMPORTANT]
> If you have more than one environment, you must run the **Excel Add-in Centralized Deployment** assisted setup on each environment that you want to use Centralized Deployment. However, you don't have to configure the Centralized Deployment in Microsoft 365 again. The only thing you have to do is turn on the **Use Centralized Deployment** switch in the assisted setup.

> [!NOTE]
> It can take up to 24 hours before users the add-in deploys automatically in Excel of users.

## <a name="install"></a>Individual acquisition: Install the add-in manually for your own use

In most cases, when you open Excel from Business Central, the add-in will either be installed automatically for you or you'll be prompted to install it. There might be cases, however, where you have to manually install the add-in.

1. Open Excel, then open any Excel workbook.
2. On the **Insert** menu, choose **Add-ins** > **Get add-ins**
3. Go to **Admin managed** and look for **Microsoft Dynamics Office Add-In**. If you see there, select it, then choose **Add**. If you don't see it, go to **Store**, then search for *Microsoft Dynamics Office Add-In* and follow the instruction on screen to add it.

When the add-in is installed, it shows up as a panel in Excel. Next, configure the connection.

### Configure the Business Central connection

If a user can't connect automatically, you can unblock them by asking them to follow these steps:

1. In the **Microsoft Dynamics** add-in pane in Excel, choose **Add server information**. If you don't see it, choose the ![More option button in Excel.](media/cogwheel.png) icon at the top to open the options dialog.
2. For [!INCLUDE[prod_short](includes/prod_short.md)] online, set **Server URL** to `https://exceladdinprovider.smb.dynamics.com`. For [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, set it the URL of the web client, like `https://myBCserver/190`.
3. Choose **OK**, and then confirm that the app reloads.
4. When prompted, sign in with your Business Central user name and password.
5. Optionally, choose the environment and company that you want to connect to.

The add-in is now connected to [!INCLUDE [prod_short](includes/prod_short.md)], and you can edit data and publish the changes to [!INCLUDE [prod_short](includes/prod_short.md)].

## Prepare devices and network for the Excel Add-In

Network services such as proxies or firewalls must allow routing between each client device on which the add-In is installed and many service endpoints. For a list of endpoints, see [Preparing your network for the Excel Add-In](/dynamics365/business-central/dev-itpro/administration/configuring-network-for-addins).

## Řešení potíží

Sometimes, users run into problems with the Excel add-in. This section gives some tips for how to unblock users in certain circumstances.

| Problém | Solution or workaround | Komentáře |
|---------|---------|---------|
| The add-in doesn't start | Check whether the add-in is deployed centrally. Or, check whether the user is blocked from installing it locally. | The admin can configure Office so that users can't acquire add-ins. In those cases, the admin must deploy the add-in centrally. For more information, see [Deploy add-ins in the admin center](/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide&preserve-view=true). |
| Data doesn't load into Excel | Test the connection by opening another list in Excel from [!INCLUDE [prod_short](includes/prod_short.md)]. Or, open the workbook in Excel in a browser. | If the user has specified a company name that contains special characters, the add-in can't connect. |
| Data can't publish back to [!INCLUDE [prod_short](includes/prod_short.md)]. | Test the connection by opening the workbook in Excel in a browser. | Sometimes an extension can block the publishing job. If the page is extended or customized, remove the extensions, and then try again. |
| The dates are wrong | Excel might show times and dates in a different format than [!INCLUDE [prod_short](includes/prod_short.md)]. This condition doesn't make them wrong, and the data in [!INCLUDE [prod_short](includes/prod_short.md)] won't get messed up. |         |
| For some list pages, editing multiple lines in Excel consistently causes errors. This condition can occur if OData calls include FlowFields and fields outside of the repeater control. | On the **Web Services** page, select the **Exclude Non-Editable FlowFields** and **Exclude Fields Outside of the Repeater** check boxes for the published page. Selecting these check boxes excludes non-editable FlowFields and field from the eTag calculation. | These check boxes are hidden by default. To show them on the **Web Services** page, use [personalization](/dynamics365/business-central/ui-personalization-user). |
| Users can no longer sign in to the add-in. When they try to sign in, the process stops without completing. | This problem might be caused by an update that we made to the add-in, sometime in July 2022. For more information and a fix, see [Modify the Excel Add-in Configuration to Support July 2022 Update](/dynamics365/business-central/dev-itpro/administration/update-excel-addin-configuration). | Applies to [!INCLUDE [prod_short](includes/prod_short.md)] on-premises only |

<!--
## Deploy the Excel add-in for Business Central online

For [!INCLUDE [prod_short](includes/prod_short.md)] online, the administrator can deploy the add-in for all users. But users can also install the add-in themselves, provided they have permission to configure their Office experience.  

> [!TIP]
> In some organizations, administrators cannot deploy add-ins centrally. For more information, see [Determine if Centralized Deployment of add-ins works for your organization](/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide&preserve-view=true).

### To deploy the Excel add-in for all users

1. As the administrator, sign in to the Microsoft commercial website and find the add-in at [https://appsource.microsoft.com/product/office/WA104379629](https://appsource.microsoft.com/product/office/WA104379629).
2. Choose the **Get it now** button.

    You'll be redirected to the Microsoft 365 admin center.
3. In the left panel, go to **Settings**, and then choose **Add-ins**.
4. In the **Configure add-in** pane, specify which users to grant access to the add-in.
5. Save your changes.


### To add the Excel add-in locally

1. Open Excel, and then open any Excel workbook.
2. On the **Insert** menu, choose **Office Add-ins**, and then choose **Admin managed** or **Store** as appropriate.
3. Search for *Dynamics Office Add-In*, and then install the add-in.

When the add-in is installed, it shows up as a panel in Excel. Next, you must configure the connection.

> [!TIP]
> If the workbook is not automatically saved to the user's OneDrive, then recommend them to save all workbooks that they export from [!INCLUDE [prod_short](includes/prod_short.md)].When they open the workbook again, the connection is still available, so they do not have to configure the connection again.

> [!NOTE]
> In certain deployments, the administrator must configure network access to unblock the Excel add-in. For more information, see [Preparing Your Network for the Excel Add-In](configuring-network-for-addins.md).-->

## Viz související školení na webu [Microsoft Learn](/learn/modules/configure-powerbi-excel-dynamics-365-business-central/index)

## Viz také

[Analyzing Financial Statements in Microsoft Excel](finance-analyze-excel.md)  
[Work with Business Central](ui-work-product.md)  
[Enhancements to Excel integration in 2019 release wave 2](/dynamics365-release-plan/2019wave2/dynamics365-business-central/enhancements-excel-integration)


[!INCLUDE[footer-include](includes/footer-banner.md)]
