---
title: Bookmark link to page or report on Role Center
description: Using the bookmark icon, you can add an action that opens a page or report from the navigation menu of your Role Center.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 06/23/2021
ms.author: edupont
---

# Záložka stránky nebo sestavy v Centru rolí
Pomocí ikony záložky můžete přidat akci, která otevře stránku nebo sestavu z navigační nabídky Centra rolí. Bookmarks allow you to quickly reach your favorite content or business tasks. Záložku přidáte z cílové stránky nebo sestavy, což znamená obrazovku, která se má otevřít z odkazu v Centru rolí.

The bookmark icon is shown in the top-right corner of a page and also in the **Tell Me** window where you can efficiently bookmark multiple pages or reports. Pokud záložka již pro stránku existuje, ikona je tmavá a popis s nápisem "Uloženo jako záložka".

## Uložení cílové stránky jako záložky
1. Otevřete jakoukoli stránku, na kterou chcete odkaz ve svém Centru rolí.
2. Choose the ![Bookmark.](media/ui_bookmark_icon.png "Bookmark") icon.

Akce pojmenovaná po stránce je nyní přidána do navigační nabídky v Centru rolí.

## Uložení vybrané sestavy jako záložky
1. Otevřete libovolnou stránku před spuštěním sestavy, kterou chcete v Centru rolí odkazovat.
2. Choose the ![Bookmark.](media/ui_bookmark_icon.png "Bookmark") icon.

Akce pojmenovaná po sestavě je nyní přidána do navigační nabídky v Centru rolí.

## Vytvoření záložky stránky nebo sestavy z okna Řekněte mi
1. Open the **Tell Me** window and enter, for example, **Sales Orders**.
2. Hover over the search result for the **Sales Orders** page or report, and then choose the ![Bookmark.](media/ui_bookmark_icon.png "Bookmark") icon.

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
   The ability to bookmark a page or report is one of many user personalization features in Business Central. If the bookmark icon isn't displayed, it's likely that your administrator has disabled personalization.

- **Why can't I bookmark certain pages or reports?**  
   Not all pages and reports can be bookmarked. When a page or report is run within some special context governed by the business application, the bookmark icon isn't displayed. For example, pages that cannot be found in the **Tell Me** window but are launched from elsewhere will not display a bookmark icon. Podobně stránky návrhu sestavy, které se používají pouze ke shromažďování filtrů bez spuštění sestavy, nezobrazí ikonu záložky.

   See technical details about [RunRequestPage](/dynamics365/business-central/dev-itpro/developer/methods-auto/report/reportinstance-runrequestpage-method) and [FilterPageBuilder](/dynamics365/business-central/dev-itpro/developer/methods-auto/filterpagebuilder/filterpagebuilder-data-type).

- **When clearing my personalization, will my bookmarks also be cleared?**  
   Yes. Záložky jsou umístěny v navigační nabídce. Pokud odstraníte změny v navigační nabídce na jakékoli stránce nebo zrušíte veškerou personalizaci v Centru rolí, budou všechny vaše záložky trvale odstraněny.

- **Why does the bookmark icon continue to indicate it's still not bookmarked?**  
   When you add a bookmark, the new action is added to the navigation menu on the Role Center and subsequent visits to the page or report show a dark bookmark icon. Pokud centrum rolí přizpůsobíte a změníte uspořádání akcí přesunutím do skupin, ikona záložky už nebude tmavá a na stejnou stránku nebo sestavu můžete přidat další záložku. This allows you to add multiple actions to the same page or report and categorize them into different groups.

- **Why does my link to a report display a different report?**  
   Some reports may be substituted by other reports after applying an extension to Business Central. When substitution occurs, the text of the new action isn't updated and will continue to display the name of the original report, but navigate to the newer report. Chcete-li opravit text nové akce, můžete novou akci odebrat a přidat ji znovu.
<!-- For more information on report substitution, see this link UNAVAILABLE AT THIS TIME -->

- **Is bookmarking available for XMLports?**  
   No. At this time, adding actions to open XMLports isn't possible from the user interface.

- **Will my bookmarks be translated when I change my language in Business Central?**  
   When you add a new action, any translated text that was available at the time is used when bookmarking. Pokud je později přidán nový přeložený text, nová akce nebude obsahovat novější překlady.

- **Why can't I add text in a page right after opening it with the bookmark?**<br>
   When a page is bookmarked, the page will always open in the view mode from the bookmark&mdash;even if it was in the edit mode when it was bookmarked. Selecting the **Make changes on the page** icon ![Shows the pencil icon for editing the page.](media/edit-pencil.png) will let you add text in the fields that are editable.


## Viz také
[Personalize Your Workspace](ui-personalization-user.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Change Which Features are Displayed](ui-experiences.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]