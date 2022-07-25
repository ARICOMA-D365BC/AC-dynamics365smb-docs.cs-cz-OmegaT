---
    title: Create Routings
    description: This topic gives an overview of the different ways to create routings including prerequisites required and how to create routing links.
    author: SorenGP


    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.form: 99000764, 99000765, 99000766, 99000767, 99000794, 99000796, 99000798, 99000806, 99000808, 99000810, 99000817, 99000834, 99000835, 99000836, 99000837, 99000840, 99000841, 99000844, 99000845
    ms.date: 06/22/2021
    ms.author: edupont

---
# Vytvoření TNG postupů

Výrobní společnosti používají rutiny k vizualizaci a řízení výrobního procesu.

TNG postup je základem plánování procesů, plánování kapacity, plánovaného přiřazení materiálových potřeb a výrobních dokladů.

Pokud jde o výrobní kusovníky, jsou TNG postupy přiřazeny k vyrobenému zboží. TNG postup obsahuje hlavní data, která zachycují procesní požadavky dané vyráběné zboží. Once a production order is created for that item, its routing will govern the scheduling of operations as represented on the **Prod. Order Routing** page under the production order.

Dříve než můžete TNG postup založit, musí být nastaveno následující:

- Karty zboží se vytvářejí pro nadřazené položky, které se podílejí na výrobě. For more information, see [Register New Items](inventory-how-register-new-items.md).
- Jsou nastaveny výrobní zdroje. For more information, see [Set Up Work Centers and Machine Centers](production-how-to-set-up-work-and-machine-centers.md).

## Vytvoření TNG postupů

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Routings**, and then choose the related link.
2. Vyberte akci **Nový**.
3. Podle potřeby vyplňte pole. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. In the **Type** field, select **Serial** to calculate the production routing according to the value in the **Operation No.** field.  
   Select **Parallel** to calculate the operations according to the value in the **Next Operation No.** field.
5. To edit the routing, set the **Status** field to **New** or **Under Development**. To activate it, set the **Status** field to **Certified**.

   Pokračujte vyplněním řádků TNG postupu.
6. In the **Operation No.** field, enter the number of the first operation, for example,  **10**.
7. In the **Type** field, specify which kind of resource is used, for example, **Work Center**.
8. In the **No.** field, select the resource to be used, or type it in the field.
9. In the **Routing Link Code** field, enter a code to connect the component to a specific operation. For more information, see [To create routing links](production-how-to-create-routings.md#to-create-routing-links).
10. In the **Run Time** and **Setup Time** fields, enter the process times needed to perform the operation.

   > [!NOTE]
   > Setup time is calculated per production order, whereas run time is calculated per produced item.

11. In the **Concurrent Capacities** field, specify how many units of the selected resource are used to perform the operation. Například dva lidé přidělení jedné balicí operaci zkrátí dobu běhu na polovinu.
12. Dále vyplňte řádky pro všechny operace, které se podílejí na výrobě daného zboží.
13. To copy lines from an existing routing, choose the **Copy Routing** action to select existing lines.
14. Certifikace TNG postupu.
15. You can now attach the new routing to the card of the production item in question, by filling in the **Routing No.** field. For more information, see [Register New Items](inventory-how-register-new-items.md).

> [!NOTE]  
> Remember also to recalculate the item's standard cost from the **Item** card: Choose the **Manufacturing** action, select the **Calc. Standard Cost** action, and then select the **All Levels** action.

## Vytvoření řádků TNG postupů

Můžete vytvořit řádky TNG postupu propojené s komponenty a určitými operacemi, aby se zachovala jejich relace i v případě, že je změněn výrobní kusovník nebo TNG postup. Zajišťuje také just-in-time vyprazdňování komponent, zejména při zahájení konkrétní propojené operace, nikoli při uvolnění celé výrobní zakázky. For more information see [Flush Components According to Operation Output](production-how-to-flush-components-according-to-operation-output.md).

Another important benefit is that linked components and operations are displayed in a logical process structure when you use the **Production Journal** page for output and consumption posting.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Routings**, and then choose the related link.
2. Otevřete TNG postup obsahující operace, které chcete propojit.

   Make sure the routing status is **Under Development**.

3. On the relevant routing line, in the **Routing Link Code** field, select a code.
4. V případě potřeby pokračujte v přidávání různých kódů vazeb TNG postupu k jiným operacím v TNG postupu.

   > [!NOTE]  
   > You should not use the same routing link code in different operations on a routing because you may incorrectly link a component to two different operations, so that it is consumed two times.
   >
   > Je vhodné pojmenovat kód vazby TNG postupu po operaci, aby bylo zajištěno propojení TNG postupu specifické pro danou operaci.

5. Set the routing status to **Certified**.

   Kódy vazeb TNG jsou nyní přiřazeny k operacím. Dále je nutné vytvořit skutečný odkaz přiřazením stejných kódů specifickým komponentám v příslušném kusovníku.

6. Open the **Production BOM** that contains the components that you want to link to the above operations. For more information, see [Create Production BOMs](production-how-to-create-production-boms.md).
7. Make sure the BOM status is **Under Development**.
8. On the relevant production BOM line, in the **Routing Link Code** field, select the code that you have just assigned to the relevant operation.
9. Pokračujte v přidávání kódů vazeb technologického postupu k jiným součástem podle jedinečných operací, ve kterých jsou použity.
10. Set the production BOM status to **Certified**.

   > [!NOTE]  
   > To enable the routing links on an existing production order, you must refresh the production order. For more information, see [Create Production Orders](production-how-to-create-production-orders.md).

Vybrané komponenty budou nyní propojeny s vybranými operacemi, když vytvoříte nebo aktualizujete výrobní zakázku pomocí výrobního kusovníku a příslušného TNG postupu. This is visible on the **Prod. Order Components** page under the production order, and here you can also remove and add the defined routing link codes at any time.

## To assign personnel, tools, and quality measures to routing operations

Požadujete-li pracovníky s kvalifikací, speciálními znalostmi nebo speciálním oprávněním pro operaci, můžete tyto osoby přiřadit k operaci. Kromě toho můžete k operaci přiřadit nástroje a požadavky na kvalitu. Tento postup popisuje přiřazení zaměstnanců. Postup je podobný jako u jiných typů informací o operacích.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Routings**, and then choose the related link.
2. Otevřete příslušný TNG postup.
3. On the **Lines** FastTab, select the line that you want to process, choose the **Operations** action, and then choose the **Personnel** action.
4. Fill in the fields on the **Routing Personnel** page.
5. Choose the **OK** button to exit the page. Zadané hodnoty se zkopírují a přiřadí se k operaci.

## Vytvoření nových verzí TNG postupu

Princip verze umožňuje spravovat několik verzí TNG postupu. Struktura verze TNG postupu odpovídá struktuře technologického postupu skládajícího se z hlavičky a z řádků verzovaného TNG postupu. Základní rozdíl je definován počátečním datem.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Routings**, and then choose the related link.
2. Select the routing to be copied, and then choose the **Versions** action.
3. On the **Routing Versions** page, choose the **New** action.
4. Podle potřeby vyplňte pole.
5. In the **Version Code** field, enter the unique identification of the version. Je povolena jakákoli kombinace číslic a písmen.

   The newly created version is automatically assigned the status **New**.
6. To create operation lines, select the first blank line, and then fill in the **Operation No.** field according to the sequence of operations.

   Řádky operací jsou seřazeny vzestupně podle čísel operací. Chcete-li provést změny později, doporučujeme vybrat odpovídající délku kroku. The **Next Operation No.** field refers to the following operation. Číslo operace lze zadat přímo.

7. When the routing version is completed, setting the **Status** field to **Certified**.

The time validity of the version is specified by the **Starting Date** field.

## Viz také

[Create Production BOMs](production-how-to-create-production-boms.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]