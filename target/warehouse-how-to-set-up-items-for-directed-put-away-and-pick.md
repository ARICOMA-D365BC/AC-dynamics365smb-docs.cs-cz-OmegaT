---
    title: Set Up Directed Put-away and Pick
    description: Set up warehouse locations for directed put-away and pick, which gives you new functionality to ensure you run the warehouse in the most efficient way possible.
    author: SorenGP


    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/25/2021
    ms.author: edupont

---
# Nastavení zboží a lokací pro přímé zaskladnění a vyskladnění
Když nastavíte lokaci pro řízené zaskladnění a vyskladnění, máte k dispozici nové funkce, které vám pomohou spustit sklad co nejefektivnějším způsobem. Chcete-li tuto funkci plně využít, zadejte další informace o zboží, které pak pomohou provést výpočty nezbytné k tomu, aby navrhli nejúčinnější způsoby provádění skladových aktivit. Pro více informací navštivte [Detaily návrhu: Nastavení skladu](design-details-warehouse-setup.md).

## Nastavení zboží pro řízené zaskladnění a vyskladnění
1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat") zadejte **Zboží** a poté vyberte související odkaz.
2. Otevřete kartu zboží, které chcete nastavit pro řízené zaskladnění a vyskladnění.
3. On the **Warehouse** FastTab of the item card, fill in the fields to define how the item should be handled in the warehouse.
4. Choose the **Units of Measure** action.
5. On the **Item Units of Measure** page, fill in the fields to define the different units of measure in which the item may be transacted, including the height, width, length, cubage, and weight for the unit of measure.
6. Choose the **Bin Contents** action.
7. On the **Bin Contents** page, define the location and bin to which the item should be associated. The **Default** field is not used when the location is set up for directed put-away and pick.

## Aktivace řízeného zaskladnění a vyskladnění
Řízené zaskladnění a vyskladnění umožňuje přístup k rozšířeným funkcím konfigurace skladu, které mohou výrazně zvýšit efektivitu a spolehlivost dat. Abyste mohli tuto funkci využívat, musíte nejprve nastavit několik parametrů ve vašem skladu.

Chcete-li použít funkci řízeného zaskladnění a vyskladnění, musíte aktivovat funkčnost na kartě lokace.
1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Lokace** a poté vyberte související odkaz.
2. Select the location where you want to use directed put-away and pick, and then choose the **Edit** action.
3. On the **Warehouse** FastTab, select the **Directed Put-away and Pick** check box.

Na kartě lokace není nutné vyplňovat žádná další pole, dokud nebude potřeba dalšího nastavení.

> [!NOTE]  
> You cannot set up the warehouse to use bins when the location has open item ledger entries.

Dalším krokem je definování typu přihrádek, které chcete používat. For more information, see [Set Up Bin Types](warehouse-how-to-set-up-bin-types.md). Typ přihrádky určuje způsob použití dané přihrádky při zpracování toku zboží ve skladu. Typ přihrádky můžete přiřadit zóně i přihrádce.

Můžete také definovat kódy tříd skladu, pokud sklad přepravuje zboží, které potřebuje různé skladovací podmínky. Kódy tříd skladu se používají při navrhování umístění zboží v přihrádkách. Kódy tříd skladu přiřadíte skupinám produktů, které jsou poté přiřazeny zboží, skladovým jednotkám nebo zónám a přihrádkám, které mohou vyhovovat podmínkám skladování vyžadovaným kódy tříd skladu.

Nyní jste připraveni nastavit zóny, pokud je chcete provozovat ve skladu. Použití zón snižuje počet polí, která je třeba vyplnit při nastavování přihrádek, protože přihrádky vytvořené v rámci zón dědí z této zóny několik vlastností. Zóny mohou také usnadnit novým nebo dočasným zaměstnancům orientaci ve vašem skladu. Všimněte si, že tok je řízen přihrádkami, proto je možné pracovat s přihrádkami a pouze s jednou zónou.

## Nastavení zóny ve skladu
1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Lokace** a poté vyberte související odkaz.
2. Select the location where you want to set up zone and open the location card, and then choose the **Zones** action.
3. On the **Zones** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

Když změníte parametr zóny, všechny přihrádky vytvořené v této zóně budou mít nové vlastnosti, ale původní přihrádky nebudou změněny.

> [!NOTE]  
> If you want to operate without zones, you must still create one zone code that is undefined except for the code.

Dalším krokem při nastavení skladu je definování přihrádek. For more information, see [Set Up Locations to Use Bins](warehouse-how-to-set-up-locations-to-use-bins.md).

Dále je nutné vytvořit šablony zaskladnění a období inventury. Pro více informací navštivte [Nastavení šablon zaskladnění](warehouse-how-to-set-up-put-away-templates.md).

## Viz také
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]