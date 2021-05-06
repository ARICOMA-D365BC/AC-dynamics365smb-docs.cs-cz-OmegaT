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
# List Views FAQ
This article answers questions that our advanced users often ask about working with list views and saving filters.  

### How do views handle expressions?

When you save a view that includes filters with expressions (like date ranges, operators, keywords, or filter tokens), only the expression gets saved&mdash;not the resulting values. For example, saving a view that filters on the **Created Date** field with the expression `-1W..today` will always find records related to the current date, even when the view is accessed next month.

### Where are list views saved?

Similarly to hiding a field or reordering your navigation menu, list views are a part of user personalization and are stored in the database. Clearing all personalization on a list will also permanently remove your personal views and clear other personalization such as reordering of views. For more information, see [Personalize your workspace](ui-personalization-user.md).

### <a name="save"></a>Why don't I have a Save icon?

There's a couple reasons why you might not see the Save icon and options menu alongside views in the filter pane.

One reason could be that personalization isn't enabled for your user role. In this case, you still have access system views that are a standard part of the pages. You can modify these views, like changing or adding filters. You just can't save the changes. Another reason could be that the page you're looking at is a *worksheet* type page&mdash;not a list.

### On which page types can I use list views?

Views are only available on list pages.

### How do I know whether I'm on list type page

Use page inspection. To open page inspection, press Ctrl+Alt+F1. Then, in the **Page** field, look for the word **List** in the parenthesis at the end.

### Are views also available on other form factors?

Yes. Any views you save on your desktop browser or desktop app will also be available on your tablet or smartphone. You can't modify or personalize views on mobile devices.

### Are my personal views always accessible?

Your views are available on a list page whether you access it from the navigation menu, using the **Tell Me** window, or through a URL link. Views aren't available in list parts, lookups or whenever a list page is displayed as a dialog.

### How do I return a view to its original filters after modifying them?

At the bottom of the filter pane, choose the **Reset filters** action to clear filter changes you have made to the view and return to its original filtered fields and filter criteria.

### What is the difference between hiding and removing views?

Removing a view will permanently delete that view. Hiding a view allows you to temporarily hide it from the filter pane, but you can unhide it again later by choosing the **Show** action.

### How can I share my views with others?

[!INCLUDE[prod_short](includes/prod_short.md)] doesn't provide a way to share the precise list view. But you can share your current filters so that other users can see a similar list of records. In your desktop browser, just copy the URL and share it with your colleagues. Sharing filters isn't guaranteed to give the recipient an identical set of filters that you see in your browser.

### Can I search for views in the Tell Me window?

No. The **Tell Me** window only displays search results for the page, but you're only a step away from getting to your favorite view once you navigate to the page.

### What is shared layout?

All views on a list page share a common column layout. The layout includes which columns are displayed, their sequence, width, freeze pane, and quick entry settings. Personalizing any column layout will also affect other views sharing the same layout on the list page.

Some system views can have unique layouts of the columns in the list. For example, they could rearrange columns to display only the columns most relevant to that view. You can identify which views have unique layouts by choosing the ![Show more options](media/show-more-options-icon.png "Show more options") icon and observing that the **Shared layout** check box isn't selected. As a user, you can personalize the column layout for a view with unique layout without it affecting any of the other views on the list page. Only developers can define a unique column layout for a view that initially has a shared layout.

### What does the Show System Filters link do?

On some list pages, the filter pane displays **Show system filters** at the bottom, specifically when the page includes filters specified by the system. These special filters are typically used to display records based on the current context. An example would be when an orders list has to be filtered for a specific customer.

System filters are set by application developers, which they set using filter group 0. For more information about system filters, see [FilterGroup Method](/dynamics365/business-central/dev-itpro/developer/methods-auto/record/record-filtergroup-method).

### I see multiple views on my page, but I didn't create them. Where did they come from?

The views you see on any list are a combination of your personal views together with system views. System views may originate from the business application, from extensions, or may be role-specific if the list was customized for your role.

### Why do some views provide fewer options?

Some views only provide the option to save a copy of the view, while others don't allow saving changes to the view. How the view was created determines the options available to that view. Views can be created in multiple ways:

- Personal views that you saved
- System views that are a standard part of the business application, or added by extensions or role-specific views. Unlike personal views, you can't save changes to filters back to that system view.
- Legacy system views that are a standard part of the business application but were created using older versions of [!INCLUDE[prod_short](includes/prod_short.md)]. These views offer fewer options. You can only save them as a new view and can't hide or reorder them either. Legacy system views will be discontinued in a future update to [!INCLUDE[prod_short](includes/prod_short.md)].

### How do I convert legacy system views?

Legacy system views are list views that were created by developers in older versions of [!INCLUDE[prod_short](includes/prod_short.md)] by placing them on the Role Center page. These views are now displayed directly on the list page but offer a degraded experience and fewer options. You can convert a legacy system view to a personal view that is fully customizable, simply by saving that legacy view as a new view. Similarly, administrators can choose to convert role-specific legacy system views by customizing the user role and saving the legacy view as a new role-specific view.

Legacy system views will be discontinued in a future update to [!INCLUDE[prod_short](includes/prod_short.md)].

### Others in my organization need similar list views as standard. What can I do?

Working with personal views is quick and effective, but [!INCLUDE[prod_short](includes/prod_short.md)] provides other tools to define list views needed by specific user roles or all users in the organization.
 - Developers can customize the environment and create list views in extensions for all users in the organization.
 - Non-coders such as administrators or department managers, can create role-specific list views when customizing a role from the **Profiles (Roles)** page.

### I work with multiple languages: how do I translate the name of the view?

When saving a new view or renaming an existing view, you must enter a recognizable and meaningful name for that view. The name is saved for your current language and will be displayed also when you or other users work with [!INCLUDE[prod_short](includes/prod_short.md)] in different languages. To provide translated view names, switch the language by using the **My Settings** page. Then rename the view, which will store the translated name in the new language.

### Do views with expressions work in all languages?

Expressions that only use symbols, such as `|` or `..` are considered safe for users to access in any language. Any views with expressions that include letters, keywords, or filter tokens will only work for the language in which they were authored.

### See Also

[Save and Personalize List Views](ui-views.md)  
[Finding Features and Information](ui-search.md)  
[Sorting, Searching, and Filtering](ui-enter-criteria-filters.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]