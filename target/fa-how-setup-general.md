---
title: Set Up General FA Information
description: Before you work with fixed assets, you must set up default G/L accounts, posting groups, allocation keys, journal templates and batches, and class codes.
author: edupont04


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 5623, 5615, 5661, 5662, 5627, 5616, 5620, 5629, 5633, 5609, 5631, 5630, 5617, 5612, 5613, 5608, 5609, 5635, 9277
ms.date: 04/01/2021
ms.author: edupont

---
# Nastavení obecných informací o dlouhodobém majetku.
Předtím než začnete se správou dlouhodobého majetku je nutné nastavit výchozí finanční účty, alokační klíče, šablony a listy deníku pro zaúčtování a přeřazení dlouhodobého majetku, dále také můžete klasifikovat dlouhodobý majetek do tříd, jako je hmotný a nehmotný.

## Nastavení obecných výchozích hodnot dlouhodobého majetku
You define the general behavior or the fixed asset functionality and set up document number series in the  on the **Fixed Assets Setup** page.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Assets Setup**, and then choose the related link.
2. Vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## Nastavení účto skupin dlouhodobého majetku
Nastavení účto skupiny dlouhodobého majetku Položky pro tyto účto skupiny jsou zaúčtovány na stejné finanční účty.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Posting Groups**, and then choose the related link.
2. Vyberte **Nový** Akce.
3. On the **FA Posting Group Card** page, fill in the fields as necessary.

   > [!NOTE]  
   > To make sure that balancing accounts for different fixed assets postings are automatically inserted when you choose the **Insert FA Bal. Account** action on journal lines, follow the next step, based on appreciation posting.
4. On the **Balancing Account** FastTab, in the **Appreciation Bal. Account** field, select the general ledger account to which you want to post balancing entries for appreciation.

For more information about using the **Insert FA Bal. Account** action on fixed asset G/L journal lines, see, for example, [Revalue Fixed Assets](fa-how-revalue.md).

## Nastavení klíčů přidělení dlouhodobého majetku
Transakce mohou být přiděleny různým oddělením nebo projektům podle uživatelem definovaných alokačních klíčů. Můžete například nastavit alokační klíč pro přidělení odpisových nákladů na automobily s 35% na oddělení správy a 65%  na prodejní oddělení. For more information, see [Allocate Costs and Income](year-allocate-costs-income.md).

Alokační klíče se vztahují na třídy dlouhodobého majetku, nikoli na jednotlivý majetek.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Posting Groups**, and then choose the related link.
2. On the **FA Posting Groups** page, choose the **Allocations** action, and then choose a posting type.
3. On the **FA Allocations** page, fill in the fields as necessary.
4. Opakujte kroky 2 a 3 pro každý typ účtování, pro který chcete definovat alokační klíče.

## Nastavení šablon deníku dlouhodobého majetku
Šablona je předdefinované rozvržení deníku. Šablona obsahuje informace o trasovacích kódech, sestavách a číselných řadách. For more information, see [Work with General Journals](ui-work-general-journals.md).

[!INCLUDE[prod_short](includes/prod_short.md)] automatically creates a fixed asset journal template the first time that you open the **Fixed Asset Journal** page, but you can set up additional journal templates.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Journal Templates**, and then choose the related link.
2. Vyplňte pole podle potřeby.

## Nastavení listů deníku dlouhodobého majetku
Můžete nastavit více listů deníku, což jsou jednotlivé deníky pro každou šablonu. Zaměstnanci mohou mít například vlastní list deníku, který používá iniciály zaměstnance jako název listu deníku. For more information, see [Work with General Journals](ui-work-general-journals.md).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Journal Templates**, and then choose the related link.
2. Select the relevant journal template, and then choose the **Batches** action.
3. On the **FA Journal Batches** page, fill in the fields as necessary.

## Nastavení šablon deníku přeřazení dlouhodobého majetku
Vyhrazené deníky přeřazení slouží k převodu, rozdělení nebo kombinování dlouhodobého majetku. [!INCLUDE[prod_short](includes/prod_short.md)] automatically creates a fixed asset reclassification journal template the first time that you open the **FA Reclass. Journal** page, but you can set up additional reclassification journal templates. For more information, see [Work with General Journals](ui-work-general-journals.md).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Reclass. Journal Templates**, and then choose the related link.
2. Vyplňte pole podle potřeby.

## Nastavení listů deníku přeřazení dlouhodobého majetku
Můžete nastavit více listů deníku, což jsou jednotlivé deníky pro každou šablonu deníku přeřazení. Zaměstnanci mohou mít například vlastní list deníku přeřazení, který používá iniciály zaměstnance jako název listu deníku přeřazení. For more information, see [Work with General Journals](ui-work-general-journals.md).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Reclass. Journal Templates**, and then choose the related link.
2. Select the relevant journal template, and then choose the **Batches** action.
3. On the **FA Reclass. Journal Batches** page, fill in the fields as necessary.

## Nastavení kódů tříd dlouhodobého majetku
Kódy tříd dlouhodobého majetku lze použít k seskupení dlouhodobého majetku, například do hmotného a nehmotného majetku.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Classes**, and then choose the related link.
2. Zadejte kódy a názvy tříd, které chcete vytvořit.

## Nastavení kódů podtříd dlouhodobého majetku
Kódy podtříd dlouhodobého majetku se používají k seskupení dlouhodobého majetku do kategorií, jako jsou budovy, vozidla, nábytek nebo stroje.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Subclasses**, and then choose the related link.
2. Zadejte kódy a názvy tříd, které chcete vytvořit.

## Nastavení kódů umístění dlouhodobého majetku
Kódy umístění dlouhodobého majetku slouží k evidenci umístění dlouhodobého majetku, například prodejního oddělení, recepce, správy, výroby nebo skladu. Tyto informace jsou užitečné pro účely pojištění a inventarizace.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA locations**, and then choose the related link.
2. Zadejte kódy a názvy skladových míst dlouhodobého majetku, které chcete vytvořit.

## Evidence vstupních záznamů
If you are using the fixed assets in [!INCLUDE[prod_short](includes/prod_short.md)] for the first time, you must set up the general ledger application area before you set up fixed assets. Způsob, jakým je to provést, závisí na tom, zda je dlouhodobý majetek integrován s financemi.

Následující postup se používá, pokud mají být transakce dlouhodobého majetku zaúčtovány do účtů účetní osnovy.

1. Ujistěte se, že jste dokončili základní postupy nastavení dlouhodobého majetku.
2. Vytvořte kartu dlouhodobého majetku pro každý existující majetek.
3. Vytvořte knihu odpisů dlouhodobého majetku pro každý účel odpisu (například daně a finanční výkazy). Pro každou knihu odpisů musíte definovat podmínky, jako je integrace s účty účetní osnovy.

   Povolte integraci účtů účetní osnovy podle následujících kroků. Nejprve se ujistěte, že je integrace účtů účetní osnovy zakázána je pro všechny knihy odpisů, potom zaúčtujte počáteční položky a nakonec zapněte integraci.
4. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Depreciation Books**, and then choose the related link.
5. Select the relevant depreciation book, and then choose the **Edit** action to open the **Depreciation Book Card** page.
6. On the **Integration** FastTab, make sure all fields are blank by clearing all check marks. Pokud máte více než jednu knihu odpisů, vypněte integraci financí pro každou z nich.
7. Do deníku dlouhodobého majetku zadejte pro každý majetek následující řádky:
   * Řádek s pořizovací cenou.
   * Řádek kumulovaného odpisu do konce předchozího fiskálního roku.
   * A line with the accumulated depreciation from the start of the current fiscal year to the date that [!INCLUDE[prod_short](includes/prod_short.md)] is set to start calculating the depreciation.

   Pokud máte jiné počáteční zůstatky, můžete je také zadat nyní, například odpis a zhodnocení.
8. Po zadání a zaúčtování řádků deníku pro každý majetek zapněte integraci financí v knihách odpisů.

Pokud dlouhodobý majetek není integrován s financemi, přeskočte krok 6 a 8.

## Viz také
[Setting Up Fixed Assets](fa-setup.md)  
[Fixed Assets](fa-manage.md)  
[Finance](finance.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]