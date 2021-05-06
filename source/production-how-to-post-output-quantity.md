---
    title: Batch Post Production Output and Run Times
    description: The output quantity represents the work progress in the form of the finished quantity and used capacity of work or machine center.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2021
    ms.author: edupont

---
# Batch Post Output and Run Times
The output quantity represents the work progress in the form of the finished quantity and used capacity of work or machine center.

You can use the output journal to:
*  Adjust inventory in connection with output of finished items from production.
*  Register quantities and scrap for each operation in production routing.
*  Register setup and run time for work and machine centers.

> [!NOTE]
> If production routing are used, the inventory is updated only when you post output quantity on the last operation.

With the **Production Journal** window, you can perform the same tasks as in the **Output Journal** window and at the same time perform the related consumption posting tasks. For more information, see [Register Consumption and Output for One Released Production order line](production-how-to-register-consumption-and-output.md).

## To post output quantities and/or register run times for one or more production order lines
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Output Journal**, and then choose the related link.  
2. Fill in the fields with the production order data and the output data and/or run time. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
  
    You can use the **Explode Routing** function to generate journal lines from production orders.
  
4. If the operation has been completed, select the **Finished** field.  
5. Choose the **Post** action to post the operations. 
 
Capacity ledger entries are updated for the used work or machine centers with information about time and quantity of output and scrap. 
If you posted the last operation, the item will be added to the inventory. 

## See Also  
[Post Scrap Manually](production-how-to-post-scrap.md)
[Reverse Output Posting](production-how-to-reverse-output-posting.md)
[Manufacturing](production-manage-manufacturing.md)    
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)      
[Inventory](inventory-manage-inventory.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
