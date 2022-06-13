---
title: Exploring and Navigating Pages per Role
description: You can get an overview of all the business features that are available for your role, and for other roles, with the Role Explorer.
author: jswymer

ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: role explorer, find features, navigate
ms.search.form: RoleExplorer, 9020, 9022, 9027, 9024
ms.date: 08/01/2021
ms.author: jswymer
---

# Finding Pages with the Role Explorer

You can get an overview of all the business features that are available for your role, and for other roles if you go a step further. In the following documentation, this feature overview is referred to as the *role explorer*.

Each element on the role explorer is an action that opens a page. Accordingly, you can also use the role explorer as a means to navigate in [!INCLUDE[prod_short](includes/prod_short.md)].

[!INCLUDE [about-ui-learn](includes/about-ui-learn.md)]

## Open the role explorer

You can open the role explorer from the Role Center and all list pages and from the **Tell Me** window.

- On your Role Center or any list page, choose the ![Menu button.](media/ui_menu_button.png "Menu button") button to the right of the navigation bar, or press Shift+F12.
- In the **Tell Me** window, choose the **exploring** action at the bottom.

When you first open the role center, it shows links to most features available for your role.

## Navigate features

The actions that open pages are organized under nodes named after the features or application areas. Each node can be collapsed or expanded individually and you can collapse/expand all nodes together.

- To expand/collapse an individual node, choose the node. This applies to top-level nodes and sub nodes.
- To expand/collapse all top-level nodes on the page, but leave the sub-nodes as they are, choose **...** at the top, then choose **Expand** or **Collapse**.
- To expand/collapse all top-levels node and all sub nodes under it, choose **...** at the top, then choose the **Expand All** or **Collapse All** action.

## Search for features

To quickly locate features, select **Find**, then enter a word or phrase for the feature your trying to find. The role center will highlight any matching text. If a feature is hidden from view in collapsed node, the collapsed node is marked with a dot. 

## Explore other roles

To explore roles other than your own, select **Explore more roles**. The role center displays each role under its own heading, with links to its features. You can then navigate and find features just like you do when exploring your role.

> [!NOTE]
> You'll only see roles that are set up to show in the role explorer. So if you don't see a role that you expected to see, it's probably not set up for it. For more information, see [Manage Profiles](admin-users-profiles-roles.md). 

When exploring other roles, you can also narrow the exploration down by using the **Report & Analysis** and **Administration** actions at the top of the role center.

- **Report & Analysis** shows only those features that are categorized as reports and analysis features.
- **Administration** shows only those features that are categorized as administration features.

> [!TIP]
> For developers, you categorize pages and reports by setting the [UsageCategory property](/dynamics365/business-central/dev-itpro/developer/properties/devenv-usagecategory-property) in the object's AL code.
<!--
 
## Role explorer actions

There a several actions along the top of the role explorer to help you locate features of your role and other roles.

|Action|Description|
|------|------|
|**All**|Shows all features that are related to the role.|
|**Find**|Lets you enter a word or phrase to quickly locate feature names that match.|
|**Explore more roles**|All business features that are available for all roles including your own. When exploring all roles, the other actions work the same way, except for all roles shown. **NOTE:** You will only see roles that are set up to show in role explorer. For more information, see [Manage Profiles](admin-users-profiles-roles.md).  |
|**Report & Analysis**|This action Shows only those features that are categorized as reports and analysis features.|
|**Administration**|Shows only those features that are categorized as administration features.|



<!--
Choose the **Find** action at the top of the role explorer to quickly locate feature names that contain a certain term.

Choose the **Explore more roles** action at the top of the role explorer to get an overview of all business features that are available for all roles including your own.

> [!NOTE]
> Only Role Center actions for profiles where the **Show in Role Explorer** check box is selected will appear on the extended version of the role explorer (shown with the **Explore more roles** action). For more information, see [Manage Profiles](admin-users-profiles-roles.md).
-->

## Expand and collapse nodes on the role explorer

The actions that open pages are organized under nodes named after the features or application areas. Each node can be collapsed or expanded individually and you can collapse/expand all nodes together.

- To expand/collapse a node, choose the node. This applies to top-level nodes and sub nodes.
- To expand/collapse all top-level nodes on the page, choose the **Expand** or **Collapse** action in the top-right corner.
- To expand/collapse all top-levels node and all sub nodes under it, do one of the following steps:
  - Press the Ctrl+Shift keys while you choose the **Expand** or **Collapse** action in the top-right corner.
  - Choose **...** in the top-right corner, then choose the **Expand All** or **Collapse All** action.

## See Also
[Finding Pages and Information with Tell Me](ui-search.md)  
[Manage Profiles](admin-users-profiles-roles.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]