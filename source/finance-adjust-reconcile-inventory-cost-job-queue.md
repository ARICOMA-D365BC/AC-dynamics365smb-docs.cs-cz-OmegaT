---
title: Schedule Jobs for Adjusting & Reconciling Inventory Cost
description: Learn how you can use the job queue to move the tasks for adjusting inventory cost or reconciling it with the general ledger to the background. For example, if your company runs many tasks or processes many transactions.
author: AndreiPanko


ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.reviewer: edupont
ms.search.form: 461
ms.date: 09/23/2021
ms.author: andreipa

---
# Schedule Jobs for Adjusting and Reconciling Inventory Cost with the General Ledger

To optimize the experience, automatic cost adjustment and posting to the general ledger are turned on by default. However, as data accumulates over time, that might impact performance. To reduce the load on the application, it is often helpful to use job queue entries to move tasks to run in the background.

## Move the task of adjusting item costs to the background with the help of assisted setup

Creating the job queue entries can be tricky, even for an experienced consultant, so we have an assisted setup guide to make the process easier for adjusting item costs.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Setup**, and then choose the related link.  
2. On the **Inventory Setup** page, toggle the **Automatic Cost Posting** field, or specify **Never** in the **Automatic Cost Adjustment** field.  
3. In the notification that now displays at the top of the page, choose the **Schedule Job Queue Entry** link. This opens the **Schedule Cost Adjustment and Posting** assisted setup guide.  
4. Specify the task that you want to schedule.  

  > [!NOTE]
  > You cannot create a new job queue entry if a job queue entry for the specified task already exists.

5. Select the **View job queue entries when finished** field to review and adjust settings. For more information, see [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).  

## To create a job queue entry for adjusting and reconciling inventory cost manually

Alternatively, you can create job queue entries manually. The following procedure shows how to set the **Adjust Cost - Item Entries** batch job to automatically run daily, but the same steps apply to the **Post Inventory Cost to G/L** batch job.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Queue Entries**, and then choose the related link.  
2. Choose the **New** action.  
3. In the **Object Type to Run** field, choose *Report*.  
4. In the **Object ID to Run** field, choose *795*, **Adjust Cost - Item Entries**.  
5. In the **Next Run Date Formula** field, enter *1D*.
6. In the **Starting Time** field, enter *2 AM*.
7. Choose the **Set Status to Ready** action.

Now, inventory cost will be updated every night.  

To schedule a task for reconciling inventory with the general ledger, choose Codeunit 2846 **Post Inventory Cost to G/L**.

> [!TIP]
> To avoid locking, do not schedule tasks for the **Adjust Cost - Item Entries** batch job, the **Post Inventory Cost to G/L** codeunit, and tasks for posting sales or purchasing transactions at the same time. Also, make sure that they use same job queue category.

## See Also

[Adjust Item Costs](inventory-how-adjust-item-costs.md)  
[Reconcile Inventory Costs with the General Ledger](finance-how-to-post-inventory-costs-to-the-general-ledger.md)  
[Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md)  
[Finding Pages and Information with Tell Me](ui-search.md)  
[Work with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
