---
title: Building Reports in Power BI Desktop to Display Business Central Data | Microsoft Docs
description: Make your data available as a data source in Power BI and build powerful reports of the state of your business.
author: jswymer

ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: business intelligence, KPI, Odata, Power App, SOAP, analysis
ms.date: 04/01/2021
ms.author: jswymer
---

# Vytváření sestav Power BI k zobrazení [!INCLUDE [prod_long](includes/prod_long.md)] dat

Svá data  můžete [!INCLUDE[prod_long](includes/prod_long.md)] zpřístupnit jako zdroj dat v Power BI Desktopu a vytvářet výkonné sestavy o stavu svého podnikání.

Tento článek popisuje, jak začít používat Power BI Desktop k vytváření sestav, které zobrazují [!INCLUDE[prod_long](includes/prod_long.md)] data.  Po vytvoření sestav je můžete publikovat do služby Power BI nebo je sdílet se všemi uživateli ve vaší organizaci. Jakmile jsou tyto sestavy ve službě Power BI, uživatelé, kteří jsou pro ně nastaveni, je můžou zobrazit v [! INCLUDE[prod_long](includes/prod_long.md)].

## Připravte se

- Zaregistrujte se ke službě Power BI.

   Pokud jste se ještě nezaregistrovali, přejděte na [https://powerbi.microsoft.com](https://powerbi.microsoft.com). Při přihlášení použijte pracovní e-mailovou adresu a heslo.

- Stáhněte si [Power BI Desktop](https://powerbi.microsoft.com/desktop/).

   Power BI Desktop je bezplatná aplikace, kterou nainstalujete do místního počítače. Další informace najdete v tématu [rychlý Start: Připojení k datům v Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data).

- Ujistěte se, že data, která chcete v sestavě, jsou k dispozici jako stránka rozhraní API nebo publikovaná jako webová služba.

   Další informace najdete v tématu [vystavení dat prostřednictvím stránek rozhraní API nebo webových služeb OData](admin-powerbi-setup.md#exposedata).

- Pro [!INCLUDE[prod_short](includes/prod_short.md)] místní prostředí, získejte následující informace:

   - Adresa URL OData pro [!INCLUDE[prod_short](includes/prod_short.md)].

      Tato adresa URL má obvykle formát `http[s]://[computer]:[port]/[serverinstance]/ODataV4`, například `https://localhost:7048/BC190 /ODataV4`. Pokud máte nasazení s více tenanty, zahrňte tenanta do adresy URL, například `https://localhost:7048/BC190/ODataV4?tenant=tenant1`.
   - Uživatelské jméno a přístupový klíč webové služby [!INCLUDE[prod_short](includes/prod_short.md)] účtu.

      Chcete-li získat data z [!INCLUDE[prod_short](includes/prod_short.md)], Power BI používá základní ověření. K připojení tedy budete potřebovat uživatelské jméno a přístupový klíč webové služby. The account might be your own user account, or your organization may have specific account for this purpose.

- Stáhněte si [!INCLUDE [prod_short](includes/prod_short.md)] motiv sestavy (volitelné).

   Další informace naleznete v tématu [Použijte tlačítko [!INCLUDE [prod_short](includes/prod_short.md)] motiv sestavy](#theme) v tomto článku.

## <a name="getdata"></a> Přidat [!INCLUDE[prod_short](includes/prod_short.md)] jako zdroj dat v Power BI Desktopu

Prvním úkolem při vytváření sestav je přidání [!INCLUDE[prod_short](includes/prod_short.md)] jako zdroj dat v Power BI Desktopu. Po připojení můžete začít vytvářet sestavu.

1. Spusťte Power BI Desktop.
2. Vyberte **Získat data**.

   Pokud nevidíte možnost **Získat data**, vyberte **Soubor** nabídka, a pak **Získat data**.
3. Na stránce **Získat data** vyberte **Online služby**.
4. V podokně **Online služby** proveďte jeden z následujících kroků:

   - Pro připojení k [!INCLUDE [prod_short](includes/prod_short.md)] online, vyberte **Dynamics 365 Business Central** a poté **Připojit**.
   - Pro připojení k [!INCLUDE [prod_short](includes/prod_short.md)] místnímu prostředí, vyberte **Dynamics 365 Business Central (místní prostředí) a** poté **Připojit**.

5. Přihlaste se do [!INCLUDE [prod_short](includes/prod_short.md)] (pouze jednorázově).

   Pokud jste se ještě nepřihlásili [!INCLUDE [prod_short](includes/prod_short.md)] do Power BI Desktop, zobrazí se výzva k přihlášení.

   - Pro [!INCLUDE [prod_short](includes/prod_short.md)] online, vyberte **Přihlásit se** a pak zvolte příslušný účet. Použijte stejný účet, který používáte k přihlášení [!INCLUDE [prod_short](includes/prod_short.md)]. Až budete hotovi, vyberte **Připojit**.

   - Pro [!INCLUDE [prod_short](includes/prod_short.md)] (místní prostředí), nejdřív zadejte adresu URL OData pro [! INCLUDE[prod_short](includes/prod_short.md)] a pak vyberte **OK.** Po zobrazení výzvy zadejte uživatelské jméno a heslo účtu, který chcete použít pro připojení k [! INCLUDE[prod_short](includes/prod_short.md)]. Do pole **Heslo** zadejte přístupový klíč webové služby. Až budete hotovi, vyberte **Připojit**.

   > [!NOTE]  
   > Jakmile se úspěšně připojíte [!INCLUDE[prod_short](includes/prod_short.md)], nebudete znovu vyzváni k přihlášení. [Jak mohu změnit nebo vymazat účet, který aktuálně používám pro připojení k Business Central z Power BI Desktop?](/dynamics365/business-central/power-bi-faq?tabs=designer#perms)

6. Po připojení se Power BI kontaktuje do služby Business Central. Zobrazí se okna **Navigátor** s dostupnými zdroji dat pro vytváření sestav. Vyberte složku, kterou chcete rozbalit a zobrazte dostupné zdroje dat.

   These data sources represent all the web services and API pages that are published for [!INCLUDE [prod_short](includes/prod_short.md)]. Zdroje dat jsou seskupeny podle prostředí Business Central a společností. S Business Central online má **Navigator** následující strukturu:

   - **Název prostředí**
      - **Název společnosti**
         - **Pokročilá rozhraní API**

            Tato složka obsahuje seznam pokročilých rozhraní stránek API publikovaných společností Microsoft, jako jsou rozhraní API pro automatizaci Business Central a [vlastní stránky rozhraní API pro Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-develop-custom-api).[](/dynamics365/business-central/dev-itpro/administration/itpro-introduction-to-automation-apis) Vlastní stránky rozhraní API jsou dále seskupeny ve složkách podle vlastností [APIPublisher](/dynamics365/business-central/dev-itpro/developer/properties/devenv-apipublisher-property)/[APIGroup](/dynamics365/business-central/dev-itpro/developer/properties/devenv-apigroup-property) zdrojového kódu stránky rozhraní API.

         - **Standardní rozhraní API v2.0**

            Tato složka obsahuje seznam stránek rozhraní API vystavených [Business Central API V2.0.](/dynamics365/business-central/dev-itpro/api-reference/v2.0/)

         - **Webové služby \(starší)**

            Tato složka obsahuje seznam stránek, kódových jednotek a dotazů, které jsou publikovány jako webové služby v Business Central.

   > [!NOTE]
   > Struktura místního prostředí Business Central je odlišná, protože nepodporuje stránky rozhrraní API.

7. Vyberte zdroj nebo zdroje dat, které chcete přidat do svého datového modelu, a poté vyberte tlačítko **Načíst**.
8. Pokud později budete chtít přidat další data Business Central, můžete opakovat předchozí kroky.

Jakmile jsou data načtena, můžete je vidět v pravém navigačním panelu na stránce. V tomto okamžiku jste se úspěšně připojili k [!INCLUDE[prod_short](includes/prod_short.md)] datům a můžete začít vytvářet sestavu Power BI.

> [!TIP]
> Další informace o používání Power BI Desktopu najdete v části [Začínáme s Power BI Desktop](/power-bi/fundamentals/desktop-getting-started).

## Vytváření přístupných sestav

Je důležité, aby vaše sestavy byly použitelné pro co nejvíce lidí. Pokuste se navrhnout sestavy tak, aby nevyžadovaly žádné speciální úpravy, aby vyhovovaly specifickým potřebám různých uživatelů. Ujistěte se, že design umožňuje uživatelům využívat standardní pomocné technologie, jako jsou čtečky obrazovky. Power BI obsahuje různé funkce přístupnosti, nástroje a pokyny, které vám pomůžou tohoto cíle dosáhnout. Další informace naleznete v tématu [Návrh přístupných sestav Power BI](/power-bi/create-reports/desktop-accessibility-creating-reports) v dokumentaci Power BI.

## Vytváření sestav pro zobrazení dat přidružených k seznamu

Můžete vytvořit sestavy, které se zobrazí v okně s fakty [!INCLUDE [prod_short](includes/prod_short.md)] stránka se seznamem. Sestavy mohou obsahovat údaje o záznamu vybraném v seznamu. Vytváření těchto sestav je podobné jako u jiných sestav s tím rozdílem, že je třeba udělat několik věcí, abyste zajistili, že se sestavy zobrazí podle očekávání. Další informace najdete v tématu [Zobrazení dat seznamu v Power BI Reports v Business Central [! INCLUDE[prod_short](includes/prod_short.md)]](across-how-use-powerbi-reports-factbox.md).

## <a name="theme"></a> Pomocí tlačítka [!INCLUDE [prod_short](includes/prod_short.md)] motiv sestavy (volitelné)

Před vytvořením sestavy doporučujeme stáhnout a importovat soubor [!INCLUDE [prod_short](includes/prod_short.md)] soubor motivu. Soubor motivu vytváří paletu barev, takže můžete vytvářet sestavy se stejným barevným stylem jako aplikace [!INCLUDE [prod_short](includes/prod_short.md)], aniž byste museli definovat vlastní barvy pro každý vizuál.

> [!NOTE]
> Tento úkol je volitelný. Vždy můžete vytvořit své sestavy a poté si šablonu stylu stáhnout a použít později.

### Stáhnout motiv

Soubor motivu je k dispozici jako soubor json v galerii motivů komunity Microsoft Power BI. Chcete-li stáhnout soubor motivu, proveďte následující kroky:

1. Přejděte na [Galerie motivů komunity Microsoft Power BI pro Microsoft Dynamics 365 Business Central](https://community.powerbi.com/t5/Themes-Gallery/Microsoft-Dynamics-365-Business-Central/m-p/385875).
2. Vyberte přílohu ke stažení **Microsoft Dynamics Business Central.json**.

### Importujte motiv do sestavy

Po stažení [!INCLUDE [prod_short](includes/prod_short.md)] motivu sestavy, můžete jej importovat do svých sestav. Chcete-li motiv importovat, vyberte **Zobrazit** > **>motivy** > **Vyhledat motivy**. Další informace najdete v části [Power BI Desktop – Import vlastních motivů sestav](/power-bi/create-reports/desktop-report-themes#import-custom-report-theme-files).

## Publikování sestav

Po vytvoření nebo úpravě sestavy ji můžete publikovat ve službě Power BI a také ji sdílet s ostatními ve vaší organizaci. Po publikování se sestava zobrazí v Power BI. Sestava bude také dostupná pro výběr v [!INCLUDE[prod_short](includes/prod_short.md)].

Pokud chcete publikovat sestavu, vyberte **Publikovat** na kartě **Domů** na pásu karet nebo v nabídce **Soubor**. Pokud jste přihlášení ke službě Power BI, sestava se publikuje do této služby. V opačném případě budete vyzváni k přihlášení.

## Distribuce nebo sdílení sestavy

Existuje několik způsobů, jak předat sestavy svým spolupracovníkům a ostatním:

- Distribujte sestavy jako soubory .pbix.

   Sestavy jsou uloženy ve vašem počítači jako soubory .pbix. Soubor .pbix sestavy můžete distribuovat uživatelům stejně jako jakýkoli jiný soubor. Uživatelé pak mohou soubor nahrát do své služby Power BI. Viz [Nahrávání přehledů ze souborů](across-working-with-business-central-in-powerbi.md#upload).

   > [!NOTE]
   > Distribuce sestav tímto způsobem znamená, že obnovování dat pro sestavy bude provádět každý uživatel individuálně. Tato situace by mohla mít dopad na [!INCLUDE[prod_short](includes/prod_short.md)] výkon.

- Sdílejte sestavu ze služby Power BI

   Pokud máte licenci Power BI Pro, můžete sestavu sdílet s ostatními přímo ze služby Power BI. Další informace najdete v tématu [Power BI – sdílení řídicího panelu nebo sestavy](/power-bi/collaborate-share/service-share-dashboards#share-a-dashboard-or-report).

## Řešení problémů

### "Nelze vložit záznam. Aktuální záměr připojení je jen pro čtení." Chyba při připojování k vlastní stránce rozhraní API

> **PLATÍ PRO:** Business Central online

Od února 2022 se nové sestavy, které používají data Business Central, ve výchozím nastavení připojí k replice databáze Business Central pouze pro čtení. V ojedinělých případech, v závislosti na návrhu stránky, se při pokusu o připojení ke stránce a získání dat ze stránky zobrazí chyba.

1. Spusťte Power BI Desktop.
2. Na pásu karet vyberte **Získat data** > **Online služby**.
3. V podokně **Online služby** vyberte **Dynamics 365 Business Central**a poté **Připojit**.
4. V okně **Navigátor** vyberte koncový bod rozhraní API, ze kterého chcete načíst data.
5. V podokně náhledu na pravé straně se zobrazí následující chyba:

   *Dynamics365BusinessCentral: Požadavek se nezdařil: vzdálený server vrátil chybu: (400) chybný požadavek. (Nelze vložit záznam. Aktuální záměr připojení je pouze pro čtení. CorrelationId: [...])".*

6. Vyberte **Transformovat data** místo **Načíst**, jak byste to mohli dělat normálně.
7. V **Editoru Power Query**vyberte na pásu karet **Pokročilý editor**.
8. V řádku, který začíná **Source =**, nahraďte následující text:

   ```
   Dynamics365BusinessCentral.ApiContentsWithOptions(null, null, null, null)
   ```

   s:

   ```
   Dynamics365BusinessCentral.ApiContentsWithOptions(null, null, null, [UseReadOnlyReplica = false])
   ```

9. Vyberte **Hotovo**.
10. Výběrem **Zavřít a použít** na pásu karet uložte změny a zavřete Editor Power Query.

## Podívejte se na související školení na webu [Microsoft Learn](/learn/modules/configure-powerbi-excel-dynamics-365-business-central/index)

## Viz také

[Povolení obchodních dat pro Power BI](admin-powerbi.md)    
[Přehled](bi.md)    
[Příprava obchodování](ui-get-ready-business.md)    
[Import obchodních dat z jiných finančních systémů](across-import-data-configuration-packages.md)    
[Setting Up [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)    
[Finance](finance.md)    
[Rychlý start: Připojení k datům v aplikaci Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data)  


[!INCLUDE[footer-include](includes/footer-banner.md)]