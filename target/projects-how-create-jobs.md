---
title: Create a Job Card for a Job and Specify Tasks
description: For a new project, you create a job card that contains job tasks and planning lines, to help you manage progress and budgets.
author: SorenGP


ms.topic: conceptual
ms.workload: na
ms.search.keywords: project management, task
ms.search.form: 88, 275, 276, 1001, 1002, 1003, 1004, 1005, 1006, 1007, 1020
ms.date: 04/01/2021
ms.author: edupont

---
# Vytváření projektů
Při spuštění nového projektu je nutné vytvořit kartu projektu s integrovanými úlohami projektu a řádky plánování projektu, strukturované ve dvou vrstvách.

První vrstvu tvoří úlohy projektu. Musíte vytvořit alespoň jeden úlohu projektu na projekt, protože všechna účtování odkazuje na úlohu projektu. Pokud ve svém projektu máte alespoň jedu úlohu projektu, můžete založit řádky plánování projektu a zaúčtovat spotřebu do projektu.

Druhá vrstva se skládá z řádků plánování projektu, které specifikují podrobné použití zdrojů, zboží a různých výdajů do hlavní knihy.

Struktura vrstvy umožňuje rozdělit projekt na menší úkoly, a proto umožňuje použít konkrétnější podrobnosti při sestavování rozpočtu, nabídek a evidencí. Kromě toho vám umožní nahlédnout do toho, jak práce postupuje. For example, you can track whether you're meeting designated milestones or if you're on target to meet budget expectations.

> [!TIP]
> Choose the **New Job** action on the **Project Manager** Role Center to launch an assisted setup guide that takes you through the steps of creating a job with integrated tasks and planning lines. Následující postup popisuje, jak provést kroky ručně. For an example of how to create a job manually, see [Video: How to create a job in Dynamics 365 Business Central](https://www.youtube.com/watch?v=VqaPWr7BWmw).

Sometimes the party that is receiving a service is different from the party that is paying the bill. On the **Jobs** page, you can specify the customer who will benefit from the project in the **Sell-to** fields, and the party to invoice in the **Bill-to** fields. You can also provide the following information:

* Where the work will happen by selecting from a list of ship-to addresses for the customer.
* Add information about external references to simplify communication about the project.
* Overwrite the standard financial terms of the project.

## Vytvoření karty projektu
Vytvořte kartu projektu a poté pro ni vytvořte úlohy projektu a řádky plánování projektu.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.
2. Choose the **New** action, and then fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. To specify the job with information on other jobs, choose the **Copy Job** action, fill in the fields as necessary, and then choose the **OK** button.

> [!NOTE]  
> If you are using time sheets with your job, you must also designate a person responsible. Tato osoba může schválit pracovní výkazy pro úlohy zaměstnance přidružené k projektu. For more information, see [Set Up Time Sheets](projects-how-setup-time-sheets.md).

## Vytvoření úlohy projektu
Klíčovou součástí vytvoření projektu je určení různých úkolů, které se v projektu vyskytují. You specify tasks by creating one line per task on the **Tasks** FastTab on the **Job Card** page. Každý projekt musí mít alespoň jednu úlohu.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.
2. Otevřete kartu projektu pro příslušný projekt.
3. On the **Tasks** FastTab, fill in the fields as necessary on a new line.
4. To indent tasks and create a hierarchy, Choose the **Tasks** action, the then choose **Indent Job Tasks** action.
5. Opakujte kroky 3 a 4 pro všechny úlohy, které potřebujete pro projekt.
6. To specify the job tasks with information on other job tasks, choose the **Copy Job Tasks from** action, fill in the fields as necessary, and then choose the **OK** button.

## Vytvoření Řádků plánování projektu
Nové úlohy projektu můžete upřesnit na řádcích plánování projektu. A planning line can capture the information that you want to track for a job. For example, you can track the resources the job requires, or the items that are needed. For example, you have a task to get a customer to approve a job. You associate the task with planning lines for items such as meeting the customer and assigning a resource.

Řádek plánování projektu může mít jeden z následujících typů.

| Typ | Popis |
| --- | --- |
| **Budget** | Poskytuje odhad spotřeby a nákladů na projekt, obvykle v projektu typu čas a materiál. Planning lines of this type can't be invoiced. |
| **Billable** | Poskytuje odhadovanou fakturaci zákazníkovi, obvykle v projektu s pevnou cenou. |
| **Both Budget and Billable** | Poskytuje odhad spotřeby a nákladů na projekt, který se zároveň bude fakturovat. |

> [!NOTE]
> While you enter information on job planning lines, cost information is automatically filled in. For example, the cost, price, and discount for resources and items are based on information from the resource and item.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.
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
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
