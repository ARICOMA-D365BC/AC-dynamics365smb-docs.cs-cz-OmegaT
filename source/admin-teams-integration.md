---
title: Managing Microsoft Teams Integration with Business Central| Microsoft Docs
description: Manage Business Central integration with Microsoft Teams.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: Teams, MS Teams, Microsoft Teams, Skype, Link, Microsoft 365, collaborate, collaboration, teamwork
ms.date: 01/20/2021
ms.author: jswymer
---

# Managing Microsoft Teams Integration with [!INCLUDE [prod_short](includes/prod_short.md)]

[!INCLUDE [online_only](includes/online_only.md)]

This article provides an overview of what you can do as an administrator to control Microsoft Teams integration with [!INCLUDE [prod_short](includes/prod_short.md)].

## In Microsoft Teams

### Minimum requirements

This section describes the minimum requirements for the [!INCLUDE [prod_short](includes/prod_short.md)] app features to work in Teams.

- Required licenses

    This table gives you an overview of the licenses needed for the [!INCLUDE [prod_short](includes/prod_short.md)] app features to work in Teams.

    |What|Teams license|[!INCLUDE [prod_short](includes/prod_short.md)] license|
    |----|---|---|
    |Paste a link to a [!INCLUDE [prod_short](includes/prod_short.md)] record into a conversation, and send it as a card.|![check mark](media/check.png "check")|![check mark](media/check.png "check")|
    |View a card of a [!INCLUDE [prod_short](includes/prod_short.md)] record in a conversation.|![check mark](media/check.png "check")||
    |View more details of card for a [!INCLUDE [prod_short](includes/prod_short.md)] record in a conversation.|![check mark](media/check.png "check")|![check mark](media/check.png "check")|

- Allow URL previews

    **Allow URL previews** policy setting must be turned on. Otherwise, a card can't be generated for [!INCLUDE [prod_short](includes/prod_short.md)] links pasted into a Teams conversation. For more information about this setting, see [Manage messaging policies in Teams](/microsoftteams/messaging-policies-in-teams).

### Managing the [!INCLUDE [prod_short](includes/prod_short.md)] app (optional)

As a Teams administrator, you can manage all apps for your organization, including the [!INCLUDE [prod_short](includes/prod_short.md)] app. You can approve or install the [!INCLUDE [prod_short](includes/prod_short.md)] app for your organization, block user's from installing the app, and more.

For more information, see the following articles in the Microsoft Teams documentation:

- [Manage your apps in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/manage-apps)
- [Manage app setup policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-app-setup-policies)

## In [!INCLUDE [prod_short](includes/prod_short.md)]

### Minimum requirements

- [!INCLUDE [prod_short](includes/prod_short.md)] version:

    [!INCLUDE [prod_short](includes/prod_short.md)] 2020 release wave 2, update 17.3, or later. Teams integration is only supported for [!INCLUDE [prod_short](includes/prod_short.md)] online; not on-premises.

- Codeunit **2718 Page Summary Provider** is published as a web service:

    This codeunit is published as a web service by default. The codeunit is part of the [!INCLUDE [prod_short](includes/prod_short.md)] system application. It's used to get the field data for a [!INCLUDE [prod_short](includes/prod_short.md)] page added to a Teams conversation. For information about publishing web services, see [Publish a Web Service](across-how-publish-web-service.md).

- <a name="permissions"></a>User permissions:

    For the most part, the pages and data that users can view and edit in a Teams conversation is controlled by their permissions in [!INCLUDE [prod_short](includes/prod_short.md)].
    
    - To paste a [!INCLUDE [prod_short](includes/prod_short.md)] link into a Teams conversation and have it expand into a card, users must have at least read permission on the page and its data.
    - Once a card is submitted into a conversation, any user in that conversation can view that card without permission to [!INCLUDE [prod_short](includes/prod_short.md)].
    - To view more details for a card or open the record in [!INCLUDE [prod_short](includes/prod_short.md)], users must have read permission on the page and its data.
    - To change data, user's need modify permissions.
    
    For information about permissions, see [Assign Permissions to Users and Groups](ui-define-granular-permissions.md).

## Managing privacy and compliance 

Microsoft Teams provides extensive controls for compliance and management of sensitive or personally identifiable data&mdash;including data added to chats and channels by the [!INCLUDE [prod_short](includes/prod_short.md)] app.

### Understanding where [!INCLUDE [prod_short](includes/prod_short.md)] cards are stored 

After a card is sent to a chat, the card and the fields shown on the card are copied to Teams. This information is subject to the Teams policies for your organization, such as data retention policies. When displaying card details, none of the data in the details window is stored in Teams. The data remains stored in [!INCLUDE [prod_short](includes/prod_short.md)] and will only be retrieved by Teams when the user chooses to view the details. 

- To learn more about where Teams stores that data, see [Location of data in Microsoft Teams](/microsoftteams/location-of-data-in-teams).
- To learn more about retention policies in Teams, see [Retention policies in Microsoft Teams](/microsoftteams/retention-policies).

### Restricting sharing of cards 

You prevent specific users or groups from sending cards to chats or channels by setting up messaging policies that turn off the **URL Previews** setting. For more information about this setting, see [Manage messaging policies in Teams](/microsoftteams/messaging-policies-in-teams). 

You can also use information barriers to prevent individuals or groups from communicating with each other. To learn more, see [Information barriers in Microsoft Teams](/microsoftteams/information-barriers-in-teams).

Data loss prevention features in the Microsoft 365 Security & Compliance Center can't be applied specifically to cards. But they can be applied to the chat messages that contain the cards. To track upcoming advanced features that include enabling DLP for cards, see [https://www.microsoft.com/en-us/microsoft-365/roadmap?featureid=67093](https://www.microsoft.com/en-us/microsoft-365/roadmap?featureid=67093).

### Responding to data requests

You allow team members and team owners to delete messages that contain sensitive cards by setting up messaging policies, like: **Owners can delete sent messages** and **Users can delete sent messages**. For more information, see [Manage messaging policies in Teams](/microsoftteams/messaging-policies-in-teams).

Content search and eDiscovery compliance features in the Microsoft 365 Security & Compliance Center can't be applied specifically to cards. But they can be applied to the chat messages that contain cards. To track upcoming compliance features for cards, see [https://www.microsoft.com/microsoft-365/roadmap?featureid=68875](https://www.microsoft.com/microsoft-365/roadmap?featureid=68875).

Because card data in Teams is a copy of data in [!INCLUDE [prod_short](includes/prod_short.md)], you can also use [!INCLUDE [prod_short](includes/prod_short.md)] features to export a customer’s data if requested. For more information about privacy in [!INCLUDE [prod_short](includes/prod_short.md)], see [Privacy FAQ for Business Central Customers](/dynamics365/business-central/dev-itpro/security/privacyfaq).

## See Also
[[!INCLUDE [prod_short](includes/prod_short.md)] and Microsoft Teams Integration Overview](across-teams-overview.md)  
[Install the [!INCLUDE [prod_short](includes/prod_short.md)] App for Microsoft Teams](across-install-app-for-teams.md)  
[Teams FAQ](teams-faq.md)  
[Troubleshooting Teams](admin-teams-troubleshooting.md)  
[Developing for Teams Integration](/dynamics365/business-central/dev-itpro/developer/devenv-develop-for-teams)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]