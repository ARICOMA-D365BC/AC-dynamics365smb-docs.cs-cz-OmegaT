---
title: Manage Saved Settings for Reports and Batch jobs
description: Describes hwo the admin can set up predefined options and filters for a report and share those settings with one or all users.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customization, personalization
ms.date: 12/21/2021
ms.author: edupont

---
# Manage Saved Settings for Reports and Batch jobs

When running reports, users are typically presented with a page that lets them select options and set filters to change the data that is included in the generated report. This page is called the *request page*. A report can include one or more *saved settings* that users can apply to the report from the request page. *Saved settings* are basically predefined options and filters. Použití uložených nastavení představuje rychlý a spolehlivý způsob, jak důsledně generovat sestavy obsahující správná data. For more information, see [Using default values - predefined settings](ui-work-report.md#SavedSettings).

> [!NOTE]
> This topic refers to *reports*, but similar information applies to *batch jobs*.

If you have the proper permissions, you can view, create, and modify the saved settings for all reports for all users in a company. You can assign saved settings for a report to individual users or to all users in the company.

## Manage saved settings

You manage saved settings on the **Reports Settings** page. Tuto stránku lze otevřít dvěma způsoby:

- Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Settings**, and then choose the related link.
- In a report's request page, choose the lookup in the **Use default values from** field, and then choose the **Select from full list** action.

   This field is only visible if you have run the report at least once earlier. The list will only show settings that are available to you, either because they are your own settings, or because the settings are shared with you.

The **Report Settings** page displays all the existing saved settings entries for all users. If there is a user name in the **Assigned to** field, only that user can use the saved settings for the associated report. If there is a check mark in the **Share with all users** field, all users can use the saved settings for the report.

> [!TIP]
> When a user has run a report that supports shared settings, their settings are saved and added to this list. In most cases, the admin can then edit those settings and choose to share the settings with all users.
>
> However, in some cases, settings cannot be shared, and the admin cannot change them either. Most batch jobs do not support shared settings.

## Create or modify saved settings for all users

From the **Report Settings** page, you can:

- Choose the **New** action to create a new saved settings entry from scratch.
- Select a saved settings entry from the list, and choose the **Copy** action to create a copy.
- Select a saved settings entry from the list, and choose the **Edit** action to modify a saved settings entry.

> [!Important]
> Consider the name that you give a saved settings entry. Pokud vytvoříte uloženou položku nastavení pro všechny uživatele a přiřadíte jí stejný název jako existující položka nastavení přiřazená pouze určitému uživateli, nebude moci tento uživatel použít uloženou položku nastavení přiřazenou všem.  In the **Saved Settings** section on the request page, the user will see two saved settings entries with the same name. However, no matter which option they choose, the user-specific saved settings entry will be used.

> [!NOTE]
> The ability to save settings is available only on reports where the [SaveValues property](/dynamics365/business-central/dev-itpro/developer/properties/devenv-savevalues-property) of the report's request page is set to **Yes**. The **SaveValues** property is set by the developer.

## Viz také

[Práce se sestavami, dávkovými úlohami a XMLporty](ui-work-report.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]