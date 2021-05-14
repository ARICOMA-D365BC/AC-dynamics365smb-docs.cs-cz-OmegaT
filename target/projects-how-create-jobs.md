---
title: Create a Job Card for a Job and Specify Tasks| Microsoft Docs'
description: For a new project, you create a job card that contains job tasks and planning lines, to help you manage progress and budgets.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.workload: na
ms.search.keywords: project management, task
ms.date: 04/01/2021
ms.author: edupont

---
# Vytváření projektů
Při spuštění nového projektu je nutné vytvořit kartu projektu s integrovanými úlohami projektu a řádky plánování projektu, strukturované ve dvou vrstvách.

První vrstvu tvoří úlohy projektu. Musíte vytvořit alespoň jeden úlohu projektu na projekt, protože všechna účtování odkazuje na úlohu projektu. Pokud ve svém projektu máte alespoň jedu úlohu projektu, můžete založit řádky plánování projektu a zaúčtovat spotřebu do projektu.

Druhá vrstva se skládá z řádků plánování projektu, které specifikují podrobné použití zdrojů, zboží a různých výdajů do hlavní knihy.

Struktura vrstvy umožňuje rozdělit projekt na menší úkoly, a proto umožňuje použít konkrétnější podrobnosti při sestavování rozpočtu, nabídek a evidencí. Kromě toho vám umožní nahlédnout do toho, jak práce postupuje. Můžete například sledovat, zda dodržujete stanovené milníky nebo zda jste v cíli, abyste splnili očekávání rozpočtu.

> [!TIP]
> Choose the **New Job** action on the **Project Manager** Role Center to launch an assisted setup guide that takes you through the steps of creating a job with integrated tasks and planning lines. Následující postup popisuje, jak provést kroky ručně. For an example of how to create a job manually, see [Video: How to create a job in Dynamics 365 Business Central](https://www.youtube.com/watch?v=VqaPWr7BWmw).

## Vytvoření karty projektu
Vytvořte kartu projektu a poté pro ni vytvořte úlohy projektu a řádky plánování projektu.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi ](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Projekty** a poté vyberte související odkaz.
2. Choose the **New** action, and then fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. To specify the job with information on other jobs, choose the **Copy Job** action, fill in the fields as necessary, and then choose the **OK** button.

> [!NOTE]  
> Pokud ve svých projektech používáte pracovní výkazy, musíte také určit odpovědnou osobu. Tato osoba může schválit pracovní výkazy pro úlohy zaměstnance přidružené k projektu. For more information, see [Set Up Timesheets](projects-how-setup-time-sheets.md).

## Vytvoření úlohy projektu
Klíčovou součástí vytvoření projektu je určení různých úkolů, které se v projektu vyskytují. You do this by adding new lines on the **Tasks** FastTab on the **Job Card** page, one task per line. Každý projekt musí mít alespoň jednu úlohu.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi ](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Projekty** a poté vyberte související odkaz.
2. Otevřete kartu projektu pro příslušný projekt.
3. On the **Tasks** FastTab, fill in the fields as necessary on a new line.
4. To indent tasks and create a hierarchy, Choose the **Tasks** action, the then choose **Indent Job Tasks** action.
5. Opakujte kroky 3 a 4 pro všechny úlohy, které potřebujete pro projekt.
6. To specify the job tasks with information on other job tasks, choose the **Copy Job Tasks from** action, fill in the fields as necessary, and then choose the **OK** button.

## Vytvoření Řádků plánování projektu
Nové úlohy projektu můžete upřesnit na řádcích plánování projektu. Řádek plánování lze použít k zachycení všech informací, které chcete sledovat na projektu. Řádky plánování můžete použít k přidání informací, například jaké zdroje jsou požadovány, nebo k zachycení zboží potřebných k provedení projektu. Pokud například máte úkol získat zákazku ze strany zákazníka, můžete ji přiřadit k plánovacím řádkům pro položky, jako je schůzka se zákazníkem a přiřazení zdroje.

Řádek plánování projektu může mít jeden z následujících typů.

| Typ | Popis |
| --- | --- |
| **Budget** | Poskytuje odhad spotřeby a nákladů na projekt, obvykle v projektu typu čas a materiál. Řádky plánování tohoto typu nelze fakturovat. |
| **Billable** | Poskytuje odhadovanou fakturaci zákazníkovi, obvykle v projektu s pevnou cenou. |
| **Both Budget and Billable** | Poskytuje odhad spotřeby a nákladů na projekt, který se zároveň bude fakturovat. |

**Note**. Při zadávání informací do řádků plánování projektu se automaticky vyplňují informace o nákladech. Například náklady, cena a sleva na zdroje a položky jsou původně založeny na informacích, které jsou definovány na kartách zdrojů a položek.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi ](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Projekty** a poté vyberte související odkaz.
2. Otevřete příslušnou kartu projektu.
3. Select a job task for which the **Job Task Type** field contains **Posting**, and then choose the **Job Planning Lines** action.
4. On the **Job Planning Lines** page, on a new line, fill in the fields as necessary.
5. Opakujte kroky 3 a 4 pro všechny řádky plánování, které potřebujete pro úlohu projektu.

## Viz také

[Project Management](projects-manage-projects.md)  
[Video: How to create a job in Dynamics 365 Business Central](https://www.youtube.com/watch?v=VqaPWr7BWmw)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]