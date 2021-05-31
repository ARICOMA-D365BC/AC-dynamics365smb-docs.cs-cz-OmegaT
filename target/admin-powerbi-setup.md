---
title: Enabling Power BI Integration With Business Central
description: Learn how to set up the connection to Power Bi so you can get insights, business intelligence, and KPIs from your Business Central data with the Business Central apps for Power BI.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: account schedule, analysis, reporting, financial report, business intelligence, KPI
ms.date: 04/01/2021
ms.author: jswymer
---
# Povolení integrace Power BI s [!INCLUDE[prod_short](includes/prod_short.md)]

Tento článek popisuje, jak získat [!INCLUDE[prod_short](includes/prod_short.md)] připraven k integraci s Power BI. [!INCLUDE[prod_short](includes/prod_short.md)] online je již povolen pro integraci, i když existují některé informace o licencování, které byste si mohli chtít přečíst. Pro [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, budete mít nastavené prostředí pro připojení k Power BI, než s ním budou uživatelé moci pracovat.

## <a name="license"></a>Licencování Power BI

S [!INCLUDE[prod_short](includes/prod_short.md)], uživatelé získají bezplatnou licenci Power BI, která poskytuje přístup k nejběžnějším funkcím v [!INCLUDE[prod_short](includes/prod_short.md)] a Power BI. Můžete si také zakoupit licenci Power BI Pro, která poskytuje přístup k dalším funkcím. Následující tabulka obsahuje přehled funkcí dostupných s každou licencí.

|Licence pro spuštění|Zobrazení sestav|Vytváření sestav|Sdílení sestav|Aktualizace sestav| Aplikace [!INCLUDE[prod_short](includes/prod_short.md)]|
|-------------|--------||
|Power BI zdarma|![zaškrtnutí](media/check.png)|![další zaškrtnutí](media/check.png)|(limitované)|(limitované)||
|Power BI Pro|![ještě další zaškrtnutí](media/check.png)|![je to zaškrtnutí](media/check.png)|![opět zaškrtnutí](media/check.png)|(rozsáhlý)|![poslední zaškrtnutí](media/check.png)|

Pro více informací navštivte [Licencování služby Power BI pro uživatele ve vaší organizaci](/power-bi/admin/service-admin-licensing-organization) nebo [Registrace ke službě Power BI jako jednotlivci](/power-bi/fundamentals/service-self-service-signup-for-power-bi).

## <a name="setup"></a>Nastavení [!INCLUDE[prod_short](includes/prod_short.md)] on-premises pro integraci Power BI

Tato část vysvětluje požadavky na nasazení [!INCLUDE[prod_short](includes/prod_short.md)] on-premises pro integraci s Power BI.

1. Nakonfigurujte pro nasazení ověřování NavUserPassword nebo Azure Active Directory.

   Integrace Power BI nepodporuje ověřování windows.

2. Povolte webové služby OData a koncový bod ODataV4.

   Webová služba OData musí být povolena na [!INCLUDE[server](includes/server.md)], a port OData se otevřel v bráně firewall. Pro více informací, navštivte [Konfigurace webové služby Business Central Server - OData](/dynamics365/business-central/dev-itpro/administration/configure-server-instance#ODataServices).

   Místní server musí být přístupný z Internetu.

3. Dejte uživatelským účtům [!INCLUDE[prod_short](includes/prod_short.md)] přístupový klíč webové služby.

   Přístupový klíč webové služby je potřeba pouze k zobrazení dat [!INCLUDE[prod_short](includes/prod_short.md)] v Power BI. Každému uživatelskému účtu můžete přiřadit přístupový klíč webové služby. Nebo místo toho vytvořte konkrétní účet s přístupovým klíčem webové služby pro použití všemi uživateli. Pro více informací navštivte [Ověřování webových služeb](/dynamics365/business-central/dev-itpro/webservices/web-services-authentication#generate-a-web-service-access-key).

   <!--
       > [!IMPORTANT]
       > With [!INCLUDE[prod_short](../developer/includes/prod_short.md)] online, the use of access keys (Basic Auth) for web service authentication is [deprecated](../upgrade/deprecated-features-w1.md#accesskeys). We recommend that you use OAuth2 instead. For more information, see [Using OAuth to Authorize Business Central Web Services](../webservices/authenticate-web-services-using-oauth.md).-->

4. Vytvořte registraci přihlášky pro [!INCLUDE[prod_short](includes/prod_short.md)] v Microsoft Azure.

   Pro zobrazení sestav Power BI vložených na stránky [!INCLUDE[prod_short](includes/prod_short.md)], musí být přihláška zaregistrována pro [!INCLUDE[prod_short](includes/prod_short.md)] v Microsoft Azure. Registrovaná aplikace potřebuje oprávnění ke službám Power BI. Pro více informací navštivte [Registrace [!INCLUDE[prod_short](includes/prod_short.md)] On-Premises v Azure AD pro integraci s jinými službami](/dynamics365/business-central/dev-itpro/administration/register-app-azure).

   > [!NOTE]
   > Pokud vaše nasazení používá ověřování NavUserPassword, [!INCLUDE[prod_short](includes/prod_short.md)] se připojuje ke stejné službě Power BI pro všechny uživatele. Tento účet služby zadáte jako součást registrace aplikace. S ověřováním Azure AD, se [!INCLUDE[prod_short](includes/prod_short.md)] připojuje ke službě Power BI přidružené k jednotlivým uživatelským účtům.

   <!-- Windows authentication can also be used but you can't get data from BC in Power BI -->
5. Propojte počáteční připojení z Business Central do Power BI.

   Než budou koncoví uživatelé moci používat Power BI v [!INCLUDE[prod_short](includes/prod_short.md)], správce aplikace Azure bude muset udělit souhlas se službou Power BI.

   Chcete-li vytvořit počáteční připojení, otevřete [!INCLUDE[prod_short](includes/prod_short.md)] a z centra rolí spusťte funkci **Začínáme s Power BI**. Tato akce vás povede procesem souhlasu a zkontroluje vaši licenci Power BI. Když se zobrazí výzva k přihlášení pomocí účtu správce Azure. Pro více informací navštivte [Připojení k Power BI - pouze jednou](across-working-with-powerbi.md#connect).

## Publikujte data jako webové služby

Kódové jednotky, stránky a dotazy, které chcete použít jako zdroj dat v sestavách Power BI, musí být publikovány jako webové služby. Ve výchozím nastavení je publikováno mnoho webových služeb. Snadný způsob, jak najít webové služby, je vyhledat *webové služby* v [!INCLUDE[prod_short](includes/prod_short.md)]. Na stránce **Webové služby** zkontrolujte, zda je pro výše uvedené webové služby vybráno pole **Publikovat**. Tento úkol je obvykle administrativní.

Pro více informací o publikování webových služeb navštivte [Publikování webové služby](across-how-publish-web-service.md).

> [!TIP]
> Chcete-li se dozvědět, co můžete udělat pro zajištění nejlepšího výkonu webových služeb, jak je vidět ze serveru Business Central (koncový bod) a od spotřebitele (klienta), přečtěte si [Psaní efektivních webových služeb](/dynamics365/business-central/dev-itpro/performance/performance-developer#writing-efficient-web-services).

## Zobrazit související školení na webu [Microsoft Learn](/learn/modules/Configure-powerbi-excel-dynamics-365-business-central/index)

## Viz také

[Business Central a Power BI](admin-powerbi.md)    
[Integrace komponent Power BI a přehledu architektur pro [!INCLUDE[prod_short](includes/prod_short.md)]](admin-powerbi-overview.md)    
[Power BI pro uživatelé](/power-bi/consumer/end-user-consumer)    
[„Nový vzhled“ služby Power BI](/power-bi/service-new-look)    
[Rychlý start: Připojení k datům v Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data)    
[Dokumentace Power BI](/power-bi/)    
[Business Intelligence](bi.md)    
[Připravte se na podnikání](ui-get-ready-business.md)    
[Import obchodních dat z jiných finančních systémů](across-import-data-configuration-packages.md)    
[Nastavení [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)    
[Použití [!INCLUDE[prod_short](includes/prod_short.md)] jako zdroje dat Power BI](across-how-use-financials-data-source-powerbi.md)    
[Použití [!INCLUDE[prod_short](includes/prod_short.md)] jako zdroje dat Power Apps](across-how-use-financials-data-source-powerapps.md)    
[Použití [!INCLUDE[prod_short](includes/prod_short.md)] v Power Automate](across-how-use-financials-data-source-flow.md)




[!INCLUDE[footer-include](includes/footer-banner.md)]