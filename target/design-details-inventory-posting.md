---
    title: Design Details - Inventory Posting | Microsoft Docs
    description: Each inventory transaction, such as a purchase receipt or a sales shipment, posts two entries of different types.
    author: SorenGP

    
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/08/2021
    ms.author: edupont

---
# Detaily návrhu: Účtování zásob

Každou skladovou transakcí, například nákupní příjemkou nebo prodejní dodávkou se zaúčtují dvě položky různých typů

| Druh položky | Popis |
|----------|-----------|  
| Množství | Odráží změnu množství v zásobách Tyto informace jsou uloženy v položkách zboží.<br /><br /> Společně s položkami vyrovnání zboží. |
| Hodnota | Odráží změnu hodnoty zásob. This information is stored in value entries.<br /><br /> One or more value entries can exist for each item ledger entry or capacity ledger entry.<br /><br /> For information about capacity value entries related to the use of production or assembly resources, see [Design Details: Production Order Posting](design-details-production-order-posting.md). |

V souvislosti se zaúčtováním množství existují položky vyrovnání zboží, které spojují zvýšení zásob se snížením zásob. To umožňuje nákladovému enginu systému předávání nákladů od zvýšení k souvisejícímu snížení a naopak. Pro více informací navštivte [Detaily návrhu: Vyrovnání zboží](design-details-item-application.md).

Položky zboží, položky ocenení a položky vyrovnání zboží jsou vytvořeny jako výsledek zaúčtování řádku deníku zboží, a to buď nepřímo zaúčtováním řádku objednávky, nebo přímo na stránce Deníku zboží.

V pravidelných intervalech jsou položky ocenění vytvořené v položkách zásob zaúčtovány do hlavní knihy, aby se obě hlavní knihy vyrovnaly z důvodů finanční kontroly. Pro více informací navštivte [Detaily návrhu: Odsouhlasení s hlavní knihou](design-details-reconciliation-with-the-general-ledger.md).

![Entry flow when reconciling inventory with G/L.](media/design_details_inventory_costing_1_entry_flow.png "Entry flow when reconciling inventory with G/L")

## Příklad

Následující příklad ukazuje, jak položky zboží, položky ocenění a položky vyrovnání zboží vedou k věcným položkám.

Zaúčtujete nákupní objednávku, která je přijatá a fakturovaná na 10 položek s přímou jednotkovou cenou 7 LM a režijní sazbou 1 LM. Zúčtovaíc datum je 01.01.20. Vytvoří se následující položky.

### Položky zboží (1)

| Zúčtovací datum | Typ položky | Částka nákladů (skutečná) | Množství | Číslo položky |
|------------|----------|--------------------|--------|---------|  
| 01.01.20 | Nákup | 80.00 | 10 | 1 |

### Položky oenení (1)

| Zúčtovací datum | Typ položky | Částka nákladů (skutečná) | Číslo položky zboží | Číslo položky |
|------------|----------|--------------------|---------------------|---------|  
| 01.01.20 | Přímé náklady | 70.00 | 1 | 1 |
| 01.01.20 | Nepřímé náklady | 10,00 | 1 | 2 |

### Položky vyrovnání zboží (1)

| Číslo položky | Číslo položky zboží | Číslo vstupní položky zboží | Číslo výstupní položky zboží | Množství |
|---------|---------------------|----------------------|-----------------------|--------|  
| 1 | 1 | 1 | 0 | 10 |

Dále zaúčtujete prodej 10 jednotek zboží se zúčtovacím datem 15.01.20.

### Položky zboží (2)

| Zúčtovací datum | Typ položky | Částka nákladů (skutečná) | Množství | Číslo položky |
|------------|----------|--------------------|--------|---------|  
| 15.01.20 | Prodej | -80.00 | -10 | 2 |

### Položky ocenění (2)

| Zúčtovací datum | Typ položky | Částka nákladů (skutečná) | Číslo položky zboží | Číslo položky |
|------------|----------|--------------------|---------------------|---------|  
| 15.01.20 | Přímé náklady | -80.00 | 2 | 3 |

### Položky vyrování zboží (2)

| Číslo položky | Číslo položky zboží | Číslo vstupní položky zboží | Číslo výstupní položky zboží | Množství |
|---------|---------------------|----------------------|-----------------------|--------|  
| 2 | 2 | 1 | 2 | -10 |

At the end of the accounting period, you run the **Post Inventory Cost to G/L** batch job to reconcile these inventory transactions with the general ledger.

For more information, see [Design Details: Accounts in the General Ledger](design-details-accounts-in-the-general-ledger.md).

Následující tabulky ukazují výsledek vyrovnání transakcí zásob v tomto příkladu s hlavní účetní knihou.

### Položky ocenění (3)

| Zúčtovací datum | Typ položky | Částka nákladů (skutečná) | Náklady zaúčtované do Hlavní finančí knihy | Číslo položky zboží | Číslo položky |
|------------|----------|--------------------|------------------|---------------------|---------|  
| 01.01.20 | Přímé náklady | 70.00 | 70.00 | 1 | 1 |
| 01.01.20 | Nepřímé náklady | 10,00 | 10,00 | 1 | 2 |
| 15.01.20 | Přímé náklady | -80.00 | -80.00 | 2 | 3 |

### Věcné položky (3)

| Zúčtovací datum | Finanční účet | Číslo účtu (En-US Demo) | Částka | Číslo položky |
|------------|-----------|------------------------|------|---------|  
| 01.01.20 | [Skladový účet] | 2130 | 70.00 | 1 |
| 01.01.20 | [Účet vyrovnaných přímých nákladů] | 7291 | -70.00 | 2 |
| 01.01.20 | [Skladový účet] | 2130 | 10,00 | 3 |
| 01-01-07 | [Overhead Applied Account] | 7292 | -10,00 | 4 |
| 15.01.20 | [Skladový účet] | 2130 | -80.00 | 5 |
| 15.01.20 | [Účet NNPZ] | 7290 | 80.00 | 6 |

> [!NOTE]  
> The posting date of the general ledger entries is the same as for the related value entries.
>
> The **Cost Posted to G/L** field in the **Value Entry** table is filled.

The relation between value entries and general ledger entries is stored in the **G/L - Item Ledger Relation** table.

### Vzah položke v tabulce Vazba věcná pol. - pol. zboží (3)

| Číslo věcné položky. | Číslo položky ocenění. | Číslo finančního žurnálu. |
|-------------|---------------|----------------|  
| 1 | 1 | 1 |
| 2 | 1 | 1 |
| 3 | 2 | 1 |
| 4 | 2 | 1 |
| 5 | 3 | 1 |
| 6 | 3 | 1 |

## Zaúčtování montáže a výroby

Položky kapacity a zdrojů představují čas, který je zaúčtován jako spotřebovaný ve výrobě nebo montáži. Tyto procesní náklady jsou zaúčtovány jako položky ocenění do hlavní knihy spolu s souvisejícími náklady na materiál v podobné struktuře, jak je popsáno pro položky zboží v tomto tématu.

Pro více informací navštivte [Podrobnosti návrhu: Účtování montážní zakázky](design-details-assembly-order-posting.md).

## Viz také

[Design Details: Inventory Costing](design-details-inventory-costing.md)  
[Design Details: Accounts in the General Ledger](design-details-accounts-in-the-general-ledger.md)  
[Design Details: Cost Components](design-details-cost-components.md)
[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Finance](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]