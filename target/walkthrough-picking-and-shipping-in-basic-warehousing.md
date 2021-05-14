---
    title: Picking and Shipping in Basic Warehouse Configurations | Microsoft Docs
    description: In Business Central, the outbound processes for picking and shipping can be performed in four ways using different functionalities depending on the warehouse complexity level.
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
# Walkthrough: Picking and Shipping in Basic Warehouse Configurations

[!INCLUDE[complete_sample_data](includes/complete_sample_data.md)]

In [!INCLUDE[prod_short](includes/prod_short.md)], the outbound processes for picking and shipping can be performed in four ways using different functionalities depending on the warehouse complexity level.

| Metoda | Inbound process | Přihrádky | Vyskladnění | Dodávky | Complexity level (See [Design Details: Warehouse Setup](design-details-warehouse-setup.md)) |
|------------|---------------------|----------|-----------|---------------|--------------------------------------------------------------------------------------------------------------------|  
| A | Zaúčtování vyskladnění a dodávky z řádku objednávky | X | 2 |
| B | Zaúčtování vyskladnění a dodávky z dokladu vyskladnění zásob | X | 3 |
| C | Zaúčtování vyskladnění a dodávky z dokladu dodávky ze skladu | X | 4/5/6 |
| D | Zaúčtování vyskladnění z dokladu vyskladnění a zaúčtování dodávky z dokladu dodávky ze skladu | X | X | 4/5/6 |

For more information, see [Design Details: Outbound Warehouse Flow](design-details-outbound-warehouse-flow.md).

The following walkthrough demonstrates method B in the previous table.

> [!NOTE]
> [!INCLUDE [locations-cronus](includes/locations-cronus.md)]

## O tomto návodu

In basic warehouse configurations where your location is set up to require pick processing but not ship processing, you use the **Inventory Pick** page to record and post pick and ship information for your outbound source documents. The outbound source document can be a sales order, purchase return order, outbound transfer order, or a production order with component need.

Tento návod ukazuje následující úkoly:

- Setting up SILVER location for inventory picks.
- Creating a sales order for customer 10000 for 30 loudspeakers.
- Releasing the sales order for warehouse handling.
- Creating an inventory pick based on a released source document.
- Registering the warehouse movement from the warehouse and at the same time posting the sales shipment for the source sales order.

> [!NOTE]
> [!INCLUDE [locations-cronus](includes/locations-cronus.md)]

## Role

Tento návod ukazuje úkoly, které jsou prováděny následujícími uživatelskými rolemi:

- Správce skladu
- Zpracovatel objednávek
- Warehouse Worker

## Předpoklady

K dokončení tohoto návodu budete potřebovat:

- For [!INCLUDE[prod_short](includes/prod_short.md)] online, a company based on the **Advanced Evaluation - Complete Sample Data** option in a sandbox environment. For [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, CRONUS International Ltd. installed.
- To make yourself a warehouse employee at the location SILVER by following these steps:

   1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Zaměstnanci skladu** a poté vyberte související odkaz.
   2. Vyberte pole **ID uživatele** a na stránce **Uživatelé** vyberte svůj vlastní uživatelský účet.
   3. In the **Location Code** field, enter SILVER.
   4. Vyberte pole **Výchozí**.

- Make item LS-81 available at SILVER location by following these steps:

   1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Deníky zboží** a poté vyberte související odkaz.
   2. Open the default journal, and then create two item journal lines with the following information about the work date (January 23).

      | Typ položky | Item Number | Kód lokace | Bin Code | Množství |
      |----------------|-----------------|-------------------|--------------|--------------|  
      | Positive Adjmt. | LS-81 | STŘÍBRNÝ | S-01-0001 | 20 |
      | Positive Adjmt. | LS-81 | STŘÍBRNÝ | S-01-0002 | 20 |

   3. Choose the **Post** action, and then select the **Yes** button.

## Příběh

Ellen, the warehouse manager at CRONUS, sets up SILVER warehouse for basic pick handling where warehouse workers process outbound orders individually. Susan, the order processor, creates a sales order for 30 units of item LS-81 to be shipped to customer 10000 from the SILVER Warehouse. John, the warehouse worker must make sure that the shipment is prepared and delivered to the customer. John manages all involved tasks on the **Inventory Pick** page, which automatically points to the bins where LS-81 is stored.

## Setting Up the Location

The setup of the **Location Card** page defines the company's warehouse flows.

### To set up the location

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Lokace** a poté vyberte související odkaz.
2. Open the SILVER location card.
3. On the **Warehouse** FastTab, choose the **Require Pick** check box.

## Creating the Sales Order

Sales orders are the most common type of outbound source document.

### Vytvoření prodejní objednávky

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Prodejní objednávky** a poté zvolte související odkaz.
2. Vyberte akci **Nový**.
3. Create a sales order for customer 10000 on the work date (January 23) with the following sales order line.

   | Zboží | Kód lokace | Množství |
   |----|-------------|--------|  
   | LS_81 | STŘÍBRNÝ | 30 |

   Proceed to notify the warehouse that the sales order is ready for warehouse handling.

4. Vyberte akci **Vydat**.

   John proceeds to pick and ship the sold items.

## Picking and Shipping Items

On the **Inventory Pick** page, you can manage all outbound warehouse activities for a specific source document, such as a sales order. [!INCLUDE[tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

### To pick and ship items

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Picks**, and then choose the related link.
2. Vyberte akci **Nový**.

   Make sure that the **No.** field on the **General** FastTab is filled in.
3. Select the **Source Document** field, and then select **Sales Order**.
4. Select the **Source No.** field, select the line for the sale to customer 10000, and then choose the **OK** button.

   Alternatively, choose the **Get Source Document** action, and then select the sales order.
5. Zvolte akci **Automat.vyplnit množ. ke zprac.**.

   Alternatively, in the **Qty. to Handle** field, enter 10 and 20 respectively on the two inventory pick lines.
6. Choose the **Post** action, select **Ship**, and then choose the **OK** button.

   The 30 loudspeakers are now registered as picked from bins S-01-0001 and S-01-0002, and a negative item ledger entry is created reflecting the posted sales shipment.

## Viz také

[Pick Items with Inventory Picks](warehouse-how-to-pick-items-with-inventory-picks.md)  
[Pick Items for Warehouse Shipment](warehouse-how-to-pick-items-for-warehouse-shipment.md)  
[Set Up Basic Warehouses with Operations Areas](warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md)  
[Move Components to an Operation Area in Basic Warehouse Configurations](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md)  
[Pick for Production or Assembly](warehouse-how-to-pick-for-production.md)  
[Move Items Ad Hoc in Basic Warehouse Configurations](warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md)  
[Design Details: Outbound Warehouse Flow](design-details-outbound-warehouse-flow.md)  
[Business Process Walkthroughs](walkthrough-business-process-walkthroughs.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]