---
    title: Set Up Put-away Templates
    description: Use Put-away templates to have the most appropriate bins for your items suggested to you at any given time.
    author: SorenGP

    
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.form: 7312, 7313, 7314, 7321, 7322, 7323, 7329
    ms.date: 06/25/2021
    ms.author: edupont

---
# Nastavení šablon zaskladnění

Při funkci řízeného zaskladnění a vyskladnění se navrhne nejvhodnější přihrádka pro vaše zboží v kterémkoli daném okamžiku podle šablony zaskladnění, kterou jste pro sklad nastavili, pořadí přihrádek, které jste přihrádkám dali, a minimální a maximální množství, které jste nastavili pro pevné přihrádky.

Můžete nastavit počet šablon zaskladnění a vybrat jednu z nich, která bude řídit zaskladnění ve vašem skladu. Můžete také vybrat šablonu zaskladnění pro jakoukoliv položku nebo skladovou jednotku, která může mít zvláštní požadavky zaskladnění.

## Nastavení šablon zaskladnění

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Put-away Templates**, and then choose the related link.
2. Vyberte akci **Nový**.
3. Zadejte kód, který je jedinečným identifikátorem šablony, kterou se chystáte vytvořit.
4. Zadejte krátký popis, pokud chcete.
5. Vyplňte první řádek požadavků přihrádky, které chcete splnit v jako první při navrhování zaskladnění.

   For example, if want the default put-away method to be based on fixed bins, then choose the **Find Fixed Bin** field. [!INCLUDE[tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]
6. Do druhého řádku zadejte požadavky na přihrádku, které jsou vaší druhou volbou při hledání přihrádky pro zaskladnění. Druhý řádek se použije pouze v případě, že nelze najít přihrádku, která splňuje požadavky prvního řádku.
7. Pokračujte v vyplňování řádků, dokud nevyplníte všechna přijatelná umístění přihrádky, které chcete v procesu zaskladnění použít.
8. On the last line in the put-away template, select the **Find Floating Bin** check box.

Můžete vytvořit různé šablony zaskladnění a pak je použít podle svého uvážení. Šablonu zaskladnění, kterou jste vybrali pro zboží nebo skladovou jednotku je použita jako první. If these fields are not filled in, then the put-away template that you selected for the warehouse on the **Bin Policies** FastTab on the location card is used.

## Viz také

[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Assembly Management](assembly-assemble-items.md)  
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]