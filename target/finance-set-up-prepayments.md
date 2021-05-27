---
title: Set Up Prepayments | Microsoft Docs
description: Prepayments are payments that are invoiced and posted to a sales or purchase prepayment order before final invoicing. You might require a deposit before you manufacture items to order, or you might require payment before you ship items to a customer. The prepayments functionality enables you to invoice and collect deposits required from customers or to remit deposits to vendors. Thus, you can ensure that all payments are posted against an invoice.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: prepayment
ms.date: 04/01/2021
ms.author: edupont

---
# Nastavení záloh
Pokud požadujete, aby vaši zákazníci odeslali platbu před odesláním objednávky, nebo pokud váš dodavatel vyžaduje, abyste platbu odešleli před odesláním objednávky, můžete použít funkci Záloha. Tato funkce umožňuje fakturovat a vybírat zálohy požadované od zákazníků nebo převádět vklady dodavatelům a zajistit, aby všechny částečné platby byly zaúčtovány na fakturu. Pro více informací navštivte [Vytvoření zálohové faktury](finance-how-to-create-prepayment-invoices.md).

Před zaúčtováním zálohových faktur musíte nastavit účty v hlavní knize a nastavit číselné řady pro zálohové doklady. Je nutné zadat účet pro zálohy související s prodejem a účet pro zálohy související s nákupem. Můžete určit stejné účtovací účty, které se použijí pro všechny platby spojené se všemi obecnými obchodními účto skupinami nebo obecnými skupinami účtování produktů, nebo můžete určit konkrétní účty pro konkrétní účto skupiny pro prodej a nákup. To závisí na požadavcích vaší společnosti na sledování záloh.

Můžete definovat procento částky řádku, která bude fakturována za zálohu pro zákazníka nebo dodavatele, pro všechno zboží nebo vybrané zboží. Po dokončení nastavení můžete vygenerovat zálohové faktury z prodejních a nákupních objednávek. Můžete použít výchozí procenta pro každý prodejní nebo nákupní řádek nebo můžete podle potřeby změnit částky na faktuře. Můžete například určit celkovou částku za celou objednávku.

> [!NOTE]
> We recommend that you do not use a prepayment percentage of 100% in the following cases:
> * Pokud se nacházíte v Severní Americe. Vzhledem k tomu, jak se daně počítají, může procento zálohy ve výši 100 % vést k problémům s fakturami za platbu předem.
> * Ve všech oblastech, pokud ručně odečtete skonto z faktury. Procento zálohy ve výši 100 % automaticky nezanechá částku, ze které lze slevu odečíst.

Vzhledem k tomu, že předplacená částka patří kupujícímu, dokud neobdržel zboží nebo služby, je nutné nastavit účty hlavní knihy, aby se částky zálohy zadržovaly, dokud nebude zaúčtována konečná faktura. Platby za prodej musí být zaznamenány na účtu závazků, dokud nebudou položky odeslány. Zálohy na nákup musí být zaznamenány na účtu majetku, dokud není zboží přijato. Kromě toho je nutné pro každý identifikátor DPH nastavit samostatný účet hlavní knihy.

[!INCLUDE[local-func-setup-link](includes/local-func-setup-link.md)]

## Přidání účtů záloh k obecnému nastavení účtování

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Nastavení obecného účtování** a poté vyberte související odkaz.
2. Na stránce **Nastavení obecného účtování** vyplňte následující pole:

   - **Účet záloh výnosů**
   - **Nákupní  účet záloh**

> [!TIP]
> If you cannot see the fields in the **General Posting Setup** page, then use the horizontal scroll bar at the bottom of the page to scroll to the right.

If you have not already set up general ledger accounts for prepayments, you can open the **G/L Account List** page from the relevant account field.

## To set up number series for prepayment documents

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Nastavení prodeje a pohledávek** a poté vyberte související odkaz.
2. On the **Sales & Receivables Setup** page, fill in the following fields:

   - **Posted Prepmt. Zásoby Nos.**
   - **Posted Prepmt. zál.  Memo Nos.**

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchases & Payables Setup**, and then choose the related link.
2. On the **Purchases & Payables Setup** page, fill in the following fields:

   - **Posted Prepmt. Zásoby Nos.**
   - **Posted Prepmt. zál.  Memo Nos.**

> [!NOTE]  
> You can use the same number series for prepayment invoices and regular invoices, or you can use different number series. If you use different series, they must not overlap because there must not be any numbers that exist in both series.

## To set up prepayment percentages for items, customers, and vendors
For an item, you can set up a default prepayment percentage for all customers, a specific customer, or a customer price group.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat") zadejte **Zboží** a poté vyberte související odkaz.
2. Select an item, and then choose the **Prepayment Percentages** action.
3. On the **Sales Prepayment Percentages** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

For a customer or vendor, you can set up one default prepayment percentage for all items and all types of sales lines. You enter this on the customer or vendor card.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Zákazníci** a poté vyberte související odkaz.
2. Open the card for a customer.
3. Fill in the **Prepayment %** field.
4. Repeat the steps for other customers or for vendors.

### To determine which prepayment percentage has first priority

An order may have a prepayment percentage on the sales header, and a different percentage for the items on the lines. To determine which prepayment percentage applies to each sale line, the system looks for the prepayment percentage in the following order and will apply the first default that it finds:

1. A prepayment percentage for the item on the line and the customer that the order is for.
2. A prepayment percentage for the item on the line and the customer price group that the customer belongs to.
3. A prepayment percentage for the item on the line for all customers.
4. The prepayment percentage on the sales or purchase header.

In other words, the prepayment percentage on the customer card will only apply if there is no prepayment percentage set up for the item. However, if you change the contents of the **Prepayment Percentage** field on the sales or purchase header after you create the lines, the prepayment percentage on all of the lines will be updated. This makes it easy to create an order with a fixed prepayment percentage, regardless of the percentage set up on items.

## Viz také

[Invoicing Prepayments](finance-invoice-prepayments.md)  
[Walkthrough: Setting Up and Invoicing Sales Prepayments](walkthrough-setting-up-and-invoicing-sales-prepayments.md)  
[Calculate Goods and Services Tax on Prepayments in Australia](LocalFunctionality/Australia/how-to-calculate-goods-and-services-tax-on-prepayments.md)  
[Calculate Goods and Services Tax on Prepayments in New Zealand](LocalFunctionality/NewZealand/how-to-calculate-goods-and-services-tax-on-prepayments.md)  
[Understanding the General Ledger and the COA](finance-general-ledger.md)  
[Finance](finance.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]