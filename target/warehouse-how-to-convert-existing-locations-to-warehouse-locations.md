---
    title: How to Convert Existing Locations to Warehouse Locations | Microsoft Docs
    description: You can enable an existing inventory location to use zones and bins and to operate as a warehouse location.
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
# Převod existujících lokací na lokace skladu
Existujícímu skladovému místu můžete povolit použití zón a přihrádek a pro provoz jako na skladu.

Dávková úloha, která povolí skladové místo pro skladové operace, vytvoří počáteční stavy skladu pro adjustační přihrádku skladu pro všechno zboží, které mají v lokaci zásoby. Tyto počáteční stavy budou vyrovnané po zadání zboží fyzické inventury skladu po spuštění dávkové úlohy.

Zóny a přihrádky můžete vytvořit před nebo po převodu. Jediná přihrádka, kterou musíte vytvořit před převodem, je ta, která má být použita jako budoucí adjustační přihrádka.

> [!IMPORTANT]  
> To clear all negative inventory and any open warehouse documents before you convert the location for warehouse handling, run a report to identify the items with negative inventory and open warehouse documents for the location. Pro více informací navštivte Kontrola záporného stavu zásob.

## Povolení fungování existujícího umístění jako lokace skladu
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Create Warehouse Location**, and then choose the related link.
2. In the **Location Code** field, specify the location that you want to enable for warehouse processing.
3. In the **Adjustment Bin Code** field, specify the bin at the location where unsynchronized warehouse entries are stored. For more information, see the [To synchronize the adjusted warehouse entries with the related item ledger entries](inventory-how-count-adjust-reclassify.md#to-synchronize-the-adjusted-warehouse-entries-with-the-related-item-ledger-entries).

   Při použití otevřených položek zboží pro zadané skladové místo jsou vytvořeny řádky deníku skladu, které tvoří součet všech kombinací čísel zboží, kód variant, kód měrné jednotky a v případě potřeby číslo šarže  a sériové číslo  v položkách zboží. Řádky deníku skladu jsou poté zaúčtovány. Toto zaúčtování vytvoří položky skladu, které umístí zásoby do adjustační přihrádky skladu. The **Adjustment Bin Code** on the location card is also set.

4. To see which items were added to the adjustment bin during the batch job, run the **Warehouse Adjustment Bin** report.
5. When the **Create Warehouse Location** batch job has completed, perform and post a warehouse physical inventory. For more information, see [Count, Adjust, and Reclassify Inventory Using Journals](inventory-how-count-adjust-reclassify.md).

> [!NOTE]  
> It is recommended that you run the **Create Warehouse Location** batch job at a time when it will not impact the daily work in the system. This job processes each entry in the **Item Ledger Entry** table, and if there are a large number of item ledger entries, the job can last several hours.

Pro skladová místa, která před převodem nepoužívaly doklady správy skladu, je nutné znovu otevřít a uvolnit všechny původní doklady, které byly částečně přijaty nebo částečně dodány před převodem.

## Viz také
[Správa skladu](warehouse-manage-warehouse.md)    
[Zásoby](inventory-manage-inventory.md)    
[Nastavení správy skladu](warehouse-setup-warehouse.md)       
[Správa montáže](assembly-assemble-items.md)      
[Detaily návrhu: Správa skladu](design-details-warehouse-management.md)    
[Práce s [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]