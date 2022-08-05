---
title: How to Work with Responsibility Centers
description: Responsibility center as administrative centers help companies set up user-specific views of sales and purchase documents related exclusively to each center.
author: SorenGP

ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.search.forms: 5714, 5715
ms.date: 06/16/2021
ms.author: edupont

---
# Práce s Centry odpovědnosti

Centra odpovědnosti poskytují schopnost zvládnout administrativní centra. Centrum odpovědnosti může být nákladové středisko, ziskové středisko, investiční centrum nebo jiné centrum správy definované společností. Příkladem center odpovědnosti je prodejní kancelář, nákupní oddělení pro několik míst a kancelář pro plánování továren. Například pomocí této funkce mohou společnosti nastavit uživatelsky specifické pohledy na prodejní a nákupní doklady související výhradně s konkrétním centrem odpovědnosti.

Použití více umístnění společně s odpovědnými centry poskytuje možnost řídit obchodní operace nejflexibilnějším a zároveň optimálním způsobem.

Více umístnění umožňuje společnostem spravovat své zásoby na více místech pomocí jedné databáze. Základními kameny této části jsou dva koncepty, umístění a skladovací jednotky. Umístění je definováno jako místo, které zpracovává fyzické umístění a množství zboží. Koncept je dostatečně široký, aby zahrnoval místa, jako jsou závody nebo výrobní zařízení, jakož i distribuční centra, sklady, předváděcí místnosti a servisní vozidla. Skladová jednotka je definována jako položka na konkrétním místě a/nebo jako varianta. Pomocí skladových jednotek mohou společnosti s více pobočkami přidávat informace o doplňování, adresy a některé finanční účetní informace na úrovni umístění. Výsledkem je, že mají schopnost doplňovat varianty téže položky pro každé místo, jakož i objednávat položky pro každé místo na základě informací o doplňování pro konkrétní umístění.

## Zřídit Centrum odpovědností

1. Vyberte ![Žárovku, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete delat"), zadejte **Centra odpovědnosti**a pak zvolte související odkaz.
2. Vyberte **Nový** Akce.
3. Podle potřeby vyplňte pole. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

   Pokud pro správu vaší společnosti používáte centra odpovědnosti, může být užitečné mít výchozí středisko odpovědnosti pro vaši společnost.
4. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi ](media/ui-search/search_small.png "Řekněte mi, co chcete dělat") zadejte **Informace o společnosti** a vyberte související odkaz.
5. Do pole **Centrum odpovědnosti** zadejte kód střediska odpovědnosti.

Tento kód bude použit ve všech dokumentech o nákupu, prodeji nebo servisu, pokud uživatel, zákazník nebo prodejce nemá žádné výchozí centrum odpovědnosti. V jakémkoli prodejním, nákupním nebo servisním dokumentu můžete zadat jiné centrum odpovědnosti než výchozí.

> [!NOTE]  
> When you enter a responsibility center code on a document, it affects the address, dimensions, and prices on the document.

## Přiřazení center odpovědnosti uživatelům

Můžete nastavit uživatele tak, aby v jejich každodenních rutinách aplikace načítala pouze dokumenty relevantní pro jejich konkrétní pracovní oblasti. Uživatelé jsou obvykle spojeni s jedním centrem odpovědnosti a pracují pouze s dokumenty souvisejícími s konkrétními oblastmi aplikace v tomto konkrétním centru.

Chcete-li to nastavit, přiřaďte centra odpovědnosti uživatelům ve třech funkčních oblastech: Nákupy, Prodej a Správa služeb.

1. Vyberte ikonu ![Žárovky, která otevře ikonu Řekněte mi](media/ui-search/search_small.png "Řeknete mi, co chcete dělat"), zadejte **Nastavení uživatelů** a poté vyberte související odkaz.
2. Na stránce **Nastavení uživatele** vyberte uživatele, kterému chcete přiřadit centrum odpovědnosti. Pokud uživatel není v seznamu, musíte zadat ID uživatele do pole **ID uživatele**.
3. V poli **Filtr prod. centra odpovědnosti centra Do pole Filtr** zadejte středisko odpovědnosti, kde bude mít uživatel úkoly související s prodejem.
4. V poli **Filtr nák. centra V poli Filtr** zadejte centrum odpovědnosti, kde bude mít uživatel úkoly související s nákupem.
5. V poli **Filtr servis. centra Do pole Filtr** zadejte centrum odpovědnosti, kde bude mít uživatel úkoly související se správou služeb.

> [!NOTE]  
> Uživatelé mohou prohlížet pouze ty zaúčtované dokumenty, které se týkají jejich vlastního centra odpovědnosti. Mohou však zobrazit všechny položky hlavní knihy a přejít na další zaúčtované dokumenty z položek hlavní knihy.

## Viz také

[Nastavení inventáře](inventory-setup-inventory.md)    
[Nastavení správy skladu](warehouse-setup-warehouse.md)    
[Inventář](inventory-manage-inventory.md)    
[Správa skladu](warehouse-manage-warehouse.md)    
[Podrobnosti návrhu: Správa skladu](design-details-warehouse-management.md)    
[Práce s [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]