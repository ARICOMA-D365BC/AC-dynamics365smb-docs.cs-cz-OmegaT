---
title: Troubleshooting Microsoft Teams Integration
description: Learn about what you can do as an administrator to control Microsoft Teams integration.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: Teams, MS Teams, Microsoft Teams, Skype, Link, Microsoft 365, collaborate, collaboration, teamwork, troubleshooting, errors
ms.date: 04/12/2021
ms.author: jswymer
---

# Troubleshooting Microsoft Teams Integration with [!INCLUDE [prod_short](includes/prod_short.md)]

[!INCLUDE [online_only](includes/online_only.md)]

This article provides information on how to identify and fix problems you may experience when using Microsoft Teams with [!INCLUDE [prod_short](includes/prod_short.md)], as a typical user or administrator.

## The sign-in link doesn't work

If you try to sign in to the [!INCLUDE [prod_short.md](includes/prod_short.md)] app for Teams immediately after installing the app, and the sign-in link doesn't react, it may be because the app hasn't fully completed installation. To try to fix the issue, sign out of your Teams client and then sign in again.

## The Settings page is empty

You must first sign in to reach your settings. To sign into the app, either paste a link to a [!INCLUDE [prod_short.md](includes/prod_short.md)] record, or try to search for contacts. Both of these actions will lead you through a sign-up experience, after which you can use the **Settings** page.

## I changed company but it didn't seem to work

After you change the company on the **Settings** page, you might notice that the command box drop-down indicates you're still searching the previous company. This issue happens when you open the **Settings** page directly from the command box. In this case, the company was successfully changed, and you'll in fact search the company you switched to. The problem is that the command box drop-down just hasn't been updated yet. For the drop-down accurately reflect the company you'll search in, close or unpin [!INCLUDE [prod_short.md](includes/prod_short.md)] from the command box, and then open the app again.


<!--When you change company from the **Settings** page that you reach from the command box, returning to the command box drop-down continues to show the previous company even though the company was successfully changed. For the drop-down accurately reflect the company you'll search in, you must close or unpin [!INCLUDE [prod_short.md](includes/prod_short.md)] from the command box and then find it again.-->

## "Something went wrong" error when searching for contacts

You may experience this error when you search in a company that hasn't been initialized or is in an unresponsive state. For example, you can't search in a new trial company that hasn't yet accepted the terms of use. To resolve this issue, try to sign in to the [!INCLUDE [prod_short.md](includes/prod_short.md)] Web client, and act on or dismiss any initial dialogs that appear.

## "Cannot find the contact/contact summary API" error when searching for contacts

This problem can be caused by customizations or industry solutions that affect or modify [!INCLUDE [prod_short.md](includes/prod_short.md)], or they don't provide a contact or contact summary API. If the problem continues, contact your administrator or supporting partner.

## None of my links expand into a card 

If you're experiencing this problem, here are a few things to try:

1. First, make sure that the [!INCLUDE [prod_short](includes/prod_short.md)] app for Teams is installed.

    To check, sign in to the Teams desktop app or Teams in the browser. Then, on the left side, select **Apps**, and search for **[!INCLUDE [prod_short](includes/prod_short.md)]**. When you find the **[!INCLUDE [prod_short](includes/prod_short.md)]** app, select it to open the app details page. If the **Add for me** button is shown, then the [!INCLUDE [prod_short](includes/prod_short.md)] app isn't installed. For more information about how to install the app, see [Install the [!INCLUDE [prod_short](includes/prod_short.md)] App for Microsoft Teams](across-install-app-for-teams.md).

    > [!NOTE]
    > Guest users can't immediately install apps. For more information about guest users, see our FAQ about collaborating with guests. 

2. Next, check that you've signed in with the correct identity.

    In Teams, go to any chat, and under the message compose box, right-click the [!INCLUDE [prod_short](includes/prod_short.md)] icon, then choose **Settings**. When the window appears, check whether the user it says that you're connected as matches what you use to connect to [!INCLUDE [prod_short](includes/prod_short.md)].

3. Make sure codeunit 2718 **Page Summary Provider** is published as a web service.

    Teams connects to [!INCLUDE [prod_short](includes/prod_short.md)] using an endpoint to this codeunit on the [!INCLUDE [prod_short](includes/prod_short.md)] service. For information about publishing web services, see [Publish a Web Service](across-how-publish-web-service.md).

4. Your organization may also restrict you from pasting links that expand into cards. Contact your administrator to understand the Teams organizational policies that may apply to you.

## My link sometimes doesn’t expand into a card 

A link won't expand into a card in the following situations:

- The link targets a page that (at a technical level) isn't connected to a source table in [!INCLUDE [prod_short](includes/prod_short.md)]. You can check whether a page has a source table by using the page inspection pane in the Web client in [!INCLUDE [prod_short](includes/prod_short.md)]. For more information about page inspection, see [Inspecting Pages](across-inspect-page.md).
- Teams doesn't support link previews in some of its features. For example, when you pop out a chat, or you're a guest to another organization.
- Teams silently abandons trying to display the card after 15 seconds, for example, because of network issues.
- Teams may not expand the link if you've already pasted a link into the same message compose box and deleted the card.

The link must also contain all the necessary information to locate the record and display the corresponding card. This information includes:

- The environment name, by including it in the URL path. If you don't specify the environment name, Teams assumes you're attempting to reach the environment named "Production".
- The company name, by using the *company=* parameter
- The page identifier, by using the *page=* parameter
- The bookmark to the record, by using the *bookmark=* parameter

For example:

`https://businesscentral.dynamics.com/?environmentname=Production&company=CRONUS%20USA%2C%20Inc.&page=21&dc=0&bookmark=21%3bEgAAAAJ7BTEAMAAwADAAMA%3d%3d`

For technical details about [!INCLUDE [prod_short](includes/prod_short.md)] URLs, see [Web Client URL](/dynamics365/business-central/dev-itpro/developer/devenv-web-client-urls) in the [!INCLUDE [prod_short](includes/prod_short.md)] Developer and IT Pro Help.

## The details window opens, but shows an error before details are shown

This problem can be caused by a couple things: lack of permissions in [!INCLUDE [prod_short](includes/prod_short.md)] or browser settings (when using Teams in the browser).

1. Verify your permissions in [!INCLUDE [prod_short](includes/prod_short.md)].

    To view details for a card, [!INCLUDE [prod_short](includes/prod_short.md)] checks your license and permissions to view that specific record and page in the specific company and environment. If you aren't authorized for any of these things, standard [!INCLUDE [prod_short](includes/prod_short.md)] error messages about permissions appear in the details window. 

    For more information about permissions, see [Assign Permissions to Users and Groups](ui-define-granular-permissions.md)

2. Check your browser settings if using Teams in the browser.

    - Your browser's pop-up blocker must be either turned off or set to allow pop-ups from the *businesscentral.dynamics.com* or *bc.dynamics.com* domains. For information about allowing pop-ups for [!INCLUDE [prod_short](includes/prod_short.md)], see [Setting Up Your Browser](across-browser-settings.md#popup).
    - Your browser must have access to local browser storage for cookies and preferences as you work.
    - Avoid using guest or private browsing unless necessary, because they discard or block certain content in some browsers.

    For more information about minimum browser requirements, see [Minimum Requirements for Using [!INCLUDE [prod_short](includes/prod_short.md)]](product-requirements.md#browsers) 

## I'm having problems with the camera or location in Teams

When using [!INCLUDE [prod_short](includes/prod_short.md)] features in the details window that require access to your location or device camera, you must first give your consent for Teams to access these device capabilities.  

- For Teams in the browser, make sure that your browser settings allow access to camera and location for https://teams.microsoft.com. 

- For Teams for iOS or Android, make sure that your device settings allow access to camera and location for the Teams mobile app. 

For help about changing these settings, see [My camera isn't working in Teams](https://support.microsoft.com/office/my-camera-isn-t-working-in-teams-9581983b-c6f9-40e3-b0d8-122857972ade?ns=msftteams&version=16&ui=en-us&rs=en-us&ad=us) on Microsoft Support.

The [!INCLUDE [prod_short](includes/prod_short.md)] app doesn't support location in the Teams desktop app. For more information about location, see the [Teams FAQ](teams-faq.md#location).

Some browsers, such as the new Microsoft Edge, allow you to choose which device camera to use when your device supports multiple cameras. 

## Teams displays mixed languages for my cards and card details

For cards and card details to display consistently in the same language in Teams, the language of your Teams client and the language you use in [!INCLUDE [prod_short](includes/prod_short.md)] Web client must match.

- To learn about changing the language in Teams, see [Change settings in Teams](https://support.microsoft.com/en-us/office/change-settings-in-teams-b506e8f1-1a96-4cf1-8c6b-b6ed4f424bc7) on Microsoft Support. 

- To learn about changing the language in [!INCLUDE [prod_short](includes/prod_short.md)], see [Change Basic Settings - Language](ui-change-basic-settings.md#language).

For more information on how languages work between Teams and [!INCLUDE [prod_short](includes/prod_short.md)], see [Teams FAQ](teams-faq.md#language).

## I edited a field in the details window, but my change wasn't saved

Changes you make to a field in the details windows are automatically saved when you leave the field. Before you close the window after changing a field, be sure to press the Tab key or click/tap outside the field.

## A new tile appeared in the App Launcher. How do I remove it?

When you view your apps on the Office 365 home page (https://home.office.com) or in the app launcher, a new tile named "Business Central Teams Integration Service Connector" will appear after installing the [!INCLUDE [prod_short](includes/prod_short.md)] app for Teams. This tile provides no value in itself and can be safely hidden.

As an administrator, who has Azure Active Directory admin permissions, you can hide the tile by doing the following steps:

1. Sign in to the [Azure Active Directory admin center](https://aad.portal.azure.com/).
2. Select **Enterprise apps**, then select **Business Central Teams Integration Service Connector**.
3. Select **Properties**, then set the **Visible To Users** switch to **No**.
4. Select **Save**.

> [!NOTE]
> It will be a while before this change takes effect.


## See Also

[[!INCLUDE [prod_short](includes/prod_short.md)] and Microsoft Teams Integration Overview](across-teams-overview.md)  
[Install the [!INCLUDE [prod_short](includes/prod_short.md)] App for Microsoft Teams](across-install-app-for-teams.md)  
[Teams FAQ](teams-faq.md)  
[Developing for Teams Integration](/dynamics365/business-central/dev-itpro/developer/devenv-develop-for-teams)  

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]