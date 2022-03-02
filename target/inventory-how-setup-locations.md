---
title: Set Up a Location Card and Define Transfer Routes (contains video)
description: If you buy, store, or sell items at more than one place or warehouse, you must set up each location with a location card and define transfer routes. 
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: warehouse, distribution center
ms.date: 06/16/2021
ms.author: edupont

---
# Nastavení Lokací

Pokud nakupujete, skladujete nebo prodáváte zboží na více místech nebo ve více skladech, musíte pro každé místo nastavit kartu místa a definovat trasy přenosu. [!INCLUDE [prod_short](includes/prod_short.md)] používá lokace ke sledování zásob v jednodušších případech i ve složitějších skladových procesech.

Můžete vytvářet řádky dokladů pro konkrétní lokace, zobrazovat dostupnost podle lokace a převádět zásoby mezi lokacemi. Pro více informací navštivte [Správa skladu](inventory-manage-inventory.md).
<br><br>

> [!Video https://www.microsoft.com/videoplayer/embed/RE4aQvq?rel=0]

## Karty lokace

Karta lokace určuje informace o umístění, jako je sklad nebo distribuční centrum. Každému místu přidělíte název a kód, který jej reprezentuje. Kód lokace pak můžete zadat v jiných částech systému, když chcete zaznamenat transakce pro dané místo.

Pro každé umístění můžete zadat informace o přihrádkách a skladových pravidlech. Na základě vybraných pravidel skladu můžete pomocí možností v záložce **Přihrádky** definovat přihrádky, které budou použity jako výchozí přihrádky při provádění transakcí. Pokud používáte řízené vyskladňování a zaskladňování, použijete většinu možností v záložce **Použití přihrádek**, abyste definovali, jak chcete používat různé pokročilé funkce skladu.

Některá pole možností jsou šedá a zakázaná jinými nastaveními na stránce **Karta lokace**, aby se omezily nepodporované kombinace nastavení.


Vyberte akci **Zóny** nebo **Přihrádky** pro zobrazení informací o zónách a přihrádkách, které mohou být pro dané umístění definovány.

### Vytvoření karty lokace

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Lokace** a poté vyberte související odkaz.
2. Vyberte akci **Nový**.
3. Na stránce **Karta lokace** vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Opakujte kroky 2 a 3 pro každou lokaci, kde chcete uchovávat zásoby.

> [!NOTE]  
> Mnoho polí na kartě umístění se týká manipulace se zbožím v procesech příjmu a výdeje ze skladu. Pole nejsou relevantní pro společnosti, které nevyžadují složitější funkce skladu. Pro více informací navštivte [Nastavení správy skladu](warehouse-setup-warehouse.md).

Konfiguraci lokace můžete změnit později, ale nemůžete upravovat nastavení lokace, které mají položky v účetní knize.

Dále, pokud máte více lokací, můžete definovat trasy transferu mezi lokacemi.

### Vytvoření trasy transferu

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Trasy transferu** a poté zvolte související odkaz.
2. Případně na jakékoli **Kartě lokace** vyberte tlačítko **Trasy transferu**.
3. Vyberte akci **Nový**.
4. Na stránce **Karta lokace** vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

Nyní můžete transferovat zboží mezi dvěma lokacemi. Pro více informací navštivte [Převádění zásob mezi lokacemi](inventory-how-transfer-between-locations.md).

## Přihrádky

Přihrádky představují základní skladovou strukturu a používají se k navrhování umístění zboží. Pokud jste vytvořili své přihrádky, můžete velmi přesně definovat obsah, který chcete umístit do každé přihrádky, nebo přihrádka může fungovat jako plovoucí přihrádka bez zadaného obsahu. Přihrádky se používají převážně v základních a pokročilých skladových operacích. Pokud spravujete zásoby v jednodušším nastavení, přihrádky pravděpodobně nepotřebujete.

pro použití přihrádek na lokaci, Musíte nejdříve zapnout funkcionalitu na kartě **Lokace** výběrem pole **Přihrádka nutná** v záložce **Sklad**. Pak navrhnete tok zboží v lokaci určením kódů přihrádek v polích nastavení, které představují různé toky.

> Předtím než nastavníte kódy přihrádek na kartě lokace, musí být přihrádky již vytvořeny.

Pro více informací navštivte [Vytvoření přihrádek](warehouse-how-to-create-individual-bins.md) a [Nastavení přihrádek](warehouse-how-to-set-up-bin-types.md).

## Zóny

Chcete-li strukturovat přihrádky podle zón, můžete to provést na stránce **Zóny**.

[!INCLUDE [prod_short](includes/prod_short.md)] zkopíruje pole, která jste nastavili pro libovolnou konkrétní zónu a přihrádky v ní. Tímto způsobem můžete přiřadit zónu k přihrádce nebo šabloně přihrádky (filtr pro vytvoření přihrádky) a několik dalších polí se pak vyplní automaticky.

Můžete se však rozhodnout nastavit pouze jednu zónu a uspořádat svůj sklad pouze podle přihrádek. Pro více informací navštivte [Nastavení správy skladu](warehouse-setup-warehouse.md).

## Viz také

[Správa skladu](inventory-manage-inventory.md)  
[Transfer zboží mezi lokacmei](inventory-how-transfer-between-locations.md)  
[Vytváření přihrádek](warehouse-how-to-create-individual-bins.md)  
[nastavení typů přihrádek](warehouse-how-to-set-up-bin-types.md)  
[Nastavení správy skladu](warehouse-setup-warehouse.md)  
[Práce s [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Změna zobrazovaných funkcí](ui-experiences.md)  
[Obecné obchodní funkcionality](ui-across-business-areas.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]