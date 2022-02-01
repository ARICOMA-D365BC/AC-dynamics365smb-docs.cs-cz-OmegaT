---
title: The VAT Group Management Extension | Microsoft Docs
description: You can engage with other businesses to form a VAT group, and act as either a member or representative of the group when reporting VAT.
author: bholtorf
manager: annbe

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms. search.keywords: VAT, value added tax, report
ms.date: 04/01/2021
ms.author: bholtorf

---

# Rozšíření Správa skupin DPH

Můžete se připojit k jedné nebo více firmám ve vaší zemi a konsolidovat vykazování DPH pod jedním registračním číslem. Tento typ režimu se označuje jako *Skupina DPH*. Do skupiny se můžete zapojit jako člen nebo zástupce skupiny.

## Vytvoření Skupiny DPH
Členové skupiny DPH a zástupce skupiny mohou pomocí průvodce asistovaným nastavením **nastavení skupiny DPH ** definovat jejich zapojení do skupiny a vytvořit spojení mezi jejich [!INCLUDE[prod_short](includes/prod_short.md)] tenanty. Členové skupiny použijí toto připojení k podání přiznání k DPH zástupci skupiny. Zástupce podá DPH daňovým orgánům jménem skupiny pomocí jediného přiznání k DPH.

## Rozvržení skupin pro DPH
Komunikace probíhá od členů skupiny k zástupci. Zástupce skupiny zpřístupní rozhraní API, které členům umožňuje odeslat svá přiznání k DPH zástupci skupiny DPH.
[!INCLUDE[prod_short](includes/prod_short.md)] podporuje meziskupiové podávání přiznání k DPH pro společnosti používající [!INCLUDE[prod_short](includes/prod_short.md)] on-premises nebo online, případně jakoukoli kombinaci Nastavení komunikace závisí na rozvržení. Následující části popisují, jak nastavit různé rozvržení skupin.

V následujícím seznamu je doporučené pořadí kroků pro nastavení skupiny DPH:

1. Vytvořte nastavení ve službě Azure Active Directory. Další informace naleznete v tématu [Požadavky na ověřování](ui-extensions-vat-group.md#requirements-for-authentication).
2. Podělte se o technické informace, které členové skupiny DPH a zástupce potřebují k propojení svých [!INCLUDE[prod_short](includes/prod_short.md)] tenantů. Zástupce skupiny pro DPH obvykle tyto informace má, například název prostředí zástupce skupiny pro DPH, do kterého členové skupiny pro DPH budou DPH vracet.
3. Vytvořte uživatele v [!INCLUDE[prod_short](includes/prod_short.md)] zástupce skupiny pro DPH, který mohou členové skupiny pro DPH použít k ověření a připojení.
4. Run the **Set up VAT Group Management** assisted setup guide to connect the VAT group members.

The guide requires some information from the VAT group representative. For more information, see the [VAT Group Member Setup](#vat-group-member-setup) section. Make a note of the **Group Member ID** for each VAT group member. The representative needs these IDs to add the companies to the VAT group.
5. Set up the VAT Group Management extension in the VAT group representative's [!INCLUDE[prod_short](includes/prod_short.md)] by using the **Set up VAT Group Management** assisted setup guide.

> [!NOTE]
> To connect to the VAT group representative, group members need a user with access to the VAT group representative's [!INCLUDE[prod_short](includes/prod_short.md)]. The VAT group representative must create at least one user for this, however, for security reasons we recommended that you create a user for each VAT group member. Make sure to distribute the credentials for these users to VAT group members in a secure way.

## Understanding the VAT Group Management Setup

The VAT group representative exposes an API that VAT group members can use to connect to their [!INCLUDE[prod_short](includes/prod_short.md)] tenant and submit VAT returns. VAT group members will often use [!INCLUDE[prod_short](includes/prod_short.md)] in separate Azure Active Directory tenants. Therefore, more setup is needed to make a connection between the VAT group member and representative's [!INCLUDE[prod_short](includes/prod_short.md)].

VAT group members connect to the representative by calling a web service on the VAT group representative tenant. The caller must be authenticated using OAuth. When the VAT Group Management extension is set up, you will be asked to authenticate to the VAT group representative to get and save an access token. This access token is used when submitting VAT returns to the VAT group representative.

Authentication is handled by Azure Active Directory, so your setup must be made in the VAT group representative's Azure Active Directory to allow connections. An Azure Active Directory app registration must be configured with access to the VAT group representative's [!INCLUDE[prod_short](includes/prod_short.md)]. This is also true if the VAT group representative is using [!INCLUDE[prod_short](includes/prod_short.md)] on-premises. Additionally, you must configure Single Sign-On if the VAT group representative is using [!INCLUDE[prod_short](includes/prod_short.md)] on-premises.

> [!NOTE]
> For a limited time, authentication using a web service access key is also supported. For more information, see [Deprecated Features in 2021 release wave 1](/dynamics365/business-central/dev-itpro/upgrade/deprecated-features-w1#deprecated-features-in-2021-release-wave-1).

## Requirements for Authentication
When the VAT group representative is using [!INCLUDE[prod_short](includes/prod_short.md)] online or on-premises, VAT group members use Azure Active Directory to authenticate when they submit VAT returns to the VAT group representative. If the VAT group members are also using [!INCLUDE[prod_short](includes/prod_short.md)] online, the VAT group member can authenticate using the designated user credentials and the endpoint information. For more information, see [VAT Group Member Setup](ui-extensions-vat-group.md#vat-group-member-setup).

VAT group members who have [!INCLUDE[prod_short](includes/prod_short.md)] on-premises must set up an app registration in Azure Active Directory for the VAT group representative's [!INCLUDE[prod_short](includes/prod_short.md)] tenant. The app registration will enable the VAT group representative's [!INCLUDE[prod_short](includes/prod_short.md)] online to authenticate the group member. For more information, see [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).

When you create the app registration in Azure Active Directory, you must specify the following.

* In the **Authentication** section, add **Web** as a platform, and use the following **Redirect URL**: https://businesscentral.dynamics.com/OAuthLanding.htm.
* In the **Authentication** section, in the option to select **Supported account types**, select **Accounts in any organizational directory (Any Azure AD directory - Multitenant)**.
* In the **Certificates & secrets** section, create a new client secret and note the value. The VAT group members will need the secret when they set up the connection to the group representative.
* In the **API permissions** section, add permissions to [!INCLUDE[prod_short](includes/prod_short.md)]. Enable delegated access to **Financials.ReadWrite.All** and **user_impersonation**.
* In the **Overview** section, note the **Application (client) ID**. The VAT group members will need the ID when they set up the connection to the group representative.

## VAT Group Member Setup
Set up the VAT group member by starting the **Set up VAT Group Management** assisted setup guide.

> [!NOTE]
> Before you get started, contact the VAT group representative for the following information about their [!INCLUDE[prod_short](includes/prod_short.md)] tenant:
>
> * The API URL
> * The name of their company
> * Client ID
> * Client secret
> * Sign in credentials for the dedicated user

1. To define the company's VAT group role, choose **Member**, and then choose **Next**.
2. Copy the value of the **Group Member ID** field, and then share it with the VAT group representative so they can add your company as an approved member of the group.
3. Add the **API URL** from the VAT group representative. Typically, the URL is formatted as follows: `https://api.businesscentral.dynamics.com/v2.0/[TENANT-ID]/[ENVIRONMENTNAME]`. For example, `https://api.businesscentral.dynamics.com/v2.0/907869c3-b252-4aca-b9cb-17a15d25477b/UKRepresentative`.
4. Add the [!INCLUDE[prod_short](includes/prod_short.md)] company name of the VAT group representative, such as *CRONUS UK Ltd*.
5. Choose **Authentication Type**, choose **OAuth2**, and then choose **Next**.
6. In the **Client ID** field, enter the ID provided by the VAT group representative.
7. In the **Client Secret provided by the VAT Group representative** field, enter the secret provided by the VAT group representative.
8. In the **OAuth 2.0 Authority Endpoint** field, enter *https://login.microsoftonline.com/common/oauth2*.
9. In the **OAuth 2.0 Resource URL** field, enter *https://api.businesscentral.dynamics.com/*.
10. In the **OAuth 2.0 Redirect URL** field, enter *https://businesscentral.dynamics.com/OAuthLanding.htm*.
11. When you have specified the various fields, choose **Next**, and then enter the user credentials that were provided by the VAT group representative.
12. Choose the VAT report configuration that you use to report VAT to authorities in your country.

For example, in the United Kingdom, the VAT report configuration would be set up to report VAT to HMRC. The VAT Group Management extension copies this setup, but replaces the submission codeunit with one that supports submission to the VAT group representative rather than the tax authorities. The codeunit is provided by Microsoft. When done, choose **Next**.

## Using the VAT Group Management Features

VAT group members use the standard processes to prepare VAT returns. The only difference is to choose the **VATGROUP** report version, which submits the VAT return to the VAT group representative rather than the authorities. For more information, see [About the VAT Return report](finance-how-report-vat.md#about-the-vat-return-report).

The following sections describe the tasks that VAT group representatives must perform.

### VAT Group Submissions

The **VAT Group Submissions** page lists the VAT returns that members have submitted. The page serves as a draft location for the submissions until the VAT group representative includes them in a VAT return for the group. You can open the submissions to review the VAT for the individual boxes reported by the VAT group member.

### Creating a Group VAT Return

To report VAT on behalf of the group, on the **VAT Returns** page, create a VAT return for your company only. Afterward, include the most recent VAT submissions from VAT group members by choosing the **Include Group VAT** action.

When the VAT Group representative's VAT Return has been submitted to the authorities on behalf of the entire group, you will normally run the **Calculate and Post VAT Settlement** action. This action closes open VAT Entries and transfers amounts to the VAT Settlement account. Currently, this action does not take the group submissions into account. This means that only the VAT Entries of the VAT Group representative company will be posted. The VAT Group member submission amounts must be posted to the VAT settlement amount manually, so that the VAT Group representative's VAT Settlement account will reflect the liability of what was reported to authorities. This behavior will change in an upcoming update of [!INCLUDE[prod_short](includes/prod_short.md)], so the entire group VAT (the Total Amount on Report Lines on the VAT Return) will be settled.

> [!NOTE]
> VAT group members can correct submitted VAT returns as long as the group representative has not released the VAT return for the group. To make a correction, the VAT group member must create a new VAT return for the VAT return period and submit it to the VAT group representative. On the VAT group representative's side, the latest VAT return will be included on the **VAT Returns** page.

> [!IMPORTANT]
> The VAT group functionality is only supported in those markets where [!INCLUDE[prod_short](includes/prod_short.md)] uses a VAT framework that consists of VAT returns and VAT return periods. You cannot use VAT groups in other markets that have other implementations of local VAT reporting, such as Austria, Germany, Italy, Spain, and Switzerland.

## Viz také
[Work with VAT on Sales and Purchases](finance-work-with-vat.md)  
[Set Up Value-Added Tax](finance-setup-vat.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
