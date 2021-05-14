---
title: Share contacts between Business Central and Outlook| Microsoft Docs
description: This service has deep integration with Microsoft 365 so you can share contacts between Outlook and Business Central.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: contacts, Microsoft 365
ms.date: 04/01/2021
ms.author: edupont

---
# Synchronizace kontaktů v Business Central s kontakty v Microsoft Outlook
You can see the same contacts in [!INCLUDE[prod_short](includes/prod_short.md)] as you see in Outlook if you set up contact synchronization. For example, if you are a sales person, you might do some of your work in Outlook and some of your work in [!INCLUDE[prod_short](includes/prod_short.md)]. Pokud jsou kontakty na obou místech stejné, je vaše práce jednodušší.

A dedicated folder in Outlook makes contacts easy to find, and you can set a filter to synchronize only the contacts from [!INCLUDE[prod_short](includes/prod_short.md)] that you want to see in Outlook. Jakmile je nastavena synchronizace kontaktů, můžete zahájit synchronizaci ručně nebo nastavit automatickou synchronizaci, která udrží kontakty synchronizované podle plánu.

## Nastavení synchronizace
You set up how you want to synchronize contacts with Outlook on the **Exchange Sync. Setup** page in [!INCLUDE[prod_short](includes/prod_short.md)]. As a prerequisite, your user profile in [!INCLUDE[prod_short](includes/prod_short.md)] must specify your Microsoft 365 email account. You can check this in the **Microsoft 365 Authentication** section of your user profile in the **Users** list.

Then, on the **Exchange Sync. Setup** page, you can validate that the connection to Exchange is working and then set up contact synchronization. Open the **Contact Sync. Setup** page and start the synchronization. Optionally, set a filter for which contacts to synchronize between [!INCLUDE[prod_short](includes/prod_short.md)] and Outlook. Můžete například nastavit filtr na jméno, typ, společnost nebo podobné. Můžete také změnit výchozí název složky, do které budou kontakty synchronizovány v aplikaci Outlook. The default name is *Business Central*.

Once this synchronization has been set up, any changes to that you make to the contact in either Outlook or in [!INCLUDE[prod_short](includes/prod_short.md)] is synchronized to the other.

Každý z vašich spolupracovníků může také nastavit vlastní synchronizaci serveru Exchange a nastavit vlastní filtr pro synchronizaci kontaktů.

## Synchronizace kontaktů
If you are used to working with contacts in [!INCLUDE[prod_short](includes/prod_short.md)], then you will find it easy to start the synchronization manually whenever it suits you from the **Contacts** list. Simply choose the **Sync with Microsoft 365** action, and then decide if you want to change the filter that you have set up. Když zvolíte tlačítko OK, synchronizace se spustí okamžitě a poslední změny se projeví u vašich kontaktů v aplikaci Outlook.

In the **Contacts** list, you can synchronize contacts in two ways:

* **Sync with Microsoft 365**

   This action synchronizes all changes from [!INCLUDE[prod_short](includes/prod_short.md)] to Microsoft 365 since the previous synchronization, based on the last modified date. Any new contacts from Microsoft 365 will be synchronized back to [!INCLUDE[prod_short](includes/prod_short.md)] as well. Toto je obvykle rychlejší než provedení úplné synchronizace.

* **Full Sync with Microsoft 365**

   Tato akce synchronizuje všechny kontakty v obou směrech bez ohledu na datum poslední synchronizace a datum poslední změny.

V obou případech jsou kontakty synchronizovány z aplikace Outlook, pouze pokud mají vyplněna povinná pole. The required fields to synchronize to Microsoft 365 are **Name**, **Email address** and they must be of type Person. [!INCLUDE[prod_short](includes/prod_short.md)] is the master of the contact information, so the [!INCLUDE[prod_short](includes/prod_short.md)] contact information will be saved in the event of duplicates.

In Outlook, the contacts from [!INCLUDE[prod_short](includes/prod_short.md)] are shown in a folder under **Other contacts** in the **People**  view. Pokud nejste obeznámeni s zobrazením osob v aplikaci Outlook, můžete se k ní dostat z možností navigace v levém dolním rohu aplikace Outlook.

## Viz také
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Finance](finance.md)  
[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Using contacts (People) in Outlook on the web](https://support.office.com/article/Using-contacts-People-in-Outlook-on-the-web-1e3438c7-26b2-420c-87de-3cea9d31b5cb?appver=OWB150)


[!INCLUDE[footer-include](includes/footer-banner.md)]