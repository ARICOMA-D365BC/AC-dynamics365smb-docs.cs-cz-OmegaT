---
title: Set Up Unrealized Value Added Tax
description: If you're using cash-based accounting, you can specify how to handle unrealized VAT for sales and purchases.
author: brentholtorf


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: cash, VAT, unrealized, cash-based
ms.search.form: 118, 472, 473
ms.date: 04/01/2021
ms.author: bholtorf

---

# Nastavení nerealizované DPH pro účetnictví založené na hotovosti

If you are using cash-based accounting methods, you can set up [!INCLUDE[prod_short](includes/prod_short.md)] to handle unrealized VAT.

## Použití účtů účetní osnovy k nerealizované DPH

Můžete zvolit, aby byly částky DPH vypočteny a zaúčtovány na dočasný účet účetní osnovy při zaúčtování faktury, poté zaúčtovány na správný účet a nakonec zahrnuty do výkazů DPH při zaúčtování skutečné platby faktury. Before you can do this, you must complete the [VAT posting setup](finance-setup-vat.md).

Chcete-li použít účty pro nerealizovanou DPH, postupujte takto:

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, and enter **General Ledger Setup**.
2. On the **General Ledger Setup** page, select the **Unrealized VAT** check box.
3. Choose the **Search for Page or Report** icon ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do"), and enter **VAT Posting Setup**.
4. On the **VAT Posting Setup** page, choose the VAT posting group, and then choose the **Edit** action.
5. In the **Unrealized VAT Type** field, choose an option to specify how to allocate payments to the invoice amount (excluding VAT) and the VAT amount itself, and how to transfer VAT amounts from the unrealized VAT account to the realized account. Následující tabulka popisuje možnosti.

| Možnost | Popis |
| --- | --- |
| Prázdný | Tuto možnost vyberte, pokud nechcete používat nerealizovanou funkci DPH. |
| Procento | Platby zahrnují jak DPH, tak i částku faktury v poměru k procentu platby ze zbývající částky faktury. Zaplacená částka DPH je převedena z nerealizovaného účtu DPH na realizovaný účet DPH. |
| První | Platby nejprve zahrnují částky DPH a poté fakturované částky. V tomto případě se částka převedená z nerealizovaného účtu DPH na účet DPH bude rovnat částce platby, dokud nebude zaplacena celková DPH. |
| Poslední | Platby nejprve pokrývají částku faktury a poté DPH. V takovém případě nebude z nerealizovaného účtu DPH převedena žádná částka na účet DPH, dokud nebude zaplacena celková částka faktury bez DPH. |
| První (plně zaplaceno) | Payments will cover VAT first (like the _First_ option), but no amount will be transferred to the VAT account until the full amount of VAT has been paid. |
| Poslední (plně zaplaceno) | Payments will cover invoice amount first (like the _Last_ option), but no amount will be transferred to the VAT account until the full amount of VAT has been paid. |

6. In the **Sales VAT Unreal. Account** field, choose the account for unrealized sales VAT.

   > [!NOTE]  
   > The VAT amount will be posted to this account, and stay there until the customer payment is posted. Částka je poté převedena na účet prodejní DPH.
7. In the **Purch.  nereal. Account** field, enter the general ledger account for unrealized purchase VAT.

> [!NOTE]  
> The VAT amount will be posted to this account, and stay there until the customer payment is posted. Částka je poté převedena na účet nákupní DPH.

## Viz také
[Set Up Calculations and Posting Methods for Value Added Tax](finance-setup-vat.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
