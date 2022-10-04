---
title: Apply Payments to Unpaid Sales Documents
description: You apply amounts paid by customers to related sales documents and post the payment to update the customer, general ledger, and bank ledger entries.
author: SorenGP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment process, cash receipts, customer payment
ms.search.form: 1290, 1294, 1287
ms.date: 04/01/2021
ms.author: edupont

---
# Odsouhlasení plateb zákazníků ze seznamu nezaplacených prodejních dokladů
Když vaši zákazníci provedli platby na váš elektronický bankovní účet, musíte použít každou zaplacenou částku na související prodejní doklad a poté zaúčtovat platbu, abyste aktualizovali odběratele, hlavní knihu a položky bankovní knihy. V závislosti na vašich obchodních potřebách můžete dostat zaplaceno a zaregistrovat tuto platbu různými způsoby: ručně, automaticky a prostřednictvím platebních služeb.

> [!NOTE]  
> Můžete provádět stejné úkoly, včetně plateb dodavatele na stránce **Deník odsouhlasení plateb** pomocí funkcí pro import výpisu z účtu, automatickou aplikaci a odsouhlasení bankovního účtu. Pro více informací navštivte [Automatické odsouhlasení plateb  .

Stránka **Registrovat platby zákazníků** je navržena tak, aby vám pomohla při vyrovnávání interních účtů pomocí skutečných peněžních údajů, aby bylo zajištěno, že platby jsou od zákazníků shromažďovány efektivně. Tento nástroj pro zpracování plateb vám umožňuje rychle ověřit a zaúčtovat jednotlivé nebo paušální platby, zpracovat zlevněné platby a najít konkrétní nezaplacené doklady, za které se platí.

Platby pro různé zákazníky, kteří mají různá data plateb, musí být zaúčtovány jako jednotlivé platby. Platby pro stejného zákazníka se stejným datem platby lze zaúčtovat jako paušální platbu. To je užitečné například v případě, že zákazník provedl jednu platbu, která pokrývá více prodejních faktur.

## Nastavení deníku registrace plateb
Protože můžete účtovat různé typy plateb na různé vyrovnávací účty, musíte před zahájením zpracování plateb zákazníků vybrat vyrovnávací účet na stránce **Nastavení registrace plateb**. Pokud vždy účtujete na stejný vyrovnávací účet, můžete tento účet nastavit jako výchozí a vyhnout se tomuto kroku při každém otevření stránky **Registrovat platby zákazníka**.

1. Zvolte ![žárovku, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Nastavení registrace plateb** a pak zvolte související odkaz.

   Případně na stránce **Registrovat platby zákazníka** vyberte akci **Nastavení**.
2. Vyplňte pole na stránce **Nastavení registrace plateb**. Vyberte pole, ve kterém si chcete přečíst krátký popis pole nebo odkaz na související informace.

## Individuální registrace plateb zákazníka

1. Zvolte žárovku![, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Zaregistrovat platby zákazníka** a pak zvolte související odkaz.

   Stránka **Registrovat platby zákazníka** zobrazuje všechny zaúčtované doklady, pro které lze platbu zaregistrovat. Stránku lze také otevřít ze stránek **Zákazníci** a **Karta zákazníka**, kde je automaticky filtrována pro zadaného zákazníka.
2. Zaškrtněte políčko **Platba provedena** na řádku, který představuje zaúčtovaný doklad, pro který byla provedena platba.

   Pokud je na stránce **Nastavení registrace plateb** zaškrtnuto políčko automatické vyplnění Data **pak,**  je pracovní datum zadáno **do pole Datum přijetí**.
3. Do pole **Datum přijetí** zadejte datum, kdy byla platba provedena. Toto datum se může lišit od pracovního data.
4. Do pole **Přijatá částka** zadejte částku, která byla zaplacena.

   U úplných plateb je to stejné jako částka v poli **Zbývající částka** na řádku. U částečných plateb je tato částka nižší než částka v poli **Zbývající částka** na řádku.
5. Opakujte kroky 2 až 4 pro další řádky, které představují zaúčtované doklady, pro které jsou prováděny platby.
6. Vyberte akci **Zaúčtovat platby**.

Informace o platbě jsou zaúčtovány pro doklady reprezentované řádky, kde je zaškrtnuto políčko **Platba provedena**.

Položky plateb jsou zaúčtovány do hlavní knihy, banky a účtů zákazníků. Každá platba se použije na související zaúčtovaný prodejní doklad.

## Odsouhlasení paušálních plateb
1. Zvolte žárovku![, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Platební registrace** a pak zvolte související odkaz.
2. Zaškrtněte políčko **Platba provedena** na řádcích, které představují zaúčtované doklady pro stejného zákazníka, pro kterého byla provedena paušální platba.

   > [!NOTE]  
   > Zákazník v poli **Jméno** musí být stejný na všech řádcích, které budou zaúčtovány jako paušální platba.

   Pokud je na stránce **Nastavení registrace plateb** zaškrtnuto políčko **Datum automatického vyplnění** pak, je pracovní datum vyplněno v poli **Datum přijetí**.
3. Do pole **Datum přijetí** zadejte datum, kdy byla platba provedena. Toto datum se může lišit od pracovního data.

   > [!NOTE]  
   > Toto datum musí být stejné na všech řádcích, které budou zaúčtovány jako paušální platba.
4. V poli **Přijatá částka** zadejte částky na více řádcích, které se sečítají až do paušální částky.

   > [!TIP]  
   > Pokuste se zaúčtovat co nejvíce úplných plateb s paušální částkou. Zadejte částky, které jsou stejné jako částka v poli **Zbývající částka** na co největším počtu řádků.
5. Opakujte kroky 2 až 4 pro další řádky, které představují zaúčtované doklady pro stejného zákazníka, pro kterého byla provedena paušální platba.
6. Vyberte akci **Zaúčtovat jako paušální platbu**. Zadané informace o platbě jsou zaúčtovány pro doklady reprezentované řádky, kde je zaškrtnuto políčko **Platba provedena**.

Položky plateb jsou zaúčtovány do hlavní knihy, banky a účtů odběratelů. Každá platba se použije na související zaúčtovaný prodejní doklad.

Pokud platba v bance není reprezentována řádkem na stránce **Registrace platby**, může to být proto, že související dokument ještě nebyl zaúčtován. V takovém případě můžete pomocí funkce vyhledávání rychle najít dokument a odeslat jej ke zpracování platby. Další informace naleznete v části [Vyhledání specifického prodejního dokladu, který není plně fakturován](receivables-how-reconcile-customer-payments-list-unpaid-sales-documents.md#to-find-a-specific-sales-document-that-is-not-fully-invoiced).

Pokud platba v bance není reprezentována žádným dokumentem v [! INCLUDE[prod_short](includes/prod_short.md)] pak můžete otevřít předvyplněný hlavní deník ze stránky **Registrace platby** a zaúčtovat platbu přímo na vyrovnávací účet bez použití platby na doklad. Případně můžete chtít evidovat platbu v deníku, dokud nebude vyřešen původ platby. Další informace naleznete v části [Zaznamenávání nebo zaúčtování platby bez souvisejícího dokumentu](receivables-how-reconcile-customer-payments-list-unpaid-sales-documents.md#to-record-or-post-a-payment-without-a-related-document).

## Pro ruční zpracování plateb zákazníků se slevami
Pokud jste se se svým zákazníkem dohodli na slevě z platby, pak mohou být částky platby nižší než částky faktury, pokud platba proběhne před dohodnutým datem slevy.

Následující postupy vysvětlují čtyři různé způsoby zaúčtování zlevněných plateb na stránce **Registrace plateb**.

* Částka platby se rovná zbývající diskontované částce a datum platby je před datem slevy. Platbu zaúčtujete tak, jak je.
* Částka platby se rovná zbývající diskontované částce, ale datum platby je po datu slevy. Platbu zaúčtujete jako částečnou. Dokument zůstává otevřen pro vyzvednutí/zaplacení zbývající částky. Případně můžete nastavit datum slevy později, abyste umožnili platbu v plné výši.
* Částka platby je nižší než zbývající diskontovaná částka. Platbu zaúčtujete jako částečnou. Dokument zůstává otevřen pro vyzvednutí/zaplacení zbývající částky.
* Částka platby je vyšší než zbývající diskontovaná částka. Platby zaúčtujete tak, jak jsou. Zaúčtuje se pouze zbývající částka. Dodatečná částka je připsána zákazníkovi.

### To process a payment amount that is equal to the discounted amount and where the payment date is before the discount date
1. Zvolte žárovku![, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Platební registrace** a pak zvolte související odkaz.
2. Enter the payment amount in the **Amount Received** field. The amount is equal to the amount in the **Rem. částka  after Discount** field.

   The **Payment Made** check box is automatically selected, and the **Date Received** field is filled with the work date.
3. In the **Date Received** field, enter the payment date. The date is before the date in the **Pmt. Discount Date** field.
4. Verify that the **Remaining Amount** field contains zero (0).
5. Choose the **Post Payments** action to post the full payment to general ledger, bank, and customer accounts.

### To process a payment amount that is equal to the discounted amount but where the payment date is after the discount date
1. Zvolte žárovku![, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Platební registrace** a pak zvolte související odkaz.
2. Enter the payment amount in the **Amount Received** field. The amount is equal to the amount in the **Rem. částka  after Discount** field.

   The **Payment Made** check box is automatically selected, and the **Date Received** field is filled with the work date.
3. In the **Date Received** field, enter a payment date that is after the date in the **Pmt. Discount Date** field. Date fields change to red font, and an error message is shown at the bottom of the page.

   > [!TIP]  
   > If you want to make an exception and grant the discount even though the payment is late, follow these steps:
4. Choose the **Details** action.
5. On the **Payment Registration Details** page, in the **Pmt. Discount Date** field on the **Payment Discount** FastTab, enter a date that is after the date in the **Date Received** field on the **Payment Registration** page.

   The error message and the red font disappear, and you can proceed to process the discounted payment.
6. Verify that the **Remaining Amount** field contains the amount that remains to pay the full invoice amount.
7. Choose the **Post Payments** action to post the partial payment to general ledger, bank, and customer accounts.

The related document remains open.

### To process a payment that is lower than the remaining discounted amount
1. Zvolte žárovku![, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Platební registrace** a pak zvolte související odkaz.
2. Enter the payment amount in the **Amount Received** field. The amount is lower than the amount in the **Rem. částka  after Discount** field.

   The **Payment Made** check box is automatically selected, and the **Date Received** field is filled with the work date.
3. In the **Date Received** field, enter the payment date. The date is before the date in the **Pmt. Discount Date** field.
4. Verify that the **Remaining Amount** field contains the amount that remains to pay the discounted amount.
5. Choose the **Post Payments** action to post the partial payment to general ledger, bank, and customer accounts.

The related document remains open.

### To process a payment that is more than the remaining discounted amount
1. Zvolte žárovku![, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Platební registrace** a pak zvolte související odkaz.
2. Enter the payment amount in the **Amount Received** field. The amount is more than the amount in the **Rem. částka  after Discount** field.

   The **Payment Made** check box is automatically selected, and the **Date Received** field is filled with the work date.
3. In the **Date Received** field, enter the payment date. The date is before the date in the **Pmt. Discount Date** field.
4. Verify that the **Remaining Amount** field contains zero (0).
5. Choose the **Post Payments** action to post the full payment to general ledger, bank, and customer accounts.

The related document is closed, and the customer is credited the excess payment amount.

## To find a specific sales document that is not fully invoiced
The **Payment Registration** page supports you in tasks needed to balance internal accounts with actual cash figures to ensure effective collection from customers. It shows outstanding incoming payments as lines that represent sales documents where an amount is due for payment.

Typically, when a payment has been made, recorded in the bank or otherwise, the related sales or purchase document is represented as a line on the **Payment Registration** page because the document in question is waiting for the payment to be posted against the outstanding amount. However, sometimes a payment that has been made is not represented by a line on the **Payment Registration** page, typically because the document in question has not been fully invoice posted.

On the **Document Search** page, you can search among documents that are not fully invoiced. You can search based on one or more of the following criteria:

* Document number
* Amount or amount range

The following procedure explains how to find a specific document by using both search criteria.

1. Zvolte žárovku![, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Platební registrace** a pak zvolte související odkaz.
2. With the pointer on any line, Choose the **Search Documents** action.
3. On the **Document Search** page, enter a search value in the **Document No.** field.

   > [!NOTE]  
   > The value that you enter in this field is enclosed in hidden wildcard characters. This means that the function searches for all document numbers that contain the entered value.
4. In the **Amount** field, enter the specific amount that exists on the document that you want to find.
5. In the **Amount Tolerance %** field, enter a percentage value to define the range of amounts that you want to search to find the open document.

   If you enter 10, then the function will search for amounts in a range between ten percent lower and ten percent higher than the value in the **Amount** field.
6. Choose the **Search** action.

The Search function searches among documents that are not fully invoiced based on the specified criteria.

If one or more documents match the criteria, then the **Document Search Result** page opens to display lines that represent those documents. Each line contains a document number, description, and amount so that you can easily find a specific document, for example based on information on your bank statement.

Pokud platba v bance není reprezentována žádným dokumentem v [! INCLUDE[prod_short](includes/prod_short.md)] pak můžete otevřít předvyplněný hlavní deník ze stránky **Registrace platby** a zaúčtovat platbu přímo na vyrovnávací účet bez použití platby na doklad. Případně můžete chtít evidovat platbu v deníku, dokud nebude vyřešen původ platby.

## To record or post a payment without a related document
If a payment in the bank is not represented by any document in [!INCLUDE[prod_short](includes/prod_short.md)], then you can open a prefilled general journal line from the **Payment Registration** page to post the payment directly to the balancing account without applying the payment to a document. Alternatively, you may want to record the payment in the journal until the origin of the payment has been clarified.

1. Zvolte žárovku![, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Platební registrace** a pak zvolte související odkaz.

   Proceed to record an undocumented payment.
2. Choose the **General Journal** action.

   The **General Journal** page opens with one line prefilled with the balancing account of the journal batch that is set up on the **Payment Registration Setup** page.
3. Fill in the remaining fields on the general journal line, such as the amount and the customer number or other information from the bank statement. For more information, see [Post Transactions Directly to the General Ledger](finance-how-post-transactions-directly.md).

You can either post the journal line to update the total on the balancing account. Alternatively, you can leave the journal line unposted, and perhaps append it with a note that the payment needs more analysis.

If you leave the journal line unposted, it will add to the value in the **Unposted Balance** field at the bottom of the **Payment Registration** page.

## Viz také
[Managing Receivables](receivables-manage-receivables.md)  
[Sales](sales-manage-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]