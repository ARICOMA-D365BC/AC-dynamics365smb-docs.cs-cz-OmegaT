---
    title: Design Details - Internal Warehouse Flows
    description: Flow between bins centers on picking components and putting away end items for assembly or production orders and ad-hoc movements, without source documents.
    author: SorenGP


    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/15/2021
    ms.author: edupont

---
# Detaily návrhu: Interní skladové toky
Tok zboží mezi přihrádkami na skladě společnosti se soustředí na komponenty vychystávání a ukládání koncového zboží pro montážní nebo výrobní zakázky a adhoc přesuny. Jedný se například o doplnění přihrádky, bez vztahu ke zdrojovým dokladům. Rozsah a povaha zapojených činností se liší mezi základním a pokročilým skladováním.

Některé interní toky se překrývají s příchozími nebo odchozími toky. Některé z těchto kroků, které se překrávají jsou zobrazeny jako kroky 4 a 5 v diagramech pro pokročilé příchozí a odchozí toky. For more information, see [Design Details: Inbound Warehouse Flow](design-details-outbound-warehouse-flow.md).

## Vnitřní toky v základním nastavení skladu
V základní konfiguraci skladu se tok zboží mezi přihrádkami uvnitř společnosti soustředí na vyskladnění komponent a zaskladnění koncového zboží pro výrobní nebo montážní zakázky a adhoc přesuny. Jedná se o procesy jako je doplnění přihrádky, bez vztahu ke zdrojovým dokladům.

### Tok do a z Výroby
The main integration between production orders and basic warehouse activities is represented by the ability to pick production components with the **Inventory Pick** or the **Inventory Movement** pages.

> [!NOTE]  
> On the **Inventory Pick** page, the component consumption is posted together with the pick posting. By using the **Inventory Movement** page, only bin adjustments are registered, no item ledger posting occurs.

In addition to component handling, the integration is represented by the ability to put produced items away with the **Inventory Put-away** page.

The **To-Production Bin Code**, **From-Production Bin Code**, and **Open Shop Floor Bin Code** fields on the location card or the machine/work center cards define default flows to and from production areas.

Další informace o tom, jak je spotřeba komponent vyskladněna a spotřebována z Do výroby nebo přihrádky dílky běžte na "Spotřeba komponent výroby ve skladu" v tomto článku.

### Tok z a do Montáže
Hlavní integrace mezi montážními zakázkami a základními aktivitami skladu je reprezentována schopností přesunout komponenty montáže do montáží.

I když pro zaskladování položek montáže neexistují žádné specifické funkce skladu, kód přihrádky v hlavičce objednávky montáže může být nastaven na výchozí přihrádku, který je nastavena pro vyskladnění. Zaúčtování montážní zakázky pak funguje jako účtování vyskladnění. The warehouse activity to move assembly items into the warehouse can be managed on the **Internal Movement** page, with no relation to the assembly order.

Existují následující toky montáže.

| Tok | Popis |
|----------|---------------------------------------|  
| Montáž-na-sklad | The components are needed on an assembly order where the output is stored in the warehouse.<br /><br /> This warehouse flow is managed on the **Inventory Movement** page. Jeden řádek take určuje, odkud se budou brát komponenty. Další řádek určuje, kam se mají komponenty umístit. |
| Montáž-na-zakázku | Komponenty jsou potřebné na montážní zakázce, která je spojena s prodejní objednávkou, která je dodána a sestavena při zaúčtování objednávky. |

> [!NOTE]  
> If items are assembled to order, then the inventory pick of the linked sales order triggers an inventory movement for all the involved assembly components, not just for the sold item as when shipping inventory items.

The **To-Assembly Bin Code**, **From-Assembly Bin Code**, and **Asm.-to-Order Shpt. Bin Code** fields on the location card define default flows to and from assembly areas.

> [!NOTE]  
> The **Asm.-to-Order Shpt. Bin Code** field functions as the from-assembly bin in assemble-to-order scenarios.

### Ad-Hoc přesuny
In basic warehousing, the movement of items from bin to bin without relation to source documents is performed on the **Internal Movement** page, which functions together with the **Inventory Movement** page.

Another way to move items ad hoc between bins is to post positive entries in the **New Bin Code** field on the **Item Reclass. Journal** page.

## Interní skladové toky v rozšířeném nastavení skladu
V rozšířeném nastavení skladu je se tok mezi přihrádkami uvnitř společnosti soustředí na výdej komponent a vyskladnění koncového zboží pro výrobní zakázky a komponenty pro montážní zakázky. Kromě toho dochází k interním tokům jako jsou ad hoc přesuny, doplnění přihrádek, bez vztahu ke zdrojovým dokumentům.

### Toky z a do výroby
The main integration between production orders and advanced warehouse activities is represented by the ability to pick production components, on the **Warehouse Pick** page and the **Pick Worksheet** page, and the ability to put produced items away with the **Whse. Internal-Put-away** page.

Another integration point in production is provided with the **Warehouse Movement** page, together with the Movement Worksheet page, which enables you to place components and take produced items for released production orders.

The **To-Production Bin Code**, **From-Production Bin Code**, and **Open Shop Floor Bin Code** fields on the location card or the machine/work center cards define default flows to and from production areas.

Další informace o tom, jak je spotřeba komponent provedena z přihrádek do výroby nebo otevřené přihrádek dílny, naleznete v části Spotřeba výrobních komponent ve skladu v tomto článku.

### Tok z a do Montáže
The main integration between assembly orders and advanced warehouse activities is represented by the ability to pick assembly components, both with the **Warehouse Pick** page and the **Pick Worksheet** page. Tato funkce funguje stejně jako při vyskladnění komponent pro výrobní zakázky.

I když pro zaskladování položek montáže neexistují žádné specifické funkce skladu, kód přihrádky v hlavičce objednávky montáže může být nastaven na výchozí přihrádku, který je nastavena pro vyskladnění. Zaúčtování montážní zakázky pak funguje jako účtování vyskladnění. The warehouse activity to move assembly items into the warehouse can be managed on the **Movement Worksheet** page or the **Whse. Internal Put-away** page, with no relation to the assembly order.

> [!NOTE]  
> If items are assembled to order, then the warehouse shipment of the linked sales order triggers a warehouse pick for all the involved assembly components, not just for the sold item as when shipping inventory items.

The **To-Assembly Bin Code** and **From-Assembly Bin Code** fields on the location card define default flows to and from assembly areas.

### Ad-Hoc přesuny
In advanced warehousing, the movement of items from bin to bin without relation to source documents is managed on the **Movement Worksheet** page and registered in the Warehouse Movement page.

## Spotřeba výrobních komponent ve skladu
Pokud jsou komponenty vyskladněné pomocí vyskladnění jsou účtované jako spotřeba montáže, když se vyskladnění zapíše. By using the **Pick + Forward** method and the **Pick + Backward** flushing method, the pick registration triggers the related consumption posting when the first operation starts or when the last operation finishes, respectively.

Consider the following scenario based on the [!INCLUDE[prod_short](includes/prod_short.md)] demonstration database.

Existuje výrobní zakázka na 15 Ks zboží LS-100. Some of the items on the component list must be flushed manually in a consumption journal, and other items on the list can be picked and flushed automatically using the **Pick + Backward** flushing method.

> [!NOTE]  
> **Pick + Forward** only works if the second production routing line operation uses a routing link code. Releasing a planned production order initiates forward flushing of components set to **Pick + Forward**. Spotřeba však nemůže probíhat, dokud není zapsáno vyskladnění komponent, což se opět může uskutečnit pouze po vydání objednávky.

Následující kroky popisují související akce různých uživatelů a odpovídající odpověď:

1. Vedoucí dílny uvolní výrobní zakázku. Items with **Forward** flushing method and no routing link code are deducted from the open shop floor bin.
2. The shop floor supervisor chooses the **Create Warehouse Pick** button on the production order. A warehouse pick document is created pick for items with **Manual**, **Pick + Backward**, and **Pick + Forward** flushing methods. Tyto položky jsou umístěny do přihrádky výroby.
3. Správce skladu přiřadí vyskladnění skladníkovi.
4. Pracovník skladu vyskladní zboží z příslušných přihrádek a umístí je do přihrádky výroby nebo do přihrádky určené ve vyskladnění, což může být přihrádka pracovního nebo strojního centra.
5. Pracovník skladu zapíše vyskladnění. Množství se odečte z přihrádek pro vyskladnění a přidá se do přihrádky spotřeby. **Množství Picked** field on the component list for all picked items is updated.

   > [!NOTE]  
   > Only the quantity that is picked can be consumed.

6. Obsluha stroje informuje vedoucího výroby, že koncové zboží je hotovo.
7. The shop floor supervisor uses the consumption journal or production journal to post the consumption of component items that use either **Manual** flushing method or **Forward** or **Pick + Forward** flushing methods together with routing link codes.
8. The production manager posts the output of the production order and changes status to **Finished**. The quantity of component items that use **Backward** flushing method is deducted from the open shop floor bin, and the quantity of component items that use **Pick + Backward** flushing method is deducted from the To-Production bin.

The following illustration shows when the **Bin Code** field on the component list is filled according to your location or machine/work center setup.

![Overview of when/how the Bin Code field is filled in.](media/binflow.png "Overview of when/how the Bin Code field is filled in")

## Viz také
[Detaily návrhu: Správa skladu](design-details-warehouse-management.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]