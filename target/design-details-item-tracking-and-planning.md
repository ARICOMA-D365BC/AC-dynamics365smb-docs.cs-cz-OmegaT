---
    title: Design Details - Item Tracking and Planning | Microsoft Docs
    description: Because they are stored in the reservation system, item tracking numbers are fully coordinated with order tracking records.
    author: SorenGP

    
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/08/2021
    ms.author: edupont

---
# Detaily návrhu: Sledování zboží a plánování
Vzhledem k tomu, že jsou čísla sledování zboží uložena v rezervačním systému, jsou plně koordinována se záznamy sledování objednávek. To znamená, že položkám se záznamem sledování objednávek mohou být přiřazena čísla sledování zboží. Naopak položky, které mají čísla sledování zboží, se mohou stát záznamy sledování objednávek. For more information, see [Design Details: Item Tracking Design](design-details-item-tracking-design.md).

For more information about the integrated systems, see [Design Details: Reservations, Order Tracking, and Action Messaging](design-details-reservation-order-tracking-and-action-messaging.md).

Protože sledování objednávek se týká pouze konkrétní aplikace na položky, vztahuje se koordinace s čísly sledování zboží pouze na položky tak, aby používaly určité sledování zboží. This is set by the **SN Specific Tracking** and **Lot Specific Tracking** fields on the item card, which specify the following:

- Zboží musí mít při účtování sériové číslo nebo číslo šarže.
- Pokud je zboží účtovano na výstupních dokladech, musí obsahovat stejné sériové číslo nebo číslo šarže.

V souladu se standardními zásadami vyrovnávání nabídky a poptávky systém plánování a související funkce sledování objednávek odpovídají číslům sledování zboží pouze v případě, že předmět používá specifické sledování zboží. Ve všech ostatních případech systémy plánování a sledování objednávek ignorují čísla sledování zboží, když vyrovnávají nabídku, aby splnily poptávku nebo vyrovnávají poptávku na dodávku. For more information, see [Design Details: Reservation, Order Tracking, and Action Messaging](design-details-reservation-order-tracking-and-action-messaging.md).

For example, when order tracking exists for a given item, it implies that records for the item are already in the **Reservation Entry** table, which is the core of the reservation system, before the item tracking numbers are defined. Proto se na čísla sledování zboží, která mají být sledována, vztahují následující omezení párování:

- Poptávka se sériovým číslem nebo číslem šarže může pokrýt pouze dodávku se stejným sériovým číslem nebo číslem šarže.
- Poptávka bez sériového čísla nebo čísla šarže může pokrýt jakoukoli dodávku s nebo bez sériového čísla nebo čísla šarže.

Kromě jejich důsledků pro dynamické sledování objednávek, omezení pro sledování zboží významně neovlivňují plánovací systém.

Na straně dodávky zboží se sériové číslo nebo číslo šarže obvykle nezadá, dokud není objednávka zaúčtována, například: Nákupní příjemkou. Při zadávání sériového čísla nebo čísla šarže na straně poptávky, například na prodejní objednávce, je toto sériové číslo nebo číslo šarže již skladem. V souladu s tím čísla sledování zboží obvykle nejsou problémem při plánování dodávek.

U zboží, které používají specifické sledování zboží, musí být všechny požadavky nesoucí sériová čísla nebo čísla šarží porovnány s odpovídajícími čísly dodávek. Ve většině případů nemá smysl změnit pořadí konkrétního sériového čísla nebo čísla šarže, takže plánování nákupu nebo dodávek výroby pravděpodobně není ovlivněno. Při převodu zboží z jedné lokace na druhou je však pravděpodobné, že transfer je pro určitou šarži, takže plánování dodávek převodu může být ovlivněno specifickým omezením.

For more information, see [Design Details: Transfers in Planning](design-details-transfers-in-planning.md).

## Vyvážení nabídky a poptávky
Pokud zboží vyžaduje určité sledování zboží, je z veškeré poptávky po sledování zboží vyroben odkaz na sledování zboží na jakoukoli odpovídající dodávku sledování zboží, s jediným omezením, že nabídka by měla přijít před poptávkou. Pokud za těchto okolností nelze nalézt žádnou dodávku sledování zboží, která by odpovídala poptávce specifické pro sledování zboží, je okamžitě a bez ohledu na velikost objednávky, parametry plánování nebo přeplánování stávající dodávky stejného sériového čísla nebo čísla šarže vytvořena nová dodávka sledování zboží.

Pokud jsou čísla sledování zboží přiřazena na straně poptávky nebo na straně nabídky, aniž by bylo vyžadováno konkrétní sledování zboží, je z poptávky na tuto nabídku vyrobeno spojení na základě nejvhodnějšího časování a množství, jako v obvyklém postupu vyrovnávání. Zadané číslo sledování zboží přejde do záznamu sledování objednávky stejným způsobem, jakým jakékoli zadané množství sledování zboží definuje jeden konec odkazu pro sledování objednávky. To znamená, že zadané sledovací číslo položky je zachováno, zatímco je také součástí záznamu o sledování objednávky.

Pokud jsou čísla sledování zboží přiřazena na straně dodávky, aniž by bylo vyžadováno konkrétní sledování zboží, považuje se tato dodávka jako pevně plánovaná systémem. Pro tuto dodávku se nenavrhují žádné změny velikosti ani přeplánování, ale dodávka se zohlední, když se plánovací systém pokusí splnit hrubé požadavky.

For more information, see [Design Details: Balancing Demand and Supply](design-details-balancing-demand-and-supply.md).

## Viz také
[Design Details: Item Tracking Design](design-details-item-tracking-design.md)  
[Design Details: Balancing Demand and Supply](design-details-balancing-demand-and-supply.md)  
[Design Details: Reservation, Order Tracking, and Action Messaging](design-details-reservation-order-tracking-and-action-messaging.md)   
[Design Details: Supply Planning](design-details-supply-planning.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]