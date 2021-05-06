---
title: Teams FAQ
description: Get answers for some typical questions about working with Teams and Business Central.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: Teams, MS Teams, Microsoft Teams, Skype, Link, Microsoft 365, collaborate, collaboration, teamwork, faq, errors
ms.date: 04/12/2021
ms.author: jswymer
---
# Teams FAQ

[!INCLUDE [online_only](includes/online_only.md)]

This article answers some of the questions you may have about working with Teams and [!INCLUDE [prod_short](includes/prod_short.md)].

## [General](#tab/general)

### How do I sign in to the [!INCLUDE [prod_short.md](includes/prod_short.md)] app in Teams?

After installing the app, you'll be asked to sign in the first time you use the app, when you paste a [!INCLUDE [prod_short.md](includes/prod_short.md)] link into Teams chat or choose the **Details** action on a card in Teams. Depending on your Teams client, you may have to enter your credentials that you use to access [!INCLUDE [prod_short.md](includes/prod_short.md)].

### How do I sign out of the [!INCLUDE [prod_short.md](includes/prod_short.md)] app in Teams?

To sign out of your current user identity in Teams used to connect to [!INCLUDE [prod_short.md](includes/prod_short.md)], go to any chat compose box, right-click the [!INCLUDE [prod_short.md](includes/prod_short.md)] icon underneath, then choose **Settings**. When the window appears, check your currently signed in identity and then choose **Sign out**.

### Does the app for Teams connect to [!INCLUDE [prod_short.md](includes/prod_short.md)] on premises? 

No. The [!INCLUDE [prod_short.md](includes/prod_short.md)] app for Teams only works with [!INCLUDE [prod_short.md](includes/prod_short.md)] online. There are no plans to support [!INCLUDE [prod_short.md](includes/prod_short.md)] deployment types&mdash;like on-premises, hybrid cloud, or private cloud&mdash;that Microsoft doesn't host or manage directly.

### Does the app work with multiple companies and environments? 

Yes. To search for contacts in a different company, go to [Settings](across-teams-settings.md). When the [!INCLUDE [prod_short.md](includes/prod_short.md)] app expands a link into a card, the link must contain the environment and company names for the app to match the record in the right company. You can paste links to any companies and environments you have access to within your organization and from the [!INCLUDE [prod_short.md](includes/prod_short.md)] account you used to sign in. Participants in the chat will see the card. But they can't view the card details unless they have permissions to the company or environment where that record is stored.

### In which countries or regions is the [!INCLUDE [prod_short.md](includes/prod_short.md)] app available? 

The [!INCLUDE [prod_short.md](includes/prod_short.md)] app for Teams isn't restricted by country or region. The app is available in all markets currently supported by the Teams marketplace. 

### Does the [!INCLUDE [prod_short.md](includes/prod_short.md)] app work with any localization of [!INCLUDE [prod_short.md](includes/prod_short.md)]? 

Yes. The app is intended to work with any localization of [!INCLUDE [prod_short.md](includes/prod_short.md)], whether that localization is offered directly from Microsoft or through a partner. For more information, see [Country/regional availability and supported languages](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations?toc=/dynamics365/business-central/toc.json).

### <a name="language"></a>Which languages does the [!INCLUDE [prod_short.md](includes/prod_short.md)] app support?

Two things determine the language used for cards and card details in Teams:

1. Your language in Teams, which you can see from your account settings in Teams. 
2. Your language in [!INCLUDE [prod_short.md](includes/prod_short.md)], which you can see the [!INCLUDE [prod_short.md](includes/prod_short.md)] Web client (see [Change Basic Setting - Language](ui-change-basic-settings.md#language)).

The following table explains how the experience differs for message authors and recipients, depending on language settings and availability of languages.

|Who|Card|Card details |
|-|----|--------------| 
|Message author |Displays in the language that's specified for you in Teams. If [!INCLUDE [prod_short.md](includes/prod_short.md)] doesn't offer that same language, the card is displayed in English. |Displayed in the language that's specified for you in [!INCLUDE [prod_short.md](includes/prod_short.md)].  which may include languages from language apps provided by partners. |
|Message recipient |Displays in the language of the message author. |Displays in the language that's specified for you in [!INCLUDE [prod_short.md](includes/prod_short.md)]. |

For the list of supported languages for [!INCLUDE [prod_short.md](includes/prod_short.md)], see [Supported languages](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations?toc=/dynamics365/business-central/toc.json#supported-languages).

### Does the [!INCLUDE [prod_short.md](includes/prod_short.md)] app work with industry solutions?

Yes. But only some features of the app work with [Embed apps](/dynamics365/business-central/dev-itpro/deployment/embed-app-overview):

- The app works with links based on the **\*.bc.dynamics.com** pattern that's typically used with Embed apps.
- Contact search isn't available for Embed apps that replace the base application from Microsoft.

### Where can I find Teams integration inside the [!INCLUDE [prod_short.md](includes/prod_short.md)] Web client? 

There's currently no embedding of Teams controls or presence of Teams features inside the [!INCLUDE [prod_short.md](includes/prod_short.md)] Web client or other clients.

### Does [!INCLUDE [prod_short.md](includes/prod_short.md)] work with the Teams mobile app?

Yes. The [!INCLUDE [prod_short.md](includes/prod_short.md)] app can be installed from the Teams desktop app or browser, or by an administrator for all users. Once installed, the [!INCLUDE [prod_short.md](includes/prod_short.md)] app is automatically available in Teams for iOS and Android. On mobile devices, you can only view cards sent by others, access details, or pop out the card to the full experience in the [!INCLUDE [prod_short.md](includes/prod_short.md)] mobile app. You can't paste links that expand into cards when composing messages or search for contacts. For minimum requirements for mobile, see [Minimum Requirements for Using Business Central](product-requirements.md).

### Is the [!INCLUDE [prod_short.md](includes/prod_short.md)] app for Teams the same as the [!INCLUDE [prod_short.md](includes/prod_short.md)] app for iOS and Android?

No. The app for Teams is an add-in to Microsoft Teams and exclusively designed for collaborative experiences that light up within Teams. On the other hand, the [!INCLUDE [prod_short.md](includes/prod_short.md)] mobile app delivers a rich experience for you to work with [!INCLUDE [prod_short.md](includes/prod_short.md)] data on your mobile devices.

Mobile users are encouraged to install both the mobile app and the app for Teams to get the most out of [!INCLUDE [prod_short.md](includes/prod_short.md)]. With both installed, you can choose the **Pop out** action on a card in Teams to open the card details in the [!INCLUDE [prod_short.md](includes/prod_short.md)] mobile app. For information about installing the [!INCLUDE [prod_short.md](includes/prod_short.md)] and Teams mobile apps, see:

- [Get Business Central on Your Mobile Device](install-mobile-app.md)
- [Get the Teams mobile app](https://support.microsoft.com/office/download-the-mobile-app-for-teams-5940ebdc-0082-4fb1-83c4-751edc23dcb5) on Microsoft Support

### Does the [!INCLUDE [prod_short.md](includes/prod_short.md)] app work in all Teams clients?

No. The [!INCLUDE [prod_short.md](includes/prod_short.md)] app for Teams isn't supported when installed as a package for macOS or Linux. On these platforms, you can access Teams using a supported browser instead.

For minimum requirements in [!INCLUDE [prod_short.md](includes/prod_short.md)], see [Minimum Requirements for Using Business Central](product-requirements.md#teams).

For information about the choice of Teams clients and how to install them, see [Get clients for Microsoft Teams](/microsoftteams/get-clients) in the Teams documentation.

### Which Teams client is best for [!INCLUDE [prod_short.md](includes/prod_short.md)]?

There are only minor differences and limitations between Teams clients that may affect your experience with the [!INCLUDE [prod_short.md](includes/prod_short.md)] app for Teams. When choosing a Teams client, consider:

- The camera and location can't be accessed from the details window in the Teams desktop app.
- Phone numbers can't be activated from the details window in Teams for iOS, Teams for Android, or Teams in the browser.
- Using Microsoft Edge with the Teams in the browser let's you easily work across multiple identities and accounts by signing in to Teams from different profiles. To learn about using profiles in Microsoft Edge, see [Sign in and create multiple profiles in Microsoft Edge](https://support.microsoft.com/office/sign-in-and-create-multiple-profiles-in-microsoft-edge-df94e622-2061-49ae-ad1d-6f0e43ce6435) on Microsoft Support.

### What is the best way for me to demonstrate [!INCLUDE [prod_short.md](includes/prod_short.md)] and Microsoft Teams to prospective customers?

If you're a reselling partner, you might want to have an environment that you can show prospects as part of pre-sales demonstrations. To avoid affecting Microsoft Teams in your organization, you can get a Microsoft 365 demo account at [https://aka.ms/CDX](https://aka.ms/CDX). This account gives you full control of an independent Azure organization that includes Microsoft Teams and [!INCLUDE [prod_short.md](includes/prod_short.md)]. For more information, see [Preparing Demonstration Environments of Dynamics 365 Business Central](/dynamics365/business-central/dev-itpro/administration/demo-environment).

### Does the [!INCLUDE [prod_short.md](includes/prod_short.md)] app for Teams cater for my customization and personalization?

The [!INCLUDE [prod_short.md](includes/prod_short.md)] app for Teams can display cards for links to customer pages and tables in [!INCLUDE [prod_short.md](includes/prod_short.md)], such as those pages and tables originating from your own custom extensions or from AppSource.

The fields shown on a card in Teams can also be affected by [!INCLUDE [prod_short.md](includes/prod_short.md)] customizations installed for your organization. Cards don't consider any role-specific customizations or user personalization. However, the card details window shows record details as you would see them in [!INCLUDE [prod_short.md](includes/prod_short.md)], including any extensions, role customizations, and user personalization.

When you search for contacts, the fields that are matched in the **Contacts** table and fields shown in the search results aren't affected by any customization or personalization.

### How do the permissions required by the app affect my privacy?

Before installing the [!INCLUDE [prod_short.md](includes/prod_short.md)] app for Teams, you can review the minimum permissions required for the app to function. By installing the app, you agree that the app has permission to receive messages and data that you provide it, and Teams has permission to store and process those messages.

Also, some [!INCLUDE [prod_short.md](includes/prod_short.md)] features require opening external links or access to your camera or geographic location. For example, suppose you wanted to capture a photo of a purchase invoice for processing. The [!INCLUDE [prod_short.md](includes/prod_short.md)] app doesn't use these capabilities without your consent and they're only used by specific features in the **Details** window. When you use one of these features for the first time, Teams will display a dialog box asking you to grant access to the required device capabilities.

- In Teams desktop, you review and adjust app permissions from the **Settings** window. Select your profile picture at the top of the app, select **Settings** > **Permissions**, then select the [!INCLUDE [prod_short.md](includes/prod_short.md)] app.

- For Teams in the browser and Teams for iOS or Android, you can review or adjust permissions from your browser or device settings.

> [!NOTE]
> Exactly which [!INCLUDE [prod_short.md](includes/prod_short.md)] features prompt you for permissions depends on the add-on apps and customizations applied to the [!INCLUDE [prod_short.md](includes/prod_short.md)] environment that you connect to.

### Where can I learn about my privacy? 

You can learn about how Microsoft handles your data in the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=2030602). 

Contact your administrator to learn how your organization handles the privacy of your data.

### How do I uninstall the [!INCLUDE [prod_short.md](includes/prod_short.md)] app for Teams?

To remove the app that you installed for yourself, go to any chat compose box, find the [!INCLUDE [prod_short.md](includes/prod_short.md)] icon underneath, right-click the icon and choose **Uninstall**.  

### Will Microsoft continue to improve the [!INCLUDE [prod_short.md](includes/prod_short.md)] app for Teams?

At Microsoft, we're constantly listening to feedback from our diverse user community and acting upon the top suggestions. To learn about what is next for the [!INCLUDE [prod_short.md](includes/prod_short.md)] app for Teams, see the [Dynamics 365 release plan](/dynamics365-release-plan/2021wave1/).

If you want to participate in improving the app for Teams, or have an idea that would help simplify your work or collaborative experiences in Teams, add an idea or vote for existing ideas at [https://aka.ms/BusinessCentralIdeas](https://aka.ms/BusinessCentralIdeas).

## [Searching for Contacts](#tab/contacts)

### Which tables does the app search in?

When searching for contacts from the [!INCLUDE [prod_short.md](includes/prod_short.md)] app for Teams, your search terms are matched against records in the **Contacts** table in [!INCLUDE [prod_short.md](includes/prod_short.md)]. 

### Which fields in the contacts table can I search?

As you type your search terms in the search box, the terms are matched against most fields in the **Contacts** table. The fields include, for example, the **No.**, **Name**, **Address** fields, **Phone No.** or **Mobile Phone No.**, and **Email**.  

### Do search results include companies and persons?

Yes. In [!INCLUDE [prod_short.md](includes/prod_short.md)], contacts can be of type **Company** or type **Person**, where one or more persons may be associated with a company. In the search results, companies and persons have different icons.

### Do contacts of any business relationship appear in the results?

Yes. Some contacts may represent customers or vendors, or both. Other contacts with no defined business relation typically represent prospective customers. Contacts with other business relations, including any custom relations you've configured in [!INCLUDE [prod_short.md](includes/prod_short.md)], will also be displayed in the search results.

### Can I look up contact details during meetings?

Yes. You can look up contact information, history of interaction, and related documents for your customer or vendor during a Teams meeting or call while the meeting is happening, without leaving Teams.

In fact, you can look up contact details from anywhere in Teams by using the command box. You can, for example, look up contact details from the Teams calendar to help you set up meetings.

### How do I view my last interactions with a contact?

The details window for a contact displays interaction log entries. The interaction log entries provide the history of interactions that your organization has had with the specific contact. The interactions may include emails you've exchanged, calls you've received, or documents you've sent.

For interactions to be displayed, [!INCLUDE [prod_short.md](includes/prod_short.md)] must be configured to track interactions. To learn more about logging interactions, see [Record Interactions With Contacts](marketing-interactions.md).

### How do I register a Teams call or meeting as an interaction?

From the details window for a contact, find the **Create Interaction** action, and choose from the incoming or outgoing calls as interaction templates. You can also create your own custom interaction templates specifically for use with Teams conversations.

### Can I call a contact from the [!INCLUDE [prod_short.md](includes/prod_short.md)] app for Teams?

[!INCLUDE [prod_short.md](includes/prod_short.md)] has limited integration to Teams calling capabilities. It isn't possible to instantly start a VOIP call from the contact card or contact details window. However, when you view the contact details in the Teams desktop app, you can select the phone number field to dial that number if Teams is set up as your default dialing app on your device. To dial landlines or mobile phone numbers using PSTN, the traditional phone system, Teams requires that you have the Microsoft 365 Business Voice app. To learn more, see [What is Microsoft 365 Business Voice?](/MicrosoftTeams/business-voice/whats-business-voice).

### How do I view recent documents for a customer or vendor?

[!INCLUDE [prod_short.md](includes/prod_short.md)] typically relates a contact with a customer or vendor record that in turn is related to business transaction records, such as sales quotes or purchase invoices. To view related documents for a contact, go to the details window for the contact, choose the **Business Relation** field value or use the actions to navigate to the associated customer or vendor. On the customer or vendor page, expand the FactBox pane to reveal statistics for various documents that you can drill down into. Your experience may differ based on your customizations and personalization.

### How do I search for contacts using special characters?

You can enter search criteria using almost any unicode characters. However, [!INCLUDE [prod_short.md](includes/prod_short.md)] reserves the following symbols for other uses: **=**, **.**, **\***, and **@**. Using these symbols in your search terms may not return the expected results. If you don't see the expected results, enclose the symbols in your search terms in single quotes, for example, **Contoso'='2**.

### How can I search contacts stored in a different company?

The [!INCLUDE [prod_short.md](includes/prod_short.md)] app for Teams can search for customers, vendors, and other contacts in one company at a time.  
To search for contacts stored in a different [!INCLUDE [prod_short.md](includes/prod_short.md)] company, open [Settings](across-teams-settings.md), then change the environment and company from there.

### Are [!INCLUDE [prod_short.md](includes/prod_short.md)] contacts different than the ones in the Teams contacts screen?

Yes. Contacts stored in [!INCLUDE [prod_short.md](includes/prod_short.md)] represent business contacts available to your organization. They're contacts with which you have an established and well-defined business relationship, or contacts that represent prospective customers. These contacts are typically external contacts. In comparison, the contacts shown in the Teams Calling contacts list are your own contacts. These contacts aren't necessarily shared with others in your organization, and they typically represent contacts internal to your organization.

### Does [!INCLUDE [prod_short.md](includes/prod_short.md)] synchronize contacts with Teams?

No. Contacts stored in [!INCLUDE [prod_short.md](includes/prod_short.md)] remain separate from your contacts stored in Teams.
There are currently no plans to synchronize the two lists together.

### What is the minimum version of [!INCLUDE [prod_short.md](includes/prod_short.md)] for contact search?

Contact search requires that you've installed the [!INCLUDE [prod_short.md](includes/prod_short.md)] app for Teams version 1.0.4 or later, and you're connecting to [!INCLUDE [prod_short.md](includes/prod_short.md)] environments of version 18 or later.

### Can I search from my mobile device?

Contact search isn't available from Teams for iOS and Teams for Android at this time.

### Which permissions do I need for contact search?

To search for contacts, you need object-level permission to the **Contacts** table within the [!INCLUDE [prod_short.md](includes/prod_short.md)] company being searched. To view the details window for a contact, you need at least read permission to the **Contact** page within the [!INCLUDE [prod_short.md](includes/prod_short.md)] company, and any other related objects.

### Can I use contact search if I'm a delegated admin?

Yes. You can also look up contacts and contact details if you have a delegated admin role in an organization.

### Is contact search affected by API limits?

Yes. Searching for contacts from Teams is based on [!INCLUDE [prod_short.md](includes/prod_short.md)] v2.0 APIs and subject to any API limits that manage usage. You can learn more about the limits at [Current API Limits](/dynamics-nav/api-reference/v2.0/dynamics-current-limits).

### Why does it sometimes ask me to set up the app?

After you sign in to the [!INCLUDE [prod_short.md](includes/prod_short.md)] app for Teams for the first time, the app will attempt to determine your preferred company in [!INCLUDE [prod_short.md](includes/prod_short.md)]. If the app can't determine the company, you might have to go to the **Settings** and choose the company you wish to search in. This situation happens, for example, if you have access to multiple companies across environments in your organization. In this case, you'll have to choose a company before you can start searching.  

The app may also ask you to visit the **Settings** if you don't have a [!INCLUDE [prod_short.md](includes/prod_short.md)] subscription, there are no [!INCLUDE [prod_short.md](includes/prod_short.md)] environments, or your account doesn't have a [!INCLUDE [prod_short.md](includes/prod_short.md)] license.

### I’d like to search for items or records from other tables. Can I do this from Teams?

Searching in other tables isn't possible at this time. The [!INCLUDE [prod_short.md](includes/prod_short.md)] app for Teams searches only in the [!INCLUDE [prod_short.md](includes/prod_short.md)] contacts list, which may include vendors, customers, and other contacts.

If you'd like to see the search capabilities evolve to include other tables, we encourage our community to add an idea or vote for existing ideas at https://aka.ms/BusinessCentralIdeas.

## [Working with cards](#tab/cards)

### Which types of links does the app support?

The [!INCLUDE [prod_short.md](includes/prod_short.md)] app for Teams reacts to most [!INCLUDE [prod_short.md](includes/prod_short.md)] Web client links. When the link refers to a single record on a page, the card will display fields for that record. The supported page types include: 

- Card pages, such as the Item card
- Document pages, such as the Sales Order document
- ListPlus pages that represent a single record composed of other records, such as a Bank Account Reconciliation statement
- Simple list pages where a record doesn't offer the ability to drill down into a separate details page, such as the Zip codes list

When pasting a link to the root Web client Url, such as https://businesscentral.dynamics.com, the card instead displays information to help new users get started with accessing [!INCLUDE [prod_short.md](includes/prod_short.md)].

### How do I delete a card I sent to a chat?

You can't delete a card that you've already sent to chat. But you can delete the entire message that the card is a part of.

As the message author, you can delete any messages you sent to chats with a person, group, or channel&mdash;unless your administrator has set up policies that prevent deleting messages. If you moderate a channel as a channel owner, your administrator may have also granted you permission to delete any messages in the channel, including those messages sent by other users.

Deleting a message that contains a card doesn't delete or affect any data in [!INCLUDE [prod_short.md](includes/prod_short.md)].

### Do cards always show up-to-date information?

No. The field values on a card in Teams, including any images, are based on the data available when that card was sent to the chat. [!INCLUDE [prod_short.md](includes/prod_short.md)] cards don't automatically refresh in Teams. 

### Will others see my card if they don’t have the [!INCLUDE [prod_short.md](includes/prod_short.md)] app for Teams? 

When you compose and send a message to chat that includes a card, all users will see the card&mdash;even if they haven't installed the [!INCLUDE [prod_short.md](includes/prod_short.md)] app for Teams.

### How do I find out which company a card in Teams belongs to?

If you work across [!INCLUDE [prod_short.md](includes/prod_short.md)] companies, talk to your administrator about enabling a company badge for each company. When enabled, this eye-catching hint appears in any details window inside Teams, and displays the company and environment that record belongs to. To learn how to set up company badge, see [To display a company badge for quick access to company information](ui-change-basic-settings.md#badge).

## [Working with card details](#tab/carddetails)

### Where is the save button in the details window in Teams?

[!INCLUDE [prod_short.md](includes/prod_short.md)] automatically saves changes you make to any field as soon as you leave the field. To leave a field, click/tap anywhere outside the field or use the Tab key to move to the next field. When data appears in a dialog within the details window, you may need to choose the **OK** button to have [!INCLUDE [prod_short.md](includes/prod_short.md)] save your changes.

### If I choose to view details for a card, will other users see my details window?

No. While everyone in the chat or meeting can view the card itself, the details window only appears for you on your device when you choose **Details**. Other users must choose **Details** if they would like to view the details window on their device.

### Can I start a Teams call from the details window in Teams?

Yes. If you're using the Teams desktop app, start a call by choosing the linked number in a phone number field, like the **Mobile Phone No.** field on the **Contact** card. Teams must be your designated dialing app.

To call local or international landlines and mobile phones, Teams requires that you have a Business Voice license for enterprise calling. Also, you must set up Teams as your call solution. To learn more, see [Plan your Teams voice solution](/microsoftteams/cloud-voice-landing-page) in the Teams documentation.

### Can I print documents from the details window in Teams?

Yes. You print reports and other documents using standard [!INCLUDE [prod_short.md](includes/prod_short.md)] printing functionality and any cloud-enabled printer configured in the **Printer Management** page in [!INCLUDE [prod_short.md](includes/prod_short.md)]. You can't print from Teams to local printers known to your client device, such as printers that you'd typically print to from your browser. For this reason, you can't print from the report preview window, but only from the main report request page, directly to your cloud printers.

For more information about setting up cloud printers, see [Set Up Printers](ui-specify-printer-selection-reports.md).

### Can I access the camera from the details window in Teams?

Yes. Any [!INCLUDE [prod_short.md](includes/prod_short.md)] features in the details window that use the camera are available on all Teams clients.

### <a name="location"></a>Can I access my location from the details window in Teams?

If you’re using functionality in [!INCLUDE [prod_short.md](includes/prod_short.md)] that accesses your current location coordinates, such as with maps, you must use Teams in the browser or the Teams mobile app. Location isn't available when using the Teams desktop app. 

## [Collaborating with guests ](#tab/collaborating)

### Can I share cards with users outside my organization?

Yes. When you compose and send a message that includes a card, all recipients in the chat will see the card&mdash;even if they're guests or external to your organization. Guests can also open the details window if they've been granted permissions to access that data in [!INCLUDE [prod_short.md](includes/prod_short.md)].

### Is the experience any different for users that are guests?

Yes. Inviting guest users from outside your organization to participate in chat or a channel gives them a similar, but not identical experience compared to users within your organization. When a guest receives a message that includes a card, they can view it. Guests can also open the details window if they have been granted permissions to access that data in [!INCLUDE [prod_short.md](includes/prod_short.md)] and assigned a [!INCLUDE [prod_short.md](includes/prod_short.md)] license within your organization. When a guest composes a message, links to their [!INCLUDE [prod_short.md](includes/prod_short.md)] or yours won't expand into cards.

To learn about other similarities and differences between guests and team members, see [Guest experience in Teams](/MicrosoftTeams/guest-experience) in the Teams documentation.

### How does a guest user install the [!INCLUDE [prod_short.md](includes/prod_short.md)] app? 

Guests don't have access to the app marketplace to install apps themselves. However, the app can be automatically installed for them based on your organization’s policies. Another way for a guest user to install the [!INCLUDE [prod_short.md](includes/prod_short.md)] app is when they receive a chat message that includes a [!INCLUDE [prod_short.md](includes/prod_short.md)] card. In this case, the user chooses the **Details** button or the menu on the card, then installs the [!INCLUDE [prod_short.md](includes/prod_short.md)] app for use with your organization. After installing the app, a user doesn't automatically receive any permissions to access data from your [!INCLUDE [prod_short.md](includes/prod_short.md)].

---

## See Also

[[!INCLUDE [prod_short](includes/prod_short.md)] and Microsoft Teams Integration Overview](across-teams-overview.md)  
[Install the [!INCLUDE [prod_short](includes/prod_short.md)] App for Microsoft Teams](across-install-app-for-teams.md)  
[Troubleshooting Teams](admin-teams-troubleshooting.md)  
[Developing for Teams Integration](/dynamics365/business-central/dev-itpro/developer/devenv-develop-for-teams)  

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]