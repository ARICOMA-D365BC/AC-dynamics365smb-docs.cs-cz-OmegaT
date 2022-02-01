---
    title: Walkthrough - Receive and put away in basic warehouse configurations
    description: In Business Central, the inbound processes for receiving and putting away can be performed in four different ways, depending on the warehouse complexity level.
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
# Walkthrough: Receiving and Putting Away in Basic Warehouse Configurations

<!-- [!INCLUDE[complete_sample_data](includes/complete_sample_data.md)]   -->

In [!INCLUDE[prod_short](includes/prod_short.md)], the inbound processes for receiving and putting away can be performed in four ways using different functionalities depending on the warehouse complexity level.

| Metoda | Inbound process | Přihrádky | Příjmy | Vyskladnění | Complexity level (See [Design Details: Warehouse Setup](design-details-warehouse-setup.md)) |
|------------|---------------------|----------|--------------|----------------|--------------------------------------------------------------------------------------------------------------------|  
| A | Zaúčtujte příjemku a zaskladněte zboží z řádku objednávky | X | 2 |
| B | Zaúčtujte příjemku a zaskladněte zboží z dokladu zaskladnění zásob | X | 3 |
| C | Zaúčtujte příjemku a zaskladněte zboží z příjemky skladu | X | 4/5/6 |
| D | Zaúčtujte příjemku z příjemky skladu a zaskladnění z dokladu zaskladnění skladu | X | X | 4/5/6 |

For more information, see [Design Details: Inbound Warehouse Flow](design-details-inbound-warehouse-flow.md).

The following walkthrough demonstrates method B in the previous table.

## O tomto návodu
In basic warehouse configurations where your location is set up to require put-away processing but not receive processing, you use the **Inventory Put-away** page to record and post put-away and receipt information for your inbound source documents. The inbound source document can be a purchase order, sales return order, inbound transfer order, or production order with output that is ready to be put away.

> [!NOTE]
> Even though the settings are called **Require Pick** and **Require Put-away**, you can still post receipts and shipments directly from the source business documents at locations where you select these check boxes.

This walkthrough demonstrates the following tasks.

- Setting up SILVER location for inventory put aways.
- Setting up SILVER location for bin handling.
- Defining a default bin for item LS-81. (LS-75 is already set up in CRONUS.)
- Creating a purchase order for vendor 10000 for 40 loudspeakers.
- Verifying that the put-away bins are preset by setup.
- Releasing the purchase order for warehouse handling.
- Creating an inventory put-away based on a released source document.
- Verifying that the put-away bins are inherited from the purchase order.
- Registering the warehouse movement into the warehouse and at the same time posting the purchase receipt for the source purchase order.

> [!NOTE]
> [!INCLUDE [locations-cronus](includes/locations-cronus.md)]

## Role
Tento návod ukazuje úkoly, které jsou prováděny následujícími uživatelskými rolemi:

- Správce skladu
- Nákupní agent
- Warehouse Worker

## Předpoklady
K dokončení tohoto návodu budete potřebovat:

- CRONUS International Ltd. installed.
- To make yourself a warehouse employee at SILVER location by following these steps:

   1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Employees**, and then choose the related link.
   2. Vyberte pole **ID uživatele** a na stránce **Uživatelé** vyberte svůj vlastní uživatelský účet.
   3. In the **Location Code** field, enter SILVER.
   4. Vyberte pole **Výchozí**.

## Příběh
Ellen, the warehouse manager at CRONUS International Ltd., creates a purchase order for 10 units of item LS-75 and 30 units of item LS-81 from vendor 10000 to be delivered to SILVER Warehouse. When the delivery arrives at the warehouse, John, the warehouse worker, puts the items away in default bins defined for the items. When John posts the put-away, the items are posted as received into inventory and available for sale or other demand.

## Setting up the Location
The setup of the **Location Card** page defines the company's warehouse flows.

### To set up the location

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.
2. Open the SILVER location card.
3. Select the **Require Put-away** check box.

   Proceed to set up a default bin for the two item numbers to control where they are put away.

4. Choose the **Bins** action.
5. Select the first row, for bin S-01-0001, and then choose the **Contents** action.

   Notice on the **Bin Content** page that item LS-75 is already set up as content in bin S-01-0001.

6. Vyberte akci **Nový**.
7. Select the **Fixed** and the **Default** fields.
8. In the **Item No.** field, enter LS-81.

## Creating the Purchase Order
Purchase orders are the most common type of inbound source document.

### To create the purchase order

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.
2. Vyberte akci **Nový**.
3. Create a purchase order for vendor 10000 on the work date (January 23) with the following purchase order lines.

   | Zboží | Location code | Bin code | Množství |
   |----------|-------------------|--------------|--------------|  
   | LS_75 | STŘÍBRNÝ | S-01-0001 | 10 |
   | LS-81 | STŘÍBRNÝ | S-01-0001 | 30 |

   > [!NOTE]  
   > The bin code is entered automatically according to the setup that you performed in the "Setting up the Location" section.

   Proceed to notify the warehouse that the purchase order is ready for warehouse handling when the delivery arrives.

4. Vyberte akci **Vydat**.

   The delivery of loudspeakers from vendor 10000 has arrived at SILVER warehouse, and John proceeds to put them away.

## Receiving and Putting the Items Away
On the **Inventory Put-away** page, you can manage all inbound warehouse activities for a specific source document, such as a purchase order.

### To receive and put the items away

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Put-aways**, and then choose the related link.
2. Vyberte akci **Nový**.
3. Select the **Source Document** field, and then select **Purchase Order**.
4. Select the **Source No.** field, select the line for the purchase from vendor 10000, and then choose the **OK** button.

   Alternatively, choose the **Get Source Document** action, and then select the purchase order.

5. Zvolte akci **Automat.vyplnit množ. ke zprac.**.

   Alternatively, in the **Qty. to Handle** field, enter 10 and 30 respectively on the two inventory put-away lines.

6. Choose the **Post** action, select the **Receive** action, and then choose the **OK** button.

   The 40 loudspeakers are now registered as put away in bin S-01-0001, and a positive item ledger entry is created reflecting the posted purchase receipt.

## Viz také
[Put Items Away with Inventory Put-aways](warehouse-how-to-put-items-away-with-inventory-put-aways.md)   
[Set Up Basic Warehouses with Operations Areas](warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md)   
[Move Components to an Operation Area in Basic Warehouse Configurations](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md)   
[Pick for Production or Assembly](warehouse-how-to-pick-for-production.md)   
[Move Items Ad Hoc in Basic Warehouse Configurations](warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md)   
[Design Details: Inbound Warehouse Flow](design-details-inbound-warehouse-flow.md)   
[Business Process Walkthroughs](walkthrough-business-process-walkthroughs.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]