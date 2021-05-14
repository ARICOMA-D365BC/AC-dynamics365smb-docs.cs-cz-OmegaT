---
    title: Flush Components According to Operation Output
    description: For items that are set up with backward flushing method, the default behavior is to calculate and post component consumption when you change the status of a released production order to Finished.
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
# Spotřeba komponent podle výstupní operace
You can define different flushing strategies, to automate registering of consumption of components.

Pokud například výrobní zakázka na výrobu 800 metrů vyžaduje 8 kg komponenty, potom při účtovaní 200 metrů jako výstup, 2 kg se automaticky zaúčtuje jako spotřeba.

Tato funkce je užitečná z následujících důvodů:

- **Inventory Valuation**

   Value entries for output and consumption are created in parallel as the production order progresses. Bez kódů TNG postupů se hodnota zásob zvýší při zaúčtování výstupu a potom se sníží v čase, kdy je hodnota spotřeby komponent zaúčtována společně s dokončenou výrobní objednávkou.
- **Inventory Availability**

   With gradual consumption posting, the availability of component items is more up-to-date, which is important to maintain the internal balance between demand and supply. Bez kódů vazeb technologického postupu se mohou jiné požadavky na komponentu domnívat, že jsou k dispozici tak dlouho, dokud čeká na zpožděné účtování spotřeby.
- **Just-in-Time**

   With the ability to customize products to customer requests, you can minimize waste by making sure that work and system changes only occur when it is necessary.

You can achieve that by combining backward flushing method and routing link codes so that the quantity that is flushed for each operation is proportional to the actual output of the finished operation. For items that are set up with backward flushing method, the default behavior is to calculate and post component consumption when you change the status of a released production order to **Finished**. Pokud definujete také kódy vazeb TNG, pak výpočet a zaúčtování proběhne po dokončení každé operace a zaúčtování množství, které bylo skutečně spotřebováno v dané operaci. For more information, see [Create Routings](production-how-to-create-routings.md).

## Spotřeba komponent podle výstupu operace

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat") zadejte **Zboží** a poté vyberte související odkaz.
2. Choose the **Edit** action.
3. On the **Replenishment** FastTab, in the **Flushing Method** field, select **Backward**.

   > [!NOTE]  
   > Select **Pick + Backward** if the component is used in a location that is set up for directed put-away and pick.

4. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Routings**, and then choose the related link.
5. Definujte kódy vazeb technologického postupu pro každou operaci, která zpracovává komponentu. For more information, see [Create Routings](production-how-to-create-routings.md).
   > [!IMPORTANT]  
   > Do not use same routing routing link for different operations in the routing, as it will lead to registration of consumption of component for each linked operation.
6. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Production BOM**, and then choose the related link.
7. Definujte kódy vazeb technologického postupu z každé instance komponenty k operaci, kde je spotřebováno.

The consumption will be posted automatically when you register output. For more information, see [Batch Post Output and Run Times](production-how-to-post-output-quantity.md)

## Flushing methods

The following table describes the available flushing method options that you can specify on **Item** cards and **Stockkeeping Unit** cards.

| Možnost | Popis |
|------------|-------------|  
| Manual | Requires that you manually enter and post consumption in the consumption journal. |
| Dopředu | Automatically posts consumption according to the production order component lines. <br><br>By default, the posting of component consumption occurs when you change the status of a production order to **Released**. However, if you use the **Routing Link** Code field on production order component lines, then posting occurs per operation when the operation starts. For more information, see [How to: Create Routing Links](production-how-to-create-routings.md#to-create-routing-links). <br><br> **Note**<br>For forward flushing, the operation-specific posting that you obtain with routing link codes is based on the expected quantity that is defined on the component line. For information about operation-specific flushing based on actual output, see the description of **Backward** in this topic.<br><br>If the location or resources where this component is consumed are set up with a default bin structure, then the item is consumed from the **Open Shop Floor Bin Code**. For more information, see [How to: Set Up Basic Warehouses with Operations Areas](warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md). <br><br> **Important** <br>Forward flushing also occurs when you choose **Refresh** on a released production order that was created from scratch. On these directly created released production orders, you cannot change bin information because the production order component lines are generated when you refresh the order, which at the same time forward flushes the components. Therefore, if you want to change bin information on production order component lines before forward flushing occurs, then that order must be created with the *Planned* or *Firm Planned* status. |
| Zpětně | Automatically calculates and posts consumption according to the production order component lines.<br><br> By default, the calculation and posting of component consumption occurs when you change the status of a released production order to **Finished**. However, if you use the **Routing Link Code** field on the production order component lines, then calculation and posting occurs when each operation is finished.<br><br> **Note** <br>Backward flushing and routing link codes can be combined so that the quantity that is flushed per operation is proportional to the actual output of that operation. For more information, see [How to: Flush Components According to Operation Output](#to-flush-components-according-to-operation-output).<br><br> If the location or machine center where this component is consumed are set up with a default bin structure, then the item is consumed from the **Open Shop Floor Bin Code**. |
| Pick + Forward | Same as for Forward flushing method, except it only works for locations that use directed put-away and pick.<br><br> Consumption is calculated and posted from the bin that is defined in the **To-Production Bin Code** field on the location or machine center after the component has been picked from the warehouse.<br><br> **Note** <br>If a component is set up with the Pick + Forward flushing method, then it cannot have a routing link code to an operation that is set up with the forward flushing method. The component would then be automatically flushed when the operation starts, which makes it impossible to request the pick activity. |
| Pick + Backward | Same as for Backward flushing method, except it only works for locations that use directed put-away and pick.<br><br> Consumption is calculated and posted from the bin that is defined in the **To-Production Bin Code** field on the location or machine center after the component has been picked from the warehouse. |

## Viz také

[Create Production BOMs](production-how-to-create-production-boms.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
