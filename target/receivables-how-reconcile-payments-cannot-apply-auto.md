---
title: Using the Transfer Difference to Account Feature to Reconcile Payments
description: Describes how to process payments that cannot be applied to a document, for example, when an exchange rate causes amounts to differ.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment process, cash receipts
ms.date: 04/01/2021
ms.author: edupont

---
# Odsouhlasení plateb, které nelze vyrovnat automaticky
Někdy budete možná muset zpracovat platby na váš bankovní účet, které nemohou být vyrovány se související položžkou zákazníka, dodavatele nebo bankovního účtu. Důvodem může být, že v [!INCLUDE[prod_short[] není doklad, na který by se platba vyrovnala, nebo související doklad v  [!INCLUDE**prod_short**] má rozdílnou částku, než transakce. Může se jednat například důvod způsobený směnou měny. On the **Payment Reconciliation Journal** page, all transaction amounts for payments that are not yet applied appear in the **Difference** field, including amounts that cannot be applied because of reasons such as the above.

Metody řešení těchto typů nevyrovnaných plateb:
* Ruční vyrovnání
* Použítí textového mapování účtů
* Převod nadbytečné částky na řádek deníku a pomocí úřtování vytvoření požadavoané položky, jako je například vrácení přeplatku.

Platby, které nelze vyrovnat se mohou na řádcích deníku odsouhlasení zobrazít následujícími způsoby:

* The value in the **Difference** field is equal to the value in the **Transaction Amount** field, which indicates that no part of the payment can be applied to a related open customer, vendor, or bank account ledger entry.
* Hodnota v poli **Rozdíl** je menší než hodnota v poli <x3/>Částka transakce<x4/> což znamená, že část platby může být vyrovnaná se související otevřenou položkou zákazníka, dodavatele nebo bankovního účtu. Zbývající část platby nelze vyrovnat a musí být odsouhlasena ručně pomocí přímého účtování na účet.

To reconcile such payments, you can choose the **Transfer Difference to Account** action and then specify to which account the amount in the **Difference** field will be posted when you post the payment reconciliation journal. You can do this either from the **Payment Reconciliation Journal** page or from the **Payment Application Review** page that you open by choosing the value in the **Match Confidence** field or by choosing the **Difference** field.

> [!TIP]  
> Podobné funkce existují pro nastavení automatického odsouhlasení opakujících se plateb, které nelze vyrovnat na související otevřené položky zákazníka, dodavatele nebo bankovního účtu. For more information, see [Map Text on Recurring Payments to Accounts for Automatic Reconciliation](receivables-how-map-text-recurring-payments-accounts-auto-reconcilliation.md).

## Odsouhlasení plateb, které nelze vyronávat automaticky
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Reconciliation Journals**, and then choose the related link.
2. Otevřete deník odsouhlasení plateb. For more information, see [Reconcile Payments Using Automatic Application](receivables-how-reconcile-payments-auto-application.md).
3. Choose the **Transfer Difference to Account**. The **Transfer Difference to Account** page opens.
4. In the **Account Type** field, specify if the type of account that the payment amount will be posted to.
5. In the **Account No.** field, specify the account that the payment amount will be posted to.
6. In the **Description** field, specify text that describes this direct payment posting. By default, the text in the **Transaction Text** field on the payment reconciliation journal line is inserted.
7. Zvolte tlačítko **OK**.

If the value in the **Difference** field was equal to the value in the **Transaction Amount** field when you post the payment reconciliation journal, the whole payment on the journal line will be posted directly to the specified balancing account.

If the value in the **Difference** field was lower than the value in the **Transaction Amount** field, then an additional journal line will be created with the same text and date and with the difference inserted in the **Transaction Amount** field. On the original journal line, the difference will be deducted from the value in the **Transaction Amount** field, and the payment will remain applied to its related customer, vendor, or bank account ledger entry. Při účtování deníku odsouhlasení plateb bude částka platby zaúčtovaná jako vyrovnání. Druhá část platby bude zaúčtována přímo na zadaný účet.

## Viz také
[Správa pohledávek  [
  Prodej[<x6/>
[Práce s [!INCLUDE<x7/>prod_short<x8/>]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]