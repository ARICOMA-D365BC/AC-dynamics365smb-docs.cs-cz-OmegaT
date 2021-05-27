---
title: Apply Entries in Different Currencies| Microsoft Docs
description: You can apply ledger entries in multiple currencies, for example, if you sell in one currency and receive payment in another.
services: project-madeira
documentationcenter: ''
author: edupont04

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: multiple currencies, payment, reconcile
ms.date: 04/01/2021
ms.author: edupont

---
# Povolení vyrovnávání položek v různých měnách
Pokud nakupujete od dodavatele v jedné měně a odešlete platbu v jiné měně, můžete vyrovnat platbu s nákupem.

Stejně tak, pokud prodáváte zákazníkovi v jedné měně a obdržíte platbu v jiné měně, můžete platbu vyrovnat prodejní fakturou.

The following procedure describes how to set this up for vendor ledger entries on the **Purchases & Payables Setup** page. The setup is similar for customer ledger entries on the **Sales & Receivables Setup** page.

## Povolení vyrovnávání položek dodavatele v různých měnách
1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat") zadejte **Nastavení nákupu a závazků** a vyberte související odkaz.
2. In the **Appln. between Currencies** field, select one of the following options.

| Možnost | Popis |
| --- | --- |
| Žádné | Vyrovnání mezi měnami není povoleno. |
| EMU | Vyrovnání mezi měnami EMU je povoleno. |
| Všechno | Vyrovnání mezi všemi měnami je povoleno. |

## Nastavení účtů účetní osnovy pro rozdíly zaokrouhlení při měnovém vyrovnání
Pokud vyrovnáte položky v různých měnách, musíte nastavit účty hlavní knihy, na které chcete zaúčtovat rozdíly zaokrouhlování.

> [!NOTE]  
> You must set up the general ledger accounts before you complete the task. For more information, see [Understanding the General Ledger and the Chart of Accounts](finance-general-ledger.md).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customer Posting Groups**, and then choose the related link.
2. In the **Debit Curr. zaok. vyrovnání Acc.** and **Credit Curr. zaok. vyrovnání Acc.** fields, enter the relevant general ledger accounts to post rounding differences.
3. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendor Posting Groups**, and then choose the related link.
4. In the **Debit Curr. zaok. vyrovnání Acc.** and **Credit Curr. zaok. vyrovnání Acc.** fields, enter the relevant general ledger accounts to post rounding differences.

## Viz také
[Managing Payables](payables-manage-payables.md)  
[Managing Receivables](receivables-manage-receivables.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]