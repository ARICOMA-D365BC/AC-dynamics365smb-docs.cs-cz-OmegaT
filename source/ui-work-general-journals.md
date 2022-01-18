---
title: Working with General Journals to Post Directly to G/L
description: Learn about using journals to post financial transactions to general ledger accounts and other accounts, such as bank and vendor accounts. Use recurring journals to post accruals and allocate balances by dimension values.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: journals, recurring, accrual, renumber, bulk-post
ms.date: 04/01/2021
ms.author: edupont

---
# Working with General Journals

Most financial transactions are posted to the general ledger through dedicated business documents, such as purchase invoices and sales orders. But you can also process business activities such as purchasing, paying, using recurring journals to post accruals, or refunding employee expenses by posting journal lines in the various journals in [!INCLUDE[prod_short](includes/prod_short.md)].  

Most journals are based on the *General Journal*, and you can process all transactions on the **General Journal** page. For more information, see [Post Transactions Directly to the General Ledger](finance-how-post-transactions-directly.md).  

For example, you can use post employees' expenditure of own money on business-related expenses, for later reimbursement. For more information, see [Record and Reimburse Employees' Expenses](finance-how-record-reimburse-employee-expenses.md).

But in many cases, you will want to use the journals that are optimized for specific types of transactions, such as the **Payment Journal** for registering payments. For more information, see [Record Payments and Refunds in the Payment Journal](payables-how-post-payments-refunds.md).  

You use general journals to post financial transactions directly to general ledger accounts and other accounts, such as bank, customer, vendor, and employee accounts. Posting with a general journal always creates entries on general ledger accounts. This is true even when, for example, you post a journal line to a customer account, because an entry is posted to a general ledger receivables account through a posting group.

The information that you enter in a journal is temporary and can be changed while it is in the journal. When you post the journal, the information is transferred to entries on individual accounts, where it cannot be changed. You can, however, unapply posted entries, and you can post reversing or correcting entries. For more information, see [Reverse Journal Postings and Undo Receipts/Shipments](finance-how-reverse-journal-posting.md).

> [!NOTE]
> [!INCLUDE[journal-showhide-columns-inline-tip](includes/journal-showhide-columns-inline-tip.md)]  

## Using Journal Templates and Batches

There are several general journal templates. Each journal template is represented by a dedicated page with particular functions and the fields that are required to support those functions, such as the **Payment Reconciliation Journal** page to process bank payments and the **Payment Journal** page to pay your vendors or reimburse your employees. For more information, see [Make Payments](payables-make-payments.md) and [Reconcile Customer Payments with the Cash Receipt Journal or from Customer Ledger Entries](receivables-how-apply-sales-transactions-manually.md).

For each journal template, you can set up your own personal journal as a journal batch. For example, you can define your own journal batch for the payment journal that has your personal layout and settings. The following tip is an example of how to personalize a journal.

> [!TIP]  
> If you select the **Suggest Balancing Amount** check box on the line for your batch on the **General Journal Batches** page, then the **Amount** field on, for example, general journal lines for the same document number is automatically prefilled with the value that is required to balance the document. For more information, see [Letting [!INCLUDE[prod_short](includes/prod_short.md)] Suggest Values](ui-let-system-suggest-values.md).

> [!TIP]
> To add or remove fields in journals, use the **Personalizing** banner. For more information, see [Personalize Your Workspace](ui-personalization-user.md).

### Validating General Journal Batches
To help prevent delays when posting, you can turn on a background check that will notify you when there is a mistake in the financial journal you're working on that will prevent you from posting the journal. On the **General Journal Batch** page, you can choose **Background Error Check** to have [!INCLUDE[prod_short](includes/prod_short.md)] validate finance journals, such as general or payment journals, while you're working on them. 

When you enable the validation the **Journal Check** FactBox displays next to the journal lines and will show issues in the current line and the whole batch. Validation happens when you load a finance journal batch, and when you choose another journal line. The **Issues total** tile in the FactBox shows the total number of issues that [!INCLUDE[prod_short](includes/prod_short.md)] found, and you can choose it to open an overview the issues. 

You can use the **Show Lines with Issues** and **Show All Lines** actions to toggle between journal lines that have or don't have issues. The new **Journal Line Details** FactBox provides quick overview and access to data from journal lines, such as the G/L account, customer, or vendor, as well as to the posting setup for specific accounts.     

### Reversing Journals to Correct Mistakes
When working with journals that have many lines and something goes wrong, it's important to have an easy way to correct mistakes. The **Posted General Journal** page offers a couple of actions that can help.

* **Copy Selected Lines to Journal** - Copy only the lines that you select.
* **Copy G/L Register to Journal** - Copy all lines that belong to the same G/L register.

These actions let you create a copy of a general journal line or a batch, and then specify the following:

* The journal to copy the lines to
* Whether with opposite signs (a reversing journal)
* A different posting date or document number

To allow journals to be copied to posted general journals, on the **General Journal Templates** page, choose the **Copy to Posted Jnl. Lines** check box. After you allow people to copy posted general journals, if needed you can turn off copying for specific batches.

## Understanding Main Accounts and Balancing Accounts
If you have set up default balancing accounts for the journal batches on the **General Journals** page, the balancing account will be filled in automatically when you fill in the **Account No.** field. Otherwise, fill in both the **Account No.** field and the **Bal. Account No.** field manually. A positive amount in the **Amount** field is debited to the main account and credited to the balancing account. A negative amount is credited to the main account and debited to the balancing account.

> [!NOTE]  
> VAT is calculated separately for the main account and the balancing account, so they can use different VAT percentage rates.

## Working with Recurring Journals
A recurring journal is a general journal with specific fields for managing transactions that you post frequently with few or no changes, such as rent, subscriptions, electricity, and heat. Using these fields for recurring transactions, you can post both fixed and variable amounts. You can also specify automatic reversal entries for the day after the posting date. You can also use allocation keys to divide the recurring entries among various accounts. For more information, see [Allocating Recurring Journal Amounts to Several Accounts](#allocating-recurring-journal-amounts-to-several-accounts).

With a recurring journal, entries that will be posted regularly need to be typed in only once. That is, the accounts, dimensions and dimension values and so on that you enter will be remain in the journal after posting. If any adjustments are necessary, you can make them with each posting.

### Recurring Method field

This field determines how the amount on the journal line is treated after posting. For example, if you will use the same amount every time you post the line, you can let the amount remain. If you will use the same accounts and text on the line but the amount will vary every time you post, you can choose to delete the amount after posting.

| To | See |
| --- | --- |
|F Fixed|The amount on the journal line will remain after posting.|
|V Variable|The amount on the journal line will be deleted after posting.|
|B Balance|The posted amount on the account on the line will be allocated among the accounts specified for the line in the Gen. Jnl. Allocation table. The balance on the account will thus be set to zero. Remember to fill in the **Allocation %** field on the **Allocations** page. For more information, see [Allocating Recurring Journal Amounts to Several Accounts](#allocating-recurring-journal-amounts-to-several-accounts).|
|RF Reversing Fixed|The amount on the journal line will remain after posting, and a balancing entry will be posted on the next day.|
|RV Reversing Variable|The amount on the journal line will be deleted after posting, and a balancing entry will be posted on the next day.|
|RB Reversing Balance|The posted amount on the account on the line will be allocated among the accounts specified for the line on the **Allocations** page. The balance on the account will be set to zero, and a balancing entry is posted on the next day.|
|BD Balance by Dimension|The journal line allocates costs based on a G/L account's balance by dimension. You'll be prompted to set the dimension filters to be used to calculate the source G/L account's balance by dimension from which you want to allocate costs. Alternatively, choose the **Set Dimension Filters** action later.|
|RBD Reversing Balance by Dimension|The journal line allocates costs based on a G/L account's reversing balance by dimension. You'll be prompted to set the dimension filters to be used to calculate the source G/L account's balance by dimension from which you want to allocate costs. Alternatively, choose the **Set Dimension Filters** action later.|

> [!NOTE]  
> The VAT fields can be filled in on either the recurring journal line or on the allocation journal line but not on both. That is, they can be filled in on the **Allocations** page only if the corresponding lines in the recurring journal are not filled in.

### Recurring Frequency field
This field determines how often the entry on the journal line will be posted. It is a date formula field, and it must be filled in for recurring journal lines. For more information, see [Using Date Formulas](ui-enter-date-ranges.md#using-date-formulas).

#### Examples
If the journal line must be posted every month, enter "1M". After every posting, the date in the **Posting Date** field will be updated to the same date in the next month.

If you want to post an entry on the last day of every month, you can do one of the following:

- Post the first entry on the last day of a month by entering 1D+1M-1D (1 day + 1 month - 1 day). With this formula, the posting date is calculated correctly regardless of how many days there are in the month.

- Post the first entry on any arbitrary day of a month by entering 1M+CM. With this formula, the posting date will be after one full month + the remaining days of the current month.

### Expiration Date field
This field determines the date on which the line will be posted for the last time. The line will not be posted after this date.

The advantage of using the field is that the line will not be deleted from the journal immediately and you can always replace the present expiration date with a later one so that you can use the line further into the future.

If the field is blank, the line will be posted every time you post until it is deleted from the journal.

### Allocating Recurring Journal Amounts to Several Accounts

On the **Recurring General Journal** page, you can choose the **Allocations** action to see or manage how amounts on the recurring journal line are allocated to several accounts and dimensions. Note that an allocation functions as balancing account line to the recurring journal line.

Just as in a recurring journal, you need to enter an allocation only once. The allocation will remain in the allocation journal after posting, so you do not need to enter amounts and allocations every time you post the recurring journal line.

If the *recurring method* in the recurring journal is set to **Balance** or **Reversing Balance**, then any dimension value codes in the recurring journal are disregarded when the account is set to zero. So if you allocate a recurring line to various dimension values on the **Allocations** page, then only one reversing entry will be created. Therefore, if you allocate a recurring journal line that contains a dimension value code, then you must not enter the same code on the **Allocations** page. If you do, the dimension values will be incorrect.  

To allocate recurring journal amounts based on dimensions, set the **Recurring Method** field to **Balance by Dimension** or **Reversing Balance by Dimension** instead. If the recurring method in the recurring journal is set to **Balance by Dimension** or **Reversing Balance by Dimension**, then any dimension value codes in the recurring journal are considered when the account is set to zero. So if you allocate a recurring line to various dimension values on the **Allocations** page, then a number of reversing entries that matches the number of dimension value combinations that the balance is comprised of, are created. If you allocate account balance through the recurring journal that contains a dimension value code, remember to use **Balance by Dimension** or **Reversing Balance by Dimension** to make sure that the dimension values are correctly balanced or reversed from the source account.  

For example, your company has a couple of business units and a handful of departments that your controllers have set up as dimensions. To speed up the purchase invoice entry process, you decide to require the accounts payable clerks to enter only business unit dimensions. Since each business unit has specific allocation keys for the Department dimension, such as based on the number of employees, you can use the **BD Balance by Dimension** or **RBD Reversing Balance by Dimension** recurring methods to re-allocate expenses for each business unit to the right departments based on the allocation keys.  

> [!NOTE]
> Dimensions that you set on allocation lines are not automatically calculated, and you must specify which dimension values must be set on the allocation accounts. In case you want to preserve the link between the source account dimension and the allocation account dimension, we recommend that you use the [Cost Accounting](finance-about-cost-accounting.md) capabilities instead.

#### Example: Allocating Rent Payments to Different Departments
You pay rent every month, so you have entered the rent amount on the cash account on a recurring journal line. On the **Allocations** page, you can divide the expense among several departments (Department dimension) according to the number of square feet that each one occupies. The calculation is based on the allocation percentage on each line. You can enter various accounts on different allocation lines (if rent will also be divided among several accounts), or you can enter the same account but with various dimension value codes for the Department dimension on each line.

### Reversal Date Calculation
When using recurring general journals to post accruals at the end of a period, it's important to have full control over reversal entries. On the **Recurring General Journals** page, the **Reversal Date Calculation** field lets you control the date that reversal entries will be posted when reversal recurring methods are used.

#### Example
Accruals are usually posted with Fixed, Variable, or Balance recurring methods on the journal line. The posting date of the posted amount on the account on journal line is calculated using the recurring frequency. The posting date for the balancing entry is calculated using the **Reversal Date Calculation** field, as follows:

* If the field is blank, the balancing entry will be posted the next day.
* If the field contains a date formula (for example, **5D** for five days), the balancing entry will be posted with a posting date calculated using the reversal date calculation.

> [!NOTE]
> By default, the **Reversal Date Calculation** field is not available on the **Recurring General Journals** page. To use the field, you must add it by personalizing the page. For more information, see [Personalize Your Workspace](ui-personalization-user.md).

## Working with Standard Journals
When you have created journal lines which you know you are likely to create again later, you can save them as a standard journal before you post the journal. This functionality applies to item journals and general journals.

> [!NOTE]  
>   The following procedure refers to the item journal, but the information also applies to the general journal.

### To save a standard journal
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Journals**, and then choose the related link.
2. Enter one or more journal lines.
3. Select the journal lines that you want to reuse.
4. Choose the **Save as Standard Journal** action.
5. In the **Save as Standard Item Journal** request page, define a new or existing standard item journal that the lines should be saved in.

    If you have already created one or more standard item journals and you want to replace one of these with the new set of item journal lines, in the Code field, select the code you want.
6. Choose the **OK** button to verify that you want to overwrite the existing standard item journal and replace all its content.
7. Select the **Save Unit Amount** field if you want to save the values in the **Unit Amount** field of the standard item journal.
8. Select the **Save Quantity** field if you want application to save the values in the **Quantity** field.
9. Choose the **OK** button to save the standard item journal.

When you have finished saving the standard item journal, the Item Journal page is displayed so you can proceed to post it, knowing that it can easily be recreated next time you need to post the same or similar lines.

### To reuse a standard journal

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Journals**, and then choose the related link.
2. Choose the **Get Standard Journals** action.

    The Standard Item Journals page opens showing codes and descriptions for all existing standard item journals.
3. To review a standard item journal before you select it for reuse, choose the **Show Journal** action.

    Any changes you make in a standard item journal are implemented right away. They will be there next time you open or reuse the standard item journal in question. You should therefore be sure that the change is important enough to apply generally. Otherwise, make the specific change in the item journal after the standard item journal lines have been inserted. See step 4 below.
4. On the **Standard Item Journals** page, select the standard item journal you want to reuse, and then choose the **OK** button.

    Now the item journal is filled with the lines you saved as the standard item journal. If journal lines already existed in the item journal, the inserted lines will be placed under the existing journal lines.

    If you did not check the **Save Unit Amount** field when you used the **Save as Standard Item Journal** function job, then the **Unit Amount** field on lines that are inserted from the standard journal is automatically filled with the item's current value, copied from the **Unit Cost** field on the item card.

    > [!NOTE]  
    > If you selected the **Save Unit Amount** or **Save Quantity** fields, you should now make sure the inserted values are correct for this particular inventory adjustment before you post the item journal.

    If the inserted item journal lines contain saved unit amounts that you do not want to post, you can quickly adjust it to the current value of the item as follows.

5. Select the item journal lines you want to adjust, and then choose the **Recalculate Unit Amount** action. This will update the Unit Amount field with the current unit cost of the item.
6. Choose the **post** action.

## To renumber document numbers in journals

To make sure that you do not receive posting errors because of the document number order, you can use the **Renumber Document Numbers** function before you post a journal.

In all journals that are based on the general journal, the **Document No.** field is editable so that you can specify different document numbers for different journal lines or the same document number for related journal lines.

If the **No. Series** field on the journal batch is filled, then the posting function in general journals requires that the document number on individual or grouped journal lines be in sequential order. Just choose the **Renumber Document Numbers** action, and relevant **Document No.** fields are then updated. If related journal lines were grouped by document number before you used the function, they will remain grouped but may be assigned a different document number.  

This function also works on filtered views.

Any renumbering of document numbers will respect related applications, such as a payment application that has been made from the document on the journal line to a vendor account. Accordingly, the **Applies-to ID** and **Applies-to Doc. No.** fields on the affected ledger entries may be updated.

### To renumber documents in journals

The following procedure is based on the **General Journal** page, but applies to all other journals that are based on the general journal, such as the **Payment Journal** page.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Journals**, and then choose the related link.
2. When you are ready to post the journal, choose the **Renumber Document Numbers** action.

Values in the **Document No.** field are changed, where required, so that the document number on individual or grouped journal lines are in sequential order. After documents are renumbered, you can proceed to post the journal.

## See Related Training at [Microsoft Learn](/learn/paths/use-journals-dynamics-365-business-central/)

## See Also

[Post Transactions Directly to the General Ledger](finance-how-post-transactions-directly.md)  
[Reverse Journal Postings and Undo Receipts/Shipments](finance-how-reverse-journal-posting.md)  
[Allocate Costs and Income](year-allocate-costs-income.md)  
[Finance](finance.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Close Open Item Ledger Entries Resulting from Fixed Application in the Item Journal](finance-how-to-close-open-item-ledger-entries-resulting-from-fixed-application-in-the-item-journal.md)  
[Revalue Inventory in the Revaluation Journal](inventory-how-revalue-inventory.md)  
[Count, Adjust, and Reclassify Inventory Using Journals](inventory-how-count-adjust-reclassify.md)  
[Reconcile Customer Payments with the Cash Receipt Journal or from Customer Ledger Entries](receivables-how-apply-sales-transactions-manually.md)  
[Reconcile Vendor Payments with the Payment Journal or from Vendor Ledger Entries](payables-how-apply-purchase-transactions-manually.md)  
[Work with Intercompany Documents and Journals](intercompany-how-work-documents-journals.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]