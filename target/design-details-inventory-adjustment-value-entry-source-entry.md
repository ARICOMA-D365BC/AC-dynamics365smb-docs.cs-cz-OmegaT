---
title: Posting Date on Adjustment Value Entry Compared to the Source Entry
description: Learn about scenario "Posting Date on Adjustment Value Entry versus Posting Date on entry causing the adjustment such as Revaluation or Item charge" when running the Adjust Cost - Item Entries batch job identifies.
author: edupont04


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 09/17/2021
ms.author: edupont

---

# Posting Date on Adjustment Value Entry Compared to the Source Entry

This article compares the Posting Date on the Adjustment Value Entry with the Posting Date on the entry causing the running of the Adjust Cost - Item Entries batch job, in particular a Revaluation scenario and an Item Charge scenario.

The **Adjust Cost - Item Entries** batch job will process your data depending on your scenario and configuration of [!INCLUDE[prod_short](includes/prod_short.md)]. In this section, we describe two separate processes, and for each one we show the type of impact the Adjust Cost - Item Entries batch job has on the data.

## Revaluation scenario

### Předpoklady

Please enter the following values:

**Inventory setup**:

- Automatické účtování nákladů=Ano

- Automatic Cost Adjustment = Always

- Typ výpočtu prům.poř. Type = Item

- Average Cost Period = Day

**General Ledger Setup**:

- Allow Posting From = January 1, 2021

- Allow Posting To = Empty

**User Setup**:

- Allow Posting From = December 1, 2020

- Allow Posting To = Empty

### Testování scénáře

Test this scenario by carrying out the following steps.

1. Create an **Item** called TEST with the following values:

   - Základní měrná jednotka = KS

   - Metoda ocenění = Průměrná

   - Vyberte volitelné účto skupiny.

2. Open an **Item Journal**, then create a new entry, and post a line as follows:

   - Posting Date = December 15, 2020

   - Zboží = TEST

   - Typ položky = Nákup

   - Množství = 100

   - Jednotková cena = 10

3. Open an **Item Journal**, then create a new entry, and post a line as follows:

   - Date = December 20, 2020

   - Zboží = TEST

   - Typ položky = Výdej

   - Množství = 2

4. Open an **Item Journal**, then create a new entry, and post a line as follows:

   - Date = January 15, 2021

   - Zboží = TEST

   - Typ položky = Výdej

   - Množství = 3

5. Open an **Item Revaluation Journal**, then create a new entry, and post a line as follows:

   - Zboží = TEST

   - Vyrovnává položku = vyberte položku nákupu zaúčtovanou v kroku 2. Datum zaúčtování přecenění bude stejné jako položka, kterou upraví.

   - Unit Cost (Revalued) = 40

The following **Item Ledger** and **Value Entries** have been posted:

**Item Ledger Entry - purchase**:

| Entry Number | Číslo zboží | Zúčtovací datum | Typ položky | Číslo dokladu | Množství | Částka nákladů (skutečná) | Zbývající množství |
|---------|---------|---------|---------|---------|---------|---------|---------|
| 317 | TEST | 2020-12-15 | Nákup | T00001 | 100 | 4000 | 95 |

**Položky ocenění**

| Entry Number | Číslo zboží | Zúčtovací datum | Číslo položky zboží | Typ položky zboží | Typ položky | Číslo dokladu | Item Number Entry Quantity | Částka nákladů (skutečná) | Náklady zaúčtované do Hlavní finančí knihy | Adjustace | Applies to Entry | Source Code |
|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| 376 | TEST | 2020-12-15 | 317 | Nákup | Přímé náklady | T00001 | 100 | 1 000,00 | 1 000,00 | Ne | 0 | ITEMNL |
| 379 | TEST | **2020-12-15** | 317 | Nákup | Přecenění | T04002 | 0 | 3 000,00 | 3 000,00 | Ne | 0 | REVALINL |

**Item Ledger Entry - negative adjustment, Step 3**

| Číslo položky | Číslo zboží | Zúčtovací datum | Typ položky | Číslo dokladu | Množství | Částka nákladů (skutečná) | Zbývající množství |
|---------|---------|---------|---------|---------|---------|---------|---------|
| 318 | TEST | 2020-12-20 | Negative Adjmt. | T00002 | -2 | -80 | 0 |

**Položky ocenění**

| Entry Number | Číslo zboží | Zúčtovací datum | Číslo položky zboží | Typ položky zboží | Typ položky | Číslo dokladu | Item Number Entry Quantity | Částka nákladů (skutečná) | Náklady zaúčtované do Hlavní finančí knihy | Adjustace | Applies to Entry | Source Code |
|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| 377 | TEST | 2020-12-20 | 318 | Negative Adjmt. | Přímé náklady | T00002 | -2 | -20 | -20 | Ne | 0 | ITEMNL |
| 380 | TEST | **2021-01-01** | 318 | Negative Adjmt. | Přímé náklady | T04002 | 0 | -60 | -60 | Ano | 377 | INVTADAMT |

**Item Ledger Entry - negative adjustment, Step 4**

| Číslo položky | Číslo zboží | Zúčtovací datum | Typ položky | Číslo dokladu | Množství | Částka nákladů (skutečná) | Zbývající množství |
|---------|---------|---------|---------|---------|---------|---------|---------|
| 319 | TEST | 2021-01-15 | Negative Adjmt. | T00003 | -3 | -120 | 0 |

**Položky ocenění**

| Entry Number | Číslo zboží | Zúčtovací datum | Číslo položky zboží | Typ položky zboží | Typ položky | Číslo dokladu | Item Number Entry Quantity | Částka nákladů (skutečná) | Náklady zaúčtované do Hlavní finančí knihy | Adjustace | Applies to Entry | Source Code |
|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| 378 | TEST | 2021-01-15 | 319 | Negative Adjmt. | Přímé náklady | T00003 | -3 | -30 | -30 | Ne | 0 | ITEMNL |
| 381 | TEST | **2021-01-15** | 319 | Negative Adjmt. | Přímé náklady | T04003 | 0 | -90 | -90 | Ano | 378 | INVTADAMT |

The **Adjust Cost – Item Entries** batch job has recognized a change in cost and adjusted the Negative Adjustments.

**Review of Posting Dates on created adjustment value entries:** The earliest allowed Posting Date the Adjust Cost - Item Entries batch job has to relate to is January 1, 2021 as stated in the General Ledger Setup.

**Negative Adjustment in step 3:** assigned Posting Date is January 1, provided by General Ledger Setup. The Posting Date of the Value Entry in the scope for adjustment is December 20, 2020. According to the General Ledger Setup, the date is not within the allowed posting date range. Proto je adjustaci položky ocenění přiřazeno datum zaúčtování uvedené v poli Povolit účto od v nastavení financí.

**Negative Adjustment in step 4:** assigned Posting Date is January 15. The Value Entry in scope of adjustment has Posting Date January 15, which is within the allowed posting date range according to General Ledger Setup.

Adjustace provedené pro negativní úpravu v kroku 3 způsobí diskusi. The favorable Posting Date for the Adjustment Value Entry would have been December 20 or at least within December as the revaluation causing the change in COGS was posted in December.

To achieve adjustment in December of the Negative Adjustment in step 3, the General Ledger Setup, Allow Posting From field, needs to state a date in December.

### Conclusion

With the experience gained in this scenario, when considering the most suitable setup for an allowed posting date range for a company, you might want to consider the following. As long as you allow changes in the inventory value to be posted in a period, such as December in this case, the setup that the company uses for allowed posting date ranges should be aligned with this decision. The Allow Posting From in the General Ledger Setup, stating December 1, would allow the revaluation made in December to be forwarded to affected outbound entries in the same period.

Skupiny uživatelů, které nemají povoleno účtovat v prosinci, ale v lednu, což bylo pravděpodobně zamýšleno v tomto scénáři jako omezené nastavením financí, by měly být místo toho řešeno prostřednictvím nastavení uživatele.

## Item charge scenario

### Předpoklady

Please enter the following values:

**Inventory setup**:

- Automatické účtování nákladů=Ano

- Automatic Cost Adjustment = Always

- Typ výpočtu prům.poř. Type = Item

- Average Cost Period = Day

**General Ledger Setup**:

- Allow Posting From = December 1, 2020.

- Allow Posting To = Empty

**User Setup**:

- Allow Posting From = December 1, 2020.

- Allow Posting to = Empty

### Testování scénáře

Test this scenario by carrying out the following steps:

1. Create an **Item** Charge with the following values:

   - Základní měrná jednotka = KS

   - Metoda ocenění = Průměrná

   - Vyberte volitelné účto skupiny.

2. Create a new **Purchase Order** with the following values:

   - Nákup od dodavatele: 10000

   - Posting Date = December 15, 2020

   - Číslo faktury dodavatele: 1234

   On the Purchase Order Line select the following values:

   - Zboží = POPLATEK

   - Množství = 1

   - Nákupní cena = 100

   To complete the step, Post the document as Received and Invoiced.

3. Create a new **Sales Order** with the following values:

   - Zákazník-číslo: 10000

   - Posting Date = December 16, 2020

   On the Sales Order Line:

   - Zboží = POPLATEK

   - Množství = 1

   - Jednotková cena = 135

   To complete the step, Post the document as Received and Invoiced.

4. Enter values for the **General Ledger Setup** page:

   - Allow Posting From = January 1, 2021

   - Povolit účto do = prázdné

5. Create a new **Purchase Order** with the following values:

   - Nákup od dodavatele: 10000

   - Posting Date = January 2, 2021

   - Číslo faktury dodavatele: 2345

   On the Purchase Order Line:

   - Poplatek za zboží = JB-PŘEPRAVA

   - Množství = 1

   - Nákupní cena = 3

   - Assign the Item Charge to the Purchase Receipt from step 2.

   To complete the step, Post the document as Received and Invoiced.


**Status Item Ledger Entry of purchase step 2**:

| Entry Number | Číslo zboží | Zúčtovací datum | Typ položky | Číslo dokladu | Množství | Částka nákladů (skutečná) | Zbývající množství |
|---------|---------|---------|---------|---------|---------|---------|---------|
| 324 | CHARGE | 2020-12-15 | Nákup | 107030 | 1 | 105 | 0 |

**Položky ocenění**

| Entry Number | Číslo zboží | Zúčtovací datum | Číslo položky zboží | Typ položky zboží | Typ položky | Číslo dokladu | Item Charge No. | Item Ledger Entry Quantity | Částka nákladů (skutečná) | Náklady zaúčtované do Hlavní finančí knihy | Adjustace | Vyrovnává položku |
|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| 397 | CHARGE | 2020-12-15 | 324 | Nákup | Přímé náklady | 108029 |         | 1 | 100 | 100 | NO | 0 |
| 399 | CHARGE | 2021-01-02 | 324 | Nákup | Přímé náklady | 108009 | JBFREIGHT | 0 | 3 | 3 | NO | 0 |

**Status Item Ledger Entry sale**:

| Číslo položky | Číslo zboží | Zúčtovací datum | Typ položky | Číslo dokladu | Množství | Částka nákladů (skutečná) | Zbývající množství |
|---------|---------|---------|---------|---------|---------|---------|---------|
| 325 | CHARGE | 2020-12-16 | Prodej | 102035 | -1 | -105 | 0 |

**Položky ocenění**

| Entry Number | Číslo zboží | Zúčtovací datum | Číslo položky zboží | Typ položky zboží | Typ položky | Číslo dokladu | Item Charge No. | Item Ledger Entry Quantity | Částka nákladů (skutečná) | Náklady zaúčtované do Hlavní finančí knihy | Adjustace | Vyrovnává položku |
|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| 398 | CHARGE | 2020-12-16 | 325 | Prodej | Přímé náklady | 109024 |         | -1 | -100 | -100 | NO | 0 |
| 400 | CHARGE | 2021-01-01 | 325 | Prodej | Přímé náklady | 109024 |         | 0 | -3 | -3 | Ano | 398 |

6. On work date January 3, a purchase invoice arrives containing an additional item charge to the purchase made in step 2. This invoice has document date December 30, and is therefore posted with Posting Date December 30, 2020.

   Create a new **Purchase Order** with the following values:

   - Nákup od dodavatele: 10000

   - Posting Date = December 30, 2020

   - Číslo faktury dodavatele: 3456

   On the Purchase Order Line select the following values:

   - Poplatek za zboží = JB-PŘEPRAVA

   - Množství = 1

   - Nákupní cena = 2

   Assign Item Charge to the Purchase Receipt from step 2

   To complete the step, Post the document as Received and Invoiced.


**Status Item Ledger Entry of purchase**:

| Entry Number | Číslo zboží | Zúčtovací datum | Typ položky | Číslo dokladu | Množství | Částka nákladů (skutečná) | Zbývající množství |
|---------|---------|---------|---------|---------|---------|---------|---------|
| 324 | CHARGE | 2020-12-15 | Nákup | 107030 | 1 | 105 | 0 |

**Položky ocenění**

| Číslo položky | Číslo zboží | Zúčtovací datum | Číslo položky zboží | Typ položky zboží | Typ položky | Číslo dokladu | Item Charge No. | Item Ledger Entry Quantity | Částka nákladů (skutečná) | Náklady zaúčtované do Hlavní finančí knihy | Adjustace | Vyrovnává položku |
|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| 397 | CHARGE | 2020-12-15 | 324 | Nákup | Přímé náklady | 108029 |            | 1 | 100 | 100 | Ne | 0 |
| 399 | CHARGE | 2021-01-02 | 324 | Nákup | Přímé náklady | 108030 | JBFREIGHT | 0 | 3 | 3 | Ne | 0 |
| 401 | CHARGE | **2020-12-30** | 324 | Nákup | Přímé náklady | 108031 | JBFREIGHT | 0 | 2 | 2 | Ne | 0 |

**Status Item Ledger Entry sale**:

| Entry Number | Číslo zboží | Zúčtovací datum | Typ položky | Číslo dokladu | Množství | Částka nákladů (skutečná) | Zbývající množství |
|---------|---------|---------|---------|---------|---------|---------|---------|
| 325 | CHARGE | 2020-12-16 | Prodej | 102035 | -1 | -105 | 0 |

**Položky ocenění**

| Číslo položky | Číslo zboží | Zúčtovací datum | Číslo položky zboží | Typ položky zboží | Typ položky | Číslo dokladu | Item Charge No. | Item Ledger Entry Quantity | Částka nákladů (skutečná) | Náklady zaúčtované do Hlavní finančí knihy | Adjustace | Vyrovnává položku |
|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| 398 | CHARGE | 2020-12-16 | 325 | Prodej | Přímé náklady | 103024 |            | -1 | -100 | -100 | Ne | 0 |
| 400 | CHARGE | 2021-01-01 | 325 | Prodej | Přímé náklady | 103024 |            | 0 | -3 | -3 | Ano | 398 |
| 402 | CHARGE | **2021-01-01** | 325 | Prodej | Přímé náklady | 103024 |            | 0 | -2 | -2 | Ano | 398 |

Inventory Valuation report is printed as of Date December 31, 2020

![Content of the Inventory Valuation report.](media/helene/TechArticleAdjustcost13.png "Content of the Inventory Valuation report")

**Shrnutí scénáře:**

Popsaný scénář končí zprávou Hodnoty zásob ukazující Množství = 0, zatímco Hodnota = 2. The Item charge posted in step 6 is part of the Inventory Increase value of December while the Inventory Decrease of the same period is not affected.

Having the General Ledger Setup stating Allow Posting From January 1 was a good thing for the first Item charge. Ve stejném období byly zaznamenány náklady na zvýšení i snížení zásob. U druhého poplatku za zboží však nastavení financí způsobí, že změna v NNPZ bude rozpoznána v období po.

**Závěr:**

It is a challenge to get the Inventory Valuation report to demonstrate Quantity = 0 while the Value <> 0. In this case it is also more difficult to express the optimal settings, having purchase invoices arriving the same day but addressing different periods or even fiscal years. Crossing to a new fiscal year usually requires some planning and as part of that the insight into Adjust Cost – Item entries process, recognizing COGS, is to be considered.

V tomto scénáři by jednou z možností mohlo být nastavení financí, konkrétně pole Povolit účto od na datum v prosinci o několik dní později a odložit zaúčtování prvního poplatku za zboží, aby bylo možné zaúčtovat všechny náklady za předchozí období/fiskální rok, se spuštěním dávkové úlohy Adjustace nákladů položek zboží a poté přesunout povolené zúčtovací datum do nového období/fiskálního roku. The first item charge with posting date January 2 could then be posted.

## Viz také

[Detaily návrhu: Zúčtovací datum adjustace položky ocenění](design-details-inventory-adjustment-value-entry-posting-date.md)  
[Detaily návrhu: Ocenění zásob](design-details-inventory-costing.md)  
[Detaily návrhu: Vyrovnání zboží](design-details-item-application.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
