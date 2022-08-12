---
title: How to Set Up Stockkeeping Units
description: You can use stockkeeping units to record information about your items for a specific location or a specific variant code.
author: SorenGP

ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.search.forms: 5704, 5700, 5702, 5701
ms.date: 04/01/2021
ms.author: edupont

---
# Nastavení skladové jednotky
Skladové jednotky můžete použít k záznamu informací o položkách pro konkrétní skladové místo nebo kód varianty.

Skladové jednotky jsou doplňkem ke kartám zboží. Nenahrazují je, i když s nimi souvisí. Skladovací jednotky umožňují rozlišovat informace o zboží pro konkrétní lokaci, jako je sklad nebo distribuční centrum, nebo konkrétní varianta, jako jsou různá čísla polic a různé informace o doplňování, pro stejné zboží.

## Nastavení skladové jednotky

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Skladové jednotky** a poté vyberte související odkaz.
2. Vyberte **Nový** Akce.
3. Vyplňte pole na kartě. Následující pole jsou povinná: **Číslo položky**, **Kód umístění**a/nebo **Kód varianty**. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

Pokud jste pro zboží nastavili první skladovou jednotku, je zaškrtnuto políčko **Skladová jednotka existuje** na kartě **Zboží**.

Chcete-li pro položku vytvořit několik skladových jednotek, použijte dávkovou úlohu **Vytvořit skladovou jednotku**.

> [!NOTE]  
> Informace na kartě **Skladová jednotka** mají přednost před kartou **Zboží**.

> [!Warning]
> Pokud je SKU dodáváno prostřednictvím výroby, pak se pole **Standardní náklady** při fakturaci a úpravě skutečných nákladů na vyrobenou položku nepoužívá. Místo toho se použije pole **Standardní cena** na kartě podkladové položky a případné odchylky se počítají proti podílům na nákladech této položky.<br /><br />
> Protože kusovníky produkce a směrování nemohou být přiřazeny k jednotkám SKU, pak souhrn jednotkových nákladů a související výpočet podílů na nákladech také nejsou k dispozici na jednotkách SKU.. Pro více informací navštivte [O výpočtu pevné pořizovací ceny](finance-about-calculating-standard-cost.md)

## Viz také
[Registrace nových položek](inventory-how-register-new-items.md)    
[Nastavení správy skladu](warehouse-setup-warehouse.md)    
[Správa skladu](warehouse-manage-warehouse.md)    
[Inventář](inventory-manage-inventory.md)    
[Správa sestavy](assembly-assemble-items.md)      
[Podrobnosti návrhu: Správa skladu](design-details-warehouse-management.md)    
[Pracovat s [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]