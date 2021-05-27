---
title: Reconcile Payments Using Automatic Application
description: Describes how to use the automatic application function to apply payments or cash receipts to their related open entries, and reconcile payments.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment process, direct payment posting, reconcile payment, expenses, cash receipts
ms.date: 04/01/2021
ms.author: edupont

---
# Odsouhlasení plateb pomocí automatického vyrovnání

The **Payment Reconciliation Journal** page specifies payments, either incoming or outgoing, that have been recorded as transactions on your online bank account or on a payment service and that you can apply to their related open customer, vendor, and bank account ledger entries. Řádky v deníku lze vyplnit importem bankovního výpisu, který je jako bankovního zdroj nebo pomocí ručního zadání transakcí, které v platební službě provádíte.

> [!NOTE]
> Stránka nabízí funkci automatického párování, která vyrovnává platby na jejich související otevřené položky na základě shody dat na řádku bankovního výpisu (řádek deníku) s daty na jedné nebo více otevřených položkách. Všimněte si, že navrhované automatické vyrovnání můžete přepsat a můžete se rozhodnout, zda automatické vyrovnání vůbec použijete. Další informace naleznete v kroku 7.

A payment reconciliation journal is related to one bank account in [!INCLUDE[prod_short](includes/prod_short.md)] that reflects the online bank account where the payment transactions are recorded. Any open bank account ledger entries related to the applied customer or vendor ledger entries will be closed when you choose the **Post Payments and Reconcile Bank Account** action. To znamená, že bankovní účet je automaticky odsouhlasen pro platby, které zaúčtujete do deníku.

Můžete importovat bankovní transakce pomocí souborů ve fommátu CSV nebo jiným, který vaše banka poskytuje. Pokud chcete importovat bankovní výpisy jako bankovní kanály, musíte nejprve povolit specializovanou službu integrace bank a poté propojit bankovní účet s jeho souvisejícím online bankovním účtem. The payment reconciliation journal will then automatically detect bank feeds when you choose the **Import Bank Transactions** action. Kromě toho můžete nastavit bankovní účet tak, aby každou hodinu automaticky importovat nové bankovní výpisy. Transakce pro platby, které již byly zaúčtovány jsou a vyrovnané nebo odsouhlasené, nebudou importovány. You can use the Envestnet Yodlee Bank Feeds service for this, which is preinstalled in some country versions of [!INCLUDE[d365fin](includes/d365fin_md.md)]. For more information, see [Set Up the Envestnet Yodlee Bank Feeds Service](bank-how-setup-bank-statement-service.md). Případně kontaktujte svého partnera společnosti Microsoft a požádejte o pomoc s plněním požadavků vaší firmy nebo země.

The **Map Text to Account** action lets you set up mappings between text on payments and specific debit, credit, and balancing accounts so that such payments are posted to the specified accounts when you post the payment reconciliation journal. To je užitečné například pro opakující se hotovostní příjmy nebo výdaje, jako jsou časté nákupy pohonných hmot pro automobily nebo bankovní poplatky a úroky, které se pravidelně vyskytují na bankovním výpisu a nepotřebují související obchodní doklad. (See step 10 below.) For more information, see [Map Text on Recurring Payments to Accounts for Automatic Reconciliation](receivables-how-map-text-recurring-payments-accounts-auto-reconcilliation.md).

Řádky deníku nemusí mít žádný návrh vyrovnaní. Může to být z různých důvodů, například kvůli chybějícímu dokladu nebo kvůli tomu, že zákazník přeplatil částku, takže po uplatnění platby na jiném řádku deníku existuje nadměrná částka. For such cases, you can use the **Transfer Difference to Account** action to create and post the missing general ledger entry, for example for a refund, that is needed to apply the payment to. (See step 11 below) For more information, see [Reconcile Payments That Cannot be Applied.](receivables-how-reconcile-payments-cannot-apply-auto.md).

You use the **Apply Automatically** function either automatically when you import a bank file or feed with payment transactions or when you activate it, to apply payments to their related open entries based on a matching of text on a bank statement line (journal line) with text on one or more open entries. This automation is based on rules that you define on the **Payment Application Rules** page, where you also define whether an application suggestion requires review. For more information, see [Set Up Rules for Automatic Application of Payments](receivables-how-set-up-payment-application-rules.md).

On journal lines where a payment has been applied automatically to one or more open entries, the **Match Confidence** field has a value of **Low**, **Medium**, or **High** to indicate the quality of the data matching that the suggested payment application is based on.

Some payment applications require your review as defined by the used matching rule, such as lines with **Low** match confidence. Other lines require your review and manual change because there is a value in the **Difference** field. To review one or more payment applications, choose the **Lines to Review** or **Lines with Difference** field at the bottom. The **Payment Application Review** page opens showing all relevant information about the customer or vendor that the payment is applied to, the matching details, and actions to process the line, such as the **Accept Application** action. (Viz kroky 7 a 8 níže.)

For each journal line on the **Payment Reconciliation Journal** page, you can open the **Payment Application** page to see all candidate open entries for the payment and view detailed information for each entry about the data matching that a payment application is based on. Zde můžete ručně vyrovnat platby nebo znovu vyrovnat platby, které byly automaticky vyrovnány na nesprávnou položku. (See step 10 below.) For more information, see [Review or Apply Payments After Automatic Application](receivables-how-review-apply-payments-auto-application.md).

> [!NOTE]  
> You can start the bank transactions import at the same time as you open the **Payment Reconciliation Journal** page for an existing journal. The following procedure describes how to import bank transactions into the **Payment Reconciliation Journal** page after you have created a new journal.

## Odsouhlasení plateb pomocí automatického vyrovnání
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Reconciliation Journals**, and then choose the related link.
2. To work in a new payment reconciliation journal, choose the **New Journal** action.
3. On the **Payment Bank Account List** page, select the bank account that you want to reconcile payments for, and then choose the **OK** button.
   The **Payment Reconciliation Journal** page opens prepared for the selected bank account.
4. Choose the **Import Bank Transactions** action.
   Pokud bankovní účet vybraného deníku není nastaven pro import bankovních transakcí, otevře se dialogové okno, které vám pomůže vyplnit příslušná pole.
5. On the **Select a file to import** page, select the file that contains the bank transactions for payments that you want to reconcile, and then choose the **Open** button.
6. If the Envestnet Yodlee Bank Feeds service is enabled, on the **Bank Statement Filter** page that opens automatically, specify the date interval for the bank statements to be imported.

   The **Payment Reconciliation Journal** page is filled with lines for payments representing bank transactions in the imported bank statement.

   On lines for payments that have been automatically applied to their related open entries, the **Match Confidence** field has a value between **Low** and **High** to indicate the quality of the data matching that the suggested payment application is based on. In addition, the **Account Name**, **Account Type**, and **Account No.** fields are filled with information about the customer or vendor that the payment is applied to.

   Automatické vyrovnání, spolehlivost párování a to, zda řádky vyžadují kontrolu jsou definovány praidly, které můžete upravovat a podle toho upravit i výsledky. For more information, see [Set Up Rules for Automatic Application of Payments](receivables-how-set-up-payment-application-rules.md).

7. To review, accept/remove, or manually change multiple payment applications that have a value in the **Difference** field, choose the **Lines with Difference** action at the bottom.

   The **Payment Application Review** page opens showing the first application to review. Další vyrovnání, které je třeba zkontrolovat, se zobrazí na stránce při zpracování předchozího vyrovnání. All relevant information about the customer or vendor that the payment is applied to, the matching details, and actions to process the line, such as the **Accept Application** and **Apply Manually** actions.

8. To review, accept/remove, or manually change multiple payment applications that are set to be reviewed, according to the payment application rule, choose the **Lines to Review** action at the bottom. Stejná akce je popsána jako v kroku 8.

9. To change an automatic application, select a journal line, and then choose the **Apply Manually** action to reapply or apply the payment manually on the **Payment Application** page. For more information, see [Review or Apply Payments After Automatic Application](receivables-how-review-apply-payments-auto-application.md).

10. Select an unapplied journal line for a recurring cash receipt or expense, such as a car gasoline purchase, and then choose the **Map Text to Account** action. For more information, see [Map Text on Recurring Payments to Accounts for Automatic Reconciliation](receivables-how-map-text-recurring-payments-accounts-auto-reconcilliation.md).

   When you have finished your mapping of payment text to accounts, choose the **Apply Manually** action.

   When a text-to-account ,map is set up, the resulting automatic payment application will contain **High - Text-to-Account Mapping** in the **Match Confidence** field.

11. For a journal line has no suggested application because no ledger entry exists that it can be applied to,  choose the **Transfer Difference to Account** action to create and post the missing general ledger entry that is needed to apply the payment to. For more information, see [Reconcile Payments That Cannot be Applied.](receivables-how-reconcile-payments-cannot-apply-auto.md)

10. When no more lines require review and the **Difference** field is blank on all lines, choose the **Post** action, and then choose one of the following options:

   - **Post Payments and Reconcile Bank Accounts** - To post the payments as applied and also close the related bank account ledger entries as reconciled.
   - **Post Payments Only** - To only post the payments as applied, but leave the related bank account ledger entries open. Required that you reconcile the bank account separately,  for example: For more information, see [Reconcile Bank Accounts](bank-how-reconcile-bank-accounts-separately.md).
   - **Test Report** - To review the result of posting before you post. The **Bank Account Statement** report opens and shows the same fields as at the bottom of the **Payment Reconciliation Journal** page.

Když zaúčtujete deník odsouhlasení plateb, otevřena vyrovnaná položka je uzavřena a související položka zákazníka, dodavatele nebo fin. účtu je aktualizována. U plateb na řádcích deníku na základě mapování textu na účet se aktualizují zadané účty zákazníků, dodavatelů a hlavní knihy. Pro všechny řádky deníku jsou vytvořeny položky bankovního účtu. If you choose the **Post Payments and Reconcile Bank Account** action, any open bank account ledger entries related to the applied customer or vendor ledger entries will be closed. To znamená, že bankovní účet je automaticky odsouhlasen pro platby, které zaúčtujete do deníku.

You can compare the value in the **Balance on Bank Account After Posting** field together with the value in the **Statement Ending Balance** field to track when the bank account is reconciled based on payments that you post.

> [!NOTE]  
> If you do not want to reconcile the bank account from the **Payment Reconciliation Journal** page, then you must use the **Bank Acc. Reconciliation** page. For more information, see [Reconcile Bank Accounts](bank-how-reconcile-bank-accounts-separately.md).

## Viz také
[Správa pohledávek  [
  Prodej[<x6/>
[Práce s [!INCLUDE<x7/>prod_short<x8/>]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]