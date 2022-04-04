---
    title: Design Details - Changing Costing Methods for Items
    description: Learn how to assign a different costing method to an item although you have already used the item in transactions.
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: costing methods, costing, item cost
    ms.date: 06/08/2021
    ms.author: bholtorf

---

# Detaily návrhu: Změna metody ocenění pro zboží

V [!INCLUDE[prod_short](includes/prod_short.md)], nelze změnit metodu ocenění pro zboží po zahrnutí zboží do transakce. Například poté, co jste zboží koupili nebo prodali. Pokud byla zboží přiřazena nesprávná metoda ocenění, je možné, že problém nezjistíte, dokud neprovedete finanční výkaznictví.

Toto téma popisuje, jak tuto situaci vyřešit. Doporučeným přístupem je nahradit zboží, které má nesprávnou metodu ocenění, novým zbožím a použít montážní zakázku k převodu zásob ze starého zboží na nové.

> [!NOTE]
> Použití montážních zakázek umožňuje, aby bylo ocenení vždy aktivní, i když je třeba zaúčtovat neuhrazené nákupní faktury nebo poplatky za dopravu. Kromě toho vám umožňuje vrátit zpět převod a v případě potřeby získat množství původního zboží zpět.

> [!TIP]
> Abyste se s procesem seznámili, doporučujeme vám zahájit proces převodu s jedným zbožím nebo malou sadou zboží.

## O metodách ocenění

Metody ocenění řídí výpočty nákladů při nákupu, přijetí ve skladu a prodeji zboží. Metody ocenění ovlivňují načasování částek zaznamenaných v NNPZ, které ovlivňují hrubý zisk. Právě tento tok vypočítává NNPZ. Náklady na prodané zboží (NNPZ) a tržby se používají k určení hrubého zisku takto:

*ghrubý zisk* = *tržby - NNPZ*

Při nastavování skladového zboží je nutné přiřadit metodu ocenění. Metoda se může lišit v souvislosti s firmou nebo konkrétním zbožím, takže je důležité vybrat tu správnou. [!INCLUDE[prod_short](includes/prod_short.md)] podporuje následující metody ocenľní:

* Průměrná
* Metoda FIFO
* Metoda LIFO
* Standardní
* Specifikcá

Pro více informace navštivte [Detaily návrhu: Metody ocenění](design-details-costing-methods.md).

## Použití montážních zakázek ke změně přiřazení metody ocenění

Tato část popisuje následující kroky pro změnu metody ocenění přiřazené ke zboží:

1. Definujte výchozí metodu ocenění.
2. Identifikujte zboží, pro které chcete změnit metodu ocenění, a přečíslujte je.
3. Vytvořte nové zboží se starým schématem číslování a zkopírujte kmenová data v dávce.
4. Ručně zkopírujte související kmenová data ze stávajícího zboží do nového zboží.
5. Určete množství zásob, které chcete převést z původního zboží na nové.
6. Převeďte zásoby na nové zboží.
7. Zpracování množství zásob, která jsou přidělena poptávce.
8. Zablokuje další použití původního zboží.

### Definování výchozí metody ocenění

Chcete-li se vyhnout budoucím chybám, můžete zadat výchozí metodu ocenění pro nové zboží. Kdykoli někdo vytvoří nové zboží, [!INCLUDE[prod_short](includes/prod_short.md)] navrhne výchozí metodu ocenění. Výchozí metodu zadáte v poli **Výchozí metoda ocenění** na stránce **Nastavení zásob**.

### Identifikujte zboží, pro které chcete změnit metodu ocenění, a přečíslujte je

Možná budete chtít dát svým novým zbožím stejná čísla jako těm, které nahrazují. Chcete-li to provést, změňte čísla stávajícího zboží. Pokud je například existující číslo zboží "P1000", můžete ho změnit na "X-P1000". Jedná se o ruční změnu, kterou musíte provést pro každé zboží.

### Vytvoření nového zboží se starým schématem číslování a zkopírování kmenových dat v dávce

Vytvořte nové zboží pomocí aktuálního číselného schématu. S výjimkou pole **Metoda ocenění** by nové zboží mělo obsahovat stejná kmenová data jako stávající zboží. Chcete-li přenést kmenová data pro zboží a související data z jiných prvků, použijte akci **Kopírovat zboží** na stránce **Karta zboží**. Pro více informací navštivte [Kopírování existujícího zboží pro vytvoření nového zboží](inventory-how-copy-items.md).

Po vytvoření nového zboží a přenosu kmenových dat přiřaďte správnou metodu ocenění.

### Ruční zkopírování souvisejících kmenových dat z původního zboží do nového zboží

Aby bylo nové zboží plně užitečné, musíte ručně zkopírovat některá kmenová data z jiných oblastí, jak je popsáno v následující tabulce.

| Oblast | Co kopírovat | Jak jej zkopírovat |
|---------|---------|---------|
| Zásoby | Skladové jednotky (SKJ) | Zkontrolujte, zda je pro původní zboží zadána SKJ. Pokud byly parametry plánování zadány pro každou kartu SKJ, musíte ručně vytvořit SKJ pro nové zboží. If the parameters are not specified, you can use the **Create Stockkeeping Unit** batch job from the **Item Card** page to create the data. |
|     | Item substitutions | Check whether any item substitutions are defined for the original item. If there are, transfer that data to the new item. To view substitute items, use the **Substitutions** action on the **Item Card** page. |
|     | Analysis reports | Review the Item Analysis, Sales Analysis, and Purchase Analysis reports. For those that reference the original items you can either create a new analysis report with a reference to the new item (keeping the original analysis report to use as history) or adjust the reports so that they reference the new item. |
|     | Standard journals | Check whether standard journals reference the original item and transfer that data to the new item when necessary. This information is found on the standard journals, which are available on the item journal. |
| Prodej | Sales prepayment percentage | Check whether any sales prepayment percentages are defined for the original item and transfer that data to the new item. To view prepayment percentages, on the **Item Card** page, choose **Sales**, and then **Prepayment Percentages**. |
| Nákup | Purchase prepayment percentage | Check whether any purchase prepayment percentages are defined for the original item and transfer that data to the new item. To view prepayment percentages, on the **Item Card** page, choose **Purchases**, and then **Prepayment Percentages**. |
| Warehouse | Bin contents | Review the bin content defined for the original item. If columns such as as Min. Qty., Max. Qty., Default, and Dedicated have been individually entered then you must manually create bin content for the new item. If they are not, no action is required. [!INCLUDE[prod_short](includes/prod_short.md)] will maintain the records when you register warehouse documents and journals. |
| Job | Job Prices | Check whether job prices are defined for the original item and transfer that data to the new item. This information is available on the **Job Card** page in the **Job Details – No. of Prices** part on the **FactBox pane**. |
| Service | Service resource skill | Check whether service resource skills are defined for the original item and transfer that data to the new item. To view resource skills, use the **Resource Skills** action on the **Item Card** page. |
|     | Service item components | Check whether components are defined for the original service item and transfer that data to the new item. To view service item components, on the **Item Card** page use the **Service Item** action to open the list of related service items, and then choose the **Components** action. |
| Výroba | Production BOMs | Check whether any production BOMs contain the original item and replace it with the new item. To replace the original item, on the **Production BOMs** page, choose the **Exchange Production BOM Item** action. |
| Montáž | Kusovníky montáže | Check whether any assembly BOMs contain the original item and manually replace it with the new item. |

> [!IMPORTANT]
> If the new costing method is Standard you should enter a value in the **Standard Cost** field on the **Item Card** page. You can use the **Standard Cost Worksheet** page to set the cost shares accordingly. For more information, see [Update Standard Costs](finance-how-to-update-standard-costs.md).

### Determine the inventory quantity to convert from the original item to the new item

> [!NOTE]
> This step does not consider quantities that are included in unshipped orders. For more information, see [Handle inventory quantities that are allocated to demand](design-details-changing-costing-methods.md#handle-inventory-quantities-that-are-allocated-to-demand).

Use a physical inventory journal to produce a list of the quantities in inventory. Depending on the warehouse location setup, use one of the following:

* Physical Invt. Journals
* Centrum Phys. Invt. Journals

Both journals can calculate the inventory quantity of the item, including the location, variant, bin, and storage location. For more information, see [Count, Adjust, and Reclassify Inventory Using Journals](inventory-how-count-adjust-reclassify.md).

### Transfer the inventory to the new item

Create and post assembly orders to transfer the cost and inventory quantity from the original item to the new item. Assembly orders can convert one item to another while preserving the costs. This helps ensure that the net totals for the inventory account and COGS are not affected (except when the new costing method is Standard, in which case costs may be distributed to variance accounts). For more information, see [Assembly Management](assembly-assemble-items.md).

When creating assembly orders, use the information from the Physical Invt. journal or Whse. Phys. Invt. journal. The following tables describe the information in the reports to enter in the header and lines on the assembly order.

#### Header

| Pole | Value to enter |
|---------|---------|
| Číslo zboží | The number of the new item. |
| Množství | The quantity in physical inventory journal.<br> **NOTE:** The quantities calculated by the physical inventory journals does not include the quantities that are on orders that have not yet shipped. |
| Variant Code | The same as in physical inventory journal. |
| Kód lokace | The same as in physical inventory journal. |
| Unit of Measure Code | The same as in physical inventory journal. |
| Bin Code | The same as in physical inventory journal. |

#### Lines

| Pole | Value to enter |
|---------|---------|
| Typ | Zboží |
| Ne.  | The number of the original item. |
| Množství za | 1 |
| Variant Code | The same as in physical inventory journal. |
| Kód lokace | The same as in physical inventory journal. |
| Unit of Measure Code | The same as in physical inventory journal. |

> [!NOTE]
> An assembly order can handle only one SKU of an item at a time. You must create an assembly order for each combination of SKU that has a quantity in inventory.

> [!NOTE]
> For a warehouse location, you might have to create picks before you can post the assembly order. To investigate that, review the setup for picking on the **Location Card** page. For more information, see [Set Up Items and Locations for Directed Put-away and Pick](warehouse-how-to-set-up-items-for-directed-put-away-and-pick.md).

### Handle inventory quantities that are allocated to demand

Ideally, the inventory for the original item should go to zero after you transfer the inventory quantities. However, there can be outstanding orders, worksheets, and journals (see the table below) that still require a quantity of the original item. The quantity could also be blocked by a reservation or item tracking.

**Example**
There are 1000 pcs. in inventory, and 20 pcs. are reserved for a sales order that has not yet shipped. In that case, you might decide to keep the 20 pcs. in the old item so that you can fulfill the outstanding order.

> [!NOTE]
> There are functional areas that can affect the quantity, as listed in the table below, so it can be tricky to find the correct amount. To be safe, using the example above, you can choose to keep 100 pcs. and transfer the remaining 900 pcs. instead. Another way to do it would be to process the documents and journals so that only a manageable few remain. Yet another alternative is to transfer the entire quantity to the new item and then transfer some of it back to the original item using the assembly order.

The following table lists functional areas where there might be outstanding quantities.

| Oblast | Where to look for outstanding quantities |
|---------|---------|
| Prodej | Sales documents, including orders, return orders, invoices, quotes, blanket orders, and credit memos |
| Zásoby | Item journals, reservations, item tracking, and standard cost worksheet |
| Nákup | Purchase documents, including orders, return orders, invoices, quotes, blanket orders, and credit memos |
| Planning | Requisition worksheet, planning worksheet, and order planning |
| Warehouse | Transfer orders, warehouse shipments, warehouse journals, and warehouse picks, put-aways, and movements, internal picks and put-aways, and bin creation worksheets |
| Montáž | Assembly documents, including orders, return orders, and blanket orders |
| Jobs | Job planning lines and job journal lines |
| Service | Service documents and service contracts |
| Výroba | Production orders (planned, firm planned, and released) |

### Block the original item from further use

When the inventory for the original item is zero, you can block the item to prevent it fom being used in new transactions. To block the item, on the **Item Card** page, turn on the **Blocked** toggle. For more information, see [Block Items from Sales or Purchasing](inventory-how-block-items.md).

## Summary

Changing the costing method on items that have been used in transactions is a process, and not a standard action in [!INCLUDE[prod_short](includes/prod_short.md)]. You can use the steps described in this topic as a template for the process.

The process can be time consuming because there are several manual steps. However, taking the time to complete it will minimize the impact of mistakes on your general ledger.

We recommend the following:

1. Assess the feasibility of the process by taking one, or maybe a few, representative items through the entire process.
2. Consider contacting an experienced partner who can help you with the process.

## Viz také

[Design Details: Costing Methods](design-details-costing-methods.md)  
[Overview](design-details-inventory-costing.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]