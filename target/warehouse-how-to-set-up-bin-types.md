---
    title: Set Up Bin Types
    description: Assign types and basic flow activities to bins and, in doing so, define the way the bins are used for particular warehouse activities.
    author: SorenGP


    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.form: 7367
    ms.date: 06/25/2021
    ms.author: edupont

---
# Set Up Bin Types
You can direct the flow of items through bins that you have defined for particular warehouse activities. You give each bin its basic flow activities, and thereby define the way a bin is used, by assigning it a bin type.

There are six types. You can operate your warehouse with all of the six possible bin types, or you can choose to operate with just the RECEIVE, PUTPICK, SHIP and QC bin types. These four bin types enable suggestions to be made that support the flow of items and allow you to record inventory discrepancies.

## To set up the bin types you want to use
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bin Types**, and then choose the related link.
2. On the **Bin Types** page, create a 10-character code for a bin type.
3. Select the activities that can be performed with each bin type.

> [!NOTE]  
> Bin types are only applicable if you are using directed put-away and pick for your location.

The bin type determines only how a bin is used when processing the flow of items through the warehouse. You can always override the suggestions for any warehouse document, and you can move items in or out of any bin by performing a warehouse movement.

The bin types that you can create are listed below.

| Typ přihrádky | Popis |
|------------------|---------------------------------------|  
| PŘÍJEM | Items registered as posted receipts but not yet put away. |
| DODÁVKA | Zboží vybrané pro skladové řádky, ale dosud nebyly zaúčtovány jako dodávané. |
| VYSKL | Typicky zboží, které má být uloženo ve velkých měrných jednotkách, ale které nechcete zpřístupňovat pro vyskladnění. Protože se tyto přihrádky nepoužívají k vyskladnění, a to ani u výrobních objednávek a ani u zásilek, může být používání přihrádky typu Zaskladnění omezené, ale tento typ přihrádky může být užitečný, pokud jste zakoupili velké množství zboží. Přihrádky tohoto typu by měly mít vždy nižší pořadí přihrádek, takže když jsou přijaté položky zaskladněny, jsou nejprve vyřazeny další přihrádky ZASKLVYSKL s vyšším pořadím. Pokud používáte tento typ přihrádky, musíte pravidelně provádět doplňování přihrádky tak, aby položky uložené v těchto přihrádkách byly také k dispozici v přihrádkách typu ZASKLVYSKL nebo VYSKL. |
| VYSKL | Items to be used only for picking, for example, for items with an approaching expiration date that you have moved into this type of bin. You would place a high bin ranking on these bins so they are suggested for picking first. |
| VYSKLZASKL | Zboží v přihrádkách, které jsou navrženy pro funkce vyskladněni a zaskladnění. Přihrádky tohoto typu pravděpodobně mají rozdílné pořadí přihrádek. Můžete nastavit své přihrádky jako objemné s nížším pořadím přihrádek ve srovnání s běžnými přihrádkami nebo přihrádkami pro vyskladnění. |
| KVAL | Tato přihrádka se používá pro úpravy zásob, pokud tuto přihrádku zadáte na kartě lokace v poli **Kód adjustační přihrádky**. Můžete také nastavit přihrádky tohoto typu pro vadné předměty a kontrolované položky. You can move items to this type of bin if you want to make them inaccessible to the usual item flow.<br /><br /> **NOTE:** Unlike all other bin types, the **QC** bin type has none of the item handling check boxes selected by default. To znamená, že veškerý obsah, který umístíte do přihrádky KVAL, je z toků zboží vyloučen. |

## Viz také
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
