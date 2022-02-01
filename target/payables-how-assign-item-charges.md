---
title: Assign Item Charges to Sales and Purchases (contains video)
description: Assign item charges when you need inventory items to carry added costs, such as freight and physical handling that you incur when purchasing or selling items.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: transportation, added cost, landed cost
ms.search.form: 5709, 5800, 5805, 5814
ms.date: 06/22/2021
ms.author: edupont

---
# Použití poplatku zboží k účtování dodatečných obchodních nákladů
Aby bylo zajištěno správné ocenění, musí vaše skladové zboží nést veškeré dodatečné náklady, jako je přeprava, fyzická manipulace, pojištění a doprava, které vám vzniknou při nákupu nebo prodeji zboží. U nákupů se vyložené náklady na nakoupené zboží skládají z nákupní ceny dodavatele a všech dodatečných přímých poplatků za zboží, které lze přiřadit k jednotlivým příjmům nebo dodávkám vratky. Pro prodej může být znalost nákladů na dopravu prodaných položek pro vaši společnost stejně důležitá jako znalost nákladů na vyložené položky.

Kromě zaznamenání přidaných nákladů do hodnoty zásob můžete použít funkci Poplatky za zboží pro následující:

- Určete náklady na vyložené zboží pro přesnější rozhodování o optimalizaci distribuční sítě.
- Pro účely analýzy rozdělte pořizovací cenu nebo jednotkovou cenu zboží.
- Include purchase allowances into the unit cost and sales allowances into the unit price.

Před přiřazením poplatků za zboží je nutné nastavit čísla poplatků za zboží pro různé typy poplatků za zboží, včetně nákladů na účty souvisejících s prodejem, nákupy a úpravami zásob. Číslo poplatku za zboží obsahuje kombinaciobecné účto skupiny zboží, daňové skupiny, DPH účto skupiny zboží a poplatku zboží. dyž zadáte číslo poplatku za zboží na nákupním nebo prodejním dokladu, příslušný účet se načte na základě nastavení čísla poplatku za zboží a informací v dokladu.

U nákupních i prodejních dokladů můžete poplatek za zboží přiřadit dvěma způsoby:
- V dokladu, kde je uvedeno zboží, ke kterému se poplatek za zboží vztahuje. To obvykle děláte pro doklady, které ještě nejsou plně zaúčtovány.
- Na samostatné faktuře propojením poplatku za zboží se zaúčtovanou příjemkou nebo dodávkou, kde je uvedeno zboží, ke kterému se poplatek za zboží vztahuje.

> [!NOTE]  
> You can assign item charges to orders, invoices, and credit memos, for both sales and purchases. Následující postupy popisují, jak pracovat s poplatky za zboží v nákupní faktuře. Kroky jsou podobné pro všechny ostatní nákupní a prodejní doklady.

## Příklad
Toto video ukazuje, jak zpracovat dodatečné náklady na dopravu v rámci nákladů zásob.
<br><br>
> [!Video https://www.microsoft.com/videoplayer/embed/RE4b0SB?rel=0]

## Nastavení čísel poplatků za zboží
Čísla poplatků za zboží slouží k rozlišení mezi různými druhy poplatků za zboží, které se používají ve vaší společnosti.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Charges**, and then choose the related link.
2. On the **Item Charges** page, choose the **New** action to create a new line.
3. Podle potřeby vyplňte pole. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## Přiřazení poplatku za zboží přímo k nákupní faktuře za zboží
Pokud znáte poplatek za zboží v době, kdy účtujete nákupní fakturu za zboží, postupujte podle tohoto postupu.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices**, and then choose the related link.
2. Vytvořte novou nákupní fakturu. For more information, see [Record Purchases](purchasing-how-record-purchases.md).
3. Ujistěte se, že nákupní faktura má jeden nebo více řádků typu Zboží.
4. On a new line, in the **Type** field, select **Charge (Item)**.
5. In the **Quantity** field, enter the units of the item charge that you have been invoiced for.
6. In the **Direct Unit Cost** field, enter the amount of the item charge.
7. Podle potřeby vyplňte zbývající pole. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

   V následujících krocích provedete skutečné přiřazení. Until the item charge is fully assigned, the value in the **Qty. to Assign** field is in red font.
8. On the **Lines** tab, choose the **Item Charge Assignment** action.

   The **Item Charge Assignment** page opens showing one line for each line of type Item on the purchase invoice. To assign the item charge to one or more invoice lines, you can use a function that assigns and distributes it for you or you can manually fill in the **Qty. to Assign** field. Následující kroky popisují, jak používat funkci Navrhnout přiřazení poplatku za zboží.

9. On the **Item Charge Assignment** page, choose the **Suggest Item Charge Assignment** action.
10. Pokud existuje více než jeden řádek faktury typu Zboží, zvolte jednu ze čtyř možností rozdělení.

It the item charge is fully assigned, the value in the **Qty. to Assign** field on the purchase invoice is zero.

Poplatek za zboží je nyní přiřazen k nákupní faktuře. Při zaúčtování příjmu nákupní faktury se hodnoty zásob zboží aktualizují o náklady na poplatek za zboží.

## Přiřazení poplatku za zboží ze samostatné faktury k nákupní faktuře za zboží
Pokud jste po zaúčtování původního nákupního dokladu obdrželi fakturu za poplatek za zboží, postupujte podle tohoto postupu.
1. Repeat steps 1 through 8 in [To assign an item charge directly to the purchase invoice for the item](payables-how-assign-item-charges.md#to-assign-an-item-charge-directly-to-the-purchase-invoice-for-the-item).
2. On the **Item Charge Assignment** page, choose the **Get Receipt Lines** action.
3. On the **Purch. Receipt Lines** page, select the posted purchase receipt for the item that you want to assign the item charge to, and then choose the **OK** button.
4. Choose the **Suggest Item Charge Assignment** action.

Poplatek za zboží na samostatné nákupní faktuře je nyní přiřazen zboží na zaúčtované nákupní příjemce, čímž se aktualizuje hodnota zásob zboží s náklady na poplatek za zboží.

## Viz také
[Managing Payables](payables-manage-payables.md)  
[Record Purchases](purchasing-how-record-purchases.md)  
[Invoice Sales](sales-how-invoice-sales.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]