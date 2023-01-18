---
title: Set Up FA Depreciation
description: There are various methods of depreciation. In Business Central you define an asset's depreciation method on the **Fixed Asset Card** page.
author: edupont04


ms.topic: conceptual
ms.search.keywords: write down
ms.date: 06/28/2021
ms.author: edupont
---

# Nastavení odpisování dlouhodobého majetku

Pro přípravu účetní závěrky a přiznání k dani z příjmu můžete použít různé metody odpisů. Mnoho velkých korporací používá ve svých účetních závěrkách lineární odpisy, protože to obecně umožňuje vykazovat vyšší zisky. Pro účely daně z příjmu však mnoho podniků používá metodu zrychleného odpisování, jako je odpis s klesajícím zůstatkem. You define an asset's depreciation method with the **Depreciation Method** field on the **Fixed Asset Card** page. For more information about what the different methods do, see [Depreciation Methods](fa-depreciation-methods.md).

You set up depreciation books where you define the different ways depreciation must be calculated for different types of fixed assets. Each depreciation book specifies individual depreciation terms. Můžete například určit, že v jedné knize se bude dlouhodobý majetek odepisovat po dobu tří a v druhé pěti let.

Po vytvoření příslušných odpisových knih musíte ke každému dlouhodobému majetku přiřadit právě jednu nebo více odpisových knih. Kniha odpisů, která je přiřazena dlouhodobému majetku, se označuje jako Kniha odpisů dlouhodobého majetku. Pro dlouhodobý majetek můžete nastavit neomezený počet knih odpisů.

## Vytvoření knihy odpisů

V knize odpisů dlouhodobého majetku určíte způsob odpisování dlouhodobého majetku. Chcete-li vyhovět různým způsobům odpisování, můžete nastavit několik knih odpisů.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Depreciation Books**, and then choose the related link.
2. On the **Depreciation Books List** page, choose the **New** action.
3. On the **Depreciation Book Card** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

   > [!NOTE]  
   > You can record fixed asset transactions on the **Fixed Asset G/L Journal** page or on the **Fixed Asset Journal** page, depending on whether the transactions are for financial reporting or for internal management. Dalším krokem definujte, který typ deníku se ve výchozím nastavení používá pro různé aktivity dlouhodobého majetku.
4. On the **Integration** FastTab, select the check box for each fixed asset activity whose transactions you want to post using the **Fixed Asset G/L Journal** page.
5. Opakujte kroky 2 až 4 pro každou metodu odpisování nebo metodu účtování, kterou chcete přiřadit dlouhodobému majetku jako odpisovou knihu.

> [!IMPORTANT]
> Choose the **Use Rounding in Periodic Depr.** field to round the calculated periodic depreciation amounts to whole numbers. For example, if your company also uses invoice rounding to whole numbers in the **General Ledger Setup** page, rounding also depreciation amounts to whole numbers can help provide transparency.

For example, if you dispose of a fixed asset where the depreciation book does not specify rounding, but your company's general ledger setup requires rounding, then, when you dispose of the fixed asset, you will see an error message that an amount must be rounded on a ledger entry.

## Přiřazení knihy odpisů k dlouhodobému majetku
1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png " Řekněte mi, co chcete dělat") zadejte **Dlouhodobý majetek<x5/> a vyberte související odkaz.
2. Vyberte dlouhodobý majetek, pro který chcete nastavit knihu odpisů dlouhodobého majetku.
3. On the **Depreciation Book** FastTab, fill in the fields as necessary.
4. If you need to assign more than one depreciation book to the fixed asset, choose the **Add More Depreciation Books** action.
5. Alternatively, choose the **Depreciation Books** action to specify one or more fixed asset depreciation books.

   > [!NOTE]  
   > When you use the manual depreciation method, you must enter depreciation manually in the fixed asset G/L journal. The **Calculate Depreciation** function omits fixed assets that use the manual depreciation method. Tuto metodu můžete použít pro majetek, který nepodléhá odpisům, například pozemky.

   > [!NOTE]  
   > When you use the user-defined depreciation method, you need to assign the depreciation book in a different way. For more information, see [Set Up User-Defined Depreciation Method](fa-how-setup-user-defined-depreciation-method.md).

## Přiřazení knihy odpisů k více DM pomocí dávkové úlohy
If you want to assign a depreciation book to several fixed assets, you can use the **Create FA Depreciation Books** batch job to create fixed asset depreciation books.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png " Řekněte mi, co chcete dělat") zadejte **Dlouhodobý majetek<x5/> a vyberte související odkaz.
2. Select the fixed asset that you want to set up a assign a depreciation book to, and then choose the **Edit** action.
3. On the **Depreciation Book Card** page, choose the **Create FA Depreciation Books** action.
4. On the **Create FA Depreciation Books** page, fill in the **Depreciation Book** field.
5. Choose the **Copy from FA No.** field, and then select the fixed asset number that you want to use as the basis for creating new fixed asset depreciation books.

   Pokud toto pole vyplníte, budou pole odpisů v nových knihách odpisů dlouhodobého majetku obsahovat stejné informace jako odpovídající pole v knize odpisů dlouhodobého majetku, ze které kopírujete. Pokud chcete vytvořit nové knihy odpisů dlouhodobého majetku s prázdnými poli odpisů, ponechejte toto pole prázdné.
6. On the **Fixed Asset** FastTab, you can set a filter to select the assets that you want to create the fixed asset depreciation books for.
7. Zvolte tlačítko **OK**.

## Nastavení typů účtování odpisů
For each depreciation book, you must set up how you want [!INCLUDE[prod_short](includes/prod_short.md)] to handle various posting types. Například, zda by účtování mělo být debetní nebo kreditní a zda by typ účtování měl být zahrnut do odpisovatelného základu.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Depreciation Books**, and then choose the related link.
2. Select the depreciation book that you want to set up, and them choose the **FA Posting Type Setup** action.
3. On the **FA Posting Type Setup** page, fill in the fields as necessary.

   > [!NOTE]  
   > You cannot insert or delete lines on the **FA Posting Type Setup** page. Můžete upravit pouze existující řádky.

Doporučujeme neměnit nastavení pro odpisy u položek, které již byly zaúčtovány. Změny neovlivní položky, které jsou již zaúčtovány, což by učinilo statistiky knihy odpisů zavádějícími.

## Nastavení výchozích šablon a dávek pro odpisy dlouhodobého majetku
Pro každou knihu odpisů definujete výchozí nastavení šablon a dávek. You use these defaults to duplicate lines from one journal to another, create journal lines using the **Calculate Depreciation** or **Index Fixed Assets** batch jobs, duplicate acquisition costs in the insurance journal.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Depreciation Books**, and then choose the related link.
2. Select the depreciation book that you want to define default journals for, and then choose the **FA Journal Setup** action.
3. If you want to have a default setup for each user, choose the **User ID** field to select from the **Users** page.
4. V ostatních polích vyberte šablonu deníku nebo list deníku, který musí být použit ve výchozím nastavení.

## Fiscal Year 365 Days Field Depreciation

When the Calculate Depreciation batch job calculates depreciations, the batch job normally uses a standardized year of 360 days where each of the 12 months has 30 days.

If you select this field, the Calculate Depreciation batch job uses the calendar year of 365 days instead, where each month is calculated with the same number of days as in the calendar. The only exception is February in leap years, which the batch job will treat as having 28 days and not 29. Because of that, all years, also leap years, are considered to have 365 days.


## Viz také
[Setting Up Fixed Assets](fa-setup.md)  
[Fixed Assets](fa-manage.md)  
[Finance](finance.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
