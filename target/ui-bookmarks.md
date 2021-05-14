---
title: Bookmark a link to a page or report on your Role Center | Microsoft Docs
description: Learn how to add a link to your Role Center.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 04/01/2021
ms.author: edupont
---

# Záložka stránky nebo sestavy v Centru rolí
Pomocí ikony záložky můžete přidat akci, která otevře stránku nebo sestavu z navigační nabídky Centra rolí. To vám umožní rychle dosáhnout vašeho oblíbeného obsahu nebo obchodních úkolů. Záložku přidáte z cílové stránky nebo sestavy, což znamená obrazovku, která se má otevřít z odkazu v Centru rolí.

The bookmark icon is shown in the top right corner of a page and also in the **Tell Me** window where you can efficiently bookmark multiple pages or reports. Pokud záložka již pro stránku existuje, ikona je tmavá a popis s nápisem "Uloženo jako záložka".

## Uložení cílové stránky jako záložky
1. Otevřete jakoukoli stránku, na kterou chcete odkaz ve svém Centru rolí.
2. Zvolte ikonu ![Záložky](media/ui_bookmark_icon.png "Přidat záložku do svého centra rolí") .

Akce pojmenovaná po stránce je nyní přidána do navigační nabídky v Centru rolí.

## Uložení vybrané sestavy jako záložky
1. Otevřete libovolnou stránku před spuštěním sestavy, kterou chcete v Centru rolí odkazovat.
2. Zvolte ikonu ![Záložky](media/ui_bookmark_icon.png "Přidat záložku do svého centra rolí") .

Akce pojmenovaná po sestavě je nyní přidána do navigační nabídky v Centru rolí.

## Vytvoření záložky stránky nebo sestavy z okna Řekněte mi
1. Open the **Tell Me** window and enter, for example, **Sales Orders**.
2. Hover over the search result for the **Sales Orders** page or report, and then choose the ![Bookmark](media/ui_bookmark_icon.png "Bookmark") icon.

Akce pojmenovaná po stránce nebo sestavě je nyní přidána do navigační nabídky v Centru rolí.


## Často kladené otázky

- **Can I reorganize my bookmarks?**  
   Yes. You can personalize your Role Center and move actions into a more optimal sequence or move them into existing groups or subgroups.  
   Learn how to [Personalize Your Workspace](ui-personalization-user.md).

- **How do I remove a bookmark?**  
   On the target page or report, choose the bookmark icon again to remove the involved action from your Role Center. Centrum rolí můžete také přizpůsobit a dočasně skrýt akce, aniž byste je zcela odstranili.

- **Where do I find my bookmarks?**  
   When adding a bookmark to a page or report, the new action is added to the top navigation menu on your current home screen (Role Center). If you happen to have many actions, you may need to activate the **More** button to display all of them because the new action is always appended at the end of those actions.
<!-- Should we add a screenshot here? -->

- **I don't have a bookmark icon. Is something wrong?**  
   The ability to bookmark a page or report is one of many user personalization features in Business Central. Pokud není ikona záložky zobrazena je pravděpodobné, že správce zakázal přizpůsobení.

- **Why can't I bookmark certain pages or reports?**  
   Not all pages and reports can be bookmarked. Pokud je stránka nebo sestava spuštěna v nějakém zvláštním kontextu, která se řídí obchodní aplikací, ikona záložky se nezobrazí. For example, pages that cannot be found in the **Tell Me** window but are launched from elsewhere will not display a bookmark icon. Podobně stránky návrhu sestavy, které se používají pouze ke shromažďování filtrů bez spuštění sestavy, nezobrazí ikonu záložky.

See technical details about [RunRequestPage](/dynamics365/business-central/dev-itpro/developer/methods-auto/report/reportinstance-runrequestpage-method) and [FilterPageBuilder](/dynamics365/business-central/dev-itpro/developer/methods-auto/filterpagebuilder/filterpagebuilder-data-type).

- **When clearing my personalization, will my bookmarks also be cleared?**  
   Yes. Záložky jsou umístěny v navigační nabídce. Pokud odstraníte změny v navigační nabídce na jakékoli stránce nebo zrušíte veškerou personalizaci v Centru rolí, budou všechny vaše záložky trvale odstraněny.

- **Why does the bookmark icon continue to indicate it is still not bookmarked?**  
   When you add a bookmark, the new action is added to the navigation menu on the Role Center and subsequent visits to the page or report show a dark bookmark icon. Pokud centrum rolí přizpůsobíte a změníte uspořádání akcí přesunutím do skupin, ikona záložky už nebude tmavá a na stejnou stránku nebo sestavu můžete přidat další záložku. To umožňuje přidat více akcí na stejnou stránku nebo sestavu a kategorizovat je do různých skupin.

- **Why does my link to a report display a different report?**  
   Some reports may be substituted by other reports after applying an extension to Business Central. Dojde-li k nahrazení, text nové akce není aktualizován a bude nadále zobrazovat název původní sestavy, ale přejde do novější sestavy. Chcete-li opravit text nové akce, můžete novou akci odebrat a přidat ji znovu.
<!-- For more information on report substitution, see this link UNAVAILABLE AT THIS TIME -->

- **Is bookmarking available for XMLports?**  
   No. V současné době není z uživatelského rozhraní možné přidávat akce k otevření XMLportů.

- **Will my bookmarks be translated when I change my language in Business Central?**  
   When you add a new action, any translated text that was available at the time is used when bookmarking. Pokud je později přidán nový přeložený text, nová akce nebude obsahovat novější překlady.


## Viz také
[Personalize Your Workspace](ui-personalization-user.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Change Which Features are Displayed](ui-experiences.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]