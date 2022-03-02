---
title: Production Reports and Analytics
description: See which production reports and analytics are available in the standard version of Business Central so that you can keep track of your business.
author: AndreiPanko

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: reporting
ms.date: 06/01/2021
ms.author: andreipa

---
# Production Reports and Analytics in Business Central

Production reporting in [!INCLUDE [prod_short](includes/prod_short.md)] allows production and business professionals to get insights and statistics about current and past production activities.

## Sestavy

The following table describes some of the key reports in production reporting.

| Sestava | ID Objektu | Popis |
|---------|---------|---------|
| **Quantity Explosion of BOM** | 99000753 | Shows an indented BOM listing for the item or items that you specify in the filters. The production BOM is completely exploded for all levels. |
| **Zboží - schopen provést (časová osa)** | 5871 | Zobrazuje, jak se v průběhu času mění pět různých klíčových údajů o dostupnosti položky kusovníku. These figures change according to expected supply and demand events and to supply that is based on available components that can be assembled or produced.<br>You can use the report to see whether you can fulfill a sales order for an item on a specified date by looking at its current availability in combination with the potential quantities that its components can supply if an assembly order has been started. The report shows you when and how many units of an assembly and production item you can make based on component availability and the item's current availability. To se zobrazuje jako celkové množství.<br>Informace jsou zobrazeny v grafu, kde každý údaj o dostupnosti představuje čáru, která postupuje po časové ose a pohybuje se nahoru a dolů podle toho, jak se mění množství. Údaje o množství pocházejí ze stejného nástroje, který poskytuje informace v okně **Dostupnost zásob za úroveň kusovníku**. |
| **Distribuce náklad.podílu kusovníku** | 5872 | Shows graphically how an assembled or produced item’s cost is distributed through its BOM.<br>Such information can be useful in deciding, for example, whether to change component suppliers, replace internal capacity usage with outsourced labor or vice versa or when reviewing and modifying an item’s bill of material.<br>The first chart in the report shows the total unit cost of the parent item’s components and labor resources broken down in up to five different cost shares, and represented graphically with different colors.<br>The pie chart with the caption *By Material/Labor* shows the proportional distribution between the parent item’s material and labor costs, as well as its own manufacturing overhead. The material cost share includes the item's material costs. Podíl mzdových nákladů zahrnuje náklady na kapacitu, režijní náklady na kapacitu a náklady na subdodávky. The cost shares are displayed differently depending on your choices in the **Show only** field.<br>The pie chart with the caption *By Direct/Indirect* shows the proportional distribution between the parent item's direct and indirect costs. The direct cost share includes the item's material, capacity, and subcontracted costs. The indirect cost share includes capacity overhead and manufacturing overhead.<br>The table at the bottom of the report is included when you select the **Include Details** check box. It shows selected values from the BOM Cost Shares window by single level or rolled up, depending on your choices in the **Show Cost Shares as** field. |
| **Detailed Calculation** | 99000756 | Shows a cost list per item taking into account the scrap. |
| **Where-Used (Top Level)** | 99000757 | Shows where and in what quantities the items are used in the product structure.<br>The report shows only the item as where-used, when the base item is used as the top-level item. For example, if item "A" is used to produce item "B", and item "B" is used to produce item "C", the report will show item B if you run this report for item A. If you run this report for item B, then item C will be shown as where-used.<br>You can also open the **Where-Used Line** page directly from the item. |
| **Item BOM Compare list** | 99000758 | This report gives you the possibility to compare similar final products concerning the costs. You will see a listing with all components and their costs as well the needed quantities. The calculation date is normally set to the work date. |
| **Production Order Statistics** | 99000791 | Specifies the various costs that have accumulated for the selected production order.<br>The content of the report are very similar to the **Production Order Statistics** page.<br>For production orders that use the *Make-to-Order* manufacturing policy, the window only shows material and capacity cost of items at the highest BOM level. |
| **Capacity Task list** | 99000780 | Shows the production orders that are waiting to be processed at the work centers and machine centers. Printouts are made for the capacity of the work center or machine center). The report includes information such as starting and ending time, date per production order and input quantity. |
| **Work Center Load** or **Machine Center Load** | 99000783 or 99000784 | Both reports show a list for the load on a work or machine center. The load on a work/machine center is the sum of the required number of times that all the planned and actual orders are run on the work center in a specified period. |
| **Výr. Order Shortage list** | 99000788 | This report can be used to see all components that are not available because of missing stock. So, this overview can be used to see in time, if the timeline for a planned or released production order if the planned time can be kept. |


## Úlohy

Následující články popisují některé klíčové úlohy pro analýzu stavu vaší firmy:

* [View Load on Work and Machine Centers](production-how-to-view-the-load-on-work-centers.md)
* [Zobrazit dostupnost zboží](inventory-how-availability-overview.md)

## Viz také

[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
