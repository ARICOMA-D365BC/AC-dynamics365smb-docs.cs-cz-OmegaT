---
    title: Design Details - Expected Cost Posting
    description: Expected costs represent the estimation of, for example, a purchased item’s cost that you record before you receive the invoice for the item.
    author: SorenGP

    
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/20/2021
    ms.author: edupont

---
# Detaily návrhu: Účtování očekávaných nákladů
Očekávané náklady představují odhad například nákladů na zakoupené zboží, které zaznamenáte před přijetím faktury za zboží.

Očekávané náklady můžete zaúčtovat do zásob a do financí. Když zaúčtujete množství, které je pouze přijato nebo odesláno, ale není fakturováno, vytvoří se položka ocenění s očekávanými náklady. Tyto očekávané náklady ovlivňují hodnotu zásob, ale nejsou zaúčtovány do financí, pokud k tomu nenastavíte systém.

> [!NOTE]  
> Očekávané náklady jsou spravovány pouze u transakcí za zboží. Očekávané náklady neplatí pro nehmotné typy transakcí, jako jsou poplatky za kapacitu a zboži.

Pokud byla zaúčtována pouze část množství, která zvyšuje zásoby, hodnota zásob ve financích se nezmění, pokud jste na stránce **Nastavení zásob** nezaškrtli políčko **Účtování oček.nákladů do fin.**. V takovém případě se očekávané náklady zaúčtují na mezitímní účty v okamžiku přijetí. Poté, co byla příjemka plně fakturována, jsou prozatímní účty vyrovnány a skutečné náklady jsou zaúčtovány na účet zásob.

Pro podporu odsouhlasení a sledovatelnosti práce zobrazuje zaúčtovaná položka ocenění očekávanou částku nákladů, která byla zaúčtována k vyrovnání mezitímních účtů.

## Prerequisites for posting expected costs

To make it possible to post expected costs you need to do the following:
1. On the **Inventory Setup** page, select the **Automatic Cost Posting** check box and the **Expected Cost Posting to G/L** check box.
2. Set up which interim accounts to use during the expected cost posting process.

On the **Inventory Posting Setup** page, verify the **Inventory Account** and the **Inventory Account (Interim)** fields for the **Location Code and Invt. Posting Group Code** of the item you will be purchasing. To learn more about these accounts see [Design Details - Accounts in the General Ledger](design-details-accounts-in-the-general-ledger.md).
3. On the **General Posting Setup** page, verify the **Invt. Accrual Acc. (Interim)** field for the **Gen. účto  Posting Group** and the **Gen. účto  Posting Group** you will be using.
4. When you create a purchase order the default is that the **Vendor Invoice No.** field is required. You need to turn that off on the **Purchase & Payables Setup** page, by unselecting the **Ext. Doc. Čísla. Mandatory** field.

## Příklad

> [!NOTE]  
> The account numbers used in this example are there for reference only, and will be different in your system. Set them up as directed in the Prerequisites above.

Zaúčtujete nákupní objednávku tak, jak byla přijata. Očekávaná cena je 95,00 CZK.

**Položky ocenění**

| Zúčtovací datum | Typ položky | Částka nákladů (očekávaná) | Očekávané náklady zaúčtované do hlavní knihy | Očekávané náklady | Číslo položky zboží | Číslo položky |
|------------------|----------------|------------------------------|----------------------------------|-------------------|---------------------------|---------------|  
| 01.01.20 | Přímé náklady | 95,00 | 95,00 | Ano | 1 | 1 |

**Vazba položek v tabulce Vazba věcná pol. - pol. zboží**

| Číslo věcné položky. | Číslo položky ocenění. | Číslo finančního žurnálu. |
|--------------------|---------------------|-----------------------|  
| 1 | 1 | 1 |
| 2 | 1 | 1 |

**Věcné položky**

| Zúčtovací datum | Finanční účet | Číslo účtu (En-US Demo) | Částka | Číslo položky |
|------------------|------------------|---------------------------------|------------|---------------|  
| 01.01.20 | Účet časového rozlišení zásob (dočasné) | 5530 | -95,00 | 2 |
| 01.01.20 | Účet zásob (dočasné) | 2131 | 95,00 | 1 |

Později zaúčtujete nákupní objednávku jako fakturovanou. Fakturované náklady jsou 100,00 CZK.

**Položky ocenění**

| Zúčtovací datum | Částka nákladů (skutečná) | Částka nákladů (očekávaná) | Náklady zaúčtované do Hlavní finančí knihy | Očekávané náklady | Číslo položky zboží | Číslo položky |
|------------------|----------------------------|------------------------------|-------------------------|-------------------|---------------------------|---------------|  
| 15.01.20 | 100,00 | -95,00 | 100,00 | Ne | 1 | 2 |

**Vazba položek v tabulce Vazba věcná pol. - pol. zboží**

| Číslo věcné položky. | Číslo položky ocenění. | Číslo finančního žurnálu. |
|--------------------|---------------------|-----------------------|  
| 3 | 2 | 2 |
| 4 | 2 | 2 |
| 5 | 2 | 2 |
| 6 | 2 | 2 |

**Věcné položky**

| Zúčtovací datum | Finanční účet | Číslo účtu (Examples only!) | Částka | Číslo položky |
|------------------|------------------|---------------------------------|------------|---------------|  
| 15.01.20 | Účet časového rozlišení zásob (dočasné) | 5530 | 95,00 | 4 |
| 15.01.20 | Účet zásob (dočasné) | 2131 | -95,00 | 3 |
| 15.01.20 | Účet použitých přímých nákl. | 7291 | -100 | 6 |
| 15.01.20 | Skladový účet | 2130 | 100 | 5 |

## Viz také
[Design Details: Inventory Costing](design-details-inventory-costing.md)   
[Design Details: Cost Adjustment](design-details-cost-adjustment.md)   
[Design Details: Reconciliation with the General Ledger](design-details-reconciliation-with-the-general-ledger.md)   
[Design Details: Inventory Posting](design-details-inventory-posting.md)   
[Design Details: Variance](design-details-variance.md)  
[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Finance](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
