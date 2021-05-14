---
    title: Add Attachments, Links, and Notes on Records| Microsoft Docs
    description: Attach a hyperlink to a document or website to a specific record, such as a customer or document.
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
# Správa příloh, odkazů a poznámek ke kartám a dokladům

Ve FactBoxu na většině karet a dokladů můžete připojit soubory, přidávat odkazy a psát poznámky. V případě odkazů a poznámek to můžete udělat také na stránce přehledu tak, že nejprve vyberete příslušný řádek.

To view or change any of these attached information types, you must first open the **Attachments** tab in the FactBox. Číslo za názvem karty udává, kolik připojených souborů, odkazů nebo poznámek existuje pro kartu nebo doklad.

Přílohy, odkazy a poznámky zůstávají připojeny, protože karta nebo doklad je zpracován do jiných oblastí systému, například z probíhající prodejní objednávky na zaúčtovanou prodejní fakturu. Žádný z typů příloh však není výstupem ze systému, například při tisku nebo při ukládání do souboru.

> [!NOTE]
> When you partially ship and invoice a sales or purchase order, the attachment will only be attached to the final invoice of the order. Similarly, when you invoice using the Deferrals feature, the attachment is attached to the G/L entries for the document but not for the deferral entries.
>
> If you delete an order before it is invoiced, the attachment is also removed. When you invoice purchase orders using the Get Receipt Lines action from a purchase invoice, the attachment on the purchase orders is not added to the purchase invoice.

## Připojení souboru k nákupní faktuře
Ke kartě nebo dokladu můžete připojit libovolný typ souboru obsahujícího text, obrázek nebo video. This is useful, for example, when you want to store a vendor's invoice as a PDF file on the related purchase invoice in [!INCLUDE[prod_short](includes/prod_short.md)].

> [!NOTE]
> Files attached with the Incoming Documents feature are not included on the **Attachments** tab. For more information, see [Incoming Documents](across-income-documents.md).

Následující postup je založen na nákupní faktuře. Kroky jsou podobné pro všechny ostatní podporované doklady a karty.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices**, and then choose the related link.
2. Otevřete prodejní objednávku, ke které chcete připojit soubor.
3. In the FactBox, open the **Attachments** tab.
4. Choose the value behind the **Documents** field, such as "0".
5. On the **Attached Documents** page, in the **Attachment** field, choose the **Select File** action.
5. Select a file from any location, and then choose the **Open** button.

Soubor je nyní připojen k nákupní faktuře.

## Zobrazení připojeného souboru
1. In the FactBox, open the **Attachments** tab.
2. Choose the value behind the **Documents** field, such as "1".
3. On the **Attached Documents** page, choose the **Preview** action.
4. Otevřete stažený soubor.

## Uložení doklad jako přílohy PDF
Whenever you need to save a document as a file, you can use the **Attach as PDF** action to capture the current document content as a PDF file attached to the FactBox of the document. To je užitečné například tehdy, když doklady sledují několik kroků v procesu, například prodejní proces nebo workflow schvalování, a chcete odkazovat na tisk předchozího kroku.

Následující postup je založen na prodejní objednávce. Kroky jsou podobné pro všechny podporované dokumenty.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Prodejní objednávky** a poté zvolte související odkaz.
2. Select a sales order, and then choose the **Attach as PDF** action.

A PDF file with the current content of the sales order is added to the **Attachments** tab in the FactBox.

## Přidání odkazu z karty zboží
Můžete přidat odkaz z karty nebo dokladu na libovolnou URL adresu nebo cestu. To je užitečné například tehdy, když chcete propojit kartu zboží s katalogem zboží dodavatele.

Následující postup je založen na kartě zboží. Postup je podobný pro všechny ostatní podporované karty a doklady.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat") zadejte **Zboží** a poté vyberte související odkaz.
2. Select the item that you want to add a link from, and then choose the **Attachments** tab in the FactBox.
3. In the **Links**, choose the **+** icon.
4. In the **Link Address** field, enter the link.

   Odkaz musí být platná internetová nebo intranetová URL adresa.

5. In the **Description** field, enter any information about the link.
6. Zvolte tlačítko **OK**.

Odkaz je nyní připojen k kartě zboží.

## Poznámka na prodejní objednávce
Můžete napsat poznámku na dokument nebo kartu, například sdělit zvláštní pokyny ostatním uživatelům dokladu nebo karty. Do poznámek můžete zahrnout odkazy na soubory a adresy URL.

> [!NOTE]
> Notes on the **Attachments** tab are not related to internal notes functionality, which is mainly used to communicate between workflow users. For more information, see [Setting Up Workflow Notifications](across-setting-up-workflow-notifications.md).

Následující postup je založen na prodejní objednávce. Kroky jsou podobné pro všechny ostatní podporované doklady a karty.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Prodejní objednávky** a poté zvolte související odkaz.
2. Select the sales order that you want to write a note on, and then choose the **Attachments** tab in the FactBox.
3. In the **Notes** section, choose the **+** icon.
4. In the **Note** field, write any text, such as "This is an urgent order.".
5. Zvolte tlačítko **OK**.

Poznámka je nyní připojena k prodejní objednávce.

## Viz také
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Incoming Documents](across-income-documents.md)  
[Setting Up Workflow Notifications](across-setting-up-workflow-notifications.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]