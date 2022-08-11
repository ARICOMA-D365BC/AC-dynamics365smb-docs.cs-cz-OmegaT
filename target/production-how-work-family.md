---
title: Work with Production Families in Manufacturing
description: The main task in customizing a base calendar for your company, or one of its business partners, is to enter any changes to working and nonworking day status.
author: SorenGP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 99000790, 99000791, 99000792, 99000793
ms.date: 04/01/2021
ms.author: edupont

---
# Práce s výrobními skupinami zboží

Produkční skupina je skupina jednotlivého zboží, jejichž vztah je založen na podobnosti jejich výrobních procesů. Vytvářením výrobních skupin lze některé položky vyrábět dvakrát nebo více v jedné výrobě, což optimalizuje spotřebu materiálu.

In the **Quantity** field on the **Family** page, you enter the quantity that will be produced when the whole family has been manufactured once.

## Příklad

Při procesu děrování mohou být čtyři kusy stejného zboží vyrobeny z jednoho listu a 10 kusů z jiného, odlišného a současně. Děrovací stroj děruje všech 14 kusů v jednom kroku.

Vytváření výrobních skupin snižuje množství šrotu, protože to, co by za normálních okolností zbylo, bude při výrobě velkých kusů použito k výrobě malých kusů.

## Nastavení skupiny výrobků

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Families**, and then choose the related link.
2. Vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## Výroba na základě skupiny výrobků

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Firm Planned Prod. zakázky** a poté vyberte související odkaz.
2. Vytvoření nové výrobní zakázky. For more information, see [Create Production orders](production-how-to-create-production-orders.md).
3. In the **Source Type** field, select **Family**.
4. In the **Source No.** field, select the relevant production family.

## Viz také

[Create Production BOMs](production-how-to-create-production-boms.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)
[Planning](production-planning.md)   
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]