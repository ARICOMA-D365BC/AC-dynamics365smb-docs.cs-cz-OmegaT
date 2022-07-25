---
title: Restructure Warehouses
description: Learn how to restructure your warehouse with new bin codes and new bin characteristics to achieve or maintain a more efficient operation.
author: SorenGP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.search.form: 9813, 9814
ms.date: 06/25/2021
ms.author: edupont

---
# Restrukturalizace skladů
Je možné, že budete chtít změnit strukturu skladu s novými kódy přihrádek a s vlastnostmi nových přihrádek. Tento druh aktivity nebudete provádět příliš často, ale situace může nastat, pokud je přeřazení nezbytné k dosažení nebo udržení účinnějšího provozu. Například:

- Je možné, že budete chtít přepnout kódy přihrádek, které podporují automatické zachycení dat, například pomocí ručních zařízení.
- Ve skladu může být zakoupen nový stojanový systém, který dává nové možnosti v skladování zboží.
- Společnost mohla změnit svůj sortiment zboží a přesunout sklad do nového fyzického umístění, aby se přizpůsobila této změně.

Pokud je sklad nastaven na používání přihrádek, ale nikoli na řízené zaskladnění a vyskladnění, proveďte restrukturalizaci skladu vytvořením nových přihrádek, které chcete v budoucnosti použít.

## Restrukturalizace skladu, který používá pouze přihrádky
1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Lokace** a poté vyberte související odkaz.
2. On the **Warehouse** FastTab, set the **Default Bin Selection** field to **Last-Used Bin**.
3. Přesuňte veškerý obsah aktuálních přihrádek do nových přihrádek, které jste právě vytvořili.

   1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Reclassification Journal**, and then choose the related link.
   2. Select a journal line, and then choose the **Get Bin Content** action.
   3. On the **Bin Content** FastTab, set filters in the **Location Code**, **Bin Code**, and **Item No.** fields to specify the content that you want to move.
   4. Choose the **OK** button to fill a journal line.
   5. In the **New Bin Code** field, select the bin to which the items should be moved.
   6. Opakujte kroky b až e pro veškerý obsah přihrádky, který chcete přesunout.
   7. Vyberte tlačítko **Zaúčtovat**.

Nyní jste vyprázdnili přihrádky, ve kterých se zboží používá. Výchozí přihrádky pro vaše položky byly nyní změněny na nové přihrádky.

## Restrukturalizace pokročilého skladu, který používá řízené zaskladnění a vyskladnění,

1. Vytvořte nové přihrádky, které chcete v budoucnosti použít. For more information, see [Create Bins](warehouse-how-to-create-individual-bins.md).
2. Přesuňte veškerý obsah aktuálních přihrádek do nových přihrádek, které jste právě vytvořili.

   1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Reclassification Journal**, and then choose the related link.
   2. For the bins where no real movement of items is involved, create a line for each of your current bins in the **Warehouse Reclassification Journal** with the old bin code, **From Bin Code**, and the new bin code, **To Bin Code**.
   3. If some of the movements involve actual physical movements that you want employees to perform, use **Movement Worksheets** to prepare movement instructions instead of using the warehouse reclassification journal. For more information, see [Move Items in Advanced Warehouse Configurations](warehouse-how-to-move-items-in-advanced-warehousing.md).

3. When the old bins are emptied, reclassify them as **QC** type bins to ensure that they are not included in item flows.

   1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Lokace** a poté vyberte související odkaz.
   2. Select the line with the location, and then choose the **Bins** action.
   3. On the **Bins** page, in the **Bin Type Code** field, enter **QC** for each of the old bins that you emptied in step 3 in the previous procedure.

Nyní jste odstranili přihrádky z toku skladu a překlasifikovali je jako přihrádky KVAL (bez typu). QC bins have none of the activity fields on the **Bin Types** page selected and are therefore not considered by the item flow. For more information, see [Set Up Bin Types](warehouse-how-to-set-up-bin-types.md).

## Odstranění přihrádky

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Lokace** a poté vyberte související odkaz.
2. Vyberte lokaci, kde chcete odstranit přihrádky. Choose the **Bins** action.
3. Vyberte řádky pro přihrádky, které chcete odstranit.
4. Choose the **Delete** action.

If you choose the **Yes** button, the bin is deleted for use in the future, but the bin code in all warehouse entries remains the same.

If you want to rename a bin so that all records associated with the bin are also renamed, including bin contents, warehouse activity lines, registered warehouse activity lines, warehouse worksheet lines, warehouse receipt lines, posted warehouse receipt lines, warehouse shipment lines, posted warehouse shipment lines, and warehouse entries, you can do so on the **Bins** page.

## Přejmenování přihrádky a změna kódu přihrádky ve všech záznamech

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Lokace** a poté vyberte související odkaz.
2. Select the location where you want to rename a bin or change the bin code, and then choose the **Bins** action.
3. Select the bin that you want to change and enter a new bin code in the **Code** field.
4. Vyberte tlačítko **Ano**.

> [!NOTE]  
> If you choose **Yes** and there are many entries concerning this bin, for example, because you have not deleted warehouse documents for some time, it may take some time to rename all the records. Therefore, if you use this method, consider running the batch job **Delete Registered Whse. Documents** before you start the renaming process. Všimněte si také, že jedinými dokumenty, které jsou v této dávkové úloze odstraněny, jsou zaskladnění, vyskladnění a přesuny.
>
> Pokud přejmenujete přijímací přihrádku nebo dodací přihrádku, budou všechny zaúčtované příjemky nebo dodávky, které se vztahují k dané přihrádce, přejmenovány.

## Viz také
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]