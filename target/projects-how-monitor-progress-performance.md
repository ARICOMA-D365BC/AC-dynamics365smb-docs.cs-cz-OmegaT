---
title: Define a WIP Method and Monitor Job Progress| Microsoft Docs
description: Describes how you can create a work in process (WIP) method and calculate WIP to estimate the financial value of jobs while they are ongoing.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: project management, KPI, work in process, work in progress
ms.date: 04/01/2021
ms.author: edupont

---
# Sledování průběhu a výkonu Projektů
V průběhu projektu se spotřebovávají materiály, zdroje a další výdaje, které je třeba zaúčtovat. Nedokončená výroba (WIP) je funkce, která umožňuje odhadnout finanční hodnotu projektů v hlavní knize v době, kdy projekty stále probíhají. V mnoha případech můžete zaúčtovat výdaje za práci před fakturací projektu. Pokud byly zaúčtovány pouze výdaje, bude finanční výkaz nepřesný. For more information, see [Understanding WIP Methods](projects-understanding-wip.md).

Chcete-li sledovat hodnotu v hlavní knize, můžete vypočítat cenu nedokončené výroby a zaúčtovat ji do hlavní knihy.

Nedokončenou výrobu lze vypočítat na základě následujících informací:

* Hodnota nákladů
* Hodnota prodeje
* Uznatelné náklady
* Procento dokončení
* Dokončené smlouvy

Chcete-li zobrazit výsledek jinou metodou, můžete metodu změnit a znovu vypočítat nedokončenou výrobu. Počet výpočtů nedokončené výroby není omezen. Nedokončená výroba se pouze vypočítá, ale nezaúčtuje se. Po výpočtu nedokončené výroby můžete zaúčtovat.

## Vytvoření projektu s nedokončenou výrobou
Můžete vytvořit projekt s nedokončenou výrobou, který bude odrážet potřeby Vaší společnosti. Po vytvoření můžete nastavit nedokončenou výrobu jako výchozí metodu kalkulace projektu, která bude použita ve Vaší společnosti.

> [!NOTE]
> Jakmile použijete novou metodu nedokončené výroby na položky, není možné tuto metodu smazat nebo měnit.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job WIP Methods**, and then choose the related link.
2. Choose the **New** action, and then fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Zavřete stránku.
4. To make this new method the default, choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs Setup**, and then choose the related link.
5. In the **Default WIP Method** field, choose the method from the list.

## Definování Nedokončené výroby pro projekt
Při vytváření nového projektu musíte určit, která metoda nedokončené výroby projektu se použije. V některých případech byla pro Vás jako výchozí nastavena metoda nedokončené výroby projektu, kterou můžete použít.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi ](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Projekty** a poté vyberte související odkaz.
2. Vyberte akci **Nový**. For more information, see [Create Jobs](projects-how-create-jobs.md).
3. On the **Job Card** page, in the **WIP Method** field, select a WIP method from the list. Pokud byla definována výchozí metoda, můžete v případě potřeby vybrat jinou možnost.

## Výpočet Nedokončené výroby
Můžete určit částku nedokončené výroby, která má být zaúčtována na rozvahové účty pro vykazování na konci období. You use the **Job Calculate WIP** batch job to do this.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Calculate WIP**, and then choose the related link.
2. Choose the **Calculate WIP** action.
3. On the **Job Calculate WIP** page, fill in the fields as necessary.
4. Zvolte tlačítko **OK**.

> [!NOTE]  
> Úloha počítá pouze nedokončenou výrobu. Nejedná se o účtování. To do so, you must run the **Post WIP to G/L** batch job when you have calculated the WIP. Další informace naleznete v následujícím postupu.

## Účtování Nedokončené výroby
Když jste vypočítali nedokončenou výrobu, můžete jí zaúčtovat na rozvahové účty pro vykazování konce období. You use the **Job Post WIP to G/L** batch job to do this.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Post WIP to G/L**, and then choose the related link.
2. On the **Job Post WIP to G/L** page, fill in the fields as necessary.
3. Zvolte tlačítko **OK**.

## To calculate and post job completion entries
When you have completed all activities for a job, including usage posting and invoicing, you must update the job to have a **Status** of **Completed**. Then, you must reverse any WIP that has been posted to the general ledger.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi ](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Projekty** a poté vyberte související odkaz.
2. Select an open job, and then choose the **Edit** action.
3. In the **Status** field, select **Completed**.
4. Follow the assistance steps to calculate and post WIP. Alternatively, follows steps 5 and 6 to do so manually.
5. Choose the **Calculate WIP** action.
6. On the **Job Calculate WIP** page, fill in the fields as necessary.

   The job WIP entries created by running the batch job will have the **Job Complete** check box selected to show that they are completion entries.
7. Choose the **Job Post WIP to G/L** action.
8. On the **Job Post WIP to G/L** page, fill in the fields as necessary.

   The job WIP general ledger entries created by running the batch job will have the **Job Complete** check box selected to show they are completion entries.

## Zobrazení Položek projektu
Všechny položky související s projektem jsou zaznamenány v žurnálech a jsou číslovány postupně, počínaje 1. Z žurnálu projektu můžete získat přehled o všech položkách projektu.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Registers**, and then choose the related link.
2. Select a relevant register, and then choose **Job Ledger** action.

On the **Job Ledger Entries** page you can review the entries that are associated with any job.

## Viz také
[Managing Projects](projects-manage-projects.md)
[Managing Inventory Costs](finance-manage-inventory-costs.md)   
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)         
[Sales](sales-manage-sales.md)      
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
