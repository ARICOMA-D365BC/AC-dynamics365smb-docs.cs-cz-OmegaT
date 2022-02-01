---
title: Enabling Power BI Integration With Business Central
description: Learn how to set up the connection to Power BI. With Power BI reports, you can get insights, business intelligence, and KPIs from your Business Central data.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: Power BI, setup, analysis, reporting, financial report, business intelligence, KPI
ms.date: 04/01/2021
ms.author: jswymer
---
# Povolení integrace Power BI s [!INCLUDE[prod_short](includes/prod_short.md)]

Tento článek popisuje, jak získat [!INCLUDE[prod_short](includes/prod_short.md)] připraven k integraci s Power BI. [!INCLUDE[prod_short](includes/prod_short.md)] online je již povolen pro integraci, i když existují některé informace o licencování, které byste si mohli chtít přečíst. Pro [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, budete mít nastavené prostředí pro připojení k Power BI, než s ním budou uživatelé moci pracovat.

## <a name="license"></a>Licencování Power BI

S [!INCLUDE[prod_short](includes/prod_short.md)], uživatelé získají bezplatnou licenci Power BI, která poskytuje přístup k nejběžnějším funkcím v [!INCLUDE[prod_short](includes/prod_short.md)] a Power BI. Můžete si také zakoupit licenci Power BI Pro, která poskytuje přístup k dalším funkcím. Následující tabulka obsahuje přehled funkcí dostupných s každou licencí.

|Power License|View reports|Create reports|Share reports|Refresh reports| [!INCLUDE[prod_short](includes/prod_short.md)] Apps|
|-------------|--------||
|Power BI free|![a checkmark.](media/check.png)|![another checkmark](media/check.png)|(limited)|(limited)||
|Power BI Pro|![yet another checkmark.](media/check.png)|![it's a checkmark](media/check.png)|![again a checkmark](media/check.png)|(extensive)|![last checkmark](media/check.png)|

Pro více informací navštivte [Licencování služby Power BI pro uživatele ve vaší organizaci](/power-bi/admin/service-admin-licensing-organization) nebo [Registrace ke službě Power BI jako jednotlivci](/power-bi/fundamentals/service-self-service-signup-for-power-bi).

## <a name="exposedata"></a>Expose data through API pages or OData web services

Business Central offers two ways to expose data that can be consumed by Power BI reports: API pages and Open Data Protocol (OData) web services.

### API pages

> **APPLIES TO:** Business Central online only

An API page is a specific page type created in AL code that provides access to database tables through a webhook-supported, OData v4-enabled, REST service. This type of page can't be displayed in the user interface, but is intended for building reliable integration services.

Business Central online comes available with a set of built-in APIs, which you can use to get data for the most common business entities, like customers, items, sales orders, and more. No extra work or setup is required to use these APIs as a data source for Power BI reports. For more information about these APIs, see [Business Central API V2.0](/dynamics365/business-central/dev-itpro/api-reference/v2.0/).

Business Central online also supports custom APIs. Application developers of Business Central solutions can create their own API pages and package them into extensions. You can install the extensions on your tenant. Once installed, you can use the API pages for your Power BI reports, like you'd do with the built-in APIs (v2.0). For more information about how to create API pages, see [Developing a Custom API](/dynamics365/business-central/dev-itpro/developer/devenv-develop-custom-api).

### OData web services

You can publish Business Central application objects, like codeunits, page, and queries, as [OData web services](/dynamics365/business-central/dev-itpro/webservices/odata-web-services). With Business Central online, there are many web services published by default. An easy way to find the web services is to search for *web services* in [!INCLUDE[prod_short](includes/prod_short.md)]. In the **Web Services** page, make sure the **Publish** field is selected for the web services listed above. For more information about publishing web services, see [Publish a Web Service](across-how-publish-web-service.md).

To learn about what you can do to ensure the best performance of web services, as seen from the Business Central server (the endpoint) and from the consumer (the client), read [Writing efficient Web Services](/dynamics365/business-central/dev-itpro/performance/performance-developer#writing-efficient-web-services).

### Choosing whether to use API pages or OData web services

Whenever possible, you're encouraged to use API pages instead of OData web service. API pages are generally faster at loading data in Power BI reports than OData web services. Plus, they're more flexible because they let you get data from table fields that aren't defined in a page object.

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
       > With [!INCLUDE[prod_short](../developer/includes/prod_short.md)] online, the use of access keys (Basic Auth) for web service authentication is [deprecated](/dynamics365/business-central/dev-itpro/upgrade/deprecated-features-w1#accesskeys). We recommend that you use OAuth2 instead. For more information, see [Using OAuth to Authorize Business Central Web Services](/dynamics365/business-central/dev-itpro/webservices/authenticate-web-services-using-oauth).-->

4. Vytvořte registraci přihlášky pro [!INCLUDE[prod_short](includes/prod_short.md)] v Microsoft Azure.

   Pro zobrazení sestav Power BI vložených na stránky [!INCLUDE[prod_short](includes/prod_short.md)], musí být přihláška zaregistrována pro [!INCLUDE[prod_short](includes/prod_short.md)] v Microsoft Azure. Registrovaná aplikace potřebuje oprávnění ke službám Power BI. Pro více informací navštivte [Registrace [!INCLUDE[prod_short](includes/prod_short.md)] On-Premises v Azure AD pro integraci s jinými službami](/dynamics365/business-central/dev-itpro/administration/register-app-azure).

   > [!NOTE]
   > Pokud vaše nasazení používá ověřování NavUserPassword, [!INCLUDE[prod_short](includes/prod_short.md)] se připojuje ke stejné službě Power BI pro všechny uživatele. Tento účet služby zadáte jako součást registrace aplikace. S ověřováním Azure AD, se [!INCLUDE[prod_short](includes/prod_short.md)] připojuje ke službě Power BI přidružené k jednotlivým uživatelským účtům.

   <!-- Windows authentication can also be used but you can't get data from BC in Power BI -->
5. Propojte počáteční připojení z Business Central do Power BI.

   Než budou koncoví uživatelé moci používat Power BI v [!INCLUDE[prod_short](includes/prod_short.md)], správce aplikace Azure bude muset udělit souhlas se službou Power BI.

   Chcete-li vytvořit počáteční připojení, otevřete [!INCLUDE[prod_short](includes/prod_short.md)] a z centra rolí spusťte funkci **Začínáme s Power BI**. Tato akce vás povede procesem souhlasu a zkontroluje vaši licenci Power BI. Když se zobrazí výzva k přihlášení pomocí účtu správce Azure. Pro více informací navštivte [Připojení k Power BI - pouze jednou](across-working-with-powerbi.md#connect).

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