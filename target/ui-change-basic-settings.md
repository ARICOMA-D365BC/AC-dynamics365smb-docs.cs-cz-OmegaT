---
title: Change basic settings for the current user
description: Learn how to change some basic settings in Business Central, for example, your role and role center, company, work date, and time zones.
author: jswymer

ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: change Role Center, notification, change company, change work date, decimal separator
ms.search.form: 9022, 9019, 9027, 9020, 9026, 9030, 9000, 9009, 9004, 9005, 9024, 9006, 9007, 9010, 9016, 9017
ms.date: 10/01/2021
ms.author: jswymer

---
# Change Basic Settings

On the **My Settings** page, you can see and change basic settings for your [!INCLUDE[prod_short](includes/prod_short.md)]. The changes that you make will only affect your workspace, not the workspaces of other users.

[!INCLUDE [about-ui-learn](includes/about-ui-learn.md)]

## <a name="role-center"></a>Role

The role determines the home page, a starting screen that is designed for the needs of a specific role in an organization. Depending on your role, the home page, or role center, gives you an overview of the business, your department, or your personal tasks. Pomáhá také při procházení každodenních úkolů a při hledání práce, která vám byla přidělena.

* Navigace v horní části umožňuje přepínat mezi zákazníky, prodejci, zbožím a dalšími důležitými seznamy informací. Similarly, actions allow you to initiate tasks, such as create a new sales invoice, directly from the home page.

* In the center, you find the **Activities** area, which shows current data and can be clicked or tapped to view more detailed information. Key performance indicators (KPIs) can be set up to display a selected chart for a visual representation of, for example, cash flow or income and expenses. You can also build up a list of favorite customers on the home page for business accounts that you do business with often or need to pay special attention to.

### To change the role

The default role is **Business Manager**, but you can select another role to use a role center that fits your needs better.

1. In the top right corner, choose the **Settings** icon ![Settings.](media/ui-experience/settings_icon_small.png "Settings icon for role center"), and then choose the **My Settings** action.
2. On the **My Settings** page, in the **Role** field, select the role that you want to use by default. For example, select **Accountant**.
3. Zvolte tlačítko **OK**.

## <a name="company"></a>Společnost

A company functions as a container for data in [!INCLUDE[prod_short](includes/prod_short.md)]. V databázi může existovat více společností, ale v jednom okamžiku lze vybrat pouze jednu.

Výchozí společnost se nazývá CRONUS a obsahuje pouze demonstrační data. You can create a new company with custom data. For more information, see [Creating New Companies](about-new-company.md).

### To change the company name

The company name is always displayed at the top left corner and works as an action that you can choose to go back to the Role Center. You can change this name on the **Company Information** page.

1. Choose the ![Sprocket icon to open the Settings menu.](media/ui-experience/settings_icon_small.png) icon, and then choose the **Company Information** action.
2. In the **Name** field, enter the new company name.
3. Leave the page. The system restarts and displays the new company in the top-left corner.

### <a name="badge"></a>To display a company badge for quick access to company information

You can add a customized badge in the top-right corner, which you can choose to quickly view company name and tenant information in a pop-up box. The company badge is also useful when [!INCLUDE[prod_short](includes/prod_short.md)] is embedded in another application, like Microsoft Teams or in some other web application. In these cases, because the [!INCLUDE[web_client](includes/web_client.md)] displays less surrounding contextual information, the company badge serves as the only way to determine which company or environment a record belongs to.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi ](media/ui-search/search_small.png "Řekněte mi, co chcete dělat") zadejte **Informace o společnosti** a vyberte související odkaz.
2. On the **Company Badge** FastTab, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)].

> [!NOTE]
> If a company badge is defined, then you cannot change the company name as described in [To change the company name](ui-change-basic-settings.md#to-change-the-company-name)

## <a name="work-date"></a>Work date
The most commonly used work date is today's date. You may have to temporarily change the work date to be able to perform tasks, such as completing transactions for a date that is not today's date.

> [!TIP]  
> In all date fields, type **t** to quickly enter today's date, and type **w** to quickly enter the work date, which is the value in the **Work Date** field on the **My Settings** page.

> [!IMPORTANT]  
> After you change the work date, if you sign out or switch to another company, the work data reverts to the default work date. Takže při příštím přihlášení nebo přepnutí zpět na původní společnost bude možná nutné znovu nastavit pracovní datum.

### Work date indication

The work date is critical on pages that can be edited. Whenever the work date isn't set to today's date on an editable page, then two types of indicators appear on the page:

* A reminder appears at the top of the page that tells you what the work date is set to. The reminder provides a direct link to the work date setting on the **My Settings** page so you change the date if you want. From the reminder, you can also choose to dismiss the reminder for the rest of your session. Unless you change the work date to "today", the reminder will appear the next time you sign in.

* If you dismiss the reminder, the work date will appear in the title of the page.

If the work date isn't set to the current day (today), then on all pages where you can edit data, the current work date appears in the upper-left corner.

## <a name="region"></a> Oblasti

The **Region** setting determines how dates, times, numbers, and currencies are shown or formatted. It also determines what character is used as the decimal separator when using a numeric keyboard to enter data. For more information, see [Entering Data](ui-enter-data.md#decimal).

## <a name="language"></a> Jazyk

Změní zobrazovaný jazyk. This field appears only when there's more than one language to choose from.

The initial language is either determined by the administrator or by your browser settings when you sign up for [!INCLUDE[prod_short](includes/prod_short.md)]. Jazyk, který nastavíte, bude použit na všech zařízeních, ze kterých se přihlašujete, jako je telefon nebo tablet.

Additional languages for [!INCLUDE[prod_short](includes/prod_short.md)] can be installed from AppSource. While all supported display languages are shown in the list, the administrator must install the relevant language app to the tenant before users can switch to the new language in [!INCLUDE[prod_short](includes/prod_short.md)].

## Time zone

Defines the time zone where you are located. When you first sign into [!INCLUDE [prod_short](includes/prod_short.md)], the time zone is set based on your company's address. Change it if it doesn't fit your physical location.

## Notifications

Choose the *Change when I receive notifications* link to view or change the notifications that you get about certain events or changes in status, such as when you are about to invoice a customer who has an overdue balance, or the available inventory is lower than the quantity you are about to sell. For more information, see [Managing Notifications](ui-smart-notifications.md).

## Teaching tips

[!INCLUDE [ua-teachingtips](includes/ua-teachingtips.md)]

## Podívejte se na související školení na webu [Microsoft Learn](/learn/modules/personalize-ui-dynamics-365-business-central/index)

## Viz také

[Creating New Companies](about-new-company.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Change Which Features are Displayed](ui-experiences.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
