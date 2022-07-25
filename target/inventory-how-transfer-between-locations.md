---
title: Transfer Items Between Warehouse Locations
description: Describes how to move inventory from one place or warehouse to another, either with the reclassification journal or with transfer orders.
author: SorenGP

ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: move, warehouse
ms.search.forms: 5746, 5745, 5759, 5753, 5743, 5758, 5752, 5744, 5749, 5740, 5741, 5742, 5757, 5748, 5747, 9285, 5756, 5755
ms.date: 04/01/2021
ms.author: edupont

---
# Převádění zásob mezi lokacemi
Nyní můžete převádět skladové zboží mezi dvěma lokacemi pomocí objednávek transferu. Případně můžete použít deník přeřazení zboží.

Pomocí objednávek transferu můžete odesílat odchozí převod z jedné lokace a příjmout na lokací druhé. To umožňuje řídit související skladové činnosti a poskytuje větší jistotu, že množství zásob je správně aktualizováno.

Pomocí deníku přeřazení zboží jednoduše vyplníte pole **Kód lokace** a **Nový kód lokace**. Po zaúčtování deníku se upraví položky zboží na příslušných lokacích. Při této metodě nejsou řízeny skladové aktivity.

> [!NOTE]  
> Pokud máte v zásobách evidováno zboží bez kódu lokace, například z doby, kdy jste měli pouze jeden sklad, nemůžete potom takové zboží převádět pomocí objednávek transferu. Místo toho musíte použít deník přeřazení zboží k přeřazení zboží z prázdného kódu lokace na skutečné skladové místo.  Další informace naleznete v kroku 3 v [Převod zboží pomocí deníku přeřazení zboží](inventory-how-transfer-between-locations.md#to-transfer-items-with-the-item-reclassification-journal).

Pro transfer zboží je třeba nastavit lokace a trasy transferu. Pro více informací navštivte [Nastavení lokace](inventory-how-setup-locations.md).

## Převod zboží pomocí objednávek transferu
1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Objednávky transferu** a poté zvolte související odkaz.
2. On the **Transfer Order** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

   > [!NOTE]  
   > Pokud jste vyplnili pole **Kód na cestě**, **Kód přepravce** a **Kód služby přepravce** na stránce **Trans. spec.transferu.** při nastavování trasy transferu se automaticky vyplní odpovídající pole na objednávce transferu.

   Když vyplníte pole **Služba přepravce** datum přijetí se na lokaci do-kód vypočítá přidáním doby expedice služby přepravce k datu expedice.

3. Chcete-li řádky vyplnit, zadejte je ručně nebo vyberte jednu z následujících možností v tlačítku **Funkce**:
   - Pokud chcete načíst specifické zboží z určité přihrádky použijte funkci **Načíst obsah přihrádky**.
   - Vyberte **Kopie řádků příjemky** pro výběr zboží, které právě přije na lokaci Transfer do-kód.

   Jako skladník na místě transferu pokračujte v odeslání zboží.
4. Zvolte tlačítko **Účtovat** a vyberte možnost **Dodat** a poté zvolte **OK**.

   Zboží je nyní na cestě mezi určenými místy podle zadané trasy transferu.

   Jako pracovník skladu na místě transferu pokračujte v přijímání zboží. Řádky objednávyk transferu jsou stejné jako při expedici a nelze je upravovat.
5. zvolte tlačítko **Účtovat** a vyberte možnost **Příjmout** a poté zvolte **OK**.

## Transfer zboží pomocí deníku přeřazení zboží
1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi ](media/ui-search/search_small.png "Řekněte mi, co chcete dělat") zadejte **Deníky  přeřazení zboží** a poté vyberte související odkaz.
2. Na stránce <f0>Deníku přeřazení zboží** vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. V poli **Kód lokace** zadejte umístění, kde je zboží momentálně uloženy.

   > [!NOTE]  
   > Chcete-li převést položky, které nemají kód lokace, ponechte pole **Kód lokace** prázdné.
4. Do pole **Kód nové lokace** zadejte lokaci, kam chcete zboží převést.
5. Vyberte tlačítko **Zaúčtovat**.

## Viz také
[Manage Inventory](inventory-manage-inventory.md)  
[Set Up Locations](inventory-how-setup-locations.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[General Business Functionality](ui-across-business-areas.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]