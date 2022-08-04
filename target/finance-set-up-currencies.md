---
title: Set Up Currencies
description: You must set up each currency if you buy or sell in currencies other than your local currency (LCY), or if you record G/L transactions in different currencies.
author: edupont04

ms.topic: conceptual
ms.search.keywords: multiple currencies
ms.search.form: 5, 118
ms.date: 03/15/2022
ms.author: edupont
---
# Nastavit měny

[!INCLUDE [finance-currencies-def](includes/finance-currencies-def.md)]

Pomocí externí služby můžete získat nejnovější směnné kurzy měn do seznamu **Měny**. Další informace naleznete v části [Nastavení služby směnného kurzu](finance-how-update-currencies.md#to-set-up-a-currency-exchange-rate-service).

[!INCLUDE [finance-currencies-lcy](includes/finance-currencies-lcy-note.md)]

## Měny

Následující tabulka popisuje pole v seznamu **Měny**.

| Pole | Popis |
|---------------------------------|---------------------------------------|  
| Kód | Identifikátor měny. |
| **Popis** | Volný textový popis měny. |
| **Kód ISO** | Mezinárodní třípísmenný kód měny definovaný v ISO 4217. |
| **Číselný kód ISO** | Mezinárodní číselný odkaz na měnu definovanou v ISO 4217. |
| **Datum směnného kurzu** | Poslední aktuální datum směnného kurzu. |
| **HMU Měna** | Určuje, zda je měnou HMU (Hospodářská a měnová unie), například EUR. |
| **Účet realizovaných zisků** | Účet, na kterém bude skutečný zisk zaúčtován při přijímání plateb za pohledávky nebo při registraci skutečného měnového kurzu plateb závazkům. Příklad měnové transakce pohledávky naleznete v příkladu pod touto tabulkou. |
| **Účet realizovaných ztrát** | Účet, na kterém bude zaúčtována skutečná ztráta, když obdržíte platby za pohledávky nebo zaregistrujete skutečný kurz měny u plateb závazků. Příklad měnové transakce pohledávky naleznete v příkladu pod touto tabulkou. |
| **Účet nerealizovaných zisků** | Účet, na kterém bude teoretický zisk zaúčtován při provádění měnové úpravy. |
| **Účet nerealizovaných ztrát** | Účet, na kterém bude zaúčtována teoretická ztráta, když provedete úpravu měny. |
| **Přesnost zaokrouhlení částky** | Některé měny mají pro fakturované částky jiné formáty, než jsou definovány na stránce **Nastavení hlavní knihy**. Pokud změníte přesnost zaokrouhlení částky pro měnu, všechny fakturované částky v této měně budou zaokrouhleny s aktualizovanou přesností. |
| **Desetinná místa v částce** | Některé měny mají pro fakturované částky jiné formáty, než jsou definovány na stránce **Nastavení hlavní knihy**. Pokud změníte částku desetinných míst pro měnu, všechny fakturované částky v měně budou zaokrouhleny aktualizovanými desetinnými místy |
| **Typ zaokrouhlení faktury** | Určuje metodu, která se má použít, pokud musí být částky zaokrouhleny. Možnosti jsou **Nejbližší**, **Nahoru**a **Dolů**. |
| **Přesnost zaokrouhlení jednotkové částky** | Některé měny mají jiné formáty pro jednotkové částky, než jsou definovány na stránce **Nastavení hlavní knihy**. pokud změníte přesnost zaokrouhlení jednotkové částky pro měnu, všechny jednotkové částky v měně budou zaokrouhleny s aktualizovanou přesností. |
| **Desetinná místa v jednotkách** | Některé měny mají jiné formáty pro jednotkové částky, než jsou definovány na stránce **Nastavení hlavní knihy**. Pokud pro měnu změníte desetinná místa částky jednotky, všechny částky jednotky v měně budou zaokrouhleny na aktualizovaná desetinná místa. |
| **Přesnost zaokrouhlení aplikace** | Určuje velikost intervalu, který je povolen jako rozdíl zaokrouhlení při vzájemném použití položek v různých měnách. |
| **Zaokrouhlení převodu LCY. Debetní účet** | Určuje informace o převodu, které musí také obsahovat debetní účet, pokud chcete vložit opravné řádky pro zaokrouhlení rozdílů ve finančních denících pomocí příkazu ** Vložit konv. LCY Rndg. zakázky**. |
| **Konverze LCY Zaokrouhlovací kreditní účet** | Určuje informace o převodu, které musí také obsahovat debetní účet, pokud chcete vložit opravné řádky pro zaokrouhlení rozdílů ve finančních denících pomocí příkazu ** Vložit konv. LCY Rndg. zakázky**. |
| **Poslední datum úpravy** | Datum poslední měnové úpravy. |
| **Datum poslední změny** | Datum změny nastavení měny. |
| **Tolerance platby %** | Maximální tolerance platby % nastavená pro tuto měnu. Další informace naleznete v tématu [ Tolerance platby a Tolerance platební slevy](finance-payment-tolerance-and-payment-discount-tolerance.md). |
| **Max. Částka tolerance platby** | Maximální částka tolerance platby nastavená pro tuto měnu. Další informace naleznete v tématu [ Tolerance platby a Tolerance platební slevy](finance-payment-tolerance-and-payment-discount-tolerance.md). |
| **Měnový faktor** | Určuje vztah mezi měnou a místní měnou pomocí skutečného kurzu měny. |
| **Účet realizovaných zisků hk** | Určuje finanční účet, který se používá k zaúčtování kurzových zisků pro měnové úpravy mezi místní měnou (LCY) a další měnou vykazování. The exchange rate gains are calculated when the Adjust Exchange Rates batch job is run to adjust general ledger accounts. This field might not be visible by default. It can be retrieved by personalizing the page. |
| **Realized G/L Losses Account** | Specifies the G/L account that is used to post exchange rate losses for currency adjustments between the local currency (LCY) and the additional reporting currency. The exchange rate gains are calculated when the Adjust Exchange Rates batch job is run to adjust general ledger accounts. This field might not be visible by default. It can be retrieved by personalizing the page. |
| **Residual Gains Account** | Specifies the G/L account that is used to post residual gain amounts (rounding differences) when an additional reporting currency is used in the general ledger application area. This field might not be visible by default. It can be retrieved by personalizing the page. |
| **Residual Losses Account** | Specifies the G/L account that is used to post residual loss amounts (rounding differences) when an additional reporting currency is used in the general ledger application area. This field might not be visible by default. It can be retrieved by personalizing the page. |
| **Max. VAT Difference Allowed** | The maximum amount allowed for VAT differences in this currency. For more information, see [Correcting VAT Amounts Manually in Sales and Purchase Documents](finance-work-with-vat.md#correcting-vat-amounts-manually-in-sales-and-purchase-documents). This field might not be visible by default. It can be retrieved by personalizing the page. |
| **VAT Rounding Type** | Specifies the rounding method for correcting VAT amounts manually in sales and purchase documents. This field might not be visible by default. It can be retrieved by personalizing the page. |

### Available currency functions

The following table outlines key actions on the **Currencies** page.

| Menu | Akce | Popis |
|-------------|--------------|------------------------------|
| **Process** | **Suggest Accounts** | Use accounts from the other currencies. The most frequently used accounts will be inserted. |
|  | **Change Payment Tolerance** | Change either or both the maximum payment tolerance and the payment tolerance percentage, and filter by currency. For more information, see [Payment Tolerance and Payment Discount Tolerance](finance-payment-tolerance-and-payment-discount-tolerance.md) |
|  | **Exchange Rates** | View updated exchange rates for the currencies that you use. |
|  | **Adjust Exchange Rates** | Adjust general ledger, customer, vendor, and bank account entries to reflect a more updated balance if the exchange rate has changed since the entries were posted. |
|  | **Exchange Rate Adjustment Register** | View the results of running the **Adjust Exchange Rates** batch job. One line is created for each currency or each combination of currency and posting group that is included in the adjustment. |
| **Exchange Rate Service** | **Exchange Rate Services** | View or edit the setup of the services that are set up to fetch updated currency exchange rates when you choose the **Update Exchange Rates** action. |
|  | **Update Exchange Rates** | Get the latest currency exchange rates from a service provider. |
| **Reports** | **Foreign Currency Balance** | View the balances for all customers and vendors in both foreign currencies and in local currency (LCY). The report displays two LCY balances. One is the foreign currency balance converted to LCY by using the exchange rate at the time of the transaction. The other is the foreign currency balance converted to LCY by using the exchange rate of the work date. |

## LCY and other currencies

[!INCLUDE [finance-currencies-lcy-def](includes/finance-currencies-lcy-def.md)]

## Rounding currencies

To manage currencies that do not use decimals and to avoid unnecessary decimals in foreign currency, you can use two different rounding features:

- Unit-amount rounding

- Amount rounding

These features can operate independently or in combination. In addition, the features can operate in connection with invoice rounding.

As opposed to the invoice rounding features, the amount rounding and unit-amount rounding features affect only amounts in foreign currency-not the corresponding amounts in LCY. These two features will not result in any postings to general ledger accounts. Consequently, no general ledger account needs to be specified on posting groups or elsewhere.

### Unit-amount rounding

The unit-amount rounding feature controls how sales prices for items and resources in foreign currencies are rounded on sales and purchase lines. You must specify the rules for each currency separately, in the **Unit-Amount Rounding Precision** field in the **Currencies** list.

The unit-amount rounding feature is used automatically every time you enter an item or resource number on a sales line. If the invoice is for a customer with a currency code, the item or resource price is converted into the customer's currency. The price is rounded according to the unit-amount rounding precision for the currency.

### Amount rounding

The amount rounding feature controls how amounts in foreign currencies are rounded on general journal lines, sales lines, and purchase lines. You must specify the rules for each currency separately, in the **Amount Rounding Precision** field in the **Currencies** list.

Amounts in foreign currencies are rounded when you fill in and post general journal lines, sales lines, and purchase lines.

## Exchange rates

You can register exchange rates for each foreign currency and specify from which dates the exchange rates are valid. For example, you can enter daily exchange rates, monthly exchange rates, or quarterly exchange rates for each foreign currency.

You can retain historical exchange rates in the **Currency Exchange Rates** page for reference purposes. When you need to update exchange rates, you can use the **Update Exchange Rates** button to get the latest exchange rates from an external service provider.

## General ledger accounts

You cannot link currency codes to general ledger accounts because amounts on general ledger accounts are in LCY. If you have a bank loan in USD and place deposits in a bank account in SEK, you can keep track of these accounts by setting up bank accounts in USD and SEK. With posting groups, you can link the accounts to the relevant general ledger accounts. In the general ledger, the value of the amounts is shown in LCY.

You can enter a currency code on a general journal line and post the line to a general ledger account. The relevant exchange rate is used to convert the amount to LCY before it is posted to the general ledger account.

## Příklad měnové transakce pohledávky

[!INCLUDE [finance-currencies-example](includes/finance-currencies-example.md)]

## Viz také

[Update Currency Exchange Rates](finance-how-update-currencies.md)  
[Set Up an Additional Reporting Currency](finance-how-setup-additional-currencies.md)
