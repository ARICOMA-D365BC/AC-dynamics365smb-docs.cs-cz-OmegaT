---
title: Create Production BOMs
description: Learn how to create a production bill of material (BOM), new versions of a production BOM, and how to use the quantity calculation formula.
author: bholtorf
ms.topic: conceptual
ms.search.form: 9287, 99000786, 99000787, 99000788, 99000789, 99000795, 99000797, 99000800, 99000809, 99000811, 99000812, 99000818
ms.date: 06/22/2021
ms.author: edupont

---
# Vytvoření výrobních kusovníků

Výrobní kusovník uchovává hlavní data popisující komponenty a sestavení použité při výrobě nadřízeného zboží. Once a production order is created for that parent item, its production BOM will govern the calculation of material requirements as represented on the **Prod. Order Components** page.

[!INCLUDE[prod_short](includes/prod_short.md)]  also support assembly BOMs. You use assembly orders for making end items from components in a simple process that can be performed by one or more basic resources, which are not machine or work centers, or without any resources. Proces montáže by například mohl být, z výběru dvou láhví vína a jednoho pytlíku kávy a následného zabalení jako dárek. For more information, see [Assembly BOMs or Production BOMs](inventory-how-work-boms.md#assembly-boms-or-production-boms).

Dříve než můžete TNG postup založit, musí být nastaveno následující:

- Karty zboží se vytvářejí pro nadřazené položky, které se podílejí na výrobě. For more information, see [Register New Items](inventory-how-register-new-items.md).
- Jsou nastaveny výrobní zdroje. For more information, see [Set Up Work Centers and Machine Centers](production-how-to-set-up-work-and-machine-centers.md).

## Vytvoření výrobních kusovníků

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Production BOM**, and then choose the related link.
2. Vyberte akci **Nový**.
3. Vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. To edit the BOM, set the **Status** field to **New** or **Under Development**. To activate it, set the **Status** field to **Certified**.

   Pokračujte vyplněním řádků výrobního kusovníku.
5. In the **Type** field, select whether the item on this BOM line is an ordinary item or a production BOM. If the item on the line is a production BOM, then it must already exist as a certified production BOM.
6. In the **No.** field, look up and select the item or production BOM in question, or type it in the field.
7. In the **Quantity Per** field, enter how many units of the item go into the parent item, for example, 4 wheels for 1 car.
8. In the **Scrap %** field you can enter a fixed percentage of components that are scrapped during production. When the components are ready to be consumed in a released production order, this percentage will be added to the expected quantity in the **Consumption Quantity** field in a production journal. For more information, see [Register Consumption and Output](production-how-to-register-consumption-and-output.md).

   > [!NOTE]  
   > This scrap percentage represents components that are scrapped during production when picking from inventory, whereas the scrap percentage on routing lines represents scrapped output before putting on inventory.

9. In the **Routing Link Code** field, enter a code to connect the component to a specific operation. For more information, see [To create routing links](production-how-to-create-routings.md#to-create-routing-links).
10. To copy lines from an existing production BOM, choose the **Copy BOM** action to select existing lines.
11. Certifikace výrobního kusovníku
12. Nyní můžete připojit nový výrobní kusovník ke kartě příslušného nadřazeného zboží. For more information, see [Register New Items](inventory-how-register-new-items.md).

> [!NOTE]  
> [!INCLUDE [bom-standard-cost](includes/bom-standard-cost.md)] To recalculate the item's standard cost from the item card, choose the **Manufacturing** action, and then choose the **Calc. Standard Cost** action.

## Vytvoření nových verzí výrobního kusovníku

Nové verze výrobních kusovníků se používají například tehdy, když je zboží nahrazeno jinou položkou, nebo když zákazník vyžaduje speciální verzi produktu. Princip verze umožňuje spravovat různé verze výrobního kusovníku. Struktura verze výrobního kusovníku odpovídá struktuře výrobního kusovníku. Základní rozdíl je v době platnosti verzí. Platnost je definována počátečním datem.

Počáteční datum označuje začátek období, ve kterém je tato verze platná. Pro všechny ostatní úvahy je počáteční datum filtrovacím kritériem pro výpočty a vyhodnocení. Verze kusovníku je platná až do doby, kdy další verze začne platit pro nové počáteční datum.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Production BOM**, and then choose the related link.
2. Select the production BOM to be copied, and then choose the **Versions** action.
3. Vyberte akci **Nový**.
4. Vyplňte pole podle potřeby.
5. In the **Version Code** field, enter the unique identification of the version. Je povolena jakákoli kombinace číslic a písmen.

   The newly created version is automatically assigned the status **New**.
6. When the BOM version is completed, setting the **Status** field to **Certified**.

The time validity of the version is specified by the **Starting Date** field.

> [!NOTE]  
> Select the **Item** option in the **Type** field to use an item from your item master data in the production BOM. If the item also has a production BOM, whereby the **Production BOM No.** field is filled in on the item card, this production BOM is also considered.
>
> Select the **Production BOM** option if you want to use a phantom production BOM on the line.
>
> Fantom kusovníky slouží ke strukturování produktů. Tento typ výrobního kusovníku nikdy nevede k hotovému produktu, ale používá se výhradně k určení závislého požadavku. Fantom kusovníky nemají vlastní kmenová data zboží.

## Vzorec pro výpočet množství na kusovnících

Množství se počítá s přihlédnutím k různým rozměrům, které jsou také zadávány na výrobních kusovnících. Rozměry se vztahují k objednávkové jednotce příslušného zboží. Délku, šířku, hloubku a hmotnost lze zadat jako rozměry.

Sloupce vzorec výpočtu, délka, šířka, hloubka a hmotnost nejsou zobrazeny, protože je používají pouze někteří uživatelé. Pokud chcete použít výpočet množství, musíte tyto sloupce nejprve zobrazit.

Vztah jednotlivých komponent je definován vzorcem výpočtu. Jako vzorec pro výpočet jsou k dispozici následující možnosti:

- **Empty** - No consideration of dimensions. (Množství = Množství za)
- **Length** - Quantity = Quantity per * Length
- **Length x Width** - Quantity = Quantity per * Length x Width
- **Length x Width x Depth** - Quantity = Quantity per x Length x Width x Depth
- **Weight** - Quantity = Quantity per x Weight
- **Fixed Quantity** - Quantity = Quantity per

> [!NOTE]
> The **Fixed Quantity** calculation formula ensures that the consumption of a component is the same, regardless of the scrap or output quantities. For production order components, when the **Calculation Formula** field is set to **Fixed Quantity**, the **Expected Quantity** field value is always equal to the **Quantity per** field. The scrap percentage that is defined on the same line is ignored. Fixed quantity is respected by the **Availability by BOM** report. The report will show the item as the bottleneck if the available quantity is less than the quantity in the **Quantity Per Parent** field. The **Able to Make Parent** and **Able to Make Top Item** fields are always blank, regardless of the available quantity. Fixed quantity is also included in calculations for standard costs. The lot size for the produced item impacts the cost that is allocated for one item.

### Příklad

Ve výrobním kusovníku je vyžadováno sedmdesát kovových dílů s rozměry: Délka = 0,20m na Šířka = 0,15m. Hodnoty se zadávají následovně: Vzorec výpočtu = délka x šířka, délka = 20, šířka = 15, množství = 70. Množství je dáno množstvím za * délka * šířka, tj. Množství = 70 x 0,20 m x 0,15 m = 2,1 m2.

## Viz také

[Create Routings](production-how-to-create-routings.md)   
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)    
[Planning](production-planning.md)   
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]