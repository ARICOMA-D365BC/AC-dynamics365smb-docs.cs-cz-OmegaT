---
    title: Create Bank Deposits
    description: You can make deposits to maintain a transaction record that contains information that can be applied to outstanding invoices and credit memos.
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.search.form: 10140, 10141, 10143, 10144, 10146, 10147, 10148, 36646
    ms.date: 04/01/2021
    ms.author: bholtorf

---
# Vytváření bankovních vkladů
> [!NOTE]
> Možnost vytvářet bankovní vklady je novinkou ve vlně 1 vydání Business Central 2022 pro mnoho verzí pro jednotlivé země. Pokud jste před tímto vydáním používali Business Central ve Spojených státech, Kanadě nebo Mexiku, možná používáte dřívější funkce. Můžete pokračovat, ale nové funkce nahradí staré v budoucí verzi. Chcete-li začít používat nové funkce popsané v tomto článku, může správce přejít na stránku **Správa funkcí** a zapnout možnost **Aktualizace funkcí: Standardizované odsouhlasení banky a vklady**.

Použijte stránku **Bankovní vklady** k registraci vkladů jako jednoho dokumentu, který zaúčtuje jeden nebo více záznamů na bankovní účet. Bankovní vklady se obvykle používají k registraci hotovostních vkladů. Stránka Bankovní vklady je k dispozici v nabídce **Správa hotovosti** v Centru rolí manažera a dalších pracovních plochách rolí, které se zabývají správou hotovosti.

Částky na bankovních vkladech mohou pocházet z několika zdrojů:

* Prodeje, použití finančního účtu pro výnosy.
* Platby zákazníků.
* Vrácení hotovosti od prodejců nebo hotovostní platby na ně.

Řádky bankovních vkladů obsahují informace o jednotlivých vkladech, například šeky od zákazníků. The total of the amounts on the lines must add up to the total amount of the deposit.

Po vyplnění informací o vkladu a řádků je musíte zaúčtovat. Zaúčtováním se aktualizují příslušné účetní knihy. Tyto knihy zahrnují hlavní knihu a knihy bank, zákazníka a dodavatele. Zaúčtované vklady jsou uloženy pro budoucí použití na stránce **Zaúčtované bankovní vklady**.

Přehled **Bankovní vklad** zobrazuje vklady zákazníků a dodavatelů s původní částkou vkladu, částkou vkladu, která zůstává otevřená, a použitou částkou. Přehled také zobrazuje celkovou zaúčtovanou částku vkladu, kterou je třeba odsouhlasit.

## Než začnete
Než budete moci používat bankovní vklady, musíte nastavit několik věcí. Musíte mít připravenou číselnou řadu a šablonu finančního deníku. Měli byste také určit, zda chcete zaúčtovat částky bankovního vkladu jako paušální částku. To znamená jako součet všech částek na depozitních řádcích. V opačném případě je každý řádek zaúčtován jako samostatná položka. Zaúčtování vkladu jako jedné položky bankovní knihy může usnadnit odsouhlasení banky.

### Číselné řady a paušální vklady
Musíte nastavit číselnou řadu pro bankovní vklady a poté zadat řadu v poli **Čísla bankovních vkladů** na stránce **Nastavení prodeje a pohledávek**. Pro další informace se podívejte na [Vytvořit číselné řady](ui-create-number-series.md).

Také na stránce **Nastavení prodeje a pohledávek**, pokud chcete zaúčtovat vklady jako paušální částky a ne jako jednotlivé řádky, zapněte přepínač **Účtovat bankovní vklady jako paušální částku**. Posting a deposit as a lump sum, which creates one bank ledger entry for the full amount of the deposit, can make it easier to do bank reconciliation.

### General Journal Templates for Bank Deposits
You must also create a general journal template for deposits. You use general journals to post entries to bank, customer, vendor, fixed asset, and general ledger accounts. The journal templates design the general journal to suit the purpose of your work. That is, the fields on the journal template are exactly the ones you need.

The deposits will be cash receipts, so you might want to reuse your number series for cash receipt journals. Alternatively, if you need to distinguish between bank deposit and cash receipt journal entries, use a different number series.

You'll also need to create a batch job for the template. To create a batch job, on the **General Journal Templates** page, choose the **Batches** action. For more information, see [Using Journal Templates and Batches](ui-work-general-journals.md#use-journal-templates-and-batches).

## Dimensions on Bank Deposit Lines
The lines on the bank deposit will automatically use the default dimensions you specified in the **Department Code** and **Customer group Code** fields. When you choose **Customer** or **Vendor** in the **Account Type** field, the dimensions that are specified for the customer or vendor will replace the defaults. You can change the dimensions on the lines, if needed.

> [!TIP]
> Dimension on lines are set according to Default Dimension Priorities. Line dimensions prioritized over header dimensions. To avoid conflicts, you can create rules that prioritize when to use a dimension depending on the source. If you want to change how dimensions are prioritized, you can change their rankings on the **Default Dimension Priorities** page. For more information, see [To set up default dimension priorities](finance-dimensions.md#to-set-up-default-dimension-priorities).

## Create a Bank Deposit
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Deposits**, and then choose the related link.
2. Choose **New** to open the **Bank Deposit** page.
3. Choose the general journal template that you created for bank deposits.

   > [!NOTE]
   > If the general journal template has more than one batch, you will be prompted to choose one.

4. In the **Bank Account No.** field, choose the bank account in which to make the deposit.

   > [!TIP]
   > You can double-check that you're depositing to the correct account by using the **Account Card** and **Account Ledger Entries** actions to look up the ledger entries for the selected bank account. For example, to see whether similar deposits were made to the account.

5. In the **Total Deposit Amount** field, enter the total amount of the deposit. This total must be the sum of the amounts on all lines.
6. Podle potřeby vyplňte zbývající pole. [!INCLUDE [tooltip-inline-tip_md](../archive/SetupAndAdministration/includes/tooltip-inline-tip_md.md)]

   The date in the **Posting Date** field and the dimensions in the **Department Code** and **Customer group Code** fields will be assigned to the lines that you create for the bank deposit. You can change them if needed.

7. Depending on whether you want to post the bank deposit as lump sum or each line individually to the bank ledger, turn the **Post as Lump Sum** toggle on or off. The default setting comes from the same toggle on the **Sales & Receivables Setup** page.

   > [!NOTE]
   > The **Currency Code** field shows the currency that is specified for the bank account you chose. You cannot choose a different currency.

8. On the **Lines** FastTab, create a new line for each cash payment that you want to deposit.
9. In the **Account Type** field, specify where the payment originated. For bank deposits, the type is typically **Customer** or **Vendor**.

   > [!NOTE]
   > You can also register a cash payment to a vendor. To do that, choose **Vendor** and then enter the payment amount as a negative number in the **Credit Amount** field on the line.

10. In the **Document No.** field, enter the document number of the invoice from which the credit amount originated. You can use a document number for each line, or the same number for all lines.

   > [!TIP]
   > Typically, you don't need to fill in the **Document Type** field for financial entries. For example, if you're depositing cash from a day's sale you leave the field blank. If you're depositing cash from a customer payment, you choose **Payment**.

11. If you're depositing a cash payment for a specific customer invoice, choose the **Apply Entries** action, and then enter the invoice number in the **Applies-to ID** field.
12. If you're ready to post the bank deposit, choose the **Post** action.

   > [!TIP]
   > Before you post the deposit you can use the **Test Report** action to review your data. The report will show whether there are any issues, such as missing data, that will prevent posting.

## Finding Posted Bank Deposits
The **Posted Bank Deposits** page lists your company's previous deposits. In the list, you can review the comments and dimensions that were specified for the deposits. You can open the bank deposit to view more details, and from there you can investigate further. For example, you can choose the Find entries action to view the posted bank ledger entries. From the bank ledger entry, you can find its corresponding posted general ledger entry.

If you want to look up all general ledger entries for the posted deposit lines, go to the **G/L Register** page and use the **General Ledger** action. There you'll find all of the general ledger entries, including the entries for customers and vendors.

## Reversing a Posted Bank Deposit
To reverse a posted deposit, go to the **G/L Registers** page, find the register for the deposit, and then choose the **Reverse Register** action.

> [!NOTE]
> You can only reverse a register that contains a single type of entry. That is, the register must contain only customer entries or vendor entries, but not both. If a register contains both you must manually reverse the deposit.

## Viz také
[Finance](finance.md)  
[Setting Up Finance](finance.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]



