---
    title: Payment Tolerance and Payment Discount Tolerance
    description: You can set up payment tolerance to close an invoice when the payment does not fully cover the amount on the invoice.
    author: SorenGP


    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.form: 118, 314, 395
    ms.date: 10/29/2021
    ms.author: edupont

---
# Práce s odchylkami platby a tolerancemi platebních slev
Můžete nastavit odchylku platby pro uzavření faktury, pokud platba plně nepokrývá částku na faktuře. Například platební tolerance jsou obvykle pro malé částky, které by stálo více opravit než jen přijmout. Můžete nastavit toleranci platební slevy a poskytnout tak platební slevu po uplynutí data platební slevy.

Můžete použít platební tolerance tak, aby každá nesplacená částka měla nastavenou maximální povolenou platební toleranci. Pokud je splněna odchylka platby, je částka platby analyzována. Pokud je částka platby nedoplatek, pak je nesplacená částka zcela uzavřena nedoplatkem. Podrobná položka je zaúčtována do položky platby, takže na vyúčtované položce faktury nezůstane žádná zbývající částka. Pokud je částka platby přeplatek, je do položky platby zaúčtována nová podrobná položka, takže na položce platby nezůstane žádná zbývající částka.

Můžete použít toleranci platební slevy, takže pokud přijmete platební slevu po datu skonta, pak je vždy zaúčtována buď na účet skonta nebo na účet odchylky skonta.

## Použití platební odchylky na více dokladech
Jeden doklad má stejnou platební toleranci bez ohledu na to, zda je použit samostatně nebo s jinými doklady. Přijetí pozdního skonta při použití odchylky platby na více dokladů se automaticky vyskytuje pro každý doklad, kde platí následující pravidlo:

*payment discount date < payment date on the selected entry <= payment tolerance date*

Toto pravidlo platí také pro určení, zda se mají zobrazit upozornění při použití odchylky platby na více dokladů. Upozornění tolerance skonta se zobrazí pro každou položku, která splňuje kritéria data. For more information, see [Example 2 - Tolerance Calculations for Multiple Documents](finance-payment-tolerance-and-payment-discount-tolerance.md#example-2---tolerance-calculations-for-multiple-documents).

Můžete zvolit zobrazení upozornění, které je založeno na různých situacích tolerance.

- První upozornění je pro toleranci skonta. Jste informováni, že můžete přijmout pozdní skonto. Poté můžete zvolit, zda chcete přijmout toleranci k datu slevy.
- Druhé upozornění je pro odchylku platby. Budete informováni, že všechny položky mohou být uzavřeny, protože rozdíl je v součtu maximální tolerance platby pro vyrovnané položky. Poté můžete zvolit, zda chcete přijmout toleranci k částce platby.

> [!NOTE]
> Enabling the warning message will let choose how to process payments that are within tolerance. Pokud zprávu nepovolíte a je zadána úroveň tolerance, budou faktury s částkami, které jsou v rámci tolerance, automaticky uzavřeny a zbývající částku nelze ponechat.

For more information, see [To enable or disable payment tolerance warning](finance-payment-tolerance-and-payment-discount-tolerance.md#to-enable-or-disable-payment-tolerance-warnings).

## Nastavení odchylek
Tolerance ve dnech a částkách vám umožňuje uzavřít fakturu, i když platba zcela nepokrývá částku na faktuře, ať už je to z důvodu překročení data splatnosti platební slevy, odečtení zboží nebo z důvodu malé chyby . To platí i pro refundace a dobropisy.

To set up tolerance you have to set up various tolerance accounts, specify both payment discount tolerance and payment tolerance posting methods and then run the **Change Payment Tolerance** batch job.
1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Nastavení obecného účtování** a poté vyberte související odkaz.
2. On the **General Posting Setup** page, set up a debit and a credit sales payment tolerance account and a debit and a credit purchase payment tolerance account.
3. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customer Posting Groups**, and then choose the related link.
4. On the **Customer Posting Groups** page, set up a debit and a credit payment tolerance account. For more information, see [Setting Up Posting Groups](finance-posting-groups.md).
5. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendor Posting Setup**, and then choose the related link.
6. On the **Vendor Posting Groups** page, set up a debit and a credit payment tolerance account.
7. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.
8. Open the **General Ledger Setup** page.
9. On the **Application** FastTab, fill in the **Payment Discount Tolerance Posting**, **Payment Discount Grace Period** and **Payment Tolerance Posting** fields.
10. Choose the **Change Payment Tolerance** action.
11. On the **Change Payment Tolerance** page, fill in the **Payment Tolerance %** and **Max Payment Tolerance Amount** fields, and then choose the **OK** button.

> [!IMPORTANT]  
> You have now set up tolerance for local currency only. If you want [!INCLUDE[prod_short](includes/prod_short.md)] to handle tolerance on payments, credit memos, and refunds in a foreign currency, you must run the **Change Payment Tolerance** batch job with a value in the **Currency Code** field.

> [!NOTE]  
> If you want to get a payment tolerance warning every time that you post an application in the tolerance, you must activate the payment tolerance warning. For more information, see [To enable or disable payment tolerance warning](finance-payment-tolerance-and-payment-discount-tolerance.md#to-enable-or-disable-payment-tolerance-warnings) section.
>
> Chcete-li deaktivovat odchylku pro odběratele nebo dodavatele, musíte zablokovat odchylky na příslušné kartě zákazníka nebo dodavatele. For more information, see [To block payment tolerance for customers](finance-payment-tolerance-and-payment-discount-tolerance.md#to-block-payment-tolerance-for-customers).
>
> When you set up tolerance, [!INCLUDE[prod_short](includes/prod_short.md)] also checks if there are any open entries and calculates the tolerance for these entries.

## Povolení nebo zakázání upozornění na odchylky plateb
Upozornění odchylky platby se zobrazí při zaúčtování vyrovnání, které má zůstatek v povolené odchylce. Poté si můžete vybrat, jak chcete zůstatek zaúčtovat a dokumentovat.
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.
2. On the **General Ledger Setup** page, on the **Application** FastTab, turn on the **Payment Tolerance Warning** toggle to activate the warning. Chcete-li varování deaktivovat, vypněte zašrtávací políčko.

> [!NOTE]  
> The default option for the **Payment Tolerance Warning** page is **Leave the Balance as Remaining Amount**. The default option for the **Payment Discount Tolerance Warning** page the is **Do Not Accept the Late Payment Discount**.

## Blokování platební odchylky pro zákazníky
Výchozí nastavení pro odchylku platby je povoleno. Chcete-li zakázat platební odchylku určitého zákazníka nebo dodavatele, musíte blokovat toleranci na příslušné kartě zákazníka nebo dodavatele. Následující text popisuje, jak to nastavit pro zákazníka. Kroky jsou podobné pro dodavatele.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Zákazník** nebo **Dodavatel** a poté vyberte související odkaz.
2. On the **Payments** FastTab, select the **Block Payment Tolerance** check box.

> [!NOTE]  
> If the customer or vendor has open entries, you must first remove payment tolerance from entries that are currently open.

## Příklad 1 - Výpočty odchylek pro jeden doklad
Následuje několik příkladů scénářů zobrazujících očekávané výpočty odchylky a účtování, ke kterým dochází v různých situacích.

The **G/L Setup** page contains the following setup:
- Lhůta odkladu skonta: 5D
- Maximální odchylka platby: 5

Scénáře s alternativou A nebo B představují následující:

- **A** In this case, the payment discount tolerance warning has been turned off OR the user has the warning on and has selected to allow the late payment discount (Post the Balance as Payment Tolerance).
- **B** In this case, the user has the warning on and has selected not to allow the late payment discount (Leave the Balance as Remaining Amount).

| — | Zásoby | Payment Discount | Max Payment Tolerance | Payment Discount Date | Payment Discount Tolerance Date | Datum platby | Payment | Typ odchylky | Všechny položky uzavřeny | Payment Discount Tolerance GL/CL | Payment Tolerance G/L |
|-------|----------|----------------|-----------------------|---------------------|--------------------------|------------------|----------|--------------------|------------------------|------------------------------|----------------------------|  
| 1 | 1,000 | 20 | 5 | 01/15/03 | 01/20/03 | <=01/15/03 | 985 | PaymentTolerance | Ano | 0 | -5 |
| 2 | **1,000** | **20** | **5** | **01/15/03** | **01/20/03** | **<=01/15/03** | **980** | **None** | **Ano** | **0** | **0** |
| 3 | 1,000 | 20 | 5 | 01/15/03 | c | <=01/15/03 | 975 | PaymentTolerance | Ano | 0 | 5 |
| 4A | 1,000 | 20 | 5 | 01/15/03 | 01/20/03 | 01/16/03 01/20/03 | 1005 | PaymentDiscountTolerance | No, 25 on the Payment | 20/-20 | 0 |
| 5A | 1,000 | 20 | 5 | 01/15/03 | 01/20/03 | 01/16/03 01/20/03 | 1000 | PaymentDiscountTolerance | No, 20 on the Payment | 20/-20 | 0 |
| 6A | 1,000 | 20 | 5 | 01/15/03 | 01/20/03 | 01/16/03 01/20/03 | 995 | PaymentDiscountTolerance | No, 15 on the Payment | 20/-20 | 0 |
| 4B | 1,000 | 20 | 5 | 01/15/03 | 01/20/03 | 01/16/03 01/20/03 | 1005 | PaymentTolerance | Ano | 0 | -5 |
| **5B** | **1,000** | **20** | **5** | **01/15/03** | **01/20/03** | **01/16/03 01/20/03** | **1000** | **None** | **Ano** | **0** | **0** |
| 6B | 1,000 | 20 | 5 | 01/15/03 | 01/20/03 | 01/16/03 01/20/03 | 995 | PaymentTolerance | Ano | 0 | 5 |
| 7 | 1,000 | 20 | 5 | 01/15/03 | 01/20/03 | 01/16/03 01/20/03 | 985 | PaymentDiscountTolerance & PaymentTolerance | Ano | 20/-20 | -5 |
| 8 | 1,000 | 20 | 5 | 01/15/03 | 01/20/03 | 01/16/03 01/20/03 | 980 | PaymentDiscountTolerance | Ano | 20/-20 | 0 |
| 9 | 1,000 | 20 | 5 | 01/15/03 | 01/20/03 | 01/16/03 01/20/03 | 975 | PaymentDiscountTolerance & PaymentTolerance | Ano | 20/-20 | 5 |
| 10 | 1,000 | 20 | 5 | 01/15/03 | 01/20/03 | >01/20/03 | 1005 | PaymentTolerance | Ano | 0 | -5 |
| **11** | **1,000** | **20** | **5** | **01/15/03** | **01/20/03** | **>01/20/03** | **1000** | **None** | **Ano** | **0** | **0** |
| 12 | 1,000 | 20 | 5 | 01/15/03 | 01/20/03 | >01/20/03 | 995 | PaymentTolerance | Ano | 0 | 5 |
| 13 | 1,000 | 20 | 5 | 01/15/03 | 01/20/03 | >01/20/03 | 985 | Žádné | Ne, 15 na faktuře | 0 | 0 |
| 14 | 1,000 | 20 | 5 | 01/15/03 | 01/20/03 | >01/20/03 | 980 | Žádné | Ne, 20 na faktuře | 0 | 0 |
| 15 | 1,000 | 20 | 5 | 01/15/03 | 01/20/03 | >01/20/03 | 975 | Žádné | Ne, 25 na faktuře | 0 | 0 |

### Schémata rozsahu plateb
Ve vztahu k výše uvedenému scénáři jsou diagramy rozsahů plateb následující:

#### (1) Datum platby <=01/15/03 (Scénář 1-3)
Zbývající částka na

Běžná pravidla vyrovnání

![Single payment tolerance rules 1.](media/singlePmtTolRules_Pre1503.gif "Single payment tolerance rules 1")

(1) Pokud platba spadá do těchto rozsahů, mohou být všechny položky vyrovnání uzavřeny s tolerancí nebo bez ní..

(2) Pokud platba spadá do těchto rozsahů, nelze všechny položky vyrovnání uzavřít ani s tolerancí.

#### (2) Datum platby je mezi 01/16/03 a 01/20/03 (scénáře 4-9)
Zbývající částka na

Běžná pravidla vyrovnání

![Single payment tolerance rules 2.](media/singlePmtTolRules_GracePeriod.gif "Single payment tolerance rules 2")

(1) Pokud platba spadá do těchto rozsahů, mohou být všechny položky vyrovnání uzavřeny s tolerancí nebo bez ní..

(2) Pokud platba spadá do těchto rozsahů, nelze všechny položky vyrovnání uzavřít ani s tolerancí.

#### (3) Datum platby je po 01/20/03 (scénáře 10-15)
Zbývající částka na

Běžná pravidla vyrovnání

![Single payment tolerance rules 3.](media/singlePmtTolRules_Post0120.gif "Single payment tolerance rules 3")

(1) Pokud platba spadá do těchto rozsahů, mohou být všechny položky vyrovnání uzavřeny s tolerancí nebo bez ní..

(2) Pokud platba spadá do těchto rozsahů, nelze všechny položky vyrovnání uzavřít ani s tolerancí.

## Příklad 2 – Výpočty odchylek pro více dokladů
Následuje několik příkladů scénářů zobrazujících očekávané výpočty odchylky a účtování, ke kterým dochází v různých situacích. Příklady jsou omezeny pouze na scénáře, které vedou k uzavření všech položek ve vyrovnání.

The **G/L Setup** page contains the following setup:
- Lhůta odkladu skonta: 5D
- Maximální odchylka platby: 5

Scénáře s alternativou A, B, C, nebo D představují následující:

- **A** In this case the payment discount tolerance warning has been turned off, OR the user has the warning on and has selected to allow the late payment discount (Post as Tolerance) in any invoice.
- **B** In this case, the user has the warning on and has selected not to allow the late payment discount on any invoice.
- **C** - In this case, the user has the warning on and has selected to allow the late payment discount on the first invoice but not the second.
- **D** - In this case, the user has the warning on and has selected not to allow the late payment discount on the first invoice but allowed it on the second.

| — | Zásoby | Payment Discount | Max Payment Tolerance | Payment Discount Date | Payment Discount Tolerance Date | Datum platby | Payment | Typ odchylky | Všechny položky uzavřeny | Payment Discount Tolerance GL/CL | Payment Tolerance G/L |
|-------|----------|---------------|-------------------|---------------------|--------------------------|------------------|---------|--------------------|------------------------|------------------------------|------------------------|  
| 1 | 1,000 <br />1,000 | 60 <br />30 | 5 <br />5 | 01/15/03 <br />01/17/03 | 01/20/03 <br />01/22/03 | <=01/15/03 | 1920 | PaymentTolerance | Ano | 0<br /><br /> 0 | -5 <br />-5 |
| **2** | **1,000** <br />**1,000** | **60** <br />**30** | **5** <br />**5** | **01/15/03** <br />**01/17/03** | **01/20/03** <br />**01/22/03** | **<=01/15/03** | **1910** | **None** | **Ano** | **0**<br /><br /> **0** | 0 <br />0 |
| 3 | 1,000 <br />1,000 | 60 <br />30 | 5 <br />5 | 01/15/03 <br />01/17/03 | 01/20/03 <br />01/22/03 | <=01/15/03 | 1900 | PaymentTolerance | Ano | 0<br /><br /> 0 | 5 <br />5 |
| 4B | 1,000 <br />1,000 | 60 <br />30 | 5 <br />5 | 01/15/03 <br />01/17/03 | 01/20/03 <br />01/22/03 | 01/16/03 01/17/03 | 1980 | PaymentTolerance | Ano | 0<br /><br /> 0 | -5<br /><br /> -5 |
| **5B** | **1,000** <br />**1,000** | **60** <br />**30** | **5** <br />**5** | **01/15/03** <br />**01/17/03** | **01/20/03** <br />**01/22/03** | **01/16/03 01/17/03** | **1970** | **None** | **Ano** | **0**<br /><br /> **0** | **0**<br /><br /> **0** |
| 6B | 1,000 <br />1,000 | 60 <br />30 | 5 <br />5 | 01/15/03 <br />01/17/03 | 01/20/03 <br />01/22/03 | 01/16/03 01/17/03 | 1960 | PaymentTolerance | Ano | 0<br /><br /> 0 | 5<br /><br /> 5 |
| 7A | 1,000 <br />1,000 | 60 <br />30 | 5 <br />5 | 01/15/03 <br />01/17/03 | 01/20/03 <br />01/22/03 | 01/16/03 01/17/03 | 1920 | PaymentDiscountTolerance & PaymentTolerance | Ano | 60/60<br /><br /> 0/0 | -5 <br />-5 |
| 8A | 1,000 <br />1,000 | 60 <br />30 | 5 <br />5 | 01/15/03 <br />01/17/03 | 01/20/03 <br />01/22/03 | 01/16/03 01/17/03 | 1910 | PaymentDiscountTolerance | Ano | 60/60<br /><br /> 0/0 | 0 <br />0 |
| 9A | 1,000 <br />1,000 | 60 <br />30 | 5 <br />5 | 01/15/03 <br />01/17/03 | 01/20/03 <br />01/22/03 | 01/16/03 01/17/03 | 1900 | PaymentDiscountTolerance & PaymentTolerance | Ano | 60/60 | 5 <br />5 |
| 10B | 1,000 <br />1,000 | 60 <br />30 | 5 <br />5 | 01/15/03 <br />01/17/03 | 01/20/03 <br />01/22/03 | 01/18/03 01/20/03 | 2010 | PaymentTolerance | Ano | 0<br /><br /> 0 | -5<br /><br /> -5 |
| **11B** | **1,000** <br />**1,000** | **60** <br />**30** | **5** <br />**5** | **01/15/03** <br />**01/17/03** | **01/20/03** <br />**01/22/03** | **01/18/03 01/20/03** | **2000** | **None** | **Ano** | **0**<br /><br /> **0** | **0**<br /><br /> **0** |
| 12B | 1,000 <br />1,000 | 60 <br />30 | 5 <br />5 | 01/15/03 <br />01/17/03 | 01/20/03 <br />01/22/03 | 01/18/03 01/20/03 | 1990 | PaymentTolerance | Ano | 0<br /><br /> 0 | 5<br /><br /> 5 |
| 13D | 1,000 <br />1,000 | 60 <br />30 | 5 <br />5 | 01/15/03 <br />01/17/03 | 01/20/03 <br />01/22/03 | 01/18/03 01/20/03 | 1980 | PaymentDiscountTolerance & PaymentTolerance | Ano | 0/0<br /><br /> 30/-30 | -5 <br />-5 |
| 14D | 1,000 <br />1,000 | 60 <br />30 | 5 <br />5 | 01/15/03 <br />01/17/03 | 01/20/03 <br />01/22/03 | 01/18/03 01/20/03 | 1970 | PaymentDiscountTolerance | Ano | 0/0<br /><br /> 30/-30 | 0 <br />0 |
| 15D | 1,000 <br />1,000 | 60 <br />30 | 5 <br />5 | 01/15/03 <br />01/17/03 | 01/20/03 <br />01/22/03 | 01/18/03 01/20/03 | 1960 | PaymentDiscountTolerance & PaymentTolerance | Ano | 0/0<br /><br /> 30/-30 | 5 <br />5 |
| 16D | 1,000 <br />1,000 | 60 <br />30 | 5 <br />5 | 01/15/03 <br />01/17/03 | 01/20/03 <br />01/22/03 | 01/18/03 01/20/03 | 1950 | PaymentDiscountTolerance & PaymentTolerance | Ano | 60/-60<br /><br /> 0/0 | -5 <br />-5 |
| 17D | 1,000 <br />1,000 | 60 <br />30 | 5 <br />5 | 01/15/03 <br />01/17/03 | 01/20/03 <br />01/22/03 | 01/18/03 01/20/03 | 1940 | PaymentDiscountTolerance | Ano | 60/-60<br /><br /> 0/0 | 0 <br />0 |
| 18D | 1,000 <br />1,000 | 60 <br />30 | 5 <br />5 | 01/15/03 <br />01/17/03 | 01/20/03 <br />01/22/03 | 01/18/03 01/20/03 | 1930 | PaymentDiscountTolerance & PaymentTolerance | Ano | 60/-60<br /><br /> 0/0 | 5 <br />5 |
| 19A | 1,000 <br />1,000 | 60 <br />30 | 5 <br />5 | 01/15/03 <br />01/17/03 | 01/20/03 <br />01/22/03 | 01/18/03 01/20/03 | 1920 | PaymentDiscountTolerance & PaymentTolerance | Ano | 60/-60<br /><br /> 30/-30 | -5 <br />-5 |
| 20A | 1,000 <br />1,000 | 60 <br />30 | 5 <br />5 | 01/15/03 <br />01/17/03 | 01/20/03 <br />01/22/03 | 01/18/03 01/20/03 | 1910 | PaymentDiscountTolerance | Ano | 60/-60<br /><br /> 30/-30 | 0 <br />0 |
| 21A | 1,000 <br />1,000 | 60 <br />30 | 5 <br />5 | 01/15/03 <br />01/17/03 | 01/20/03 <br />01/22/03 | 01/18/03 01/20/03 | 1900 | PaymentDiscountTolerance & PaymentTolerance | Ano | 60/-60<br /><br /> 30/-30 | 5 <br />5 |
| 22B | 1,000 <br />1,000 | 60 <br />30 | 5 <br />5 | 01/15/03 <br />01/17/03 | 01/20/03 <br />01/22/03 | 01/21/03 01/22/03 | 2010 | PaymentTolerance | Ano | 0<br /><br /> 0 | -5<br /><br /> -5 |
| **23B** | **1,000** <br />**1,000** | **60** <br />**30** | **5** <br />**5** | **01/15/03** <br />**01/17/03** | **01/20/03** <br />**01/22/03** | **01/21/03 01/22/03** | **2000** | **None** | **Ano** | **0**<br /><br /> **0** | **0**<br /><br /> **0** |
| 24B | 1,000 <br />1,000 | 60 <br />30 | 5 <br />5 | 01/15/03 <br />01/17/03 | 01/20/03 <br />01/22/03 | 01/21/03 01/22/03 | 1990 | PaymentTolerance | Ano | 0<br /><br /> 0 | 5<br /><br /> 5 |
| 25A | 1,000 <br />1,000 | 60 <br />30 | 5 <br />5 | 01/15/03 <br />01/17/03 | 01/20/03 <br />01/22/03 | 01/21/03 01/22/03 | 1980 | PaymentDiscountTolerance & PaymentTolerance | Ano | 0/0<br /><br /> 30/30 | -5 <br />-5 |
| 26A | 1,000 <br />1,000 | 60 <br />30 | 5 <br />5 | 01/15/03 <br />01/17/03 | 01/20/03 <br />01/22/03 | 01/21/03 01/22/03 | 1970 | PaymentDiscountTolerance | Ano | 0/0<br /><br /> 30/30 | 0 <br />0 |
| 27A | 1,000 <br />1,000 | 60 <br />30 | 5 <br />5 | 01/15/03 <br />01/17/03 | 01/20/03 <br />01/22/03 | 01/21/03 01/22/03 | 1960 | PaymentDiscountTolerance & PaymentTolerance | Ano | 0/0<br /><br /> 30/30 | 5 <br />5 |
| 28 | 1,000 <br />1,000 | 60 <br />30 | 5 <br />5 | 01/15/03 <br />01/17/03 | 01/20/03 <br />01/22/03 | >01/22/03 | 2010 | PaymentTolerance | Ano | 0 | -5 |
| **29** | **1,000** <br />**1,000** | **60** <br />**30** | **5** <br />**5** | **01/15/03** <br />**01/17/03** | **01/20/03** <br />**01/22/03** | **>01/22/03** | **2000** | **None** | **Ano** | **0** | **0** |
| 30 | 1,000 <br />1,000 | 60 <br />30 | 5 <br />5 | 01/15/03 <br />01/17/03 | 01/20/03 <br />01/22/03 | >01/22/03 | 1990 | PaymentTolerance | Ano | 0 | 5 |

### Schémata rozsahu plateb
Ve vztahu k výše uvedenému scénáři jsou diagramy rozsahů plateb následující:

#### (1) Datum platby <=01/15/03 (Scénář 1-3)
Zbývající částka na

Běžná pravidla vyrovnání

:::image type="content" source="media/multiplePmtTolRules_Pre1503.gif" alt-text="Multiple payment tolerance rules 1a":::

(1) Pokud platba spadá do těchto rozsahů, mohou být všechny položky vyrovnání uzavřeny s tolerancí nebo bez ní..

(2) Pokud platba spadá do těchto rozsahů, nelze všechny položky vyrovnání uzavřít ani s tolerancí.

#### (2) Datum platby se pohybuje mezi 01/16/03 a 01/17/03 (Scénář 4-9)
Zbývající částka na

Běžná pravidla vyrovnání

:::image type="content" source="media/multiplePmtTolRules_GracePeriodInv1-2.gif" alt-text="Multiple payment tolerance rules 2":::

(1) Pokud platba spadá do těchto rozsahů, mohou být všechny položky vyrovnání uzavřeny s tolerancí nebo bez ní..

(2) Pokud platba spadá do těchto rozsahů, nelze všechny položky vyrovnání uzavřít ani s tolerancí.

#### (3) Datum platby se pohybuje mezi 01/18/03 a 01/20/03 (Scénář 10-21)
Zbývající částka na

Běžná pravidla vyrovnání

:::image type="content" source="media/multiplePmtTolRules_GracePeriodInv1.gif" alt-text="Multiple payment tolerance rules 3":::

(1) Pokud platba spadá do těchto rozsahů, mohou být všechny položky vyrovnání uzavřeny s tolerancí nebo bez ní..

(2) Pokud platba spadá do těchto rozsahů, nelze všechny položky vyrovnání uzavřít ani s tolerancí.

#### (4) Datum platby se pohybuje mezi 01/21/03 and 01/22/03 (Scénář 22-27)
Zbývající částka na

Běžná pravidla vyrovnání

:::image type="content" source="media/multiplePmtTolRules_GracePeriodInv2.gif" alt-text="Multiple payment tolerance rules 4":::

(1) Pokud platba spadá do těchto rozsahů, mohou být všechny položky vyrovnání uzavřeny s tolerancí nebo bez ní..

(2) Pokud platba spadá do těchto rozsahů, nelze všechny položky vyrovnání uzavřít ani s tolerancí.

#### (5) Datum platby je po 01/22/03 (Scénář 28-30)
Zbývající částka na

Běžná pravidla vyrovnání

:::image type="content" source="media/multiplePmtTolRules_Post0122.gif" alt-text="Multiple payment tolerance rules 5":::

(1) Pokud platba spadá do těchto rozsahů, mohou být všechny položky vyrovnání uzavřeny s tolerancí nebo bez ní..

(2) Pokud platba spadá do těchto rozsahů, nelze všechny položky vyrovnání uzavřít ani s tolerancí.

## Viz také
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Managing Receivables](receivables-manage-receivables.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]