---
title: Update Currency Exchange Rates (contains video)
description: If you track amounts in different currencies, you can let Business Central help you adjust FX exchange rates of posted entries with an external service.
author: edupont04


ms.topic: conceptual
ms.search.keywords: multiple currencies, adjust exchange rates, FX rates
ms.search.form: 5, 118
ms.date: 03/15/2022
ms.author: edupont

---
# Update Currency Exchange Rates

You can define different currencies in [!INCLUDE [prod_short](includes/prod_short.md)], for example if you do trade in currencies other than your local currency. Then, to help you keep track of changes in currency exchange rates, you can manage the currencies manually, or you can set up a currency exchange rate service.

## Měny

> [!TIP]  
> Pokud v [!INCLUDE[prod_short](includes/prod_short.md)] hledáte aktuální informace o směnných kurzech nebo historických kurzech, najdete je označované jako měna. Kromě tohoto článku si také přečtěte [Nastavení přídavní měny pro hlášení](finance-how-setup-additional-currencies.md).

[!INCLUDE [finance-currencies-def](includes/finance-currencies-def.md)]

Kódy měn zadáte v seznamu **Měny**, včetně dalších informací a nastavení, které jsou nezbytné pro každý kód měny. Pro více informací navštivte [Měny](finance-set-up-currencies.md#curr)

### Příklad měnové transakce pohledávky

[!INCLUDE [finance-currencies-example](includes/finance-currencies-example.md)]

## Směnné kurzy

Směnné kurzy jsou nástrojem pro výpočet hodnoty lokální měny (LCY) každé měnové transakce. The **Exchange Rates** page includes the following fields:

| Pole | Popis |
|---------------------------------|---------------------------------------|  
| **Starting Data** | The date when the currency rate was effectuated |
| **Currency Code** | The currency code related to this exchange rate |
| **Relational Currency Code** | If this currency is part of a triangular currency calculation, then the related currency code can be set up here |
| **Exchange Rate Amount** | The exchange rate amount is the rate to use for the currency code selected on the line. Normally 1 or 100 |
| **Relational Exch. Rate Amount** | The relational exchange rate amount relates to the rate to use for the relational currency code |
| **Adjustment Exch. Rate Amount** | The adjustment exchange rate amount is the rate to use for the currency code selected on the line for use of the **Adjust Exchange Rates** batch job |
| **Relational Adjmt Exch. Rate Amt** | The relational adjustment exchange rate amount is the rate to use for the currency code selected on the line for use of the **Adjust Exchange Rates** batch job |
| **Fix Exchange Rate Amount** | Specifies if the currency's exchange rate can be changed on invoices and journal lines. |

In general, the values of the **Exchange Rate Amount** and **Relational Exchange Rate Amount** fields are used as the default currency rate on all new receivables and payables documents that are created going forward. The document is assigned the currency rate according to the current working date.

> [!Note]
> The actual currency rate will be calculated using this formula:
>
> `Currency Amount = Amount / Exchange Rate Amount * Relational Exch. Rate Amount`

The adjustment exchange rate amount or relational adjustment exchange rate amount will be used to update all open bank, receivables, or payables transactions.

> [!Note]
> The actual currency rate will be calculated using this formula:
>
> `Currency Amount = Amount / Adjustment Exch. Rate Amount * Relational Adjmt Exch. Rate Amt`

## Úprava směnných kurzů

Vzhledem k tomu, že směnné kurzy neustále kolísají, musí být pravidelně upravovány další měnové ekvivalenty ve vašem systému. Pokud tyto úpravy nejsou provedeny, částky, které byly převedeny ze zahraničních (nebo dodatečných) měn a zaúčtovány do hlavní knihy v lokální měně, mohou být zavádějící. Kromě toho musí být denní položky zaúčtované před vstupem denního směnného kurzu do aplikace aktualizovány po zadání denních informací o směnném kurzu.

The **Adjust Exchange Rates** batch job is used to manually adjust the exchange rates of posted customer, vendor, and bank account entries. Může také aktualizovat další částky měny vykazování u položek hlavní knihy.

> [!TIP]
> You can use a service to update exchange rates in the system automatically. Další informace naleznete v části [Nastavení služby směnného kurzu](finance-how-update-currencies.md#to-set-up-a-currency-exchange-rate-service). However, this does not adjust exchange rates on already posted transactions. To update exchange rates on posted entries, use the **Adjust Exchange Rates** batch job.

You can preview the effect that an adjustment will have on posting before you actually post by choosing **Preview** on the **Adjust Exchange Rates** page. Additionally, you can select whether the general ledger posting will be detailed (per entry) or summarized (per currency) by choosing **Summarize Entries**. You can also specify how to handle dimensions for unrealized gains and losses postings by choosing one of the following options in the **Transfer Dimension Values** field:

- **Source Entry**: G/L entries for unrealized gains and losses will have dimensions values transferred from the adjusted entry.
- **By G/L Account**: G/L entries for unrealized gains and losses will have dimensions values transferred from the unrealized gains and losses G/L account's dimension settings source entry.
- **No Transfer**: G/L entries for unrealized gains and losses won't have dimensions values.

### Effect on Customers and Vendors

For customer and vendor accounts, the batch job adjusts the currency by using the exchange rate that is valid on the posting date that is specified in the batch job. The batch job calculates the differences for the individual currency balances and posts the amounts to the general ledger account that is specified in the **Unrealized Gains Acc.** field or the **Unrealized Losses Acc.** field on the **Currencies** page. Balancing entries are automatically posted to the receivables/payables account in the general ledger.

The batch job processes all open customer ledger entries and vendor ledger entries. If there is an exchange rate difference for an entry, the batch job creates a new detailed customer or vendor ledger entry, which reflects the adjusted amount on the customer or vendor ledger entry.

#### Dimensions on Customer and Vendor Ledger Entries

The adjustment entries are assigned the dimensions from the customer/vendor ledger entries, and the adjustments are posted per combination of dimension values.

### Effect on Bank Accounts

For bank accounts, the batch job adjusts the currency by using the exchange rate that is valid on the posting date specified in the batch job. The batch job calculates the differences for each bank account that has a currency code and posts the amounts to the general ledger account that is specified in the **Realized Gains Acc.** field or the **Realized Losses Acc.** field on the **Currencies** page. Balancing entries are automatically posted to the general ledger bank accounts that are specified in the bank account posting groups. The batch job calculates one entry per currency per posting group.

#### Dimensions on Bank Account Entries

The adjustment entries for the bank account's general ledger account and for the gain/loss account are assigned the bank account's default dimensions.

### Effect on G/L Accounts
If you post in an additional reporting currency, you can have the batch job create new general ledger entries for currency adjustments between LCY and the additional reporting currency. The batch job calculates the differences for each general ledger entry and adjusts the general ledger entry depending on the contents of the **Exchange Rate Adjustment** field for each general ledger account.

##### Dimensions on G/L Account Entries
The adjustment entries are assigned the default dimensions from the accounts they are posted to.

> [!Important]
> Before you can use the batch job, you must enter the adjustment exchange rates that are used to adjust the foreign currency balances. You do so on the **Currency Exchange Rates** page.<br><br>

> [!Video https://www.microsoft.com/videoplayer/embed/RE3Q24s?rel=0]

## To set up a currency exchange rate service
You can use an external service to keep your currency exchange rates up to date, such as FloatRates.

> [!NOTE]
> Most exchange rate services provide data that is compatible with the import process in [!INCLUDE[prod_short](includes/prod_short.md)]. However, sometimes the data is formatted differently and you will need to customize your import process. You can use the data exchange framework to do that by adding your own codeunit. You'll probably need some help from a developer to do that. For more information, see [Set Up Data Exchange Definitions](across-how-to-set-up-data-exchange-definitions.md).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Currency Exchange Rate Services**, and then choose the related link.
2. Vyberte akci **Nový**.
3. On the **Currency Exchange Rate Service** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Turn on the **Enabled** toggle to enable the service.

> [!NOTE]
> The following video shows an example of how to connect to a currency exchange rate service, using the European Central Bank as an example. In the segment that describes how to set up field mappings, the setting in the **Source** column for the **Parent Node for Currency Code**  will only return the first currency found. The setting should be `/gesmes:Envelope/Code/Code/Code`.

<br><br>

> [!Video https://www.microsoft.com/en-us/videoplayer/embed/RE4A1jy?rel=0]

## To update currency exchange rates through a service
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Currencies**, and then choose the related link.
2. Choose the **Update Exchange Rates** action.

The value in the **Exchange Rate** field on the **Currencies** page is updated with the latest currency exchange rate.

## Podívejte se na související školení na webu [Microsoft Learn](/learn/paths/use-multiple-currencies-dynamics-365-business-central/)

## Viz také

[Currencies in Business Central](finance-currencies.md)  
[Set Up Currencies](finance-set-up-currencies.md)  
[Set Up an Additional Reporting Currency](finance-how-setup-additional-currencies.md)  
[Closing Years and Periods](year-close-years-periods.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
