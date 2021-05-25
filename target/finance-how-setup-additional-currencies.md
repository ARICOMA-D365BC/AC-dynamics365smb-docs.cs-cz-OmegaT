---
title: Setting Up Additional Currencies| Microsoft Docs
description: Your general ledger is set up to use your local currency (LCY), and another currency is set up as an additional currency, with a current exchange rate assigned.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: multiple currencies
ms.date: 04/01/2021
ms.author: edupont

---
# Nastavení přídavné měny pro hlášení
Vzhledem k tomu, že společnosti působí ve stále více zemích nebo oblastech, je důležitější, aby byly schopny kontrolovat a vykazovat finanční údaje ve více než jedné měně.

Finance jsou nastaveny tak, aby používaly lokální měnu (LM), ale můžete je nastavit tak, aby používaly i jinou měnu s přiřazeným aktuálním směnným kurzem. By designating a second currency as a so-called additional reporting currency, [!INCLUDE[prod_short](includes/prod_short.md)] will automatically record amounts in both LCY and this additional reporting currency on each G/L entry and other entries, such as VAT entries.

> [!WARNING]
> Funkce doplňkové měny vykazování by neměla být použita jako základ pro účetní závěrky. Nejedná se o nástroj, který může provádět převody zahraničních dceřiných účetních závěrek v rámci konsolidace společnosti. Přídavnou měnu pro hlášení lze použít pouze k přípravě sestav v jiné měně, jako by tato měna byla lokální měnou společnosti.

## Zobrazení sestav a částek v přídavné měně
Použití přídavné měny pro hlášení může pomoci procesu vykazování pro společnost v následujících případech:

- Společnosti v zemích nebo oblastech mimo EU, které mají vysoký podíl transakcí se společnostmi  v EU. V takovém případě může společnost ze zemí mimo EU rovněž chtít podávat zprávy v eurech, aby její finanční zprávy byly pro obchodní partnery EU použitelnější.
- Společnosti, které také chtějí zobrazit přehledy v mezinárodně obchodovanější měně než ve své vlastní lokální měně.

Několik finančních výkazů je založeno na věcných položkách. To display report data in the additional reporting currency, you simply place a check mark in the **Show Amounts in Add. Reporting Currency** field on the **Options** FastTab for the relevant G/L report.

## Úprava směnných kurzů
Vzhledem k tomu, že směnné kurzy neustále kolísají, musí být pravidelně upravovány další měnové ekvivalenty ve vašem systému. Pokud tyto úpravy nejsou provedeny, částky, které byly převedeny ze zahraničních (nebo dodatečných) měn a zaúčtovány do hlavní knihy v lokální měně, mohou být zavádějící. Kromě toho musí být denní položky zaúčtované před vstupem denního směnného kurzu do aplikace aktualizovány po zadání denních informací o směnném kurzu. The **Adjust Exchange Rates** batch job is used to adjust the exchange rates of posted customer, vendor and bank account entries. Může také aktualizovat další částky měny vykazování u položek hlavní knihy. For more information, see [Update Currency Exchange Rates](finance-how-update-currencies.md).

## Nastavení přídavné měny pro hlášení
Chcete-li nastavit další měnu pro hlášení, je nutné postupovat takto:

- Určete účty hlavní knihy pro účtování úprav směnného kurzu.
- Určete metodu úpravy směnného kurzu pro všechny účty hlavní knihy.
- Zadejte způsob úpravy směnného kurzu pro položky DPH.
- Aktivujte další měnu pro hlášení.

### Určení účtů hlavní knihy pro účtování úprav směnného kurzu

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Currencies**, and then choose the related link.
2. On the **Currencies** page, fill in the following fields for the additional reporting currency.

| Pole | Popis |
|---------------------------------|---------------------------------------|  
| **Realized GL Gains Account** | Účet hlavní knihy, na který budou zaúčtovány kurzové zisky pro měnové úpravy mezi LM a přídavnou měnou vykazování. |
| **Realized GL Losses Account** | Účet hlavní knihy, na který budou zaúčtovány kurzové ztráty pro měnové úpravy mezi LM a přídavnou měnou vykazování. |
| **Residual Gains Account** | Účet hlavní knihy, na který jsou zaúčtovány zbývající částky, které jsou zisky, pokud účtujete v oblasti aplikace hlavní knihy v LM i v přídavné měně pro hlášení. |
| **Residual Losses Account** | Účet hlavní knihy, na který jsou zaúčtovány zbývající částky, které jsou ztrátami, pokud účtujete v oblasti aplikace hlavní knihy v LM i v přídavné měně pro hlášení. |

> [!NOTE]  
> Residual amounts can occur when [!INCLUDE[prod_short](includes/prod_short.md)] rounds debit and credit amounts that have been converted from LCY to an additional reporting currency.

Pro každý účet hlavní knihy je nutné určit, jak budou částky hlavní knihy pro tento účet upraveny o kolísání směnného kurzu mezi LM a přídavnou měnou pro hlášení.

### Určení metody úpravy směnného kurzu pro všechny účty hlavní knihy
1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Účtovní osnova** a poté vyberte související odkaz.
2. On the **Chart of Accounts** page, select the relevant account, and then choose the **Edit** action.
3. On the **GL Account Card** page, select the relevant method in the **Exchange Rate Adjustment** field.

   If you post in an additional reporting currency, specify in the **Exchange Rate Adjustment** field how this general ledger account will be adjusted for exchange-rate fluctuations between LCY and the additional reporting currency. V následující tabulce jsou uvedeny možnosti výběru.

   | Pole | Popis |
   |----------------------------------|---------------------------------------|  
   | **No Adjustment** | Na účtu hlavní knihy se neprovede žádná úprava směnného kurzu. Toto je výchozí možnost.<br /><br /> **NOTE:** This option should be selected if the exchange rate between the LCY and additional reporting currency is always fixed. |
   | **Adjust Amount** | Částka LM je upravena o kurzové zisky nebo ztráty. Exchange rate gains or losses are posted to the general ledger account in the **Amount** field and to the accounts you specified for gains or losses in the **Realized G/L Gains Account** and **Realized G/L Losses Account** fields on the **Currencies** page. |
   | **Adjust Additional-Currency Amount** | Přídavná měna vykazování je upravena o kurzové zisky nebo ztráty. Exchange rate gains or losses are posted to the general ledger account in the **Additional-Currency Amount** field and to the accounts you specified for gains or losses in the **Realized G/L Gains Account** and **Realized G/L Losses Account** fields on the **Currencies** page. |

   Exchange rate gains and losses are posted when you run the **Adjust Exchange Rates** batch job. In that batch job, the adjustment exchange rate is identified on the **Currency Exchange Rates** page, and then the amounts in the **Amount** and **Additional-Currency Amount** fields on the general ledger entry are compared to determine whether there is an exchange rate gain or loss. The batch job uses the option that you select in the **Exchange Rate Adjustment** field to determine how to calculate and post exchange rate gains or losses for general ledger accounts.

4. Close the **G/L Account Card** page.

### Určení metody úpravy směnného kurzu pro položky DPH
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.
2. On the **General Ledger Setup** page, select the relevant method in the **VAT Exchange Rate Adjustment** field.
3. If you post in an additional reporting currency, you can specify in the **VAT Exchange Rate Adjustment** field how the accounts set up for VAT posting on the **VAT Posting Setup** page will be adjusted for exchange-rate fluctuations between LCY and the additional reporting currency.

   When you run the **Adjust Exchange Rates** batch job, the adjustment exchange rate is identified on the **Currency Exchange Rate** page and then the amounts in the **Amount** and **Additional-Currency Amount** fields on the VAT entry are compared to determine if there is an exchange rate gain or loss. Dávková úloha používá možnost, kterou vyberete v tomto poli, k určení, jak zaúčtovat zisky nebo ztráty směnného kurzu pro účty DPH.

   Máte stejné možnosti jako u položek hlavní knihy, ale v tomto případě budou upraveny položky DPH. V následující tabulce jsou uvedeny možnosti výběru.

   | Pole | Popis |
   |----------------------------------|---------------------------------------|  
   | **No Adjustment** | Na účtu hlavní knihy se neprovede žádná úprava směnného kurzu. This is the default option. |
   | **Adjust Amount** | Částka LM je upravena o kurzové zisky nebo ztráty. Exchange rate gains or losses are posted to the general ledger account in the **Amount** field and to the accounts you specified for gains or losses in the **Realized G/L Gains Account** and **Realized G/L Losses Account** fields on the **Currencies** page. |
   | **Adjust Additional-Currency Amount** | Přídavná měna vykazování je upravena o kurzové zisky nebo ztráty. Exchange rate gains or losses are posted to the general ledger account in the **Additional-Currency Amount** field and to the accounts you specified for gains or losses in the **Realized G/L Gains Account** and **Realized G/L Losses Account** fields on the **Currencies** page. |

### Aktivace přídavné měny pro hlášení
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.
2. On the **General Ledger Setup** page, choose the **Additional Reporting Currency** field to select the additional currency that you want to report in.
3. When you leave the field, [!INCLUDE[prod_short](includes/prod_short.md)] displays a confirmation message describing the effects of activating the additional reporting currency.
4. Choose the **Yes** button to confirm that you want to activate the currency.
5. The **Adjust Add. Reporting Currency** batch job opens.

   Tato dávková úloha převádí částky LM u existujících položek na přídavnou měnu pro hlášení. The batch job uses a default exchange rate copied from the exchange rate that is valid on the work date on the **Currency Exchange Rates** page. Residual amounts that occur on conversion of LCY to additional reporting currency are posted to the residual gains and losses accounts specified on the **Currencies** page. Datum zaúčtování a číslo dokumentu pro tyto položky jsou stejné jako pro původní položku hlavní knihy. Po zaúčtování všech těchto zbývajících položek dávková úloha zaúčtuje položku zaokrouhlení k datu uzávěrky každého uzavřeného roku na účet nerozděleného zisku. Tím zajistíte, že konečný zůstatek účtů příjmů za každý uzavřený rok je 0 v LM i v přídavné měně pro vykazování.
6. Podle potřeby vyplňte pole. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
7. Zvolte tlačítko **OK** pro spuštění dávkové úlohy.

Po spuštění dávkové úlohy budou částky na následujících existujících položkách v LM i v přídavné měně pro hlášení:

- Položky hlavní knihy
- Položky vyrovnání zboží
- Položky DPH
- Položky DPH
- Položky ocenění
- Řádky výrobní zakázky
- Položky objednávky výrobní zakázky

Kromě toho budou mít všechny budoucí položky stejného typu částky zaznamenané jak v LM, tak v přídavné měně pro hlášení.

> [!NOTE]  
> The **Add. Reporting Currency** field will only be activated after you choose the **OK** button in the **Adjust Add. Reporting Currency** batch job.

## Zobrazit související školení na webu [Microsoft Learn](/learn/paths/use-multiple-currencies-dynamics-365-business-central/)

## Viz také
[Update Currency Exchange Rates](finance-how-update-currencies.md)  
[Closing Years and Periods](year-close-years-periods.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]