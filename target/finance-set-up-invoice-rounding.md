---
    title: Set Up Invoice Rounding
    description: If you need to round invoice amounts when you create invoices, you can use the automatic rounding function explained here.
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.form: 5, 16, 118, 459, 460, 495
    ms.date: 06/16/2021
    ms.author: bholtorf

---
# Nastavení zaokrouhlování faktur
Pokud potřebujete při vytváření faktur zaokrouhlit částky faktur, můžete použít funkci automatického zaokrouhlování. Při zaokrouhlování faktury se přidá další řádek se zaokrouhlovací částkou a zaúčtuje se s ostatními řádky faktury.

> [!NOTE]  
> Local regulations or local custom may require the invoice to be rounded in a specific way, for example, to an amount divisible by 0.05.

Chcete-li použít automatické zaokrouhlování faktur, musíte:

* Určete účty účetní osnovy, na které budou zaokrouhleny rozdíly.
* Nastavte pravidla pro zaokrouhlení faktur v lokálná měně a v cizí měně.
* Aktivujte funkci.

> [!NOTE]  
> In addition to the invoice rounding features, you can round amounts on invoices by the unit-amount rounding feature and the amount rounding feature.

## Nastavení účtů hlavní knihy pro rozdíly zaokrouhlení faktur
Chcete-li použít funkci automatického zaokrouhlování faktur, musíte nastavit účet hlavní knihy nebo účty, na kterých budou zaúčtovány rozdíly zaokrouhlování. Než to budete moci provést, musíte nastavit DPH účto skupiny zboží. For more information, see [Set up VAT](finance-setup-vat.md).

### Nastavení účtů hlavní knihy pro rozdíly zaokrouhlení faktur
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, and then choose the related link.
2. On the **Chart of Accounts** page, set up the account and name it **Invoice Rounding** or something similar. [!INCLUDE[prod_short](includes/prod_short.md)] will use the account name as text for invoices that are rounded.
3. Depending on whether you use VAT or sales tax, in the **Tax Prod. Posting Group** or **VAT Prod. Posting Group** fields, choose a posting group for rounded amounts. Možná budete chtít nastavit nový kód skupiny, který se použije pro zaokrouhlování faktur.
4. Leave the **Gen. Posting Type**, and either the **Tax Bus. Posting Group** or **VAT Bus. Posting Group** fields blank. <!-- Why do we say to leave these blank, when there are a lot of other fields we also leave blank but don't mention? -->

Now you can assign the invoice rounding account to posting groups on the **Vendor Posting Groups** page.  <!-- Why only the vendor posting groups? -->

## Nastavení zaokrouhlení pro cizí a lokální měny
Před použitím funkce automatického zaokrouhlení faktury je nutné nastavit pravidla zaokrouhlení pro cizí a místní měny.

### Nastavení zaokrouhlování cizí měny
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Currencies**, and then choose the related link.
2. On the **Currencies** page, choose the foreign currency to open the **Currency Card**, and then fill in the **Amount Rounding Precision**, **Unit-Amount Rounding Precision**, **Invoice Rounding Precision** and **Invoice Rounding Type** fields.

### Nastavení zaokrouhlení lokální měny
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.
2. On the **General Ledger Setup** page, on the **General** FastTab, fill in the **Inv. Rounding Precision** and **Inv. Rounding Type** fields.

## Aktivace funkce zaokrouhlení faktur
Chcete-li zajistit automatické zaokrouhlení prodejních a nákupních faktur, je nutné zapnout funkci zaokrouhlení faktur. Zaokrouhlení faktur se zapíná samostatně pro prodejní a nákupní faktury.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales & Receivables Setup** or **Purchases & Payables Setup**, and then choose the related link.
2. On the **General** FastTab, choose the **Invoice Rounding** check box.

## Viz také
[Invoice Sales](sales-how-invoice-sales.md)  
[Record Purchases](purchasing-how-record-purchases.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]