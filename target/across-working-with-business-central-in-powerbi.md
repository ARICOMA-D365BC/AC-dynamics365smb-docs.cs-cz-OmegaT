---
title: Working with Business Central Data In Power BI| Microsoft Docs
description: Getting insight, business intelligence, and KPIs from your Business Central data using Power BI.
author: jswymer

ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: account schedule, analysis, reporting, financial report, business intelligence, KPI
ms.date: 04/01/2021
ms.author: jswymer

---
# Work with [!INCLUDE [prod_short](includes/prod_short.md)] Data in Power BI

V tomto článku se dozvíte některé základy práce se sestavami a řídicími panely v Power BI, které používají [!INCLUDE [prod_short](includes/prod_short.md)] jako zdroj dat. Článek pojednává o některých aspektech, které vám pomohou začít jako uživatel [!INCLUDE[prod_short](includes/prod_short.md)]. Obecné pokyny a pokyny k používání Power BI najdete v dokumentaci [Power BI pro spotřebitele](/power-bi/consumer).

## Připravte se

Zaregistrujte se ke službě Power BI. Pokud jste se ještě nezaregistrovali, přejděte na [https://powerbi.microsoft.com](https://powerbi.microsoft.com). Při registraci použijte pracovní e-mailovou adresu a heslo.

## Začínáme

Jakmile máte účet Power BI, můžete se přihlásit na [https://powerbi.microsoft.com/](https://powerbi.microsoft.com/).

Služba Power BI je hostitelem všech sestav, které máte k dispozici. Chcete-li zobrazit sestavu, vyberte možnost **Můj pracovní prostor** > **Sestavy**. Pak stačí vybrat sestavu, kterou chcete zobrazit.

S [!INCLUDE[prod_short](includes/prod_short.md)] online, budete mít automaticky sadu výchozích sestav v pracovním prostoru. Pokud chcete vytvořit vlastní sestavy, můžete k vytváření sestav použít Power BI Desktop a pak je publikovat do pracovního prostoru. Pro další informace navštivte [Začínáme vytvářet sestavy v Power BI Desktop k zobrazení dat [!INCLUDE [prod_long](includes/prod_long.md)]](across-how-use-financials-data-source-powerbi.md).

Pokud používáte [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, budete muset začít od začátku pomocí Power BI Desktop. Volitelně lze sestavy Power BI distribuovat jako soubory, které můžete nahrát.

## Získání nejnovějších dat

Každá sestava Power BI je založena na datové sadě, která získává zdrojová data z [!INCLUDE[prod_short](includes/prod_short.md)]. Chcete se ujistit, že data v sestavách Power BI jsou aktuální s daty v [!INCLUDE[prod_short](includes/prod_short.md)]. Tento koncept se označuje jako *Aktualizace*.  V závislosti na tom, jak vaše organizace nastavila Power BI, nemusí být aktualizace prováděná automaticky. Data lze aktualizovat dvěma způsoby: ručně nebo naplánováním aktualizace. Ruční aktualizace se provádí podle potřeby na vyžádání. Plánovaná aktualizace umožňuje automatickou aktualizaci v definovaných časových intervalech.

### Ruční aktualizace

V navigačním podokně vyberte v části **Sada dat** vedle datové sady možnost **Další možnosti (...)** a pak vyberte **Obnovit nyní**.

### Naplánování aktualizace

V navigačním podokně vyberte v části Sady dát vedle datové sady Další možnosti (...) a pak vyberte **Naplánovat aktualizaci**. Vyplňte informace v části **Naplánovat aktualizaci** a vyberte **Použít**.

Pro více informací navštivte [Konfigurace naplánované aktualizace](/power-bi/connect-data/refresh-scheduled-refresh).

## <a name="upload"></a>Nahrávání sestav ze souborů

Sestavy Power BI lze mezi uživatele distribuovat jako soubory PBIX. Pokud máte soubor .pbix, můžete soubor nahrát do pracovního prostoru. Chcete-li sestavu odeslat, vykonejte následující kroky:

1. V novém pracovním prostoru vyberte **Získat data**.

2. V poli Soubory vyberte **Získat**.

3. Vyberte **Místní soubor**, přejděte na místo, kam jste soubor uložili, a vyberte **Otevřít**.

Pro více informací navštivte [Nahrání sestavy do služby](/power-bi/paginated-reports/paginated-reports-quickstart-aw#upload-the-report-to-the-service).

> [!NOTE]
> Nahrání sestavy vyžaduje, abyste měli pracovní prostor s [kapacitou Premium](/power-bi/service-premium-what-is). Pro více informací navštivte [Správa kapacit Premium](/power-bi/admin/service-premium-capacity-manage).

> [!TIP]
> Pokud používáte [!INCLUDE[prod_short](includes/prod_short.md)] online, můžete také nahrát zprávu zevnitř [!INCLUDE[prod_short](includes/prod_short.md)]. For more information, see [Work with Power BI Reports in [!INCLUDE [prod_short](includes/prod_short.md)] - Upload Reports](across-working-with-powerbi.md#upload).

## <a name="share"></a>Sdílení sestav s ostatními

Jakmile je sestava ve vašem pracovním prostoru, můžete ji sdílet s ostatními ve vaší organizaci.

Chcete-li sdílet sestavu, vyberte v seznamu sestav nebo v otevřené sestavě možnost **Sdílet**. V ppodokně **Sdílet sestavu** zadejte úplné e-mailové adresy jednotlivců nebo distribučních skupin, se kterými chcete sestavu sdílet. Sdílení dokončete podle pokynů na obrazovce. Pro více informací navštivte [Sdílení řídicího panelu nebo sestavy](/power-bi/collaborate-share/service-share-dashboards#share-a-dashboard-or-report).

> [!NOTE]
> Musíte mít licenci [Power BI Pro](/power-bi/service-features-license-type) a také jí musí mít lidé, se kterými chcete sestavu sdílet sdílíte. Obsah musí být v pracovním prostoru s  [kapacitou Premium](/power-bi/service-premium-what-is). Pro více informací navštivte [Způsoby sdílení práce v Power BI](/power-bi/service-how-to-collaborate-distribute-dashboards-reports).

## Podívejte se na související školení na webu [Microsoft Learn](/learn/modules/configure-powerbi-excel-dynamics-365-business-central/index)

## Viz také

[Business Central and Power BI](admin-powerbi.md)  
[Building Power BI Reports to Display [!INCLUDE [prod_long](includes/prod_long.md)] Data](across-how-use-financials-data-source-powerbi.md)  
[Power BI Integration Component and Architecture Overview for [!INCLUDE[prod_short](includes/prod_short.md)]](admin-powerbi-overview.md)  
[Work with Power BI Reports in [!INCLUDE [prod_short](includes/prod_short.md)]](across-working-with-powerbi.md)  
[Power BI for consumers](/power-bi/consumer/end-user-consumer)  
[The 'new look' of the Power BI service](/power-bi/service-new-look)  
[Quickstart: Connect to data in Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data)  
[Power BI documentation](/power-bi/)  
[Business Intelligence](bi.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Setting Up [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Use [!INCLUDE[prod_short](includes/prod_short.md)] as a Power BI Data Source](across-how-use-financials-data-source-powerbi.md)  
[Use [!INCLUDE[prod_short](includes/prod_short.md)] as a Power Apps Data Source](across-how-use-financials-data-source-powerapps.md)  
[Use [!INCLUDE[prod_short](includes/prod_short.md)] in Power Automate](across-how-use-financials-data-source-flow.md)




[!INCLUDE[footer-include](includes/footer-banner.md)]