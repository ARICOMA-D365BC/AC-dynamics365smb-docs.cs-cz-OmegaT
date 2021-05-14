---
title: Reconcile Bank Accounts and Apply Payments | Microsoft Docs
description: Outlines tasks to reconcile your bank, receivables, and payables accounts, post cash receipts or expenses, and apply payments automatically.
services: project-madeira
documentationcenter: ''
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
# Automatické vyrovnávání plateb a odsouhlasení bankovních účtů
You must regularly reconcile your bank, receivables, and payables accounts by applying payments recorded in the bank to their related open (unpaid) invoices and credit memos or other open entries in [!INCLUDE[prod_short](includes/prod_short.md)].

You can perform this task on the **Payment Reconciliation Journal** page, for example, by importing a bank statement file or feed to quickly register the payments. Platby jsou vyrovnány s otevřenými položkami zákazníků nebo dodavatelů na základě shod mezi textem platby a informacemi o položce. Před zaúčtováním deníku můžete zkontrolovat a změnit vyrovnání aplikace. Při zaúčtování deníku můžete zavřít všechny otevřené položky bankovního účtu související s vyrovnanými položami. Bankovní účet je automaticky vyrovnán, když jsou vyrovnány všechny platby.

The logic that governs how payment text is automatically matched with entry information is set up on the **Payment Application Rules** page as a number of prioritized rules that you can edit.

Můžete také odsouhlasit bankovní účty bez současného vyrovnání plateb. You perform this work on the **Bank Acc. Reconciliation** page. For more information, see [Reconcile Bank Accounts](bank-how-reconcile-bank-accounts-separately.md).

Chcete-li importovat bankovní výpisy jako bankovní zdroj, musíte nejprve nastavit a povolit službu Envestnet Yodlee Bank Feed a poté propojit své bankovní účty se souvisejícími online bankovními účty. For more information, see [Set Up the Envestnet Yodlee Bank Feeds Service](bank-how-setup-bank-statement-service.md).

> [!TIP]
> You can also import bank statement files in comma or semicolon delimited format (.CSV). Use the **Set up a bank statement file format** assisted setup to define bank statement import formats and attach the format to a bank account. You can then use these formats when you import bank statements in the **Bank Account Reconciliation** page.

Alternatively, you can use the AMC Banking 365 Fundamentals extension to convert a bank statement file, from any format, to a data stream that you can import into [!INCLUDE[prod_short](includes/prod_short.md)]. For more information, see [Using the AMC Banking 365 Fundamentals extension](ui-extensions-amc-banking.md).

Následující tabulka popisuje sekvenci úloh s odkazy na témata, které je popisují.

| Viz | Také |
| --- | --- |
| Využití vyrování plateb k otevření položek zákazníků nebo dodavatelů importem bankovního výpisu a odsouhlasení bankovních účtů po vyrovnání všech plateb. | [Reconcile Payments Using Automatic Application](receivables-how-reconcile-payments-auto-application.md) |
| Ruční vyrovnání plateb prohlížením podrobných informací spojených dat a návrhy a doporučení pro otevřené položky, které se mají vyrovnat. | [Review or Apply Payments After Automatic Application](receivables-how-review-apply-payments-auto-application.md) |
| Vyřešte platby, které nelze automaticky vyrovnat na souvisejících položkách účetní knihy. Například proto, že částky se liší nebo protože související položka knihy neexistuje. | [Reconcile Payments that Cannot be Applied Automatically](receivables-how-reconcile-payments-cannot-apply-auto.md) |
| Propojte text plateb s konkrétními účty zákazníka, dodavatele nebo hlavní knihy tak, aby vždy zaúčtoval opakované příjmy v hotovosti nebo výdaje na tyto účty, pokud neexistují žádné doklady, na které by se vztahovaly. | [Map Text on Recurring Payments to Accounts for Automatic Reconciliation](receivables-how-map-text-recurring-payments-accounts-auto-reconcilliation.md) |
| Set up the rules to govern how payments/bank transactions should be automatically applied to their related open ledger entries when you use the **Apply Automatically** function on the **Payment Reconciliation Journal** page. | [Set Up Rules for Automatic Application of Payments](receivables-how-set-up-payment-application-rules.md) |

## Zobrazit související školení na webu [Microsoft Learn](/learn/modules/use-journals-dynamics-365-business-central/index)

## Viz také
[Reconcile Bank Accounts](bank-how-reconcile-bank-accounts-separately.md)  
[Managing Receivables](receivables-manage-receivables.md)  
[Sales](sales-manage-sales.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]