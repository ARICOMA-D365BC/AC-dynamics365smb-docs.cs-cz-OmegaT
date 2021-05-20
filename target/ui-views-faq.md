---
title: Frequently Asked Questions about List Views
description: Detailed information about saving filters as list views.
author: mikebcMSFT
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: list, filter, pane, views
ms.date: 04/01/2021
ms.author: mikebc

---
# Nejčastějších dotazy - Seznamy
This article answers questions that our advanced users often ask about working with list views and saving filters.

### Jak seznamy zpracovávají výrazy?

When you save a view that includes filters with expressions (like date ranges, operators, keywords, or filter tokens), only the expression gets saved&mdash;not the resulting values. For example, saving a view that filters on the **Created Date** field with the expression `-1W..today` will always find records related to the current date, even when the view is accessed next month.

### Kde jsou uloženy seznamy?

Podobně jako skrytí políčka, nebo přeskládání vašeho navigačníhé menu se jedná o perzonalizaci, který je uložena v databázi. Clearing all personalization on a list will also permanently remove your personal views and clear other personalization such as reordering of views. For more information, see [Personalize your workspace](ui-personalization-user.md).

### <a name="save"></a>Why don't I have a Save icon?

There's a couple reasons why you might not see the Save icon and options menu alongside views in the filter pane.

One reason could be that personalization isn't enabled for your user role. In this case, you still have access system views that are a standard part of the pages. You can modify these views, like changing or adding filters. You just can't save the changes. Another reason could be that the page you're looking at is a *worksheet* type page&mdash;not a list.

### Na kterých typech stránek lze použít zobrazení seznamu?

Views are only available on list pages.

### How do I know whether I'm on list type page

Use page inspection. To open page inspection, press Ctrl+Alt+F1. Then, in the **Page** field, look for the word **List** in the parenthesis at the end.

### Jsou k dispozici také pohledy na jiné formy?

Ano. Všechna zobrazení, která uložíte v prohlížeči pro stolní počítače nebo v aplikaci pro stolní počítače, budou k dispozici také na tabletu nebo smartphonu. You can't modify or personalize views on mobile devices.

### Jsou moje pohledy vždy přístupné?

Your views are available on a list page whether you access it from the navigation menu, using the **Tell Me** window, or through a URL link. Views aren't available in list parts, lookups or whenever a list page is displayed as a dialog.

### Jak mohu po úpravě vrátit seznam na původní filtry?

At the bottom of the filter pane, choose the **Reset filters** action to clear filter changes you have made to the view and return to its original filtered fields and filter criteria.

### Jaký je rozdíl mezi skrytím a odebráním pohledů?

Odebráním pohledu se toto zobrazení trvale odstraní. Hiding a view allows you to temporarily hide it from the filter pane, but you can unhide it again later by choosing the **Show** action.

### Jak mohu sdílet své pohledy s ostatními?

[!INCLUDE[prod_short](includes/prod_short.md)] doesn't provide a way to share the precise list view. But you can share your current filters so that other users can see a similar list of records. In your desktop browser, just copy the URL and share it with your colleagues. Sharing filters isn't guaranteed to give the recipient an identical set of filters that you see in your browser.

### Mohu vyhledávat přehledy v okně Řekněte mi?

Číslo  The **Tell Me** window only displays search results for the page, but you're only a step away from getting to your favorite view once you navigate to the page.

### Co je sdílené rozvržení?

All views on a list page share a common column layout. The layout includes which columns are displayed, their sequence, width, freeze pane, and quick entry settings. Personalizing any column layout will also affect other views sharing the same layout on the list page.

Některá systémová zobrazení mohou mít jedinečná rozložení sloupců v seznamu. For example, they could rearrange columns to display only the columns most relevant to that view. You can identify which views have unique layouts by choosing the ![Show more options](media/show-more-options-icon.png "Show more options") icon and observing that the **Shared layout** check box isn't selected. Jako uživatel si můžete přizpůsobit rozvržení sloupců pro pohled s jedinečným rozvržením, aniž by to ovlivnilo kterékoli z ostatních pohledů na stránce seznamu. Pouze vývojáři mohou definovat jedinečné rozložení sloupců pro zobrazení, které má sdílené rozložení.

### Co dělá odkaz Zobrazit systémové filtry?

On some list pages, the filter pane displays **Show system filters** at the bottom, specifically when the page includes filters specified by the system. These special filters are typically used to display records based on the current context. An example would be when an orders list has to be filtered for a specific customer.

System filters are set by application developers, which they set using filter group 0. For more information about system filters, see [FilterGroup Method](/dynamics365/business-central/dev-itpro/developer/methods-auto/record/record-filtergroup-method).

### I see multiple views on my page, but I didn't create them. Kde se tu vzali?

Pohledy, které vidíte v kterémkoli seznamu, jsou kombinací vašich osobních pohledů a systémových pohledů. Systémové pohledy mohou pocházet z obchodní aplikace, z rozšíření nebo mohou být specifická pro roli, pokud byl seznam přizpůsoben pro vaši roli.

### Proč některá zobrazení poskytují méně možností?

Some views only provide the option to save a copy of the view, while others don't allow saving changes to the view. Způsob vytvoření pohledů určuje možnosti, které jsou pro toto zobrazení k dispozici. Pohledy lze vytvořit několika způsoby:

- Osobní, které jste uložili
- Systémové pohledy, která jsou standardní součástí obchodní aplikace nebo jsou přidány rozšířeními nebo zobrazeními specifických pro roli. Unlike personal views, you can't save changes to filters back to that system view.
- Legacy system views that are a standard part of the business application but were created using older versions of [!INCLUDE[prod_short](includes/prod_short.md)]. These views offer fewer options. You can only save them as a new view and can't hide or reorder them either. Legacy system views will be discontinued in a future update to [!INCLUDE[prod_short](includes/prod_short.md)].

### Jak převést starší systémové pohledy?

Legacy system views are list views that were created by developers in older versions of [!INCLUDE[prod_short](includes/prod_short.md)] by placing them on the Role Center page. These views are now displayed directly on the list page but offer a degraded experience and fewer options. Starší systémové pohledy můžete převést na osobní pohledy, které jsou plně přizpůsobitelné, jednoduše uložením tohoto staršího pohledu jako nového. Podobně se správci mohou rozhodnout převést starší systémové pohledy specifické pro roli přizpůsobením uživatelem a uložením staršího pohledu jako nového pro specifickou roli.

Legacy system views will be discontinued in a future update to [!INCLUDE[prod_short](includes/prod_short.md)].

### Ostatní v mé organizaci potřebují podobné pohledy jako standard. Co můžu dělat?

Working with personal views is quick and effective, but [!INCLUDE[prod_short](includes/prod_short.md)] provides other tools to define list views needed by specific user roles or all users in the organization.
- Vývojáři mohou přizpůsobit prostředí a vytvořit zobrazení seznamu rozšíření pro všechny uživatele v organizaci.
- Non-coders such as administrators or department managers, can create role-specific list views when customizing a role from the **Profiles (Roles)** page.

### Pracuji s několika jazyky: jak přeložím název seznamu?

Při ukládání nového seznamu nebo přejmenování existujícího je nutné zadat rozpoznatelný a smysluplný název tohoto seznamu. The name is saved for your current language and will be displayed also when you or other users work with [!INCLUDE[prod_short](includes/prod_short.md)] in different languages. To provide translated view names, switch the language by using the **My Settings** page. Then rename the view, which will store the translated name in the new language.

### Fungují seznamy se výrazy ve všech jazycích?

Expressions that only use symbols, such as `|` or `..` are considered safe for users to access in any language. Any views with expressions that include letters, keywords, or filter tokens will only work for the language in which they were authored.

### Viz také

[Save and Personalize List Views](ui-views.md)  
[Finding Features and Information](ui-search.md)  
[Sorting, Searching, and Filtering](ui-enter-criteria-filters.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]