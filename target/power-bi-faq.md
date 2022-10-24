---
title: Power BI FAQ
description: Get answers for some typical questions about working with Power BI and Business Central.
author: jswymer

ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: Power BI, reports, faq, errors
ms.date: 04/22/2021
ms.author: jswymer
---
# Nejčastější dotazy Power BI

Tento článek odpovídá na některé otázky, které můžete mít ohledně práce s Power BI a [!INCLUDE [prod_short](includes/prod_short.md)].

## [Obecné](#tab/general)
<!-- 26 -->
### Vybral jsem sestavu pro své centrum rolí v Business Central. Pokud později provádím změny vizuálů sestavy online, bude centrum rolí automaticky aktualizovat mé změny?

Ano, protože sestavy jsou vložené z Power BI.

<!-- 3 -->
### Jsou aplikace Business Central pro Power BI dostupné v jiných jazycích než v angličtině?

Čísla. Tyto aplikace jsou v současné době k dispozici pouze v angličtině.

<!-- 24 -->
### Jakmile je sestava publikována na mém powerbi.com pracovním prostoru, mohu si stáhnout její pbix?

Ano. Pro více informací navštivte [Stažení sestavy ze služby Power BI do Power BI Desktop](/power-bi/create-reports/service-export-to-pbix).

<!-- 27 -->
### Mohu si stáhnout aplikace jako soubory pbix?

Čísla. V současné době nenabízíme stahování souborů pbix pro oficiální aplikace Power BI, protože jsou publikovány v AppSource.

## [Licence](#tab/license)

<!-- 14 -->
### Potřebuji k publikování sestav licenci Power BI Pro?

<!-- todo What does " or for every user that consults the published report" mean? fixed -->
Čísla. K publikování sestav není potřeba licence Pro. Stačí standardní (bezplatná) licence Power BI. Pro více informací navštivte [Licencování Power BI](admin-powerbi-setup.md#license).

<!-- 15 -->
### Je něco, co nemůžu udělat s licencí zdarma?

Nemůžete sdílet sestavy ani instalovat aplikace Business Central pro Power BI. Kromě toho vám bezplatná licence umožňuje vytvářet téměř všechny varianty grafů a sestav.

<!-- 16 -->
### Pokud někdo sdílí sestavu s jinou osobou, pak tato osoba potřebuje licenci Pro, aby ji viděla. Existují plány, jak tuto možnost umožnit pomocí bezplatné licence?

Nad tímto požadavkem nemáme kontrolu. Tento požadavek je nastaven pomocí Power BI. Pro více informací navštivte [Sdílení řídicích panelů a sestav Power BI se spolupracovníky a dalšími](/power-bi/collaborate-share/service-share-dashboards).

## [Návrhář](#tab/designer)

<!-- 7 -->
### Funguje konektor se stránkami rozhraní API?

Ano. Od června 2021 však bude nový konektor Power BI podporovat webové služby Business Central i stránky rozhraní API. Pro více informací navštivte [Povolení práce s rozhraními API Business Central pomocí konektoru Power BI, nikoli pouze s webovými službami](/dynamics365-release-plan/2021wave1/smb/dynamics365-business-central/enable-power-bi-connector-work-business-central-apis-instead-web-services-only).

### Můžu sestavu Power BI vytvořit pomocí Řádků prodejní faktury nebo rozhraní API řádků deníku?

Nejčastěji používané řádkové záznamy jsou k dispozici v [Business Central API v2.0](/dynamics365/business-central/dev-itpro/api-reference/v2.0/)). Můžete je tedy použít k vytváření sestav v Power BI tak, že je vyberete v konektoru **Dynamics 365 Business Central**. Rozhraní **Lines** API jsou však navržena pro použití pouze s některými velmi specifickými filtry a ve vašem scénáři nemusí fungovat. Může se zobrazit chyba podobná chybě "Chcete-li získat řádky, musíte zadat ID nebo ID dokumentu". Pokud chcete tento problém vyřešit, proveďte následující kroky při získávání dat z Business Central pro sestavu v Power BI Desktopu:

1. Místo zahrnutí zdroje dat pro entitu řádků přidejte nadřazený zdroj dat. Například přidejte **Prodejní fakturu** namísto **Řádků prodejní faktury**.
2. Na panelu akcí Power BI Desktopu vyberte **Transformovat data**.
3. Vyberte dotaz, který jste právě přidali, například **Prodejní faktury**.
4. Použijte na záznamy jakékoli potřebné filtrování, abyste snížili množství záznamů načtených ve vaší sestavě.
5. Posouvejte se doprava, dokud nenajdete sloupec pojmenovaný jako řádky, například **Řádky prodejní faktury**.
6. Vyberte tlačítko Rozbalit v záhlaví sloupce vedle názvu sloupce.

   :::image type="content" source="media/saleinvoicelines.png" alt-text="Zobrazuje sloupec Řádky prodejní faktury v Power BI Desktopu.":::
<!-- 11 -->
### Je možné zvolit, ze kterého prostředí Business Central chcete získat data pro Power BI, například sandbox nebo produkční prostředí?

Ano. Lze jej snadno vybrat. Když se připojíte k Business Central pomocí konektoru, musíte zvolit prostředí a název společnosti.

<!-- 6 -->
### Mohu sloučit data z několika produkčních prostředí stejného tenanta?

Ano. V Power BI spusťte znovu operaci získat data a vyberte prostředí, které chcete.

<!-- 25 -->
### Which pages in Business Central have the Power BI Report part?

V současné době existuje několik vybraných stránek, které mají panel s fakty s částí **Sestavy Power BI** pro zobrazení sestavy.

Na stránkách se seznamy je část **Sestavy Power BI** filtrována tak, aby zobrazovala sestavy, které se týkají dat v seznamu. Tady jsou stránky typu seznam, které obsahují část **Sestavy Power BI**:

| ID stránky | Jméno |
|-------|----|
| 22 | Přehled zákazníků |
| 27 | Přehled dodavatelů |
| 31 | Přehled zboží |
| 9305 | Seznam prodejních objednávek |
| 9308 | Nákupní faktury |

Tady jsou další stránky, které obsahují větší část **Sestav Power BI**:

| ID stránky | Jméno |
|-------|----|
| 1156 | Podrobnosti o společnosti |
| 4013 | Intelligent Cloud Insights |
| 9006 | Centrum rolí Zpracovatel objednávek |
| 9008 | Deník rolí Skladník |
| 9010 | Centrum rolí Výrobní plánovač |
| 9015 | Centrum rolí Vedoucí projektuC |
| 9016 | Centrum rolí Správce servisu |
| 9022 | Centrum rolí Obchodní ředitel |
| 9024 | Centrum rolí Správce zabezpečení |
| 9026 | Centrum rolí Manažer prodeje a vztahů   |
| 9027 | Centrum rolí Účtárna |

> [!TIP]
> V tuto chvíli nemáme v plánu přidat jej na všechny stránky seznamu. Můžete však vytvořit jednoduchou extension stránky, která přidá část **Sestavy Power BI** do okna s fakty. Pro více informací navštivte [Přidání částí sestav Power BI na stránky](/dynamics365/business-central/dev-itpro/developer/devenv-power-bi-report-parts) v nápovědě vývojáře a IT Pro.

<!-- 5 -->
### Existuje nějaký způsob, jak filtrovat datovou sadu z Business Central *dříve* než ji vytáhnu do Power BI, místo toho, abych potom použil filtry přímo v Power BI?

Chcete-li filtrovat větší datové sady, nejjednodušším způsobem je nastavit filtr v sestavě Power BI přímo úpravou vzorce Power Query. Většina filtrů, které nastavíte tímto způsobem, bude předána do Business Central prostřednictvím skládání dotazů. Viz [Inkrementální aktualizace pro datové sady](/power-bi/admin/service-premium-incremental-refresh).

V současné době neexistuje žádný způsob, jak nastavit filtr pro data webové služby z Business Central. Pokud vaše aplikace potřebuje nastavit filtr z Business Central, budete si pro tento účel muset vytvořit vlastní aplikaci Business Central.

<!-- 10 -->
### Existuje z Power BI kromě použití dotazu i jiný způsob, jak získat data z tabulek Business Central, které nemají přidruženou stránku? Například jako tabulka *Atributy zboží mapování hodnot*.

Čísla. V tuhle chvíli ne.

<!-- 12 -->
### Jsou publikované dotazy rychlejší než publikované stránky?

Pokud jde o webové služby, publikované dotazy jsou obvykle rychlejší než ekvivalentní publikované stránky. Důvodem je, že dotazy jsou optimalizovány pro čtení dat a neobsahují triggery, jako je OnAfterGetRecord.

Web services are based on pages or queries that are built for access from the web and usually not optimized for access from external services. Even though the Business Central connector still supports getting data from web services, we encourage you to use API pages instead of web services whenever possible.

<!-- 13 -->
### Existuje způsob, jak může koncový uživatel vytvořit webovou službu se sloupcem, který je v tabulce Business Central, ale ne na stránce? Nebo bude muset vývojář vytvořit vlastní dotaz?

There is currently no way of adding a new field to a web service. API pages offer full flexibility on the page structure, so a developer can create a new API page to meet this requirement.

<!-- 28 -->
### Můžu Power BI připojit k databázi Business Central online jen pro čtení?

This functionality will be available soon. Starting in February 2022, new reports you create based on Business Central online data will automatically try to connect to a read-only database replica. This will cause your reports to refresh faster, and will have less impact on performances if you're using Business Central while a report is refreshing. We still recommend, whenever possible, that you schedule your reports to refresh outside of normal working hours.

If you have old reports based on Business Central data, they won't connect to the read-only database replica.

### <a name="databasemods"></a>I've tried the preview of the new connector for the February 2022 update. When I connect to my custom Business Central API page, I get the error "Cannot insert a record. Current connection intent is Read-Only.". How can I fix it?

With the new connector, new reports that use Business Central data will connect to a read-only replica of the Business Central database by default. This change will bring a performance improvement. However, in rare cases, it might cause the error. This error typically happens because your custom API is making modifications to Business Central records while Power BI tries to get the data. In particular, it happens as part of the AL triggers: OnInit, OnOpenPage, OnFindRecord, OnNextRecord, OnAfterGetRecord, and OnAfterGetCurrRecord.

To fix this issue by forcing the Business Central connector to allow this behavior, see [Building Power BI Reports to Display Business Central Data - Fixing Problems](across-how-use-financials-data-source-powerbi.md#fixing-problems).

<!--
In general, we recommend avoiding any database modifications in API pages when they're opening or loading records, because they cause performance issues and might cause your report refresh to fail. In some cases, you might still need to make a database modification when your custom API page opens or loads records. You can force the Business Central connector to allow this behavior. Do the following steps when getting data from Business Central for the report in Power BI Desktop:

1. Start Power BI Desktop.
2. In the ribbon, select **Get Data** > **Online Services**.
3. In the **Online Services** pane, select **Dynamics 365 Business Central**, then **Connect**.
4. In the **Navigator** window, select the API endpoint that you want to load data from.
5. In the preview pane on the right, you'll see the following error:

   *Dynamics365BusinessCentral: Request failed: The remote server returned an error: (400) Bad Request. (Cannot insert a record. Current connection intent is Read-Only. CorrelationId: [...])".*

6.	Select **Transform Data** instead of **Load** as you might normally do.
7. In **Power Query Editor**, select **Advanced Editor** from the ribbon.
8.	Replace the following line:

   ```
   Source = Dynamics365BusinessCentral.ApiContentsWithOptions(null, null, null, null),
   ```

   with the line:

   ```
   Source = Dynamics365BusinessCentral.ApiContentsWithOptions(null, null, null, [UseReadOnlyReplica = false]),
   ```

9.	Select **Done**.
10. Select **Close & Apply** from the ribbon to save the changes and close Power Query Editor.

-->
### <a name="perms"></a>Jak změním nebo vymažu uživatelský účet, který aktuálně používám pro připojení k Business Central z Power BI Desktopu?

V Power BI Desktopu proveďte následující kroky:

1. V nabídce Soubor vyberte **Možnosti a nastavení** > **Nastavení zdroje dat**.
2. Ze seznamu vyberte **Dynamics Business Central** a poté vyberte **Vymazat oprávnění** > **Odstranit**.

Až se příště připojíte k Business Central, abyste získali data, budete vyzváni k přihlášení.

## [Výkon](#tab/performance)

<!-- 17 -->

### Je rychlejší získat data pomocí stránek ROZHRANÍ API než pomocí webových služeb?

Ano. Naše testy ukazují, že stránky API jsou až o 25 % výkonnější než webové služby.

<!-- 18 -->
### Existují plány na zrcadlení instance Azure SQL Database, ke které se mohu připojit přímo?

Čísla. V tuhle chvíli ne. S Business Central můžu komunikovat pouze prostřednictvím rozhraní API.

<!-- 19 -->
### Načítání dat z webových služeb Business Central se zdá být pomalé. Existuje nějaký způsob, jak získat data přímo z databázové tabulky SQL?

Čísla. Přímý přístup k databázi není možný, ale přechod na stránky rozhraní API (když je k dispozici nový konektor) výrazně pomůže.

## [Pokročilé](#tab/advanced)
<!-- 1 -->

### Existují plány pro konektor Power BI, který podporuje přírůstkové funkce aktualizace ve službě Power BI?

Ano. Je to v našem plánu.

<!-- 2 -->
### Pokud řešení Business Central on-premises nemá přístup k internetu, můžu pořád používat Power BI?
<!-- todo: please explain this one-->

Ano. V takovém případě používáte Power BI Desktop lokálně a připojujete se k Business Central on-premises. Po připojení můžete vytvářet a prohlížet si sestavy, ale nemůžete je publikovat do služby Power BI.
<!-- 20 -->
### Existují nějaké plány, které by umožnily replikaci online databází Business Central, aby byly přístupné pro dotazy SQL jen pro čtení? Tato funkce by podporovala přírůstkovou aktualizaci a byla by mnohem rychlejší než rozhraní API nebo webové služby.

<!-- todo: what does "BC-Saas-DB-replicated DB accessible" mean? fixe-->
Ano. Tuto funkci máme v našem dlouhodobém plánu.

<!-- 21 -->
### Když použiju Azure Data Factory k získání dat z Business Central a jejich využití v Power BI, pomůže to zvýšit výkon?

Ano. Tento pokročilý scénář pomůže Business Central zůstat výkonným, protože přístup k datům se bude provádět prostřednictvím Azure Data Factory.

<!-- 22 -->
### Existují nějaké plány na podporu kanálů nasazení Power BI nebo způsob, jak vytvořit kanály nasazení pro sestavy PBI, podobně jako rozšíření? Nebo možná i jednoduché rozhraní API v Centru pro správu?

Prověřujeme tuto funkci. Power BI nabízí bohatá rozhraní API pro řízení nasazení sestav. Pro více informací navštivte [Úvod do nasazení kanálů](/power-bi/create-reports/deployment-pipelines-overview).

### When I get data from Business Central to use in my Power BI reports, I see some values like "_x0020_". Co znamenají tyto hodnoty?

Some API pages, including most API v2.0 pages, have fields based on [AL Enum objects](/dynamics365/business-central/dev-itpro/developer/devenv-extensible-enums). Fields based on AL enum objects must have names that are consistent and always the same, so that filters on the report always work&mdash;no matter the language or operating system you're using. For this reason, the fields based on AL enums aren't translated and are encoded to avoid any special character, including the space. Zejména vždy, když je v objektu AL Enum prázdná možnost, je zakódována na "_x0020_". Transformaci dat v Power BI můžete použít vždy, pokud chcete pro tato pole zobrazit jinou hodnotu, například "Prázdná".


---

## Viz také

[Power BI Licensing](admin-powerbi-setup.md#license)
[Business Central and Power BI Introduction](admin-powerbi.md)  
[Power BI Integration Overview](admin-powerbi-overview.md)  
[Enabling Power BI in Business Central](admin-powerbi-setup.md)  
[Work with Power BI Reports in Business Central](across-working-with-powerbi.md)  
[Work with Business Central Data in Power BI](across-working-with-business-central-in-powerbi.md)  
[Building Power BI Reports to Display Business Central Data](across-how-use-financials-data-source-powerbi.md)    
[Power BI documentation](/power-bi/)


[!INCLUDE[footer-include](includes/footer-banner.md)]
