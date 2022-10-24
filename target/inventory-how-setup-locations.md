---
title: Set Up a Location Card and Define Transfer Routes (contains video)
description: If you buy, store, or sell items at more than one place or warehouse, you must set up each location with a location card and define transfer routes. 
author: SorenGP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: warehouse, distribution center
ms.search.forms: 5703, 15
ms.date: 06/16/2021
ms.author: edupont

---
# Nastavení Lokací

Locations are places such as warehouses where you buy, store, or sell items. [!INCLUDE [prod_short](includes/prod_short.md)] uses locations to help keep track of inventory in both simple and complex warehouse processes.

Můžete vytvářet řádky dokladů pro konkrétní lokace, zobrazovat dostupnost podle lokace a převádět zásoby mezi lokacemi. Pro více informací navštivte [Správa skladu](inventory-manage-inventory.md).
<br><br>

> [!Video https://www.microsoft.com/videoplayer/embed/RE4aQvq?rel=0]

## Karty lokace
You specify information about a location, such as a warehouse or distribution center, on the **Location Card** page. Každému místu přidělíte název a kód, který jej reprezentuje. Kód lokace pak můžete zadat v jiných částech systému, když chcete zaznamenat transakce pro dané místo.

Pro každé umístění můžete zadat informace o přihrádkách a skladových pravidlech. Na základě vybraných pravidel skladu můžete pomocí možností v záložce **Přihrádky** definovat přihrádky, které budou použity jako výchozí přihrádky při provádění transakcí. Pokud používáte řízené vyskladňování a zaskladňování, použijete většinu možností v záložce **Použití přihrádek**, abyste definovali, jak chcete používat různé pokročilé funkce skladu.

Some option fields depend on settings in the **Location Card** page to restrict unsupported setup combinations.

Choose the **Zones** or **Bins** actions to view information about zones and bins that are defined for the location.

### To set up a location

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Lokace** a poté vyberte související odkaz.
2. Vyberte akci **Nový**.
3. Na stránce **Karta lokace** vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Opakujte kroky 2 a 3 pro každou lokaci, kde chcete uchovávat zásoby.

> [!NOTE]  
> Many fields on the Location Card page are related to the handling of items in inbound and outbound warehouse processes. These fields are not relevant for companies that do not require complex warehouse functionality. Pro více informací navštivte [Nastavení správy skladu](warehouse-setup-warehouse.md).

Konfiguraci lokace můžete změnit později, ale nemůžete upravovat nastavení lokace, které mají položky v účetní knize.

If you have multiple locations, you can define transfer routes between locations. For more information, see [To create a transfer route
](inventory-how-setup-locations.md#to-create-a-transfer-route).

### Vytvoření trasy transferu

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Trasy transferu** a poté zvolte související odkaz.
2. Případně na jakékoli **Kartě lokace** vyberte tlačítko **Trasy transferu**.
3. Vyberte akci **Nový**.
4. Na stránce **Karta lokace** vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

Nyní můžete transferovat zboží mezi dvěma lokacemi. Pro více informací navštivte [Převádění zásob mezi lokacemi](inventory-how-transfer-between-locations.md).

## Přihrádky

Přihrádky představují základní skladovou strukturu a používají se k navrhování umístění zboží. When you have created your bins, you can define their contents, or they can function as a floating bins without specified contents. Přihrádky se používají převážně v základních a pokročilých skladových operacích. Pokud spravujete zásoby v jednodušším nastavení, přihrádky pravděpodobně nepotřebujete.

To use the bin functionality at a location, you first activate the functionality on the **Location Card** page by selecting the **Bins Mandatory** field on the **Warehouse** FastTab. Pak navrhnete tok zboží v lokaci určením kódů přihrádek v polích nastavení, které představují různé toky.

> [!NOTE]
> Before you can specify bin codes on a location, you must create bin codes. For more information, see [Create Bins](warehouse-how-to-create-individual-bins.md) and [Set Up Bin Types](warehouse-how-to-set-up-bin-types.md).

## Zóny

Chcete-li strukturovat přihrádky podle zón, můžete to provést na stránce **Zóny**.

[!INCLUDE [prod_short](includes/prod_short.md)] zkopíruje pole, která jste nastavili pro libovolnou konkrétní zónu a přihrádky v ní. Tímto způsobem můžete přiřadit zónu k přihrádce nebo šabloně přihrádky (filtr pro vytvoření přihrádky) a několik dalších polí se pak vyplní automaticky.

Můžete se však rozhodnout nastavit pouze jednu zónu a uspořádat svůj sklad pouze podle přihrádek. Pro více informací navštivte [Nastavení správy skladu](warehouse-setup-warehouse.md).

## Default Dimensions for Locations
You set default dimensions for a location on the **Location Card** page by choosing **Location**, and then **Dimensions**. The location's default dimensions are copied to journals and documents when you specify the location on a line, but you can delete or change the dimension on the line if needed. You can require that people specify dimensions for specific locations before they can post an entry. You can also include location dimension values in **Default Dimension Priorities** and **Dimension Combinations** for combinations of priority and dimension rules.

## Viz také

[Manage Inventory](inventory-manage-inventory.md)  
[Transfer Inventory Between Locations](inventory-how-transfer-between-locations.md)  
[Create Bins](warehouse-how-to-create-individual-bins.md)  
[Set Up Bin Types](warehouse-how-to-set-up-bin-types.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[General Business Functionality](ui-across-business-areas.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]