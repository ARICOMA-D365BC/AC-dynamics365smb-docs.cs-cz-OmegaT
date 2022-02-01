---
title: Verify Automatically Applied Payments, and Reapply Payments Manually | Microsoft Docs
description: After payments are applied automatically, you can review all the entries for a payment and manually reapply those that were applied incorrectly.

author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment process, reconcile payment, expenses, cash receipts
ms.date: 04/01/2021
ms.author: edupont

---
# Ruční kontrola nebo vyrovnání plateb po automatickém vyrovnání
U každého řádku deníku představujícího platbu na stránce **Deníky odsouhlasení plateb** můžete otevřít stránku  **Vyrovnání plateb** a zobrazit všechny kandidátní otevřené položky pro platbu a zobrazit detailní informace o každé položce o spolehlivosti párování, na které je založeno vyrovnání platby. Zde můžete ručně vyrovnat platby nebo znovu vyrovnat platby, které byly automaticky vyrovnány na nesprávnou položku. Další informace o automatickém vyrovnání nalezenete na [Odsouhlasení plateb pomocí automatického vyrovnání](receivables-how-reconcile-payments-auto-application.md).

> [!IMPORTANT]  
> When the bank account that you are reconciling payments for is set up for the local currency, then the **Payment Application** page will show all open entries in the local currency, including open entries for documents that were originally invoiced in foreign currencies. Payments applied to entries with converted currencies may therefore be posted with different amounts than on the original document because of the potentially different exchange rates used by the bank and [!INCLUDE[prod_short](includes/prod_short.md)] respectively.

Therefore, we recommend that you look for foreign currency codes in the **Currency Code** field on the **Payment Application** page to check if applications are based on converted currencies. To review the original document amount in the foreign currency and to see the exchange rate used, choose the **Applies-to Entry No.** field, and then, on the shortcut menu, choose the drilldown button to open the **Customer Ledger Entries** or **Vendor Ledger Entries** page.

Any gains-and-loss adjustment required due to currency conversions is not handled automatically by [!INCLUDE[prod_short](includes/prod_short.md)].

> [!NOTE]  
> You cannot apply entries with a different sign than the sign on the payment. Chcete-li například uzavřít dobropis se záporným znaménkem a související fakturu s kladným, musíte nejprve vyrovnat dobropis na fakturu a poté vyrovnat platbu na fakturu se sníženou zbývající částkou.

> [!WARNING]  
> If you use payment discounts, and if the payment date is before the payment due date, then the **Remaining Amt. včetně Discount** field on the **Payment Application** page will be used for matching. Otherwise, the value in the **Remaining Amount** field will be used. Pokud byla platba provedena se zlevněnou částkou po datu splatnosti platby nebo byla vyplacena celá částka, ale byla poskytnuta sleva, částka nebude spárována.

> [!NOTE]  
> You can only apply a payment to one account. Pokud chcete vyrovnání rozdělit na více otevřených položek, například chcete-li vyrovnat jednorázovou platbu, musí být otevřená položka pro stejný účet. Pro více informací se podívejte na kroky 7 a 8 v postupu tohoto tématu.

## Kontrola nebo vyrovnání plateb po automatickém vyrovnání
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Reconciliation Journals**, and then choose the related link.
2. Otevřete deník odsouhlasení plateb pro bankovní účet, pro který chcete odsouhlasit platby. For more information, see [Reconcile Payments Using Automatic Application](receivables-how-reconcile-payments-auto-application.md).
3. On the **Payment Reconciliation Journal** page, select a payment that you want to review or manually apply to one or more open entries, and then choose the **Apply Manually** action.
4. Select the **Applied** check box on the line for the open entry that you want to apply the payment to.
5. The payment amount, which is also shown in the **Transaction Amount** field on the **Payment Application** page, is inserted in the **Applied Amount** field, but you can modify the field, for example if you want to apply the amount to several open entries.
6. To apply a part of the paid amount to another open entry for the account, for example to apply a lump-sum payment, select the **Applied** check box for the line. Vyrovnaná částka se automaticky odečte od částky transakcí, aby odrážela rozdělení na dvě otevřené položky.
7. Chcete-li část platby vyrovnat na jednu nebo více otevřených položek, které v databázi neexistují, vytvořte nový řádek pod řádkem pro stejný účet. V poli **Vyrovnaná částka**, zadejte částku, která se má vyrovnat na nový řádek, a poté upravte pole **Vyrovnaná částka** na existujícím řádku.
8. Opakujte kroky 5, 6, nebo 7 pro další otevřené položky, u které chcete vyronat celou nebo část částky platby.
9. When you have reviewed a payment application or manually applied to one or more open entries, choose the **Accept Application** action.

The **Payment Application** page  closes, and on the **Payment Reconciliation Journal** page, the value in the **Match Confidence** field is changed to **Accepted** to indicate to you that you have reviewed or manually applied the payment.

## Viz také
[Správa pohledávek  [
  Prodej[<x6/>
[Práce s [!INCLUDE<x7/>prod_short<x8/>]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]