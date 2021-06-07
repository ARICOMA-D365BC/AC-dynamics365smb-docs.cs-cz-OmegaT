---
title: Manage user settings and preferences as the administrator
description: Manage user settings and preferences in Dynamics 365 Business Central.
author: sorenfriisalexandersen

ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.reviewer: edupont
ms.search.keywords: user settings, preferences, language, region, time zone, regional settings
ms.date: 04/01/2021
ms.author: soalex

---
# Správa předvoleb a uživatelských nastavení

Jako správce můžete konfigurovat uživatelská nastavení v [!INCLUDE[prod_short](includes/prod_short.md)], podobně jako jednotliví uživatelé mohou spravovat své vlastní předvolby na stránce **Má nastavení** page.

Získejte přehled o všech uživatelích na přehledu **Uživatelé** a změňte jednotlivá nastavení výběrem funkce **Uživatelská nastavení** pro příslušného uživatele

> [!TIP]
> Seznam **Nastavení uživatelů** zobrazuje aktuální nastavení pro každého uživatele. Chcete-li zobrazit nebo upravit jednotlivé uživatele, vyberte talčítko **Zobrazit** nebo **Upravit**.

Stránka **Karta nastavení uživatelů** je podobný jako stránka **Má nastavení**, ke které má každý uživatel přístup, a je to výkonný nástroj pro vás jako správce například pro nastavení výchozího nastavení a vymazání přizpůsobených stránek.

## Typy uživatelských nastavení

*Uživatelská nastavení* nejsou stejná jako *Nastavení uživatelů*, které se týká uživatele jako entity a přístupu uživatele do systému. Uživatelské nastavení navíc nemá nic společného s přizpůsobením uživatele, jako jsou například lehké změny uživatelského rozhraní. Uživatelská nastavení určují předdefinovaná nastavení pro každého uživatele v různých aspektech způsobu, jakým se mu aplikace prezentuje. Následující odstavec uvádí pět typů uživatelských nastavení a předvoleb, které může nastavit jednotlivec nebo centrálně správce:

- **Společnost**

   Toto nastavení určuje společnost, ke které se má uživatel přihlásit při příštím přihlášení. Uživatel může mít přístup k více společnostem a může být aktivní v několika společnostech.

- **Role**

   Role nebo profil popisuje funkci uživatele ve společnosti, například *Manažer prodeje*, *Účetní* nebo *Nákupčí*. Profil pak určuje centrum rolí uživatele - domovskou stránku, kterou uživatelé uvidí při přihlášení. Profil nemá vliv na přístupová práva k funkcím v [!INCLUDE[prod_short](includes/prod_short.md)].

- **Jazyk**

   Definuje jazyk aplikace, který [!INCLUDE[prod_short](includes/prod_short.md)] zobrazuje texty, popisy a chybové hlášky. Pokud jsou uživatelé [!INCLUDE[prod_short](includes/prod_short.md)] synchronizováni z Microsoft 365, použije se jazykové nastavení z Microsoft 365 za předpokladu, že uživatel chce použít stejné nastavení v produktech Office a [!INCLUDE[prod_short](includes/prod_short.md)]. Správce může změnit výchozí nastavení a každý uživatel si může vybrat mezi dostupnými jazyky na stránce Moje nastavení. Po provedení další synchronizace, se hodnoty resetují dle Microsoft 365.

   Pokud se jazykové nastavení z Microsoftu 365 shoduje s podporovaným jazykem v [!INCLUDE[prod_short](includes/prod_short.md)], bude pro uživatele zvolen tento jazyk.

   > [!NOTE]
   > Možná budete muset nainstalovat jazykovou vrstvu pro [!INCLUDE[prod_short](includes/prod_short.md)], aby se jazyk mohl správně zobrazit.
   >  Proto je dobrým zvykem instalovat nezbytné jazykové aplikace před tím, než se jakýkoli uživatel přihlásí poprvé, aby měl dobrý zážitek z prvního dne. Další informace naleznete v seznamu  [podporované jazyky](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations).

- **Oblast**

   Definuje způsob, jakým jsou data a čísla prezentována v klientu [!INCLUDE[prod_short](includes/prod_short.md)] například zda použít evropské nebo americké formáty data nebo jak zobrazit desetinné znaménko a oddělovače tisíců v částkách. If [!INCLUDE[prod_short](includes/prod_short.md)] users are synchronized from Microsoft 365, the regional settings from Microsoft 365 are used, assuming that the user wants to use the same settings in Office products and [!INCLUDE[prod_short](includes/prod_short.md)]. An administrator or user can change these settings manually in [!INCLUDE[prod_short](includes/prod_short.md)], but they will be reset to the value from Microsoft 365 once the next synchronization is performed.

- **Time zone**

   Defines the time zone in which the user is located. Currently this is not synchronized from Microsoft 365 and must be set manually.

- **Teaching tips**

   [!INCLUDE [ua-teachingtips](includes/ua-teachingtips.md)] As an administrator, you can switch off teaching tips for all users, such as if you are in process of onboarding users who are already familiar with [!INCLUDE [prod_short](includes/prod_short.md)].

> [!NOTE]
> If a Microsoft 365 user synchronization is made while users are logged into [!INCLUDE[prod_short](includes/prod_short.md)], these users must refresh the browser or log out and back in to [!INCLUDE[prod_short](includes/prod_short.md)] to see a potential different language set by the synchronization action.

## Overview of all user-specific changes

As the administrator, you can get an overview of individual changes to [!INCLUDE [prod_short](includes/prod_short.md)] that each user might have made to various pages in [!INCLUDE [prod_short](includes/prod_short.md)]. As users make changes to their experience in [!INCLUDE [prod_short](includes/prod_short.md)], these changes will be reflected in the **User Personalizations** list. <!--Administrators can also set these settings for users before they log in the first time, so users do not have to do it themselves, providing them a better *getting started* experience.-->

<!-- >[!NOTE]
> User personalizations do not have anything to do with the *personal* lightweight changes a user can make to the user experience.-->

## To review or delete user personalizations

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Personalized Pages**, and then choose the related link.
2. This shows the list of users and their personalized pages. To clear a user's personalization, click the relevant row, or choose **Manage**, and then choose **Delete**.

This deletes the personalization, and the user's experience of the relevant page returns to the default state.

## Viz také

[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Country/regional availability and supported languages](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations)  
[Changing Language and Locale](about-locale-language.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
