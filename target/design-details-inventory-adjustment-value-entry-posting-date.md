---
title: Posting date on value entries
description: Learn how the Adjust Cost - Item Entries batch job identifies and assigns a posting date to the value entries that the batch job is about to create.
author: edupont04


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 09/17/2021
ms.author: edupont

---
# Detaily návrhu: Zúčtovací datum adjustace položky ocenění

This article provides guidance for users of the Inventory Costing functionality in [!INCLUDE[prod_short](includes/prod_short.md)], and in particular for how the **Adjust Cost - Item Entries** batch job identifies and assigns a posting date to the value entries that the batch job is about to create.

## How posting dates are assigned

The **Adjust Cost – Item Entries** batch job assigns a posting date to the value entry it is about to create in the following steps:

1. Zpočátku je datum zaúčtování položky, která má být vytvořena, stejné datum jako položka, která se upravuje.

2. Zúčtovací datum je ověřeno podle skladových období a/nebo nastavení financí.

3. Přiřazení data zaúčtování; Pokud počáteční datum zaúčtování není v povoleném rozsahu data zaúčtování, přiřadí dávková úloha povolené datum zaúčtování buď z nastavení financí, nebo z období zásob. Pokud jsou definována skladová období i povolená zúčtovací data v nastavení financí, bude pozdější datum obou období přiřazeno k Adjustaci položky ocenění.

Podívejme se na tento proces více v praxi. Předpokládejme, že máme položku zboží prodeje. The item was shipped on September 5, 2020 and it was invoiced the day after.

#### Item Ledger Entry

| Číslo položky | Číslo zboží | Zúčtovací datum | Typ položky | Číslo dokladu | Kód lokace | Množství | Částka nákladů (skutečná) | Fakturované množství | Zbývající množství |
|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| 319 | A | 2020-09-05 | Prodej | 102033 | Blue | -1 | -11 | -1 | 0 |

Below are the related value entries:

- **Entry No. 379** represents the shipment and carry the same Posting Date as the parent Item ledger Entry.
- **Entry No. 381** represents the invoice.
- **Entry No. 391** is an Adjustment of the invoicing Value Entry (Entry No. 381 above).

| Číslo položky | Číslo zboží | Zúčtovací datum | Typ položky zboží | Typ položky | Číslo dokladu | Číslo položky zboží | Kód lokace | Item Ledger Entry Quantity | Fakturované množství | Částka nákladů (skutečná) | Částka nákladů (očekávaná) | Adjustace | Vyrovnává položku | Source Code |
|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|--------|---------|---------|---------|---------|
| 379 | A | 2020-09-05 | Prodej | Přímé náklady | 102033 | 319 | Blue | -1 | 0 | 0 | -10 | Ne | 0 | Prodej |
| 381 | A | 2020-09-06 | Prodej | Přímé náklady | 103022 | 319 | Blue | 0 | -1 | -10 | 10 | Ne | 0 | Prodej |
| 391 | A | 2020-09-10 | Prodej | Přímé náklady | 103022 | 319 | Blue | 0 | 0 | -1 | 0 | Ano | 181 | INVTADJMT |

To assign the posting date for **Entry No. 391** the following steps were applied:

1. The **Adjustment Value Entry** to be created (**Entry No. 391**) is assigned same **Posting Date** as the entry it adjusts.

2. Dávková úloha **Adjustace nákladů položek zboží** určuje, zda je počáteční datum zaúčtování adjustace položky ocenění v povoleném rozsahu období účtování na základě období zásob a/nebo nastavení financí.

Podívejme se na výše uvedený prodej přidáním nastavení povolených rozsahů zúčtovacího data.

#### Období zásob

| Koncové datum | Jméno | ZAVŘENO |
|---------|---------|---------|
| 2020-01-31 | Leden 2020 | Ano |
| 2020-02-28 | Únor 2020 | Ano |
| 2020-03-31 | Březen 2020 | Ano |
| 2020-04-30 | Duben 2020 | Ano |
| 2020-05-31 | Květen 2020 | Ano |
| 2020-06-30 | Červen 2020 | Ano |
| 2020-07-31 | Červenec 2020 | Ano |
| 2020-08-31 | Srpen 2020 | Ano |
| 2020-09-30 | Září 2020 |         |
| 2020-10-31 | Říjen 2020 |         |
| 2020-11-30 | Listopad 2020 |         |
| 2020-12-31 | Prosinec 2020 |         |

The first allowed posting date is the first day in the first open period, which is September 1, 2020.

#### Nastavení financí

| Pole | Hodnota |
|---------|---------|
| Povolit účtování z | 2020-09-10 |
| Povolit účtování do | 2020-09-30 |
| Sledovat čas: |         |
| Formát místní adresy: | PSČ |

The first allowed posting date is the date stated in field **Allow Posting From**: September 10, 2020. If both Inventory Periods and allowed posting dates in **General Ledger Setup** are defined, the later date of the two will define the allowed posting date range.

**Assignment of an allowed posting date**

The initial assigned Posting Date was September 6 as illustrated in step 1. However, in the second step the Adjust Cost – Item entries batch job identifies that earliest allowed Posting Date is September 10 and thereby assigns September 10 to the Adjustment Value Entry (**Entry No. 391**), below.


| Číslo položky | Číslo zboží | Zúčtovací datum | Typ položky zboží | Typ položky | Číslo dokladu | Číslo položky zboží | Kód lokace | Item Ledger Entry Quantity | Fakturované množství | Částka nákladů (skutečná) | Částka nákladů (očekávaná) | Adjustace | Vyrovnává položku | Source Code |
|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| 379 | A | 2020-09-05 | Prodej | Přímé náklady | 102033 | 319 | Blue | -1 | 0 | 0 | -10 | Ne | 0 | Prodej |
| 381 | A | 2020-09-06 | Prodej | Přímé náklady | 103022 | 319 | Blue | 0 | -1 | -10 | 10 | Ne | 0 | Prodej |
| 391 | A | **2020-09-10** | Prodej | Přímé náklady | 103022 | 319 | Blue | 0 | 0 | -1 | 0 | Ano | 181 | INVTADJMT |

## Common problems with the "Adjust Cost - Item entries"-batch job

There are two scenarios that the support team encounters frequently enough for them to warrant their own problem resolution articles.

### Chybová zpráva: "Zúčtovací datum není v rozsahu povolených dat účtování..."

If you encounter this error you need to adjust the dates for which the user is allowed to post entries. To learn more, see [Error Message "Posting Date is not within your range of allowed posting dates"](design-details-inventory-adjustment-value-entry-allowed-posting-dates.md).

### Posting Date on Adjustment Value Entry versus Posting Date on entry causing the adjustment such as Revaluation or Item charge

To learn more, see [Posting Date on Adjustment Value Entry Compared to the Source Entry](design-details-inventory-adjustment-value-entry-source-entry.md).

## Viz také

[Detaily návrhu: Ocenění zásob](design-details-inventory-costing.md)    
[Detaily návrhu: Vyrovnání zboží](design-details-item-application.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
