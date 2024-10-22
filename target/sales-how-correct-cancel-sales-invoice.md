---
title: Correct or Cancel a Posted Sales Invoice
description: This topic describes how to correct, undo, or cancel a posted sales invoice and apply a sales credit memo.
author: SorenGP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: undo, credit memo, return
ms.date: 06/23/2021
ms.author: edupont

---
# Oprava nebo zrušení nezaplacené prodejní faktur

You can correct or cancel an unpaid posted sales invoice, provided that it has not been fully shipped. This is useful if you make a mistake or if the customer requests a change before the shipment is complete. In all other scenarios, we recommend that you create a corrective sales credit memo directly. For more information, see [To create a sales credit memo from a posted sales invoice](sales-how-process-sales-returns-cancellations.md#to-create-a-sales-credit-memo-from-a-posted-sales-invoice).

> [!NOTE]  
> After a posted sales invoice has been partially or fully paid, you cannot correct or cancel it from the posted sales invoice itself. Místo toho musíte ručně vytvořit dobropis prodeje, který zruší prodej a odškodní zákazníka, případně je to možné udělat objednávkou prodejní vratky. For more information, see [Process Sales Returns or Cancellations](sales-how-process-sales-returns-cancellations.md).

The difference between canceling or correcting a posted sales invoice that has not been paid or shipped is described in the following table.

| Akce | Popis |
| --- | --- |
| **Zrušit** | Účtovaná prodejní faktura je zrušena. Automaticky se vytvoří a zaúčtuje opravný prodejný dobropis, který zruší původní účtovanou prodejní fakturu. On the initial posted sales invoice, the **Canceled** and **Paid** check boxes are selected. |
| **Opravit** | Účtovaná prodejní faktura je zrušena. A new sales invoice with the same information is created, unless the posted sales order was posted from a sales order. In that case, we suggest you cancel the posted sales invoice instead and then make the correction and continue the sales process from the original sales order. <br/><br/>The new sales invoice has a different number than the initial sales invoice. Automaticky se vytvoří a zaúčtuje opravný prodejný dobropis, který zruší původní účtovanou prodejní fakturu. On the initial posted sales invoice, the **Canceled** and **Paid** check boxes are selected. |

Při opravě nebo zrušení zaúčtované prodejní faktury je opravný prodejní dobropis aplikován na všechny věcné a skladové položky, které byly vytvořeny při účtování původní prodejní faktury. To obrátí účtovanou prodejní fakturu ve vašich finančních záznamech a ponechá účtovaný opravný prodejní dobropis pro vaši auditní stopu.

> [!TIP]
> If you have posted a prepayment invoice for a sales invoice that you then correct or cancel, you must correct or cancel the prepayment as well. For more information, see [Correct Prepayments](finance-how-to-correct-prepayments.md).

## Pro zrušení účtované prodejní faktury

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Sales Invoices**, and then choose the related link.
2. Vyberte účtovanou prodejní fakturu, kterou chcete zrušit.

   > [!NOTE]  
   > If the **Canceled** check box is selected, then you cannot cancel the posted sales invoice because it has already been canceled or corrected.
3. Na stránce **Účtovaná prodejní faktura** vyberte akci **Zrušit**.

   Prodejní dobropis je automaticky vytvořen a účtován pro zrušení původní účtované prodejní faktury. Pole **Zrušeno** na původní účtované prodejní faktuře se změní na **Ano**.
4. Zvolte **Zobrazit opravný dobropis** pro zobrazení účtovaného prodejního dobropisu, který zruší původní účtovanou prodejní fakturu.

### Partial invoice posting also supported

Pokud zrušení souvisí s částečným účtováním faktury, je původní řádek prodejní objednávky aktualizován tak, aby odrážel zrušené fakturované množství. **Množství fakturovat** a **Množství Fakturovaná** pole na souvisejícím řádku prodejní objednávky jsou obnoveny na hodnoty před částečným účtováním.

## Pro opravu účtované prodejní faktury

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Sales Invoices**, and then choose the related link.
2. Vyberte účtovanou prodejní fakturu, kterou chcete opravit.

   > [!NOTE]  
   > If the **Canceled** check box is selected, then you cannot correct the posted sales invoice because it has already been corrected or canceled.
3. Na stránce **Účtovaná prodejní faktura** vyberte akci **Opravit**.

   > [!NOTE]
   > If the sales invoice was posted from a sales order, we recommend that you *cancel* this sales invoice and then process the correction from the original sales order. If the original sales order has been deleted, such as if it has been fully shipped, you can create a new sales order by using the **Copy Document** action. For more information, see [To create a sales credit memo by copying a posted sales invoice](sales-how-process-sales-returns-cancellations.md#to-create-a-sales-credit-memo-by-copying-a-posted-sales-invoice).
4. Vytvoří se nová prodejní faktura se stejnými informacemi, kde můžete provést opravu. Pole **Zrušeno** na původní účtované prodejní faktuře se změní na **Ano**.

   Prodejní dobropis je automaticky vytvořen a účtován pro zrušení původní účtované prodejní faktury.
5. Zvolte akci **Zobrazit opravný dobropis** pro zobrazení účtovaného prodejního dobropisu, který zruší původní účtovanou prodejní fakturu.

## Viz také

[Sales](sales-manage-sales.md)  
[Setting Up Sales](sales-setup-sales.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]