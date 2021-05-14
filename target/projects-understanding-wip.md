---
title: WIP Methods for Calculating and Recording Job Progress| Microsoft Docs
description: Describes the different work in process (WIP) methods you can use to post, monitor, and calculate financial information for ongoing jobs that are in progress.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: work in process, work in progress, calculate project WIP
ms.date: 04/01/2021
ms.author: edupont

---
# Understanding WIP Methods
V průběhu projektu se spotřebovávají materiály, zdroje a další výdaje, které je třeba zaúčtovat. Nedokončená výroba (WIP) je funkce, která umožňuje odhadnout finanční hodnotu projektů v hlavní knize v době, kdy projekty stále probíhají. V mnoha případech můžete zaúčtovat výdaje za práci před fakturací projektu. Pokud byly zaúčtovány pouze výdaje, bude finanční výkaz nepřesný.

Chcete-li sledovat hodnotu v hlavní knize, můžete vypočítat cenu nedokončené výroby a zaúčtovat ji do hlavní knihy. For more information, see [Monitor Job Progress and Performance](projects-how-monitor-progress-performance.md).

[!INCLUDE[prod_short](includes/prod_short.md)] supports the following methods of calculating and recording the value of work in process.

| WIP Method | Vzorec výpočtu | Calculation Description |
| --- | --- | --- |
| Hodnota nákladů | Recognized Revenue = Billable Invoiced Price<br /><br /> Estimated Total Costs = Billable Total Price x Budget Cost Ratio<br /><br /> WIP Costs = (Percentage of Completion - Invoiced %) x Estimated Total Costs<br /><br /> Percentage of Completion = Usage Total Costs / Budget Total Costs<br /> Invoiced % = Billable Invoiced Price<br /><br /> Billable Total Price Recognized Costs = Usage Total Costs - WIP | Cost value calculations start by calculating the value of what has been provided by taking a proportion of the estimated total costs based on percentage of completion. Invoiced costs are subtracted by taking a proportion of the estimated total costs based on the invoiced percentage.<br /><br /> This calculation requires that the billable total price, budget total price, and budget total costs be correctly entered for the whole job. |
| Cost of Sales | Recognized Revenue = Billable Invoiced Price<br /><br /> Recognized Costs = Budget Total Cost x Invoiced Percentage<br /><br /> Invoiced % = Billable Invoiced Price / Billable Total Price<br /><br /> (Invoiced % exists as column on job task lines)<br /><br /> WIP Costs = Usage Total Costs – Recognized Costs | Cost of sales calculations begin by calculating the recognized costs. Costs are recognized proportionally based on budget total costs.<br /><br /> This calculation requires that the billable total price and budget total costs be correctly entered for the whole job. |
| Hodnota prodeje | Recognized Costs = Usage Total Costs<br /><br /> Recognized Revenue = Usage Total Price x Expected invoicing ratio<br /><br /> Cost Recovery % = Billable Total Price / Budget Total Price<br /><br /> WIP Sales = Recognized Sales - Billable Invoiced Price | Sales value calculations recognize revenue proportionally based on usage total costs and the expected cost recovery ratio.<br /><br /> This calculation requires that the billable total price and budget total price be correctly entered for the whole job. |
| Procento dokončení | Recognized Costs = Usage Total Costs<br /><br /> Recognized Revenue = Billable Total Price x Percentage of Completion<br /><br /> Percentage of Completion = Usage Total Costs / Budget Total Costs<br /> (Referred to as "Cost Completion %" on job task lines)<br /><br /> WIP Sales = Recognized Sales - Billable Invoiced Price | Percentage of completion calculations recognize revenue proportionally based on the percentage of completion, that is, usage total costs vs. budget costs.<br /><br /> This calculation requires that the billable total price and budget total costs be correctly entered for the whole job. |
| Dokončené smlouvy | WIP Amount = WIP Cost Amount = Usage (Total Cost)<br /><br /> WIP Sales Amount = Billable (Invoiced Price) | Completed contract does not recognize revenue and costs until the job is complete. You may want to do this when there is high uncertainty around the estimates of costs and revenue for the job.<br /><br /> All usage is posted to the WIP Costs account (asset) and all invoiced sales are posted to the WIP Invoiced Sales account (liability) until the job is complete. |

## Viz také
[Project Management](projects-manage-projects.md)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)         
[Sales](sales-manage-sales.md)      
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]