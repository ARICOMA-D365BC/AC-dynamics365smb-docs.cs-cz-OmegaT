---
    title: Use the Manufacturing Batch Unit of Measure
    description: This topic gives an overview of how to work with manufacturing batch units of measure in Business Central. 
    author: SorenGP

    
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/25/2021
    ms.author: edupont

---
# Práce s měrnými jednotkami výrobní dávky
If an item is stocked in one unit of measure but produced in another, a production order is created that uses a manufacturing batch unit of measure to calculate the correct quantity of the components during the **Refresh Production Order** batch job. Příkladem výpočtu měrné jednotky výrobní dávky je, když je vyrobeno zboží skladované v kusech, ale vyrobené v tunách.

## Vytvoření výrobního kusovníku pomocí měrné jednotky dávky
1. The manufacturing batch unit of measure is set up as an alternative unit of measure on the **Item Units of Measure** page on the item to be produced. Měrná jednotka dávky nenahrazuje základní měrnou jednotku zboží.
2. Vytvořte výrobní kusovník pro položku nastavenou s měrnou jednotkou výrobní dávky. Další informace naleznete v tématu [Vytváření výrobních kusovníků](production-how-to-create-production-boms.md).
3. In the **Unit of Measure Code** field, select the manufacturing batch unit of measure.
4. For each production BOM line, in the **Quantity Per** field, enter the quantity of this component item that is required to create this batch unit of measure.
5. Open the **Item Card** for the related item.

   On the **Replenishment** FastTab, in the **Production BOM No.** field, select the production BOM created above.
6. Vytvořte hlavičku výrobní zakázky pomocí zboží nastavené s měrnou jednotkou výrobní dávky. For more information, see [Create Production Orders](production-how-to-create-production-orders.md).
7. Choose the **Refresh** action, and then choose  the **OK** button.

On the **Lines** FastTab, choose the **Line** action, and then choose the **Components** action to view the result. The application calculates the correct quantity of the components needed to satisfy the production BOM based on the manufacturing batch unit of measure.

## Výpočet měrné jednotky výrobní dávky na výrobní zakázce
1. Vytvořte hlavičku výrobní zakázky pomocí zboží nastavené s měrnou jednotkou výrobní dávky.
2. In the **Item No.** field in the Production Order line, type the same item number used in the header.
3. In the **Quantity** field, enter the same quantity used in the header.
4. In the **Unit of Measure Code** field, select the manufacturing batch unit of measure code.
5. Choose the **Refresh** action.
6. On the **Calculate** FastTab, clear the **Lines** check box.
7. Zvolte tlačítko **OK**.
8. On the **Lines** FastTab, choose the **Line** action, and then choose the **Components** action to view the result. Správné množství komponent potřebných k uspokojení výrobního kusovníku se vypočítá na základě výrobní šarže měrné jednotky.

## Viz také
[Create Routings](production-how-to-create-routings.md)  
[Create Production BOMs](production-how-to-create-production-boms.md)     
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)    
[Planning](production-planning.md)   
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]