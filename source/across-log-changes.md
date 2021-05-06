---
title: Auditing changes| Microsoft Docs
description: You can activate a user log so that you have a history of any changes made to data in tracked tables. You can also track activities with certain types of activity logs.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: user log, user activity, tracking
ms.date: 04/01/2021
ms.author: edupont

---
# Auditing Changes in Business Central
A common challenge in many business management applications is avoiding unwanted changes in data. It could be anything from an incorrect customer telephone number to an incorrect posting to the general ledger. This topic describes the capabilities for finding out what changed, who changed it, and when the change was made.

## About the Change Log 
The change log lets you track all direct modifications a user makes to data in the database. You must specify each table and field that you want the system to log, and then you must activate the change log.  

Tracking changes can impact performance, which can cost you time, and increase the size of your database, which might cost you money. To reduce those costs, consider the following:
- Use caution when choosing the tables and operations.
- Do not add ledger entries and posted documents. Instead, prioritize system fields such as Created By and Created Date.
- Do not use the All Fields tracking type. Instead, choose Some Fields and track only the most important fields.

The change log is based on changes that are made to data in the tables that you track. On the **Change Log Entries** page, entries are chronologically ordered and show all changes that are made to the values in fields on the tables you specify.

> [!Important]
> Changes display in the **Change Log Entries** only after the user's session is restarted, which happens as follows:
<br />
> * The session expired and was refreshed.
> * The user selected another company or Role Center.
> * The user signed out and back in.

### Working with the Change Log
You activate and deactivate the change log on the **Change Log Setup** page. When a user activates or deactivates the change log, this activity is logged, so you can always see which user deactivated or reactivated the change log.

On the **Change Log Setup** page, if you choose the **Tables** action, you can specify which tables you want to track changes for, and which changes to track. [!INCLUDE[prod_short](includes/prod_short.md)] also tracks a number of system tables.

> [!NOTE]
> You can monitor specific fields for changes, such as fields that contain sensitive data, by setting up field monitoring. If you do, to avoid redundancy the table that contains the field will not be available for the change log setup. For more information, see [Monitoring Sensitive Fields](across-log-changes.md#monitoring-sensitive-fields).

After you have set up the change log, activated it, and made a change to data, you can view and filter the changes on the **Change Log Entries** page. If you want to delete entries, you can do that on the **Delete Change Log Entries** page, where you can set filters based on dates and time.  

## About Activity Logs
From some pages in [!INCLUDE [prod_short](includes/prod_short.md)], you can view an activity log that shows the status and any errors from files that you export from or import into [!INCLUDE [prod_short](includes/prod_short.md)].  

### Working with Activity Logs
The information is displayed in the **Activity Log** page according to the context that it is opened from. For example, you can open the page from the **Document Exchange Service Setup**, **Incoming Document**, **Posted Sales Invoice**, and **Posted Sales Credit Memo** pages. You can empty the list of log entries, or just clear the list of entries older than seven days.  

## Monitoring Sensitive Fields
Keeping sensitive data secure and private is a core concern for most businesses. To add a layer of security, you can monitor important fields and be notified by email when someone changes a value. For example, you might want to be notified if someone changes your company's IBAN number.

> [!NOTE]
> Sending notifications by email requires that you set up the email feature in [!INCLUDE[prod_short](includes/prod_short.md)]. For more information, see [Set Up Email](admin-how-setup-email.md).

### Setting Up Field Monitoring
You can use the **Monitor Field Change Setup** assisted setup guide to specify the fields that you want to monitor based on filter criteria, such as the data sensitivity classification for the fields. For more information, see [Classifying Data Sensitivity](admin-classifying-data-sensitivity.md). The guide also lets you specify the person who will receive an email notification when a change occurs, and the email account that will send the notification email. You must specify both the user notify and the account from which to send the notification. After you finish the guide, you can manage settings for field monitoring on the **Field Monitoring Setup** page. 

Over time, the list of entries on the **Monitored Fields Log Entries** page will grow. To reduce the number of entries you can create a retention policy that will delete entries after a specified period of time. For more information, see [Define Retention Policies](admin-data-retention-policies.md).

When you set up field monitoring, or change something in the setup, entries are created for your changes. You can specify whether to display entries related to the monitoring setup by showing or hiding them. 

You can manage settings for field monitoring, such as whether to send an email notification or just log the change, for each field on the **Monitored Fields Worksheet** page. The page is also where you can add or remove fields to monitor.

> [!NOTE]
> After you add one or more fields and start monitoring, you must sign out of [!INCLUDE[prod_short](includes/prod_short.md)] and sign in again to apply your settings.

### Working with Field Monitoring

Entries for all changed values for monitored fields are available on the **Monitored Fields Log Entries** page. For example, entries contain information such as the field for which the value was changed, the original and new values, and who made the change and when they did so. To further investigate a change, choose a value to open the page where it was made. To view a list of all entries, choose **Field Change Entries**.

### Viewing Field Monitoring Telemetry 

You can set up [!INCLUDE[prod_short](includes/prod_short.md)] to send field monitoring activity to an Application Insights resource in Microsoft Azure. Then, using Azure Monitor, you create reports and set up alerts on the gathered data. For more information, see the following articles in the [!INCLUDE[prod_short](includes/prod_short.md)] Developer and IT Pro help:

- [Monitoring and Analyzing Telemetry - Enabling Application Insights](/dynamics365/business-central/dev-itpro/administration/telemetry-overview#enable)
- [Analyzing Field Monitoring Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-field-monitoring-trace)

## Defining Retention Policies

You can create retention policies to delete unneeded data in logs after a period of time that you specify. For example, over time the number of entries in a log can build up. By cleaning up old entries you can make it easier to focus on more recent, and probably more relevant, entries. For more information, see [Define Retention Policies](admin-data-retention-policies.md).

## See Also
[Change Basic Settings](ui-change-basic-settings.md)  
[Sorting, Searching, and Filtering](ui-enter-criteria-filters.md)  
[Finding Pages and Information with Tell Me](ui-search.md)  
[Assign Permissions to Users and Groups](ui-define-granular-permissions.md)    
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Define Retention Policies](admin-data-retention-policies.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
