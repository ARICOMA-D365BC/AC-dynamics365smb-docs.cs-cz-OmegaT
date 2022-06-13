---
title: Set up email in Business Central (contains video)
description: Describes how to connect email accounts to Business Central so that you can send outbound messages without having to open another app.
author: brentholtorf
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: SMTP, email, Office 365, connector
ms.search.form: 1805, 9813, 9814, 1262, 1263
ms.date: 02/06/2022
ms.author: bholtorf

---

# Set Up Email
People in businesses send information and documents, such as sales and purchase orders and invoices, by email every day. Administrators can connect one or more email accounts to [!INCLUDE[prod_short](includes/prod_short.md)], letting you send documents without having to open an email app. You can compose each message individually with basic formatting tools, such as fonts, styles, colors, and so on, and add attachments of up to 100 MB. Additionally, report layouts enable administrators to include only the key information from documents. For more information, see [Send Documents by Email](ui-how-send-documents-email.md).

Email capabilities in [!INCLUDE[prod_short](includes/prod_short.md)] are for outbound messages only. You can't receive replies, that is, there's no "Inbox" page in [!INCLUDE[prod_short](includes/prod_short.md)].

> [!NOTE]
> You can use the email capabilities of [!INCLUDE[prod_short](includes/prod_short.md)] online only with Exchange Online. We don't support hybrid scenarios, such as connecting [!INCLUDE[prod_short](includes/prod_short.md)] online to an on-premises version of Exchange.
> 
> If you're using [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, before you can set up email you must create an app registration for [!INCLUDE[prod_short](includes/prod_short.md)] in the Azure Portal. The app registration will enable [!INCLUDE[prod_short](includes/prod_short.md)] to authorize and authenticate with your email provider. For more information, see [Setting Up Email for Business Central On-Premises](admin-how-setup-email.md#setting-up-email-for-business-central-on-premises). In [!INCLUDE[prod_short](includes/prod_short.md)] online, we handle this for you.

## Required Permissions
To set up email, you must have the **EMAIL SETUP** permission set. For more information, see [Assign Permissions to Users and Groups](ui-define-granular-permissions.md). 

## Adding Email Accounts
You add email accounts through extensions that enable accounts from different providers to connect to [!INCLUDE[prod_short](includes/prod_short.md)]. The standard extensions let you use accounts from Microsoft Exchange Online. However, other extensions that let you connect accounts from other providers, such as Gmail, might be available.

You can specify predefined business scenarios in which to use an email account to send emails. For example, you can specify that all users send sales documents from one account, and purchase documents from another. For more information, see [Assign Email Scenarios to Email Accounts](admin-how-setup-email.md#assign-email-scenarios-to-email-accounts).

The following table describes the email extensions that are available by default.

|Extension  |Description  |Examples of when to use  |
|---------|---------|---------|
|**Microsoft 365 Connector**|Everyone sends email from a shared mailbox in Exchange Online.|When all messages come from the same department, for example, your sales organization sends messages from a sales@cronus.com account. This option requires that you set up a shared mailbox in the Microsoft 365 admin center. For more information, see [Shared mailboxes](/Exchange/collaboration/shared-mailboxes/shared-mailboxes).|
|**Current User Connector**|Everyone sends email from the account they used to sign in to [!INCLUDE[prod_short](includes/prod_short.md)].|Allow communications from individual accounts.|
|**SMTP Connector**|Use SMTP protocol to send emails.|Allow communications through your SMTP mail server. |

> [!NOTE]
> The **Microsoft 365 Connector** and **Current User Connector** extensions use the accounts you set up for users in the Microsoft 365 admin center for your Microsoft 365 subscription. To send email using the extensions, users must have a valid license for Exchange Online. Additionally, these extensions require that the **Allow HttpClient Requests** setting is enabled. To check whether it is enabled for these extensions, go to the **Extension Management** page, choose the extension, and then choose the **Configure** option.

> External users, such as delegated admins and external accountants, cannot use these extensions to send email messages from [!INCLUDE[prod_short](includes/prod_short.md)].

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4JsUk]

## Using SMTP
If you want to use SMTP protocol to send emails from [!INCLUDE[prod_short](includes/prod_short.md)], you can use the SMTP Connector extension. When you set up an account that uses SMTP, the Sender Type is an important field. If you choose Specific User, emails will be sent using the name and other information from the account you're setting up. However, if you choose Current User, emails will be sent from the email account specified for each user's account. Current User is similar to the Send As feature. For more information, see [Use a Substitute Sender Address on Outbound Email Messages](admin-how-setup-email.md#use-a-substitute-sender-address-on-outbound-email-messages). 

> [!IMPORTANT]
> If you'e using [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, you can use the OAuth 2.0 for authentication. You must create an application registration in the Azure portal, and then run the **Set up Azure Active Directory** assisted setup guide in [!INCLUDE[prod_short](includes/prod_short.md)] to connect to Azure AD. For more information, see [Create an App Registration for Business Central in Azure Portal](admin-how-setup-email.md#create-an-app-registration-for-business-central-in-azure-portal).

## Add Email Accounts
The **Set Up Email** assisted setup guide can help you get started quickly with emails.

> [!NOTE]
> You must have a default email account, even if you add only one account. The default account will be used for all email scenarios that aren't assigned to an account. For more information, see [Assign Email Scenarios to Email Accounts](admin-how-setup-email.md#assign-email-scenarios-to-email-accounts).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Set Up Email Accounts**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] 


<!--
> [!NOTE]
> If you choose **Other (SMTP)** and are using an account that requires two-factor authentication, the password that you enter in the **Password** field must be the same that you use for your Microsoft 365 subscription, and it must be of type **App Password**. For more information, see [Manage app passwords for two-step verification](/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords). 

is this still true?-->
## Assign Email Scenarios to Email Accounts
Email scenarios are processes that involve sending a document. For example, a sales or purchase order or a notification, such as an invitation to an external accountant. Specific email accounts can be used for specific scenarios. For example, you can specify that all users always send sales documents from one account, purchase documents from another, and warehouse or production documents from a third account. You can assign, reassign, and remove scenarios whenever you want. A scenario can only be assigned to one email account at a time. The default email account will be used for all scenarios that aren't assigned to an account.
 
<!--
## To set up email
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **SMTP Email Setup**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]
    > If you are using an account that requires two-factor authentication, then the password that you enter in the **Password** field must be the same that you use for your Microsoft 365 subscription and it must be of type **App Password**. For more information, see [Manage app passwords for two-step verification](/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords).
3. Alternatively, choose the **Apply Microsoft 365 Server Settings** action to insert any information that is already defined for your Microsoft 365 subscription.
4. When all the fields are correctly filled in, choose the **Test Email Setup** action.
5. When the test succeeds, close the page.

-->

## Set Up View Policies
You can control the email messages that a user can see in the Email Outbox and Sent Emails pages.

On the **User Email View Policies**, choose a user, and then choose one of the following options in the **Email View Policy** field:

* **View own emails** - The user can view only their own email messages.
* **View all emails** - The user can view all email messages, including emails that were sent by other users.
* **View if access to all related records** - This view policy is used if no other policy is specified. A user can view email messages that other users sent if the user has access to the record that was sent and all of the related records. For example, User A sent a posted sales invoice to a customer. User B can see the email message if they have access to both the invoice and the customer.
* **View if access to any related records** - The user can view email messages that were sent by other people if the user has access to at least one record that is related to the record that was sent. For example, User A sent a posted sales invoice to a customer. User B can see the email message if they have access to either the invoice or the customer.

> [!NOTE]
>  If you leave the **User ID** field empty and then choose the Email View Policy action, the policy that you define applies to all users.

## Set Up Reusable Email Texts and Layouts
You can use reports to include key information from sales and purchase documents in texts for emails. This procedure describes how to set up the **Sales - Invoice** report for posted sales invoices, but the process is similar for other reports.

> [!NOTE]
> To use the layout to create content for email messages, you must use the Word file type for your layout.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Selections Sales**, and then choose the related link.
2. On the **Report Selection - Sales** page, in the **Usage** field, select **Invoice**.
3. On a new line, in the **Report ID** field, select, for example, standard report 1306.
4. Select the **Use for Email Body** check box.
5. Choose the **Email Body Layout Description** field, and then select a layout from the list.

    Report layouts define the style and the content of the text in the email. For example, the content might include texts such as a greeting or instructions that precede the document information. If your organization has many layouts, you can choose **Select from full list** to access all available report layouts.
6. To view or edit the layout that the email text is based on, select the layout on the **Custom Report Layouts** page, and then choose the **Update Layout** action.
7. If you want to let customers use a payment service, such as PayPal, you'll need to set up the service. Afterward, the PayPal information and link are inserted in the email text. For more information, see [Enable Customer Payments Through PayPal](sales-how-enable-payment-service-extensions.md).
8. Choose the **OK** button.

Now, when you choose, for example, the **Send** action on the **Posted Sales Invoice** page, the email body will contain the document information of report 1306 preceded by styled standard text according to the report layout that you selected in step 5.

## Use a Substitute Sender Address on Outbound Email Messages
If you're using the SMTP Connector extension, you can use the **Send As** or **Send on Behalf** capabilities from Microsoft Exchange to change the sender address on outbound messages. [!INCLUDE[prod_short](includes/prod_short.md)] will use the SMTP account to authenticate to Exchange, but will either replace the sender address with the one you specify, or amend it with "on behalf of."

When you set up an account and you want to use the Send As or Send on Behalf capabilities from Exchange, in the **Sender Type** field, choose **Specific User**.

Alternatively, you can choose **Current User** to allow people to send messages through the SMTP Connector. The message will appear to be sent from the email account specified in the Contact Email field on the User Card for the user they're signed in as. However, it will function similar to the Send As feature and will be sent from the account specified in the setup of the SMTP Connector.

The following are examples of how Send As and Send on Behalf are used in [!INCLUDE[prod_short](includes/prod_short.md)]:

 * You might want the purchase or sales orders that you send to vendors and customers to appear to comefrom a _noreply@yourcompanyname.com_ address.
 * When your workflow sends an approval request by email using the email address of the requestor.

> [!Note]
> You can only use one account to substitute sender addresses. That is, you cannot have one substitute address for purchasing processes, and another for sales processes.

<!--
### To set up the substitute sender address for all outbound email messages
1. In the **Exchange admin center** for your Microsoft 365 account, find the mailbox to use as the substitute address, and then copy or make a note of the address. If you need a new address, go to your Microsoft 365 admin center to create a new user and set up their mailbox.
2. In [!INCLUDE[prod_short](includes/prod_short.md)] choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **SMTP Email Setup**, and then choose the related link.
3. In the **Send As** field, enter the substitute address.
4. Copy or make a note of the address in the **User ID** field.
5. In the **Exchange admin center**, find the mailbox to use as the substitute address, and then enter the address from the **User ID** field in the **Send As** field. For more information, see [Use the EAC to assign permissions to individual mailboxes](/Exchange/recipients/mailbox-permissions?view=exchserver-2019&preserve-view=true#use-the-eac-to-assign-permissions-to-individual-mailboxes).

### To use the substitute address in approval workflows
1. In [!INCLUDE[prod_short](includes/prod_short.md)] choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **SMTP Email Setup**, and then choose the related link.
2. Copy or make a note of the address in the **User ID** field.
3. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Approval User Setup**, and then choose the related link.
4. In the **Exchange admin center**, find the mailboxes for each user listed in the **Approval User Setup** page, and in the **Send As** field enter the address from the **User ID** field of the **SMTP Email Setup** page in [!INCLUDE[prod_short](includes/prod_short.md)]. For more information, see [Manage permissions for recipients](/Exchange/recipients/mailbox-permissions?view=exchserver-2019&preserve-view=true).
5. In [!INCLUDE[prod_short](includes/prod_short.md)] choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **SMTP Email Setup**, and then choose the related link.
6. To enable substitution, turn on the **Allow Sender Substitution** toggle.

> [!Note]
> [!INCLUDE[prod_short](includes/prod_short.md)] will determine which address to display in the following order: <br><br> 1. The address specified in the **E-Mail** field on the **Approval User Setup** page for messages in a workflow. <br> 2. The address specified in the **Send As** field in the **SMTP Email Setup** page. <br> 3. The address specified in the **User ID** field in the **SMTP Email Setup** page. -->

## Set Up Document Sending Profiles
You can save time by setting up a preferred method of sending sales documents for each of your customers. You won't have to select a sending option, such as whether to send the document by email or as an electronic document, every time you send a document. For more information, see [Set Up Document Sending Profiles](sales-how-setup-document-send-profiles.md).

## Optional: Set Up Email Logging in Exchange Online
Get more out of the communications between salespeople and your existing or potential customers. You can track email exchanges, and then turn them into actionable opportunities. For more information, see [Track Email Message Exchanges Between Salespeople and Contacts](marketing-set-up-email-logging.md).  
<!--
[!INCLUDE[admin-setup-email-public-folder](includes/admin-setup-email-public-folder.md)]

Next, you connect [!INCLUDE[prod_short](includes/prod_short.md)] with Exchange Online. For more information, see [Track Email Message Exchanges Between Salespeople and Contacts](marketing-set-up-email-logging.md).  -->

## Setting Up Email for Business Central On-Premises 
[!INCLUDE[prod_short](includes/prod_short.md)] on-premises can integrate with services that are based on Microsoft Azure. For example, you can use Cortana Intelligence for smarter cash flow forecasts, Power BI to visualize your business, and Exchange Online for sending email. Integration with these services is based on an app registration in Azure Active Directory. The app registration provides authentication and authorization services for communications. To use the email capabilities in [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, you must register [!INCLUDE[prod_short](includes/prod_short.md)] as an app in the Azure portal, and then connect [!INCLUDE[prod_short](includes/prod_short.md)] to the app registration. The following sections describe how.

### Create an App Registration for Business Central in Azure portal
The steps to register [!INCLUDE[prod_short](includes/prod_short.md)] in Azure portal are described in [Register an application in Azure Active Directory](/dynamics365/business-central/dev-itpro/administration/register-app-azure#register-an-application-in-azure-active-directory). The settings that are specific to the email capabilities are the delegated permissions that you grant to your app registration. The following table lists the minimum permissions.

|API / Permission Name  |Type  |Description  |
|---------|---------|---------|
|Microsoft Graph / User.Read |Delegated|Sign in and read user profile.         |
|Microsoft Graph / Mail.ReadWrite |Delegated|Compose email messages.         |
|Microsoft Graph / Mail.Send|Delegated|Send email messages.         |
|Microsoft Graph / offline_access|Delegated|Maintain data access consent.|

If you're using the SMTP Connector and want to use OAuth 2.0 for authentication, the permissions are slightly different. The following table lists the permissions.

|API / Permission Name  |Type  |Description  |
|---------|---------|---------|
|Microsoft Graph / offline_access|Delegated|Maintain data access consent.|
|Microsoft Graph / openid|Delegated|Sign users in.|
|Microsoft Graph / User.Read |Delegated|Sign in and read user profile.         |
|Microsoft Graph / SMTP.Send|Delegated|Send emails from mailboxes using SMTP AUTH.         |
|Office 365 Exchange Online / User.Read |Delegated|Sign in and read user profile.         |

When you create your app registration, note the following information. You'll need it to connect [!INCLUDE[prod_short](includes/prod_short.md)] to your app registration.
 
* Application (client) ID 
* Redirect URI (optional)
* Client secret

For general guidelines for registering an app, see [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app). 

> [!NOTE]
If you have trouble using the SMTP protocol to send email after you connect [!INCLUDE[prod_short](includes/prod_short.md)] to your app registration, it might be because SMTP AUTH is not enabled for your tenant. We recommend that you use the Microsoft 365 and Current User email connectors instead, because they use Microsoft Graph Mail APIs. However, if you must use SMTP protocol you can enable SMTP AUTH. For more information, see [Enable or disable authenticated client SMTP submission (SMTP AUTH) in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission#disable-smtp-auth-in-your-organization).

### Connect [!INCLUDE[prod_short](includes/prod_short.md)] to Your App Registration
After you register your application in Azure portal, in [!INCLUDE[prod_short](includes/prod_short.md)], use the **Email Application AAD Registration** assisted setup guide to connect [!INCLUDE[prod_short](includes/prod_short.md)] to it.

1. In [!INCLUDE[prod_short](includes/prod_short.md)], choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Email Application AAD Registration**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!TIP]
> Alternatively, if you are connecting for the first time, you can run the **Set up email** assisted setup guide. The guide will require the information for connecting to your app registration. <!--Need to verify this too. Ask John to clear the aad settings, delete the email accounts, and then run the guide.-->

<!--

1. In [!INCLUDE[prod_short](includes/prod_short.md)], start the **Email Application AAD Registration** assisted setup guide.
2. On the first page of the guide, copy the value in the **Redirect URL** field.
3. In Azure Active Directory, search for **App registrations**, and then open the **App registrations** page.
4. Choose **New registration**.
5. In the **Name** field, enter a name for your app.
6. Under **Supported account types**, choose either the **Accounts in any organizational directory (Any Azure AD Directory - Multitenant)** or **Accounts in any organizational directory (Any Azure AD Directory - Multitenant) and personal Microsoft accounts (/e.g. Skype, Xbox)** options, depending on your needs. If you're unsure, choose **Help me choose** for more information.
7. Under **Redirect URI (optional)**, choose **Web**, paste the URL you copied from the **Redirect URL** field in the assisted setup guide in Business Central, and then choose **Register**.
8. On the navigation pane, choose **Overview**, and then copy the value in the **Application (client) ID** field.
9. In [!INCLUDE[prod_short](includes/prod_short.md)], in the assisted setup guide, paste the ID in **Client ID** field.
10. In Azure Active Directory, on the navigation pane, choose **API permissions**, and then choose **Add a permission**.
11. On the **Request API permissions** pane, on the **Microsoft APIs** tab, choose **Microsoft Graph**.  
12. Choose **Delegated permissions**, and then in the **Select permissions** field, search for **Mail.ReadWrite**, **Mail.Send**, and **offline_access**. Choose those permissions, and then choose **Add permissions**.
13. On the navigation pane, choose **Certificates & secrets**.
14. Under **Client secrets**, choose **New client secret**.
15. Under **Add a client secret**, enter a description of the client, specify how long you want your secret to be available, and then choose **Add**.
16. When the secret is generated, copy it. 
17. In [!INCLUDE[prod_short](includes/prod_short.md)], in the assisted setup guide paste the secret in the **Client Secret field**.
18. The **Verify Registration** button becomes available. 

-->

## See Related Training at [Microsoft Learn](/learn/modules/set-up-email/)

## See Also

[Shared mailboxes in Exchange Online](/exchange/collaboration-exo/shared-mailboxes)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Setting Up [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Customizing [!INCLUDE[prod_short](includes/prod_short.md)] Using Extensions](ui-extensions.md)  
[Use [!INCLUDE[prod_short](includes/prod_short.md)] as Your Business Inbox in Outlook](admin-outlook.md)  
[Getting [!INCLUDE[prod_short](includes/prod_short.md)] on My Mobile Device](install-mobile-app.md)
[Getting [!INCLUDE[prod_short](includes/prod_short.md)] on My Mobile Device](install-mobile-app.md)
[Analyzing Email Telemetry (administration content)](/dynamics365/business-central/dev-itpro/administration/telemetry-email-trace)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
