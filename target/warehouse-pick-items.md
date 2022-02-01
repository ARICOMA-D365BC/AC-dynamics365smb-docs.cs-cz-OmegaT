---
title: Pick Items
description: The activity of picking items before they are shipped or consumed is performed in different ways, depending on how warehouse management features are configured.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 5779, 5798, 7343, 7345, 7357, 7359, 7377, 7392, 7395, 7397, 9313, 9316, 9344
ms.date: 06/25/2021
ms.author: edupont

---
# Vyskladnění zboží

Aktivita skladu vyskladnění zboží před jeho dodáním nebo spotřebou se provádí různými způsoby v závislosti na konfiguraci funkcí správy skladu. Složitost se může řadit od žádných funkcí skladu, přes základní konfigurace skladu pro zpracování podle objednávek pouze v jedné nebo více aktivitách, až po pokročilé konfigurace, kde musí být všechny aktivity skladu prováděny v řízeném workflow. Pro více informací navštivte [Nastavení správy skladu](warehouse-setup-warehouse.md).

Pokud se rozhodnete uspořádat a zaznamenat svou aktivitu vyskladnění pomocí dokladů skladu, zaškrtnete políčko **Vyžadovat vyskladnění** na kartě lokace. To naznačuje, že když máte zboží, které je třeba vyskladnit pro odchozí zdrojový doklad, chcete, aby vyskladnění tohoto zboží bylo řízené systémem. Výstupním původním dokladem může být prodejní objednávka, objednávka nákupní vratky, výstupní objednávka transferu, servisní zakázka nebo výrobní zakázka, jejíž komponenty by měly být vyskladněny.

> [!NOTE]
> Even though the setting is called **Require Pick**, you can still post shipments directly from the source business document at location where you select this check box.

Pokud je vaša lokace nastavena tak, aby vyžadovala zpracování vyskladnění, ale nikoli zpracování zásilky, můžete pomocí stránky **Vyskladnění zásob** uspořádat informace o vyskladnění, vytisknout informace o vyskladnění, zadat výsledek vyskladnění a odeslat informace o vyskladnění, pomocí kterých následně zaúčtujete zásilku zboží. V případě vyskladnění komponent pro výrobní zakázku zaúčtování vyskladnění také zaúčtuje spotřebu.

Pokud je vaše lokace nastavena tak, aby vyžadovala zpracování vyskladnění i dodávky, takže jste na kartě lokace zaškrtli pole **Vyžadovat vyskladnění** a **Vyžadovat dodání**, ke zpracování vyskladnění použijete stránku **Vyskladnění**. Vyskladnění funguje podobně jako vyskladnění zásob, kromě toho, že místo zaúčtování informací o vyskladnění vyskladnění i zaregistrujete. Tento proces registrace nezaúčtuje dodávku, ale pouze zpřístupní zboží k dodávce. Jako správce skladu můžete pomocí pracovních listů pro výběr uspořádat informace o vyskladnění před vytvořením jednotlivých pokynů pro vyskladnění skladu.

Následující tabulka popisuje sekvenci úloh s odkazy na témata, které je popisují.

| **Viz** | **také** |
|------------|-------------|  
| Zaúčtovat dodávku zboží přímo do výstupního dokladu objednávky, protože neexistují žádné prvky skladu. (Totéž platí pro prodejní objednávky, výstupní objednávky transferu a dodávky vratky.) | [Dodání zboží](warehouse-how-ship-items.md) |
| Vyberte zboží po objednávkách a zaúčtujte zásilku ve stejné aktivitě, v základní konfiguraci skladu. | [Vyskladnění zboží pomocí Vyskladnění zásob](warehouse-how-to-pick-items-with-inventory-picks.md) |
| Vyberte zboží pro více objednávek v pokročilé konfiguraci skladu. | [Vyskladnění zboží pomocí Vyskladnění](warehouse-how-to-pick-items-for-warehouse-shipment.md) |
| Vyberte komponenty pro výrobu nebo montáž v základní konfiguraci skladu. | [Vyskladnění pro výrobu nebo montáž v základních konfiguracích skladu](warehouse-how-to-pick-for-production.md) |
| Vyskladnění komponent pro výrobu nebo montáž v pokročilé konfiguraci skladu. | [Vyskladnění pro výrobu nebo montáž v pokročilých konfiguracích skladu](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md) |
| Naplánujte optimalizované pokyny pro vyskladnění pro řadu dodávek, nikoli aby pracovníci skladu jednali přímo na zaúčtovaných dodávkach. | [Plánujte vyskladnění v sešitech](warehouse-how-to-plan-picks-in-worksheets.md) |
| Vyskladnění zboží technicky pro zvláštní účel, jako je výrobní jednotka, která potřebuje další komponenty, tak, aby zboží technicky neopustilo sklad. | [Vyskladnění a zaskladnění bez původního dokladu](warehouse-how-to-create-put-aways-from-internal-put-aways.md) |
| Pochopte, jak automaticky vyskladnit zboží podle data vypršení platnosti, například zboží podléhající rychlé zkáze. | [Vyskladnění podle FEFO](warehouse-picking-by-fefo.md) |
| Rozdělte řádek vyskladnění na více řádků, například proto, že v určené přihrádce není dostatek zboží, ze kterých je možné požadované množství vyskladnit. | [Rozdělení řádků aktivit skladu](warehouse-how-to-split-warehouse-activity-lines.md) |
| Získejte okamžitý přístup k vyskladnění, která jsou vám přiřazena jako pracovníkovi skladu. | [Najděte svá přiřazení skladu](warehouse-how-to-find-your-warehouse-assignments.md) |

## Viz také
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)
[Assembly Management](assembly-assemble-items.md)
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]