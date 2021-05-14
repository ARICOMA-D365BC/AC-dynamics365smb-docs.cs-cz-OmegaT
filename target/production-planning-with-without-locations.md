---
    title: Planning With or Without Locations | Microsoft Docs
    description: Planning with or without location codes on demand lines is important to understand.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2021
    ms.author: edupont

---
# Planning With or Without Locations
Concerning planning with or without location codes on demand lines, the planning system operates in a straight forward way when:

- demand lines always carry location codes and the system fully uses stockkeeping units, including the relevant location setup.
- demand lines never carry location codes and the system does not use SKUs or any location setup (see last scenario below).

However, if demand lines sometimes have location codes and other times do not, the planning system will follow certain rules depending on setup.

## Poptávka v lokaci
When the planning system detects demand at a location (a line with a location code), it will behave in different ways depending on 3 critical setup values.

During a planning run, the system checks for the 3 setup values in sequence and plans accordingly:

1. Is there a check mark in the **Location Mandatory** field?

   Pokud ano, tak:

2. Existuje karta skladové jednotky pro vybrané zboží?

   Pokud ano, tak:

   Položka je plánována podle parametrů plánování na kartě skladové jednotky.

   Pokud ne, pak:

3. Does the **Components at Location** field contain the demanded location code?

   Pokud ano, tak:

   Zboží je plánováno podle parametrů plánování na kartě zboží.

   Pokud ne, pak:

   The item is planned according to: Reordering Policy =  *Lot-for-Lot*, Include Inventory =  *Yes*, all other planning parameters = Empty. (Items using reordering policy  *Order* remain using  *Order* as well as the other settings.)

> [!NOTE]  
> This minimal alternative only covers the exact demand. Any planning parameters defined are ignored.

See variations in the scenarios below.

## Demand at "Blank Location"
Even if the **Location Mandatory** check box is selected, the system will allow demand lines to be created without a location code – also referred to as *BLANK* location. Jedná se o odchylku pro systém, protože má různé hodnoty nastavení vyladěné na práci s lokacemi (viz výše) a v důsledku toho plánovací modul nevytvoří řádek plánování pro takový řádek poptávky. If the **Location Mandatory** field is not selected but any of the location setup values exist, then that is also considered a deviation and the planning system will react by outputting the "minimal alternative":   
The item is planned according to: Reordering Policy =  *Lot-for-Lot* ( *Order* remains *Order)*, Include Inventory =  *Yes*, all other planning parameters = Empty.

See variations in the setup scenarios below.

### Nastavení 1:

- Location Mandatory = *Yes*
- SKU is set up for  *RED*
- Component at Location =  *BLUE*

#### Case 1.1: Demand is at  *RED* location

The item is planned according to planning parameters on the SKU card (including possible transfer).

#### Case 1.2: Demand is at  *BLUE* location

Zboží je plánováno podle parametrů plánování na kartě zboží.

#### Case 1.3: Demand is at  *GREEN* location

The item is planned according to: Reordering Policy =  *Lot-for-Lot* ( *Order* remains  *Order*), Include Inventory =  *Yes*, all other planning parameters = Empty.

#### Case 1.4: Demand is at  *BLANK* location

Zboží není plánována, protože na řádku poptávky není definováno žádné umístění.

### Nastavení 2:

- Location Mandatory = *Yes*
- Neexistují SKJ
- Component at Location =  *BLUE*

#### Case 2.1: Demand is at  *RED* location

The item is planned according to: Reordering Policy =  *Lot-for-Lot* ( *Order* remains  *Order*), Include Inventory =  *Yes*, all other planning parameters = Empty.

#### Case 2.2: Demand is at  *BLUE* location

Zboží je plánováno podle parametrů plánování na kartě zboží.

### Nastavení 3:

- Location Mandatory = *No*
- Neexistují SKJ
- Component at Location =  *BLUE*

#### Case 3.1: Demand is at  *RED* location

The item is planned according to: Reordering Policy =  *Lot-for-Lot* ( *Order* remains  *Order*), Include Inventory =  *Yes*, all other planning parameters = Empty.

#### Case 3.2: Demand is at  *BLUE* location

Zboží je plánováno podle parametrů plánování na kartě zboží.

#### Case 3.3: Demand is at  *BLANK* location

The item is planned according to: Reordering Policy =  *Lot-for-Lot* ( *Order* remains  *Order*), Include Inventory =  *Yes*, all other planning parameters = Empty.

### Nastavení 4:

- Location Mandatory = *No*
- Neexistují SKJ
- Component at Location =  *BLANK*

#### Case 4.1: Demand is at  *BLUE* location

The item is planned according to: Reordering Policy =  *Lot-for-Lot* ( *Order* remains  *Order*), Include Inventory =  *Yes*, all other planning parameters = Empty.

#### Case 4.2: Demand is at  *BLANK* location

Zboží je plánováno podle parametrů plánování na kartě zboží.

As you can see from the last scenario, the only way to get a correct result for a demand line without a location code is to disable all setup values relating to locations. Similarly, the only way to get stable planning results for demand at locations is to use stockkeeping units.

Therefore, if you often plan for demand at locations, it is strongly advised to use the Stockkeeping Units feature.

## Viz také
[Planning](production-planning.md)    
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)    
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Design Details: Supply Planning](design-details-supply-planning.md)   
[Setup Best Practices: Supply Planning](setup-best-practices-supply-planning.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]