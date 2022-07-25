---
title: Managing Microsoft Teams Integration with Business Central| Microsoft Docs
description: Manage Business Central integration with Microsoft Teams.
author: jswymer

ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: Teams, MS Teams, Microsoft Teams, Skype, Link, Microsoft 365, collaborate, collaboration, teamwork
ms.date: 04/12/2021
ms.author: jswymer
---

# Správa integrace Microsoft Teams s [!INCLUDE [prod_short](includes/prod_short.md)]

[!INCLUDE [online_only](includes/online_only.md)]

Tento článek obsahuje přehled toho, co můžete jako správce udělat pro řízení integrace Microsoft Teams s [!INCLUDE [prod_short](includes/prod_short.md)].

## v Microsoft Teams

### Minimální požadavky

Tato část popisuje minimální požadavky na aplikaci [!INCLUDE [prod_short](includes/prod_short.md)] pro práci v Teams.

- Požadované licence

   The [!INCLUDE[prod_short](includes/prod_short.md)] app requires a Teams license through a Microsoft 365 Business or Enterprise subscription. Standalone Teams subscriptions such as Microsoft Teams (free) or Microsoft Teams Essentials aren't supported.

   Most features of the [!INCLUDE[prod_short](includes/prod_short.md)] app for Teams also require a [!INCLUDE [prod_short](includes/prod_short.md)] license, as shown in the following table.

   | Co | [!INCLUDE [prod_short](includes/prod_short.md)] licence |
   |----|---|
   | Vyhledávání [!INCLUDE [prod_short](includes/prod_short.md)] kontaktů. | ![check mark](media/check.png "check") |
   | Vložení odkazu na záznam [!INCLUDE [prod_short](includes/prod_short.md)] do konverzace a odelsání jako karty. | ![check mark](media/check.png "check") |
   | Share a link from a page in [!INCLUDE [prod_short](includes/prod_short.md)] to Teams conversation. | ![check mark](media/check.png "check") |
   | Zobrazení karty záznamu [!INCLUDE [prod_short](includes/prod_short.md)] v konverzaci. |
   | Zobrazení podrobností karty záznamu [!INCLUDE [prod_short](includes/prod_short.md)] v konverzaci. | ![check mark](media/check.png "check") |
   | Open a page link in [!INCLUDE [prod_short](includes/prod_short.md)] from a conversation. | ![check mark](media/check.png "check") |

- Povolit náhledy URL adres

   Musí být zapnuto nastavení zásad **Povolit náhledy URL adres**. V opačném případě nelze kartu vygenerovat pro [!INCLUDE [prod_short](includes/prod_short.md)] vkládáné do konverzace Teams. Další informace o tomto nastavení najdete v tématu [Správa zásad zasílání zpráv v Teams](/microsoftteams/messaging-policies-in-teams).

### Správa aplikace [!INCLUDE [prod_short](includes/prod_short.md)] (volitelné)

Jako správce Teams můžete spravovat všechny aplikace pro vaši organizaci, včetně aplikace [!INCLUDE [prod_short](includes/prod_short.md)]. Můžete schválit nebo nainstalovat aplikaci [!INCLUDE [prod_short](includes/prod_short.md)] pro vaši organizaci, zablokovat uživatelům instalaci aplikace a další.

Další informace najdete v následujících článcích v dokumentaci Microsoft Teams:

- [Správa aplikací v Centru pro správu Microsoft Teams](/MicrosoftTeams/manage-apps)
- [Správa zásad nastavení aplikací v Microsoft Teams](/microsoftteams/teams-app-setup-policies)

## V [!INCLUDE [prod_short](includes/prod_short.md)]

### Minimální požadavky

- [!INCLUDE [prod_short](includes/prod_short.md)] verze:

   [!INCLUDE [prod_short](includes/prod_short.md)] 2021 release wave 1 nebo novější. Integrace Teams je podporována pouze pro [!INCLUDE [prod_short](includes/prod_short.md)] online; ne on-premises.

- Procedura **2718 Page Summary Provider** je publikovaná jako webová služba:

   Tato procedura je ve výchozím nastavení publikována jako webová služba. Procedura je součástí systémové aplikace [!INCLUDE [prod_short](includes/prod_short.md)]. Používá se k získání dat z políček pro stránky [!INCLUDE [prod_short](includes/prod_short.md)] přidaných do konverzace Teams. Informace o publikování webových služeb naleznete v tématu [Publikování Webové Služby](across-how-publish-web-service.md).

- <a name="permissions"></a>Uživatelská oprávnění:

   Vyhledávání kontaktů, stránek a dat, která mohou uživatelé zobrazit a upravovat v konverzaci Teams, jsou většinou řízeny jejich oprávněními v [!INCLUDE [prod_short](includes/prod_short.md)].

   - Chcete-li vyhledat kontakty, musí mít uživatelé alespoň oprávnění ke čtení tabulky **Kontakty**.
   - Pro vkládání odkazů [!INCLUDE [prod_short](includes/prod_short.md)] do konverzace Teams a jeho rozbalení na kartu, uživatelé musí mít alespoň oprávnění ke čtení na stránce a jejích datech.
   - Jakmile je karta odeslána do konverzace, každý uživatel v této konverzaci může tuto kartu zobrazit bez povolení [!INCLUDE [prod_short](includes/prod_short.md)].
   - Chcete-li zobrazit další podrobnosti o kartě nebo otevřít záznam v [!INCLUDE [prod_short](includes/prod_short.md)], uživatelé musí mít oprávnění ke čtení na stránce a jejích datech.
   - Chcete-li změnit data, je potřeba upravit oprávnění uživatele.

   Informace o oprávněních najdete v části [Přiřazení práv uživatelům a uživatelským skupinám](ui-define-granular-permissions.md).

## Installing the Business Central app by using Centralized Deployment

The Microsoft Teams admin center is where you configure Teams app setup policies for the organization. In the Teams admin center, you can use the Centralized Deployment feature to automatically install the Business Central app in Teams for all users in your organization, specific groups, or individual users.

> [!NOTE]
> To set up Centralized Deployment, your Teams account must have the **Teams Service admin**  role or the **Global admin** role.

1. In Business Central, choose the ![Magnifying glass that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Teams App Centralized Deployment**, and then choose the related link. Or, select [here](https://businesscentral.dynamics.com/?page=1833) to open the page directly.
2. Read the information on the **Set up the Business Central app for Teams**, then choose **Next** when ready.
3. Open the [Teams admin center](https://go.microsoft.com/fwlink/?linkid=2163970), and complete the following steps.
   1. Go to **Teams apps** > **Setup policies**.
   2. Create a new policy or select the policy that you want to use to install the Business Central app, then select **Add apps**.
   3. In the **Add installed apps** page, search for and select **Business Central**.
   4. Choose **Add**.

      Business Central should now appear under **Installed apps** for the policy.
   5. Configure any additional settings, then choose **Save**.

   For more information about setup policies in Teams, see [Manage app setup policies in Microsoft Teams](/MicrosoftTeams/teams-app-setup-policies) in the Teams documentation.
4. Go back to **Teams App Centralized Deployment** in Business Central, and select **Done**.

> [!IMPORTANT]
> It can take up to 24 hours for the app set up policy to be applied and the app deployed to users.

## Správa ochrany osobních údajů a dodržování předpisů

Microsoft Teams poskytuje rozsáhlé ovládací prvky pro dodržování a správu citlivých nebo osobně identifikovatelných dat - včetně dat přidaných do chatů a kanálů aplikace [!INCLUDE [prod_short](includes/prod_short.md)].

### Pochopení kde jsou karty [!INCLUDE [prod_short](includes/prod_short.md)] uloženy

Po odeslání karty do chatu se karta a pole zobrazená na kartě zkopírují do Teams. Na tyto informace se vztahují zásady Teams pro vaši organizaci, například zásady uchovávání dat. Při zobrazování podrobností o kartě se žádná data v okně s podrobnostmi neuloží v Teams. Data zůstávají uložena v [!INCLUDE [prod_short](includes/prod_short.md)] a Teams je načte pouze v případě, že se uživatel rozhodne zobrazit podrobnosti.

- Další informace o tom, kam Teams ukládá tato data, najdete v tématu [Umístění dat v Microsoft Teams](/microsoftteams/location-of-data-in-teams).
- Další informace o zásadách uchovávání informací v Teams naleznete v tématu [Zásady uchovávání informací v Microsoft Teams](/microsoftteams/retention-policies).

### Omezení sdílení karet

Nastavením zásad zasílání zpráv, které vypnou nastavení náhledů adres URL, zabráníte určitým uživatelům nebo skupinám v nastavení **Náhledů URL**. Další informace o tomto nastavení najdete v tématu [Správa zásad zasílání zpráv v Teams](/microsoftteams/messaging-policies-in-teams).

Můžete také použít informační bariéry, abyste zabránili jednotlivcům nebo skupinám ve vzájemné komunikaci. Další informace najdete v tématu [Informační bariéry v Microsoft Teams](/microsoftteams/information-barriers-in-teams).

Funkce prevence ztráty dat v Centru zabezpečení a dodržování předpisů Microsoftu 365 nelze použít konkrétně na karty. Lze je však použít na chatovací zprávy, které obsahují karty. <!-- To track upcoming advanced features that include enabling DLP for cards, see [https://www.microsoft.com/en-us/microsoft-365/roadmap?featureid=67093](https://www.microsoft.com/en-us/microsoft-365/roadmap?featureid=67093).-->

### Odpověď na žádosti o data

Členům týmu a vlastníkům týmu umožníte odstraňovat zprávy obsahující citlivé karty nastavením zásad zasílání zpráv, například: **Vlastníci mohou mazat odeslané zprávy** a **Uživatelé mohou smazat odeslané zprávy**. Další informace najdete v tématu [Správa zásad zasílání zpráv v Teams](/microsoftteams/messaging-policies-in-teams).

Funkce vyhledávání obsahu a dodržování předpisů eDiscovery v Centru zabezpečení a dodržování předpisů Microsoftu 365 lze také použít na karty.

Protože data karty v Teams jsou kopií dat ve službě [!INCLUDE [prod_short](includes/prod_short.md)], můžete na požádání exportovat data zákazníka také pomocí funkcí [!INCLUDE [prod_short](includes/prod_short.md)]. Další informace o ochraně osobních údajů naleznete v [!INCLUDE [prod_short](includes/prod_short.md)] v části [Časté dotazy k ochraně osobních údajů pro zákazníky v Business Central](/dynamics365/business-central/dev-itpro/security/privacyfaq).

## Viz také
[Přehled integrace [!INCLUDE [prod_short](includes/prod_short.md)] a Microsoft Teams](across-teams-overview.md)  
[Instalace aplikace [!INCLUDE [prod_short](includes/prod_short.md)] pro Microsoft Teams](across-install-app-for-teams.md)  
[Teams FAQ](teams-faq.md)  
[Řešení problémů Teams](admin-teams-troubleshooting.md)  
[Vývoj pro integraci Teams](/dynamics365/business-central/dev-itpro/developer/devenv-develop-for-teams)

## [!INCLUDE[prod_short](includes/free_trial_md.md)]


[!INCLUDE[footer-include](includes/footer-banner.md)]