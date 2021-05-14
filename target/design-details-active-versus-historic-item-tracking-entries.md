---
    title: Design Details - Active versus Historic Item Tracking Entries | Microsoft Docs
    description: When parts of a document line quantity are posted, only that particular quantity is transferred to the item ledger entries and its item tracking numbers. However, you will want to access all relevant item tracking information directly from the active document line. That is, not only will you want to see the entries that are related to the remaining quantity, you will also want information about the units that have been posted. When you view or modify the **Item Tracking Lines** page, the collective contents of the **Tracking Specification** table (T336) and **Reservation Entry** table (T337) are presented in a temporary version of T336. This ensures that historic and active item tracking data is accessed as one.
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
# Detaily návrhu: Aktivní versus historické položky sledování zboží
Při zaúčtování částí řádku dokladu je do položek zboží a jeho čísel sledování zboží převedeno pouze toto určité množství. Nicméně budete chtít získat přístup ke všem relevantním informacím o sledování položek přímo z aktivního řádku dokumentu. To znamená, že budete chtít nejen zobrazit položky, které souvisejí se zbývajícím množstvím, ale budete také chtít informace o položkách, které byly zaúčtovány. When you view or modify the **Item Tracking Lines** page, the collective contents of the **Tracking Specification** table (T336) and **Reservation Entry** table (T337) are presented in a temporary version of T336. Tím je zajištěno, že historické a aktivní sledování zboží je přístupné jako jedno.

The following table shows how T336 and T337 are used in a purchase scenario. The bold figures represent values that the user manually enters on the **Item Tracking Lines** page.

Krok 1: Vytvořte řádek nákupní objednávky se sedmi kusy se sledování zboží.

||**Quantity (Base)**|**Qty. to Handle**|**Qty. to Invoice (Base)**|**Quantity Handled (Base)**|**Quantity Invoiced (Base)**|  
|-|----------------------------------------------|--------------------------------------------|------------------------------------------------------|-------------------------------------------------------|--------------------------------------------------------|  
|**T337**|7|0|0|0|0|  
|**T336**|0|0|0|0|0|

Krok 2: Napřímujte čtyři kusy.

||**Quantity (Base)**|**Qty. to Handle**|**Qty. to Invoice (Base)**|**Quantity Handled (Base)**|**Quantity Invoiced (Base)**|  
|-|----------------------------------------------|--------------------------------------------|------------------------------------------------------|-------------------------------------------------------|--------------------------------------------------------|  
|**Item Tracking Lines** page|7|**4**|**0**|0|0|  
|**T337**|3|0|0|0|0|  
|**T336**|4|0|0|4|0|

Krok 3: Napřímujte a vyfakturujte dva kusy.

||**Quantity (Base)**|**Qty. to Handle**|**Qty. to Invoice (Base)**|**Quantity Handled (Base)**|**Quantity Invoiced (Base)**|  
|-|----------------------------------------------|--------------------------------------------|------------------------------------------------------|-------------------------------------------------------|--------------------------------------------------------|  
|**Item Tracking Lines** page|7|**2**|**2**|4|0|  
|**T337**|1|0|0|0|0|  
|**T336**|6|0|0|6|2|

Krok 4: Napřímujte jeden kus.

||**Quantity (Base)**|**Qty. to Handle**|**Qty. to Invoice (Base)**|**Quantity Handled (Base)**|**Quantity Invoiced (Base)**|  
|-|----------------------------------------------|--------------------------------------------|------------------------------------------------------|-------------------------------------------------------|--------------------------------------------------------|  
|**Item Tracking Lines** page|7|**1**|**0**|6|2|  
|**T336**|7|0|0|7|2|

Vyfakturujte pět kusů.

||**Quantity (Base)**|**Qty. to Handle**|**Qty. to Invoice (Base)**|**Quantity Handled (Base)**|**Quantity Invoiced (Base)**|  
|-|----------------------------------------------|--------------------------------------------|------------------------------------------------------|-------------------------------------------------------|--------------------------------------------------------|  
|**Item Tracking Lines** page|7|0|**5**|7|2|  
|**T336**|7|0|0|7|7|

## Viz také
[Design Details: Item Tracking](design-details-item-tracking.md)   
[Design Details: Item Tracking Lines Page](design-details-item-tracking-lines-window.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]