---
    title: Archive Sales and Purchase Documents
    description: You can archive sales and purchase orders, quotes, return orders, and blanket orders so that you can use the archived document to recreate the document that it was archived from.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/29/2021
    ms.author: edupont

---
# Archivování dokladů
Můžete archivovat prodejní a nákupní objednávky, nabídky, objednávky vratky a hromadné objednávky, například proto, že chcete uložit kopii dokumentu pro pozdější použití. Prodejní nebo nákupní doklad můžete archivovat několikrát a pokaždé uložit jinou archivovanou verzi.

For archived sales documents where the original still exists and is not posted, you can use the **Restore** function to overwrite the original with the archived version of the document. To je praktické, pokud potřebujete obnovit obsah dokladu do dřívějšího stavu.

For archived documents where the original is deleted, you can only reuse the content by copying the data, for example with the **Copy from Document** function.

## Nastavení automatické archivace dokladu

Před odstraněním dokladů můžete nastavit automatickou archivaci prodejních a nákupních objednávek, nabídek, hromadných objednávek a objednávek vratek.

Následující postup popisuje, jak nastavit automatickou archivaci prodejních dokladů. Kroky jsou podobné i pro nákupní dokumenty.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Nastavení prodeje a pohledávek** a poté vyberte související odkaz.
2. On the **Sales & Receivables Setup** page, fill in the fields. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

Specifically for the **Archive Quotes** field, the following table outlines the difference between the options.

| Možnost | Popis |
|------|-----------|
| **Never** | Never archive sales quotes when they are deleted. |
| **Question** | Select to prompt the user to choose whether to archive sales quotes when they are deleted. |
| **Always** | Select to archive sales quotes automatically when they are deleted. |

## Archivace prodejní objednávky

Následující postup popisuje, jak archivovat prodejní objednávku. Postup je podobný jako u všech objednávek, hromadných objednávek, objednávek vratek a nabídek.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.
2. Otevřete prodejní objednávku, kterou chcete archivovat.
3. Choose the **Archive Document** action.

Prodejní objednávka je archivována. You can view it on the **Archived Sales Orders** page.

## Obnovení nezaúčtované prodejní objednávky z archivu

Následující postup popisuje, jak přenést obsah archivované prodejní objednávky zpět na původní prodejní objednávku. To je možné pouze tehdy, pokud původní dokument nebyl zaúčtován. Postup je podobný jako u všech objednávek, hromadných objednávek, objednávek vratek a nabídek.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Order Archives**, and then choose the related link.
2. Select the archived sales order, or version of it, that you want to restore, and then choose the **Restore** action.

Obsah původní prodejní objednávky bude nahrazen textem vybrané archivované verze.

## Odstranění archivovaných prodejních objednávek

Následující postup popisuje, jak odstranit archivované prodejní objednávky. Postup je podobný ostatním archivovaným prodejním a nákupním dokladům.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Order Archives**, and then choose the related link.
2. Choose the **Delete Archived Sales Order Versions** action, and then, on the **Delete Archived Sales Order Versions** page, select the appropriate filters.
3. Zvolte tlačítko **OK**.

## Viz také

[Track Document Lines](across-how-to-track-document-lines.md)  
[Sales](sales-manage-sales.md)  
[General Business Functionality](ui-across-business-areas.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
