---
    title: Design Details - Integration with Inventory
    description: The Warehouse Management and the Inventory application area interact with one another in physical inventory and in inventory or warehouse adjustment.
    author: SorenGP

    
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/15/2021
    ms.author: edupont

---
# Detaily návrhu: Integrace zásob
Oblast aplikace Správa skladu a Zásob vzájemně komunikují pomocí fyzických inventur a v úpravách zásob nebo skladu.

## Fyzická inventura
Stránka **Whse. fyzické Inventory Journal** page is used with the **Phys. Inventory Journal** page for all advanced warehouse locations. Zásoby na úrovni přihrádky se vypočítají a pro zaměstnance skladu je následně k dispozici vytištěný seznam. Seznam ukazuje, v které přihrádce musí být zboží spočítáno.

The warehouse employee enters the counted quantity on the **Whse. fyzické Inventory Journal** page and then posts the journal.

Pokud je napočítané množství větší než množství na řádku deníku, bude pro tento rozdíl zaúčtován jako přesun z adjustační přihrádky do právě počítané přihrádky. Tím se zvýší množství v počítané přihrádce a sníží se množství v adjustační přihráce.

Pokud je počítané množství menší než množství na řádku deníku, přesun tohoto rozdílu se zaúčtuje z počítané přihrádky do adjustační přihrádky. Tím se sníží množství v počítané přihrádce a zvýší se množství ve výchozí adjustační přihrádce.

In advanced warehouse configurations, the value in the **Quantity (Calculated)** field is retrieved from item ledger entries and the value in the **Quantity (Phys. Inventory)** field is retrieved from warehouse entries, excluding the adjustment bin content. The **Quantity** field specifies the difference between the first two fields, which should be equal to the contents of the adjustment bin.

Při zaúčtování deníku fyzické inventury se aktualizují zásoby a výchozí adjustační přihrádka.

### Úpravy skladu v položkách zboží
You use the **Item Journal** page and the **Calculate Whse. Adjustment** function to adjust inventory on the item ledger in accordance with an adjustment that has been made to the item quantity in a warehouse bin. Chcete-li vytvořit propojení mezi zásobami a skladem, musíte definovat výchozí adjustační přihrádku daného skladu.

Výchozí adjustační přihrádka eviduje zboží ve skladu při zaúčtování zvýšení zásob. Pokud však zaúčtujete snížení, sníží se také množství ve výchozí adjustační přihrádce. V obou případech se vytvoří položky zboží a položky skladu.

> [!NOTE]  
> The adjustment bin is not included in the availability calculation.

Chcete-li upravit obsah přihrádky, můžete použít deník zboží skladu, ze kterého můžete zadat číslo zboží, kód zóny, kód přihrádky a množství, které chcete upravit.

Pokud zadáte kladné množství a zaúčtujete řádek, zásoby v přihrádce se zvýší a množství výchozí adjustační přihrádky se odpovídajícím způsobem sníží.

## Viz také
[Detaily návrhu: Správa skladu](design-details-warehouse-management.md)     
[Detaily návrhu: Dostupnost ve skladu](design-details-availability-in-the-warehouse.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]