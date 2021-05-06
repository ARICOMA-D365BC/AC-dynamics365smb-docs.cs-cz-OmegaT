---
title: Create Business Contacts
description: Outlines the tasks to create contacts and define your business relationships.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: relationship, prospect
ms.date: 01/05/2021
ms.author: edupont

---
# Create Contacts
When you develop a business relationship to someone in another company, add them as a contact in [!INCLUDE[prod_short](includes/prod_short.md)]. Then, add any information about them, or their company, that can be useful for future communications. On the **Contact Card** page, you can create the following types of contacts:

* **Person** - Typically, this is when you've had direct contact with someone and have their contact details.
* **Company** - For example, if the contact is not an individual person but an entity, such as a contractor or a bank. 

The information that's relevant for each type of contact differs, so the fields and actions that are available are different. For example, you can only assign job responsibilities to a person, and an industry group to a company. 

You can change the value of the **Type** field later. Alternatively, use the fields on the **Inheritance** FastTab on the **Marketing Setup** page to specify the data to share between a person and their company. For more information, see [Setting Up Contacts](marketing-setup-contacts.md).

When a contact is converted to a customer, for example, the contact person or contact company becomes the name of the customer. The record for the contact is kept, and you can link the contact and the customer so that their data is synchronized going forward.

## To create a contact manually
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Contacts**, and then choose the related link.
2. Choose the **New** action.
3. In the **No.** field, enter a number for the contact.

    Alternatively, if you have set up a number series for contacts on the **Marketing Setup** page, you can press **Enter** to insert the next available contact number.  
5. Fill in the remaining fields as required. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## To create a contact from a customer, vendor, or bank account
If you have customers, vendors, and bank accounts that you want to create contact cards for, you can use the **Create Contacts from** batch jobs to create contacts from the existing data. When you create a contact this way, the contact information is afterwards synchronized with the related customer, vendor, or bank account information. For more information, see [Synchronizing Contacts with Customers, Vendors, and Bank Accounts](marketing-create-contact-companies.md#synchronizing-contacts-with-customers-vendors-employees-and-bank-accounts).

> [!NOTE]  
> Before you can create contacts based on existing data, you must specify a business relation code for customers, vendors, or bank accounts on the **Interactions** FastTab on the **Marketing Setup** page. For more information, see [Set up Contacts](marketing-setup-contacts.md).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter one of the following, depending what you want to create contacts from, and then choose the related link.
   * **Create Contacts from Customers**
   * **Create Contacts from Vendors**
   * **Create Contacts from Bank Accounts**
2. On the request page that opens, in the **Customer**, **Vendor**, or **Bank Account** section, set filters if you want to create contacts from specific customers, vendors, or bank accounts.
3. Choose the **OK** button to start creating contacts.

The next contact numbers in the number series are assigned to the new contacts. The business relations that are specified on the **Marketing Setup** page is assigned to the newly created contacts.

> [!TIP]  
> You can also do this the other way around, namely by creating a customer, vendor, or bank account from a contact. For more information, see [To create a contact as a customer, vendor, or bank account](marketing-create-contact-companies.md#to-create-a-customer-vendor-employee-or-bank-account-from-a-contact).

## To create a customer, vendor, employee, or bank account from a contact
If you have a customer, vendor, employee, or bank account for the company that you want to create a contact for, use the **Create as** action. When you create a contact this way, the contact information is afterwards synchronized with the related customer, vendor, employee, or bank account information. For more information, see [Synchronizing Contacts with Customers, Vendors, and Bank Accounts](marketing-create-contact-companies.md#synchronizing-contacts-with-customers-vendors-employees-and-bank-accounts).

> [!NOTE]  
> Before you can create customers, vendors, employees, or bank accounts from contacts, you must specify a business relation code on the **Marketing Setup** page on the **Interactions** FastTab. For more information, see [Setting up Contacts](marketing-setup-contacts.md).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Contacts**, and then choose the related link.
2. Select the contact you want to create as a customer, vendor, employee, or bank account.
3. Choose the **Create As** action, and then choose either **Customer**, **Vendor**, **Bank**, or **Employee**.
4. Choose the **OK** button.

The contact information is transferred from the contact card to a new customer, vendor, employee, or bank account card. You may want to add specific information to each of the cards, such as invoicing and payment details. For more information, see, for example, [Register New Customers](sales-how-register-new-customers.md).

## To link a contact to an existing customer, vendor, employee, or bank account
If you have a contact and either a customer, vendor, employee, or bank account for the same company, you can link the two entities to synchronize data.

1. Open the contact that you want to link.
2. Choose the **Link with existing** action, and then choose the **Customer**, **Vendor**, **Bank**, or **Employee** action.
3. On the page that opens, select the customer, vendor, employee, or bank account to link to.
4. In the **Current Master Fields** field, specify whose fields to prioritize in when there is conflicting information in fields common to the contact and customer, vendor, employee, or bank account. For example, if the salesperson code is different for the contact and customer, you can choose to keep the one on the contact card by selecting **Contact**.
5. Choose the **OK** button.

## To remove a link between a contact and an existing customer, vendor, employee, or bank account

If you have wrongly linked a contact and a customer, vendor, employee, or bank account, remove the link between the entities so that data no longer synchronizes.

1. Open the contact that has the wrong link.  
2. Choose the **Business Relations** action.  
3. On the page that opens, select the customer, vendor, employee, or bank account to remove the link from.  
4. Choose the **Delete** action.  

> [!NOTE]  
> Do not use the **Business Relations** window to change existing relations. Instead, remove the relation and use the **Link with existing** action. For more information, see the [To link a contact to an existing customer, vendor, or bank account](marketing-create-contact-companies.md#to-link-a-contact-to-an-existing-customer-vendor-employee-or-bank-account) section.

## Synchronizing Contacts with Customers, Vendors, Employees, and Bank Accounts
If some of your contacts are also customers, vendors, employees, or bank accounts, you can synchronize then with data from the contact and gain the following benefits:

* You only have to update information in one place. For example, if you modify the phone number on the contact, the phone number is automatically updated for the customer, vendor, employee, or bank account.
* If you have specified a number series for contacts, when you create a customer, vendor, employee, or bank account card, a contact is automatically created.
* You can create sales quotes and orders, and purchase quotes and orders, from the contact.
* You can record your interactions, such as printing orders, blanket orders, creating sales service orders, sending e-mails, and so on.
* If you delete a contact linked to a customer, vendor, employee, or bank account, only the contact is removed. The customer, vendor, employee, or bank account remains.
* If you delete a customer, vendor, employee, or bank account that is linked to a contact, the contact remains.

> [!NOTE]  
> Certain details, such as invoicing and posting details, are not available for contacts. When you create contacts as customers, vendors, employees, or bank accounts, you may want to add them manually.

There are three ways to enable data synchronization between contacts and customers, vendors, employees, or bank accounts:

* When you create contacts from customers, vendors, employees, or bank accounts. See [To create a contact from a customer, vendor, or bank account](marketing-create-contact-companies.md#to-create-a-contact-from-a-customer-vendor-or-bank-account).
* When you create customers, vendors, employees, or bank accounts from contacts. See [To create a customer, vendor, or bank account from a contact](marketing-create-contact-companies.md#to-create-a-customer-vendor-employee-or-bank-account-from-a-contact).
* When you link contacts with existing customers, vendors, employees, or bank accounts from the contact card. See [To link a contact to an existing customer, vendor, or bank account](marketing-create-contact-companies.md#to-link-a-contact-to-an-existing-customer-vendor-employee-or-bank-account).

## To view which customer, vendor, employee, or bank account a contact is related to
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Contacts**, and then choose the related link.
2. Select the line for a contact, choose the **Related Information** action, and then choose the **Customer/Vendor/Bank Acc/Employee** action.

## See Also
[Managing Contacts](marketing-contacts.md)  
[Setting Up Contacts](marketing-setup-contacts.md)  
[Working with Business Central](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]