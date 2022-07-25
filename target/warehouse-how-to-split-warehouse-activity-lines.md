---
    title: How to Split Warehouse Activity Lines
    description: Read how to split warehouse activity lines if the available capacity in a suggested bin is not sufficient.
    author: SorenGP


    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/25/2021
    ms.author: edupont

---
# Rozdělení řádků aktivit skladu
Při zaskladnění, přesunech nebo vyskladnění a ve skladových zaskladnění a vyskladnění zásob se přihrádky navrhují pro vyskladnění nebo zaskladnění zboží. Skutečné množství v navrhované přihrádce nemusí být dostatečné nebo v navrhované přihrádce není dostatek místa pro zaskladnění požadovaného množství. V těchto případech je třeba řádek rozdělit, aby bylyo zboží pro jeden řádek odebráno nebo umístěno do více než jedné přihrádky.

Následující postup platí pro doklady skladu, jako je zaskladnění, přesun a řádky vyskladnění nebo řádky zaskladnění zásob, přesun a vyskladnění.

## Rozdělení řádků aktivit skladu
1. Otevřete řádek aktivity skladu, kde se pokoušíte zpracovat nedostatečné množství.
2. V poli **Množ. ke zprac.** zadejte snížené množství, které jste schopni zpracovat.
3. Na záložce **Řádky** vyberte akci **Akce**, poté vyberte akci **Funkce** a pak vyberte akci **Rozdělit řádek**. Zobrazí se nový řádek, který je kopií původního řádku, kromě toho, že pole **Množ. ke zprac.** obsahuje množství, které jste odebrali z původního řádku.
4. Přiřaďte tomuto novému řádku příslušnou přihrádku, pokud používáte zónu řízeného zaskladnění a vyskladnění, nebo pokračujte v rozdělování řádku podle potřeby, dokud nenajdete vhodné přihrádky pro celé množství.

> [!NOTE]  
> If the location uses directed put-away and pick and you split the lines, you must be familiar with the warehouse and be able to choose a bin that matches the storage requirements of the item and that fulfills the general requirements of the warehouse document. Například byste nerozdělili řádek na dokladu vyskladnění a neuložili by jste některé položky do hromadného úložiště.

## Viz také
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]