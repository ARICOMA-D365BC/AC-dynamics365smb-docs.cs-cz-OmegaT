---
title: Troubleshooting Microsoft Teams Integration
description: Learn about what you can do as an administrator to control Microsoft Teams integration.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: Teams, MS Teams, Microsoft Teams, Skype, Link, Microsoft 365, collaborate, collaboration, teamwork, troubleshooting, errors
ms.date: 04/12/2021
ms.author: jswymer
---

# Odstraňování problémů s integrací Microsoft Teams a [!INCLUDE [prod_short](includes/prod_short.md)]

[!INCLUDE [online_only](includes/online_only.md)]

Tento článek obsahuje informace o tom, jak identifikovat a opravit problémy, ke kterým může dojít při používání Microsoft Teams s [!INCLUDE [prod_short](includes/prod_short.md)] jako typický uživatelem nebo správcem.

## Přihlašovací odkaz nefunguje

Pokud se pokusíte přihlásit k aplikaci [!INCLUDE [prod_short.md](includes/prod_short.md)] pro Teams ihned po instalaci aplikace a přihlašovací odkaz nereaguje, může to být proto, že aplikace ještě nedokončila úplně instalaci. Pokud se chcete problém pokusit vyřešit, odhlaste se z klienta Teams a pak se znovu přihlaste.

## Stránka Nastavení je prázdná

Chcete-li dosáhnout nastavení, musíte se nejprve přihlásit. Chcete-li se do aplikace přihlásit, vložte odkaz záznamu v [!INCLUDE [prod_short.md](includes/prod_short.md)] nebo zkuste vyhledat kontakty. Obě tyto akce vás povedou k přihlašení, po kterém můžete jít na stránku **Nastavení**.

## Změnil jsem společnost, ale nezdálo se mi, že by to fungovalo

Po změně společnosti na stránce **Nastavení** si můžete všimnout, že rozbalovací seznam příkazového pole označuje, že stále hledáte v předchozí společnosti. K tomuto problému dochází, když otevřete stránku **Nastavení** přímo z příkazového pole. V tomto případě byla společnost úspěšně změněna a ve skutečnosti budete vyhledávat ve společnosti, na kterou jste se přepli. Problém je v tom, že rozevírací seznam příkazového pole ještě nebyl aktualizován. Rozbalovací nabídka přesně odráží společnost, ve které budete hledat, zavírat nebo odepínat [!INCLUDE [prod_short.md](includes/prod_short.md)] z příkazového pole, a poté znovu otevřete aplikaci.


<!--When you change company from the **Settings** page that you reach from the command box, returning to the command box drop-down continues to show the previous company even though the company was successfully changed. For the drop-down accurately reflect the company you'll search in, you must close or unpin [!INCLUDE [prod_short.md](includes/prod_short.md)] from the command box and then find it again.-->

## Při hledání kontaktů došlo k chybě „Něco se pokazilo“

K této chybě může dojít při hledání ve společnosti, která nebyla inicializována nebo nereaguje. Například nemůžete hledat v nové zkušební společnosti, ve které dosud nebyly přijaty podmínky použití. Chcete-li tento problém vyřešit, pokuste se přihlásit k webovému klientu [!INCLUDE [prod_short.md](includes/prod_short.md)] a proklikejte všechna dialogová okna, která se zobrazí.

## Při hledání kontaktů došlo k chybě „Nelze najít rozhraní API kontaktů/souhrných kontaktů“

Tento problém může být způsoben přizpůsobením nebo průmyslovými řešeními, která ovlivňují nebo upravují [!INCLUDE [prod_short.md](includes/prod_short.md)] nebo neposkytují rozhraní API pro kontakty nebo souhrné kontakty. Pokud problém přetrvává, obraťte se na správce nebo partnera, který poskytuje podporu.

## Žádný z mých odkazů se nerozbalí na kartu

Pokud máte tento problém, je třeba vyzkoušet několik věcí:

1. Nejprve se ujistěte, že aplikace [!INCLUDE [prod_short](includes/prod_short.md)] pro Teams nainstalovaná.

   Chcete-li to zkontrolovat, přihlaste se k desktopové aplikaci Teams nebo Teams v prohlížeči. Pak na levé straně vyberte **Aplikace**nebo vyhledejte **[!INCLUDE [prod_short](includes/prod_short.md)]**. Když najdete aplikaci **[!INCLUDE [prod_short](includes/prod_short.md)]**, vyberte ji a otevřete stránku s podrobnostmi o aplikaci. Pokud je zobrazeno tlačítko **Přidat pro mě**, pak aplikace [!INCLUDE [prod_short](includes/prod_short.md)] není naistalovaná. Další informace o instalaci aplikace naleznete v tématu [Instalace aplikace [!INCLUDE [prod_short](includes/prod_short.md)] pro Microsoft Teams](across-install-app-for-teams.md).

   > [!NOTE]
   > Hostující uživatelé nemohou ihned instalovat aplikaci. Další informace o uživatelích typu host najdete v nejčastějších dotazech v tématu spolupráci s hosty.

2. Dále zkontrolujte, zda jste se přihlásili se správnou identitou.

   V Teams přejděte na libovolný chat a v poli pro psaní zpráv klikněte pravým tlačítkem myši na ikonu [!INCLUDE [prod_short](includes/prod_short.md)] a zvolte **Nastavení**. Když se zobrazí okno, zkontrolujte, zda se uživatel, který říká, že jste připojeni, shoduje s tím, co používáte pro připojení k [!INCLUDE [prod_short](includes/prod_short.md)].

3. Ujistěte se, že proedura 2718 **Page Summary Provider** je vypublikovaná jako webová služba.

   Teams se připojí k [!INCLUDE [prod_short](includes/prod_short.md)] pomocí koncového bodu k této procedury ve službě [!INCLUDE [prod_short](includes/prod_short.md)] service. Informace o publikování webových služeb naleznete v tématu [Publikování Webové Služby](across-how-publish-web-service.md).

4. Vaše organizace může také omezit vkládání odkazů, které se rozbalují na karty. Obraťte se na správce k porozumění zásadám organizace Teams, které se na vás mohou vztahovat.

## Můj odkaz se někdy nerozbalí na kartu

Odkaz se nerozbalí na kartu v následujících situacích:

- Odkaz cílí na stránku, která (na technické úrovni) není připojena ke zdrojové tabulce v [!INCLUDE [prod_short](includes/prod_short.md)]. Můžete zkontrolovat, zda má stránka zdrojovou tabulku, pomocí podokna kontroly stránky ve webovém klientovi v [!INCLUDE [prod_short](includes/prod_short.md)]. Další informace o kontrole stránek najdete v tématu [Prohlížení dat stránky](across-inspect-page.md).
- Teams nepodporuje náhledy odkazů v některých jeho funkcích. Například když vyskočíte z chatu nebo jste hostem jiné organizace.
- Teams se na pozadí vzdají pokusu o zobrazení karty po 15 sekundách, například kvůli problémům se sítí.
- Teams nemusí rozšířit odkaz, pokud jste již vložíly odkaz do stejného pole pro psaní zpráv a kartu jste již odstranili.

Odkaz musí také obsahovat všechny potřebné informace k vyhledání záznamu a zobrazení odpovídající karty. Tyto informace zahrnují:

- Název prostředí jeho, včetně URL cesty. Pokud nezadáte název prostředí, Teams předpokládá, že se pokoušíte dostat do prostředí "Produkčního".
- Název společnosti pomocí parametru *company=*
- Identifikátor stránky pomocí parametru *page=* 
- Záložka záznamu pomocí parametru *bookmark=* 

Například:

`https://businesscentral.dynamics.com/?environmentname=Production&company=CRONUS%20USA%2C%20Inc.&page=21&dc=0&bookmark=21%3bEgAAAAJ7BTEAMAAwADAAMA%3d%3d`

Technické podrobnosti o URL adresách [!INCLUDE [prod_short](includes/prod_short.md)] bežte na [Web Client URL](/dynamics365/business-central/dev-itpro/developer/devenv-web-client-urls) v [!INCLUDE [prod_short](includes/prod_short.md)] Developer a IT Pro Help.

## Otevře se okno s podrobnostmi, ale před zobrazením podrobností se zobrazí chyba

Tento problém může být způsoben několika věcmi: nedostatkem oprávnění v [!INCLUDE [prod_short](includes/prod_short.md)] nebo nastavením prohlížeče (když používáte Teams ve webovém prohlížeči).

1. Ověřte svá oprávnění v [!INCLUDE [prod_short](includes/prod_short.md)].

   Chcete-li zobrazit podrobnosti karty, [!INCLUDE [prod_short](includes/prod_short.md)] zkontroluje vaši licenci a oprávnění k zobrazení konkrétního záznamu a stránky v konkrétní společnosti a prostředí. Pokud nemáte oprávnění pro žádnou z těchto věcí, zobrazí se v okně podrobností standardní [!INCLUDE [prod_short](includes/prod_short.md)] chybové zprávy o oprávněních.

   Další informace o oprávněních naleznete v tématu [Přiřazení práv uživatelům a uživatelským skupinám](ui-define-granular-permissions.md)

2. Pokud používáte Teams v prohlížeči, zkontrolujte nastavení prohlížeče.

   - Your browser's pop-up blocker must be either turned off or set to allow pop-ups from the *businesscentral.dynamics.com* or *bc.dynamics.com* domains. For information about allowing pop-ups for [!INCLUDE [prod_short](includes/prod_short.md)], see [Setting Up Your Browser](across-browser-settings.md#popup).
   - Your browser must have access to local browser storage for cookies and preferences as you work.
   - Avoid using guest or private browsing unless necessary, because they discard or block certain content in some browsers.

   For more information about minimum browser requirements, see [Minimum Requirements for Using [!INCLUDE [prod_short](includes/prod_short.md)]](product-requirements.md#browsers)

## I'm having problems with the camera or location in Teams

When using [!INCLUDE [prod_short](includes/prod_short.md)] features in the details window that require access to your location or device camera, you must first give your consent for Teams to access these device capabilities.

- For Teams in the browser, make sure that your browser settings allow access to camera and location for https://teams.microsoft.com.

- For Teams for iOS or Android, make sure that your device settings allow access to camera and location for the Teams mobile app.

For help about changing these settings, see [My camera isn't working in Teams](https://support.microsoft.com/office/my-camera-isn-t-working-in-teams-9581983b-c6f9-40e3-b0d8-122857972ade?ns=msftteams&version=16&ui=en-us&rs=en-us&ad=us) on Microsoft Support.

The [!INCLUDE [prod_short](includes/prod_short.md)] app doesn't support location in the Teams desktop app. For more information about location, see the [Teams FAQ](teams-faq.md#location).

Some browsers, such as the new Microsoft Edge, allow you to choose which device camera to use when your device supports multiple cameras.

## Teams displays mixed languages for my cards and card details

For cards and card details to display consistently in the same language in Teams, the language of your Teams client and the language you use in [!INCLUDE [prod_short](includes/prod_short.md)] Web client must match.

- To learn about changing the language in Teams, see [Change settings in Teams](https://support.microsoft.com/en-us/office/change-settings-in-teams-b506e8f1-1a96-4cf1-8c6b-b6ed4f424bc7) on Microsoft Support.

- To learn about changing the language in [!INCLUDE [prod_short](includes/prod_short.md)], see [Change Basic Settings - Language](ui-change-basic-settings.md#language).

For more information on how languages work between Teams and [!INCLUDE [prod_short](includes/prod_short.md)], see [Teams FAQ](teams-faq.md#language).

## I edited a field in the details window, but my change wasn't saved

Changes you make to a field in the details windows are automatically saved when you leave the field. Before you close the window after changing a field, be sure to press the Tab key or click/tap outside the field.

## A new tile appeared in the App Launcher. How do I remove it?

When you view your apps on the Office 365 home page (https://home.office.com) or in the app launcher, a new tile named "Business Central Teams Integration Service Connector" will appear after installing the [!INCLUDE [prod_short](includes/prod_short.md)] app for Teams. This tile provides no value in itself and can be safely hidden.

As an administrator, who has Azure Active Directory admin permissions, you can hide the tile by doing the following steps:

1. Sign in to the [Azure Active Directory admin center](https://aad.portal.azure.com/).
2. Select **Enterprise apps**, then select **Business Central Teams Integration Service Connector**.
3. Select **Properties**, then set the **Visible To Users** switch to **No**.
4. Select **Save**.

> [!NOTE]
> It will be a while before this change takes effect.


## Viz také

[[!INCLUDE [prod_short](includes/prod_short.md)] and Microsoft Teams Integration Overview](across-teams-overview.md)  
[Install the [!INCLUDE [prod_short](includes/prod_short.md)] App for Microsoft Teams](across-install-app-for-teams.md)  
[Teams FAQ](teams-faq.md)  
[Developing for Teams Integration](/dynamics365/business-central/dev-itpro/developer/devenv-develop-for-teams)

## [!INCLUDE[d365fin](includes/free_trial_md.md)]


[!INCLUDE[footer-include](includes/footer-banner.md)]