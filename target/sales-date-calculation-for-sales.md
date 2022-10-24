---
    title: Date Calculation for Sales
    description: The application automatically calculates the date on which you must order an item to have it in inventory on a certain date and available for picking.
    author: SorenGP


    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/23/2021
    ms.author: edupont

---
# Výpočet data pro prodej
[!INCLUDE[prod_short](includes/prod_short.md)] automatically calculates the earliest possible date that an item on a sales order line can be shipped.

Pokud zákazník požádal o konkrétní datum dodání, vypočítá se datum, kdy musí být zboží k dispozici pro vyskladnění, aby splnilo dané datum dodání.

Pokud zákazník nepožaduje konkrétní datum dodání, vypočítá se datum, kdy lze zboží doručit, počínaje dnem, kdy jsou položky k dispozici k vyskladnění.

## Výpočet požadovaného data dodání
Pokud zadáte požadované datum dodání na řádku prodejní objednávky, stane se toto datum výchozím bodem pro následující výpočty.

- požadované datum dodání - čas dodávky = plánované datum dodávky
- plánované datum dodávky -  výstupní sklad doba zpracování = datum dodávky

Pokud je zboží dostupné k vyskladnění k datu dodávky, může proces prodeje pokračovat. Jinak se zobrazí varování o vyprodání zásob.

> [!Note]
> If your process is based on backward calculation, for example, if you use the requested delivery date to get the planned shipment date, we recommend that you use date formulas that have fixed durations, such as "5D" for five days or "1W" for one week. Datové vzorce bez pevné doby trvání, například „CW“ pro aktuální týden nebo CM pro aktuální měsíc, mohou mít za následek nesprávné výpočty data. For more information about date formulas, see [Work with Calendar Dates and Times](ui-enter-date-ranges.md).

## Výpočet nejbližšího možného data dodání
Pokud na řádku prodejní objednávky nezadáte požadované datum dodání nebo pokud požadované datum dodání nelze splnit, vypočítá se nejbližší možné datum, kdy bude zboží k dispozici. Toto datum se poté zadá do pole Datum dodávky na řádku a datum, kdy plánujete zboží odeslat, stejně jako datum, kdy budou zákazníkovi dodány, se vypočítá podle následujících vzorců.

- datum dodávky + výstupní sklad doba zpracování = plánované datum dodávky
- plánované datum dodávky + doba dodávky = plánované datum dodání


## Viz také
[Date Calculation for Purchases](purchasing-date-calculation-for-purchases.md)   
[Calculate Order Promising Dates](sales-how-to-calculate-order-promising-dates.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]