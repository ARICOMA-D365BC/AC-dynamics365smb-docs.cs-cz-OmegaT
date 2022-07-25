---
title: Error Message "Posting Date is not within your range of allowed posting dates"
description: Resolve the error behind the message "Posting date is not within your range of allowed posting dates" when running the Adjust Cost - Item Entries batch job.
author: edupont04


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 09/17/2021
ms.author: edupont

---

# Error message: "Posting Date is not within your range of allowed posting dates…"

When using the **Adjust Cost - Item Entries** batch job you may run into the following error message:

**Posting date is not within your range of allowed posting dates**

This error message indicates that the user is not allowed to post entries for the date in question, and this can be remedied by changing the user setup.

## Change the user setup

| ID uživatele | Allow Posting From | Allow Posting To |
|---------|---------|--------|
| EUROPE | 2020-09-11 | 2020-09-30 |

The user in this case has an allowed posting date range from September 11th to September 30th and is therefore not allowed to post the Adjustment Value Entry with Posting Date September 10th.

### Overview of involved posting date setup

#### Inventory Periods

| Koncové datum | Jméno | Closed |
|---------|---------|---------|
| 2020-01-31 | January 2020 | Ano |
| 2020-02-28 | February 2020 | Ano |
| 2020-03-31 | March 2020 | Ano |
| 2020-04-30 | April 2020 | Ano |
| 2020-05-31 | May   2020 | Ano |
| 2020-06-30 | June   2020 | Ano |
| 2020-07-31 | July  2020 | Ano |
| 2020-08-31 | August   2020 | Ano |
| 2020-09-30 | September   2020 |         |
| 2020-10-31 | October   2020 |         |
| 2020-11-30 | November   2020 |         |
| 2020-12-31 | December   2020 |         |

#### Nastavení financí

| Pole | Hodnota |
|---------|---------|
| Allow Posting From: | 2020-09-10 |
| Allow Posting To: | 2020-09-30 |
| Register Time: |         |
| Local Address Format: | Post Code |

#### User Setup

| ID uživatele | Allow Posting From | Allow Posting To |
|---------|---------|--------|
| USERNAME | 2020-09-10 | 2020-09-30 |

Assigning a wider allowed posting date range, as in Inventory Period or General Ledger Setup, makes it possible to avoid the conflict that causes the error message. The Adjustment Value Entry with Posting Date September 10th will be posted successfully with this setup.

## Viz také

[Design Details: Posting Date on Adjustment Value Entry](design-details-inventory-adjustment-value-entry-posting-date.md)  
[Design Details: Inventory Costing](design-details-inventory-costing.md)  
[Design Details: Item Application](design-details-item-application.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
