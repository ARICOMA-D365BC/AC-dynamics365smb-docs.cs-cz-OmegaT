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

# Chybová zpráva: "Zúčtovací datum není v rozsahu povolených dat účtování..."

Při použití dávkové úlohy **Upravit náklady - položky zboží** můžete narazit na následující chybovou zprávu:

**Zúčtovací datum nespadá do vašeho rozsahu povolených dat účtování**

Tato chybová zpráva označuje, že uživatel nemá povoleno zaúčtovat položky pro dané datum, což lze napravit změnou nastavení uživatele.

## Změňte nastavení uživatelů

| ID uživatele | Povolit účtování z | Povolit účtování do |
|---------|---------|--------|
| EVROPA | 2020-09-11 | 2020-09-30 |

Uživatel má v tomto případě povolený rozsah dat účtování od 11. září do 30. září, a proto nesmí zaúčtovat položku hodnoty úpravy s datem účtování 10. září.

### Přehled nastavení příslušného data účtování

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

#### Nastavení financí

| Pole | Hodnota |
|---------|---------|
| Povolit účtování z | 2020-09-10 |
| Povolit účtování do | 2020-09-30 |
| Sledovat čas: |         |
| Formát místní adresy: | PSČ |

#### Nastavení uživatele

| ID uživatele | Povolit účtování z | Povolit účtování do |
|---------|---------|--------|
| UŽIVATELSKÉ JMÉNO | 2020-09-10 | 2020-09-30 |

Přiřazení širšího rozsahu povoleného účetního data zaúčtování, například v Nastavení období zásob nebo Nastavení financí, umožňuje vyhnout se konfliktu, který způsobuje chybovou zprávu. Položka hodnoty úpravy s datem účtování 10. září bude s tímto nastavením úspěšně zaúčtována.

## Viz také

[Detaily návrhu: Zúčtovací datum adjustace položky ocenění](design-details-inventory-adjustment-value-entry-posting-date.md)  
[Detaily návrhu: Ocenění zásob](design-details-inventory-costing.md)  
[Detaily návrhu: Vyrovnání zboží](design-details-item-application.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
