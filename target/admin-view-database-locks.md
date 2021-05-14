---
title: "View Database Locks"
description: Learn how you can view information about any database locks right from the client interface in Business Central.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2021
ms.author: jswymer
---
# Prohlížení zámku databáze

Uzamykání databáze řídí přístup uživatelů ke stejným datům současně. Aby byly transakce chráněny před jinými transakcemi upravujícími stejná data, první transakce zamkne data. Zámek zůstává, dokud není transakce dokončena.

Uživatelé mohou být blokováni v provádění transakcí na uzamčených datech. Obvykle se jim zobrazí zpráva, která označuje stav uzamčení.

## Zobrazení zámků databáze

Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Database Locks**, and then choose the related link.

The **Database Locks** page gives snapshot of all current database locks.

For more information about database locking, see [Monitoring Database Locks](/dynamics365/business-central/dev-itpro/administration/monitor-database-locks) in the Business Central Developer and IT Pro help.

## Viz také

[Monitor Database Locks](/dynamics365/business-central/dev-itpro/administration/monitor-database-locks)


[!INCLUDE[footer-include](includes/footer-banner.md)]