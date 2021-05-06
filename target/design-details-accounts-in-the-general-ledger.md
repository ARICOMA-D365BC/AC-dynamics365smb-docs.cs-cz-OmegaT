---
    title: Design Details - Accounts in the General Ledger | Microsoft Docs
    description: To reconcile inventory and capacity ledger entries with the general ledger, the related value entries are posted to different accounts in the general ledger.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 10/01/2020
    ms.author: edupont

---
# Design Details: Accounts in the General Ledger
To reconcile inventory and capacity ledger entries with the general ledger, the related value entries are posted to different accounts in the general ledger. Pro více informací navštivte [Detaily návrhu: Odsouhlasení s hlavní knihou](design-details-reconciliation-with-the-general-ledger.md).

## From the Inventory Ledger
The following table shows the relationship between different types of inventory value entries and the accounts and balancing accounts in the general ledger.

| **Typ položky zboží** | **Value Entry Ttype** | **Variance Type** | **Expected Cost** | **Account** | **Balancing Account** |
|--------------------------------|--------------------------|-----------------------|-----------------------|-----------------|---------------------------|  
| Nákup | Přímé náklady | Ano | Inventory  (Interim) | Invt. Accrual Acc. (Interim) |
| Nákup | Přímé náklady | Ne | Zásoby | Direct Cost Applied |
| Nákup | Indirect Cost | Ne | Zásoby | Overhead Applied |
| Nákup | Variance | Nákup | Ne | Zásoby | Purchase Variance |
| Nákup | Přecenění | Ne | Zásoby | Inventory Adjmt. |
| Nákup | Rounding | Ne | Zásoby | Inventory Adjmt. |
| Prodej | Přímé náklady | Ano | Inventory  (Interim) | COGS (Interim) |
| Prodej | Přímé náklady | Ne | Zásoby | COGS |
| Prodej | Přecenění | Ne | Zásoby | Inventory Adjmt. |
| Prodej | Rounding | Ne | Zásoby | Inventory Adjmt. |
| Positive Adjmt.,Negative Adjmt., Transfer | Přímé náklady | Ne | Zásoby | Inventory Adjmt. |
| Positive Adjmt.,Negative Adjmt., Transfer | Přecenění | Ne | Zásoby | Inventory Adjmt. |
| Positive Adjmt.,Negative Adjmt., Transfer | Rounding | Ne | Zásoby | Inventory Adjmt. |
| (Production) Consumption | Přímé náklady | Ne | Zásoby | WIP |
| (Production) Consumption | Přecenění | Ne | Zásoby | Inventory Adjmt. |
| (Production) Consumption | Rounding | Ne | Zásoby | Inventory Adjmt. |
| Assembly Consumption | Přímé náklady | Ne | Zásoby | Inventory Adjmt. |
| Assembly Consumption | Přímé náklady | Ne | Direct Cost Applied | Inventory Adjmt. |
| Assembly Consumption | Indirect Cost | Ne | Overhead Applied | Inventory Adjmt. |
| (Production) Output | Přímé náklady | Ano | Inventory  (Interim) | WIP |
| (Production) Output | Přímé náklady | Ne | Zásoby | WIP |
| (Production) Output | Indirect Cost | Ne | Zásoby | Overhead Applied |
| (Production) Output | Variance | Material | Ne | Zásoby | Material Variance |
| (Production) Output | Variance | Capacity | Ne | Zásoby | Capacity Variance |
| (Production) Output | Variance | Subcontracted | Ne | Zásoby | Subcontracted Variance |
| (Production) Output | Variance | Capacity Overhead | Ne | Zásoby | Cap. Overhead Variance |
| (Production) Output | Variance | Manufacturing Overhead | Ne | Zásoby | Mfg. Overhead Variance |
| (Production) Output | Přecenění | Ne | Zásoby | Inventory Adjmt. |
| (Production) Output | Rounding | Ne | Zásoby | Inventory Adjmt. |
| Assembly Output | Přímé náklady | Ne | Zásoby | Inventory Adjmt. |
| Assembly Output | Přecenění | Ne | Zásoby | Inventory Adjmt. |
| Assembly Output | Indirect Cost | Ne | Zásoby | Overhead Applied |
| Assembly Output | Variance | Material | Ne | Zásoby | Material Variance |
| Assembly Output | Variance | Capacity | Ne | Zásoby | Capacity Variance |
| Assembly Output | Variance | Capacity Overhead | Ne | Zásoby | Cap. Overhead Variance |
| Assembly Output | Variance | Manufacturing Overhead | Ne | Zásoby | Mfg. Overhead Variance |
| Assembly Output | Rounding | Ne | Zásoby | Inventory Adjmt. |

## From the Capacity Ledger
The following table shows the relationship between different types of capacity value entries and the accounts and balancing accounts in the general ledger. Capacity ledger entries represent labor time consumed in assembly or production work.

| **Work Type** | **Capacity Ledger Entry Type** | **Value Entry Type** | **Account** | **Balancing Account** |
|-------------------|------------------------------------|--------------------------|-----------------|---------------------------|  
| Montáž | Zdroj | Přímé náklady | Direct Cost Applied | Inventory Adjmt. |
| Montáž | Zdroj | Indirect Cost | Overhead Applied | Inventory Adjmt. |
| Production | Machine Center/Work Center | Přímé náklady | WIP Account | Direct Cost Applied |
| Production | Machine Center/Work Center | Indirect Cost | WIP Account | Overhead Applied |

## Assembly Costs are Always Actual
As shown in the table above, assembly postings are not represented in interim accounts. This is because the concept of work in process (WIP) does not apply in assembly output posting, unlike in production output posting. Assembly costs are only posted as actual cost, never as expected cost.

Pro více informací navštivte [Podrobnosti návrhu: Účtování montážní zakázky](design-details-assembly-order-posting.md).

## Calculating the Amount to Post to the General Ledger
The following fields in the **Value Entry** table are used to calculate the expected cost amount that is posted to the general ledger:

- Částka nákladů (skutečná)
- Zaúčtované náklady
- Částka nákladů (očekávaná)
- Zaúčtované očekávané náklady

The following table shows how the amounts to post to the general ledger are calculated for the two different cost types.

| Cost Type | Calculation |
|---------------|-----------------|  
| Actual Cost | Cost Amount (Actual) – Cost Posted to G/L |
| Očekávané náklady | Cost Amount (Expected) –  Expected Cost Posted to G/L |

## Viz také
[Design Details: Inventory Costing](design-details-inventory-costing.md)   
[Design Details: Inventory Posting](design-details-inventory-posting.md)   
[Design Details: Expected Cost Posting](design-details-expected-cost-posting.md)  
[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Finance](finance.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]