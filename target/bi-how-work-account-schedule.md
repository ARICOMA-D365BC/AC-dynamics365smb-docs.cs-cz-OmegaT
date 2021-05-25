---
title: Build financial reports using account schedules
description: Describes how to use account schedules to create various views and report for analyzing financial performance data.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: bi, power BI, analysis, KPI
ms.date: 04/01/2021
ms.author: edupont

---
# Příprava finančních výkazů s účetními schématy a kategoriemi účtů

Pomocí účetních schémat získáte přehled o finančních datech uložených v účetní osnově. Účetní schémata analyzují údaje v účetních závěrkách a porovnávají položky hlavní knihy s položkami rozpočtu hlavní knihy. Výsledky se zobrazují v grafech v Centru rolí, například v grafu cashflow a v sestavách, jako je rozvaha výsledovka.

You access these two reports, for example, with the **Financials Statements** action on the Business Manager and Accountant Role Centers.

[!INCLUDE[prod_short](includes/prod_short.md)] provides a few sample account schedules that you can use right away, or you can set up your own rows and columns to specify the figures to compare. Můžete například vytvořit účetní schémata pro výpočet ziskových marží pro dimenze, jako jsou oddělení nebo skupiny zákazníků. Můžete vytvořit tolik vlastních finančních výkazů, kolik chcete.

Nastavení účetních schémat vyžaduje pochopení finančních dat v účetní osnově. Můžete například zobrazit položky hlavní knihy jako procenta položek rozpočtu. To vyžaduje vytvoření rozpočtů. For more information, see [Create G/L Budgets](finance-how-create-budgets.md).

## Účetní schémata

Účetní schémata se používají k uspořádání účtů uvedených v účetní osnově způsobem, který je vhodný pro prezentaci informací o těchto účtech. Můžete nastavit různá rozvržení pro definování informací, které chcete získat z účetní osnovy. Jednou z hlavních funkcí účetních schémat je poskytnout místo pro výpočty, které nelze provést přímo v účetní osnově, jako je například vytváření mezisoučtů pro skupiny účtů, které mohou být zahrnuty do nových součtů a pak mohou být použity v jiných součtech. Uživatelé mohou například vytvářet účetní schémata pro výpočet ziskových marží pro takové dimenze, jako jsou oddělení nebo skupiny zákazníků. Kromě toho lze filtrovat položky hlavní knihy a položky rozpočtu hlavní knihy, například podle čisté změny nebo částky Má dáti.

Pomocí vzorců můžete také porovnat dvě nebo více účetních schémat a rozložení sloupců. Tento druh porovnání poskytuje možnost:

* Vytvářet vlastní finanční sestavy.
* Vytvářet tolik účetních schémat kolik bude potřeba, každý s jedinečným názvem.
* Nastavit různá rozvržení sestav a tisk sestavy s aktuálními čísly.

## Kategorie finančního účtu

Kategorie finančních účtů můžete použít ke změně rozvržení finančních výkazů. After you set up your account categories on the **G/L Account Categories** page, and you choose the **Generate Account Schedules** action, the underlying account schedules for the core financial reports are updated. The next time you run one of these reports, such as the **Balance Statement** report, new totals and subentries are added, based on your changes.

> [!NOTE]
> The top-level account categories, such as the **Liabilities** node are fixed and you cannot add your own. However, you can delete and add account categories at lower levels and change their structure to define how the related account schedule appears in reports.
>
> It is recommended to create and structure your own lower-level G/L account categories from scratch, in a hierarchy if needed, rather than try to rearrange the existing ones. For example, you can restructure the **Liabilities** node to contain a new **Equity** node followed by the **Current Liabilities** and **Long Term Liabilities** nodes.

## Vytvoření nového účetního schématu

Účetní schémata slouží k analýze číselných údajů na účtech hlavní knihy nebo k porovnání položek hlavní knihy s položkami rozpočtu hlavní knihy. Můžete například zobrazit položky hlavní knihy jako procenta položek rozpočtu.

The account schedules in the standard version of [!INCLUDE[prod_short](includes/prod_short.md)] are the basis of the standard financial reports, which may not suit the needs of your business. Chcete-li rychle vytvořit vlastní finanční sestavy, můžete začít kopírováním existujícího účetního schématu. Viz krok 3 níže.

The **Acc. Schedule Overview** page is where you preview the financial report that the account schedule defines. In the following, it is important to understand that what you set up as account schedule rows and columns can only be seen and validated on the **Acc. Schedule Overview** page, which you open from an account schedule by choosing the **Overview** action. The **Account Schedule** page itself is only a setup area.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Účetní schémata** a poté vyberte související odkaz.
2. On the **Account Schedules** page, choose the **New** action to create a new account schedule name.
3. Alternatively, choose the **Copy Account Schedule** action, fill in the two fields, and then choose the **OK** button.
4. Podle potřeby vyplňte pole. In the **Default Column Layout** field select an existing layout. Pokud chcete, můžete jej upravit později.

   Rozložení sloupců slouží k definování sloupců pro různé parametry, podle kterých jsou zobrazena finanční data na řádcích. Můžete například navrhnout rozložení sloupce pro porovnání čisté změny a zůstatku za stejné období letošního a minulého roku ve čtyřech sloupcích. For more information, see [To edit a column layout](bi-how-work-account-schedule.md#to-edit-a-column-layout).

5. Choose the **Edit Account Schedule** action.
6. Vytvořte řádek pro každý finanční prvek, který chcete v přehledu zobrazit, například jeden řádek pro aktuální aktiva a druhý řádek pro dlouhodobá aktiva. Inspiraci najdete v existujících účetních schématech v demonstrační společnosti CRONUS.
7. Choose the **Overview** action to see the resulting financial report.
8. Na stránce **Náhled  Schedule Overview** page, in the **Column Layout Name** field, select another column layout to see the financial data by other parameters.
9. Zvolte tlačítko **OK**.

Nyní jste definovali základ účetního schématu, řádky finančních dat, která mají být zobrazena a existující rozložení sloupců, které zobrazí data na řádcích podle různých parametrů. Pokud výchozí rozložení sloupců, které jste vybrali v kroku 4, nevyhovuje vašemu účelu, postupujte podle následujícího postupu.

### Úprava rozložení sloupců

Rozložení sloupců slouží k definování sloupců, které mají být zahrnuty do výsledné sestavy. Můžete například navrhnout rozložení pro porovnání čisté změny a zůstatku za stejné období tohoto roku a loňského roku.

> [!NOTE]
> A printed/previewed/saved version of an account schedule can display a maximum of five columns. If the account schedule is only meant for analysis on the **Acc. Schedule Overview** page, you can create as many columns as you want.

1. On the **Account Schedules** page, select the relevant account schedule, and then choose the **Edit Column Layout Setup** action.
2. On the **Column Layouts** page, create a row for each column by which financial data is shown in the financial report. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Zvolte tlačítko **OK**.
4. Open the **Acc. Schedule Overview** page from time to time to verify that the new column layout works as intended.

> [!NOTE]
> The columns that you define on each row represent columns 3 and up on the **Acc. Schedule Overview** page. The first two columns, **Row No.** and **Description**, are fixed.

### Vytvoření sloupce, který vypočítává procenta

Někdy můžete chtít zahrnout sloupec do účetního schématu pro výpočet procent z celkového počtu. Například, pokud máte několik řádků, které rozdělují tržby podle dimenzí, můžete chtít, aby sloupec označil procento z celkových prodejů, které každý řádek představuje.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Účetní schémata** a poté vyberte související odkaz.
2. On the **Account Schedule Names** page, select an account schedule.
3. Choose the **Edit Account Schedule** action to set up an account schedule row to calculate the total on which the percentages will be based.
4. Vložte řádek bezprostředně nad první řádek, pro který chcete zobrazit procento.
5. Fill in the fields on the line as follows: In the **Totaling Type** field, enter **Set Base for Percent**. In the **Totaling** field, enter a formula for the total that the percentage will be based on. For example, if row 11 contains the total sales, enter **11**.
6. Choose the **Edit Column Layout Setup** action to set up a column.
7. Fill in the fields on the line as follows: In the **Column Type** field, select **Formula**. In the **Formula** field, enter a formula for the amount that you want to calculate a percentage for, followed by %. For example, if column number N contains the net change, enter **N%**.
8. Opakujte kroky 4 až 7 pro každou skupinu řádků, které chcete rozdělit podle procent.

## Nastavení účetních schémat s náhledy

Účetní schémata můžete použít k vytvoření výkazu porovnávajícího čísla hlavní knihy a obecné údaje o rozpočtu.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Účetní schémata** a poté vyberte související odkaz.
2. On the **Account Schedule Names** page, select an account schedule.
3. Choose the **Edit Account Schedule** action
4. On the **Account Schedule** page, in the **Name** field, select the default account schedule name.
5. Choose the **Insert Accounts** action.
6. Select the accounts that you want to include in your statement, and then choose the **OK** button.

   Účty jsou nyní vloženy do vašeho účetního schématu. Pokud chcete, můžete také změnit rozložení sloupce.
7. Choose the **Overview** action.
8. Na stránce **Náhled  Schedule Overview** page, on the **Dimension Filters** FastTab, set the budget filter to the desired filter name.
9. Zvolte tlačítko **OK**.

Nyní můžete zkopírovat a vložit výkaz rozpočtu do tabulky.

## Porovnání účetních období pomocí vzorců za období

Účetní schéma může porovnat výsledky různých účetních období, například tento měsíc oproti stejnému měsíci loňského roku. To do that, open the **Column Layout** page, and personalize it by adding the **Comparison Period Formula** field as a column. Více informací viz [Přizpůsobení pracovního prostoru](ui-personalization-user.md). You can then set that field to a period formula.

Účetní období nemusí odpovídat kalendáři, ale každý fiskální rok musí mít stejný počet účetních období, i když každé období se může lišit délkou.

[!INCLUDE[prod_short](includes/prod_short.md)] uses the period formula to calculate the amount from the comparison period in relation to the period represented by the date filter on the report request. Období srovnání je založeno na období počátečního data filtru data. Zkratky pro specifikace období jsou:

| Zkratka | Popis |
| ------------ | ------------------------------------------------------------------------------------- |
| P | Období |
| LP | Last period of a fiscal year, half-year, or quarter. |
| CP | Current period of a fiscal year, half-year, or quarter. Use CP in formulas to set the period that starts or ends the formula. For example, FY\[1..CP\] denotes the time from the beginning of the current fiscal year to the current period. |
| FY | Fiskální rok. For example, FY\[1..3\] denotes first quarter of the current fiscal year |

Příklady vzorců:

| Vzorec | Popis |
| --------------- | ----------------------------------------------------------------------------------------------- |
| \<Blank\> | Aktuální období |
| \-1P | Předchozí období |
| \-1FY\[1..LP\] | Celý předchozí fiskální rok |
| \-1FY | Aktuální období v předchozím fiskálním roce |
| \-1FY\[1..3\] | První čtvrtletí předchozího fiskálního roku |
| \-1FY\[1..CP\] | From the beginning of previous fiscal year to current period in previous fiscal year, including both periods |
| \-1FY\[CP..LP\] | From current period in previous fiscal year to last period of previous fiscal year, including both periods |

If you want to calculate by regular time periods, you must enter a formula in the **Comparison Date Formula** field instead. For example, if the field is set to -1Y, [!INCLUDE [prod_short](includes/prod_short.md)] compares to the same period 1 year earlier.

> [!NOTE]
> It is not always transparent which periods you are comparing because you can set a date filter on a report that spans different dates than the accounting periods that are reflected in the data in the chart of accounts. For example, you create an account schedule where you want to compare this period with the same period last year, so you set the **Comparison Date Formula** field to *-1FY*. Poté spustíte sestavu 28. února a nastavíte filtr data na leden a únor. V důsledku toho účetní schéma porovnává leden a únor letošního roku s lednem loňského roku, což je jediné dokončené účetní období dvou za loňský rok.

For more information about date formulas, see [Working with Calendar Dates and Times](ui-enter-date-ranges.md).

## Zobrazit související školení na webu [Microsoft Learn](/learn/modules/configure-financial-reports-dynamics-365-business-central/index)

## Viz také

[Business Intelligence](bi.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]