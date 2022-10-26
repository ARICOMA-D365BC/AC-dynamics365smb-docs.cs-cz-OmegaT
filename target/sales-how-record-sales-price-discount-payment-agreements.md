---
title: Record Special Sales Prices and Discounts
description: Describes how to define pricing and discount agreements for sales documents.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: special price, alternate price, pricing
ms.date: 06/03/2022
ms.author: bholtorf

---

# Záznam speciálních prodejních cen a slev

> [!NOTE]
> 2020 release wave 2 introduced new, streamlined processes for setting up and managing prices and discounts. If you're a new customer using the latest version, you're using the new experience. If you're an existing customer, whether you are using the new experience depends on whether your administrator has enabled the **New sales pricing experience** feature update in **Feature Management**. Další informace naleznete v tématu [Povolení nadcházejících funkcí s předstihem](/dynamics365/business-central/dev-itpro/administration/feature-management).

[!INCLUDE[prod_short](includes/prod_short.md)] supports various pricing strategies, such as:

* One-price-fits-all models where an item is always sold at the same price.
* Special price agreements with specific customers, or groups of customers.
* Campaigns when a sale meets criteria for a special offer. For example, criteria might be when an order meets a minimum quantity, is before a certain date, or includes a certain type of item.

To use a basic pricing model, you only need to specify a unit price when you set up an item or resource. That price will always be used on sales documents. For more advanced models, for example, when you want to offer special prices for a sales campaign, you can specify criteria on the **Sales Prices** page. You can offer special prices based on a combination of the following information:

* Zákazník
* Zboží
* Unit of measure
* Minimum quantity
* Dates that define the period for which the prices are valid.

After you set up special prices, [!INCLUDE[prod_short](includes/prod_short.md)] can calculate best prices on sales and purchase documents, and on job and item journal lines. Pro více informací navštivte [Výpočet nejlepší ceny](sales-how-record-sales-price-discount-payment-agreements.md#best-price-calculation).

For sales discounts, you can set up two types:

| Typ slevy | Popis |
| --- | --- |
| **Sales Line Discount** | An amount inserted on sales lines if they contain a certain combination of customer, item, minimum quantity, unit of measure, or starting/ending date. This type works in the same way as for sales prices. |
| **Fakturační sleva** | A discount percentage that is subtracted from the sales document total if the sum of all lines on the document exceeds a certain minimum. |

> [!TIP]  
> Pokud by zboží nemělo být nikdy prodáváno se slevou, ponechte pole pro slevu na stránce položky prázdné a nezařazujte zboží do žádných nastavení řádkových slev.

## To set up a sales price for a customer

Tyto kroky se liší podle toho, zda správce zapnul aktualizaci funkce **Nové prodejní ceny**. If the feature update isn't turned on, follow the steps on the Current Experience tab.

#### [Aktuální zkušenosti](#tab/current-experience/)

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Zákazníci** a poté vyberte související odkaz.
2. Vyberte zákazníka a poté vyberte akci **Ceny**.
3. Vyplňte pole na řádku podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Vyplňte řádek pro každou kombinaci, která zákazníkovi poskytne speciální prodejní cenu.

#### [Po novu](#tab/new-experience/)

By default, the status of new price lists is Draft. Draft price lists aren't included in price calculations. When you're done adding lines and want to start using the prices, change the status to Active.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Zákazníci** a poté vyberte související odkaz.
2. Vyberte zákazníka a poté zvolte akci **Prodejní ceníky**.
3. Chcete-li vytvořit nový prodejní ceník, zvolte **Nový**.
4. Na záložkáck **Obecné** a **Daň** vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
5. To add items to the list, do one of the following steps:
   * Chcete-li přidat více položek, vyberte možnost **Navrhnout řádky** a poté zadejte kritéria filtru, abyste určili typy položek, které chcete přidat. Optionally, you can enter other settings for the items that are specific to the price list. You can change these settings later, if needed.
   * Chcete-li zkopírovat položky z jiného ceníku, zvolte **Kopírovat řádky** a poté vyberte ceník, který chcete zkopírovat.
   * To add items manually, in the grid, in the **Product Type** field, choose the type of product that the price list is for. V závislosti na výběru vyplňte zbývající pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
6. Chcete-li ceník začít používat, vyberte v poli **Stav** možnost **Aktivní**.

---

## Using Sales and Purchase Price Lists
> [!NOTE]
> Using price lists requires that your administrator has enabled the **New sales pricing experience** feature update in **Feature Management**. Další informace naleznete v tématu [Povolení nadcházejících funkcí s předstihem](/dynamics365/business-central/dev-itpro/administration/feature-management).

Most of the new sales pricing experience is similar to the current experience, but there are a few differences. Those differences are described in the following sections.

The **Applies-to Type** and **Applies-to No.** fields let you choose what a price list will apply to, such as customer or customer price group. Using **View Columns for**, you can show or hide columns relevant for setting prices, discounts, or prices and discounts.

### Converting Existing Prices When You Turn On the Pricing Feature Update
When you enable the **New sales pricing experience** feature update on the **Feature Management** page, the **Feature Data Update** guide opens. Use the **Use default prices** toggle as follows:

* If you want to work with all prices on a single page, turn it on. Existing prices will be converted to one default price list for each of the following documents:

   * Prodej
   * Purchases
   * Job sales
   * Job purchases

   You can edit all prices for these areas on the **Prices Worksheet** page. The default prices lists will be set on the **Sales & Receivables Setup**, **Purchases & Payables Setup,** and **Jobs Setup** pages.

> [!NOTE]
> If prices are set only on item or resource cards, default price lists will not be filled in with those prices during feature data update. However, you can open any of default price lists or the Price Worksheet page and use the **Suggest Lines** action to add the prices set on item or resource cards.

* To use sales price lists, turn it off. Existing prices will be converted to a new price list for each combination of the following things:

* Zákazník
* Customer group or campaign
* Starting and ending dates
* Měny

If you have many combinations, you'll have many price lists.

If you've already enabled the New Pricing Experience, you can create default price lists manually or specify an existing price list as the default. To set an existing price list as default, turn on the **Allow Updating Defaults** toggle on the price list. Then, on the **Sales & Receivables Setup**, **Purchase & Payables** or **Jobs Setup** pages, set the price list as the default.

### Editing Active Price Lists
To allow people to edit prices on active price lists for items, resources, customers, vendors, or other entities that use pricing, turn on the **Allow Editing Active Price** toggle on the **Sales & Receivables Setup** and **Purchase & Payables Setup** pages.

When the **Allow Editing Active Price** toggle is turned off, to update prices in a price list you must change the status of the price list to **Draft**, make your change, and then reactivate the price list.

The **Prices Overview** page provides an overview of all prices across price lists. You can set filters to narrow down the list of prices you may want to modify or add to. After you modify prices, you must use the **Verify Lines** action to verify the prices against other price list lines. Verifying prices helps avoid duplicates and ambiguity during price calculation.

> [!NOTE]
> When you edit a line in an active price list the status of the line becomes Draft, and the line will not be considered during price calculation until you use the **Verify lines** action. After you verify the price the line's status becomes Active and it will be considered in price calculations.

To add new prices, on the **Prices Overview** page, use the **Add New Lines** action. The **Prices Worksheet** page opens, and you can add price lines either by suggesting them based on criteria, copying them from other price lists, or manually entering them. Afterward, you can use the **Implement Price Change** action to compare the new prices with other price lists to avoid duplicates and ambiguity during price calculation.

## Kopírování prodejních cen
Tyto kroky se liší podle toho, zda správce zapnul aktualizaci funkce **Nové prodejní ceny**. If the feature update isn't turned on, follow the steps on the Current Experience tab.

#### [Aktuální zkušenosti](#tab/current-experience/)

Chcete-li kopírovat prodejní ceny, například prodejní ceny jednotlivých zákazníků, které chcete použít pro cenovou skupinu zákazníka, je nutné spustit dávkovou úlohu **Navrhnout cenu z ceny** v sešitu **Sešit prodejní ceny**.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat<"), zvolte **Sešit prodejní ceny** a poté vyberte související odkaz.
2. Vyberte akci **Navrhnout cenu z ceny**.
3. V záložce **Prodejní ceny** vyplňte pole **Typ prodeje** a **Kód prodeje** původními prodejními cenami, které chcete zkopírovat.
4. V horní části stránky požadavku vyplňte pole **Typ prodeje** a **Kód prodeje** typem a názvem, do které chcete zkopírovat prodejní ceny.
5. Pokud chcete, aby dávková úloha vytvářela nové ceny, zaškrtněte políčko **Vytvořit nové ceny**.
6. Choose the **OK** button to fill in the lines on the **Sales Price Worksheet** page with the suggested new prices, indicating that they're valid for the selected sales type.

   > [!NOTE]  
   > Tato dávková úloha vytváří pouze návrhy a neimplementuje navrhované změny. Pokud jste s návrhy spokojeni a chcete je implementovat, to znamená vložit je na stránku **Prodejní ceny**, zvolte akci **Provést změnu ceny** na stránce **Sešit prodejní ceny**.

#### [Po novu](#tab/new-experience/)
You can specify whether the new price list will use the settings from the header on the list you're copying, or the settings from the new list you're copying to. To use the settings from the price list you're copying prices to, turn on the **Use defaults from target** toggle.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat<"), zvolte **Sešit prodejní ceny** a poté vyberte související odkaz.
2. Vyberte ceník, který chcete zkopírovat, a poté zvolte **Kopírovat řádky**.
3. Vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

   > [!NOTE]
   > You can't have two items that have the same settings but different prices. If that happens, a message will display when you activate the price list. Cenu, kterou chcete použít, můžete zvolit otevřením seznamu a odstraněním nesprávné ceny.

---

## Hromadná aktualizace cen zboží
Tyto kroky se liší podle toho, zda správce zapnul aktualizaci funkce **Nové prodejní ceny**. If the feature update isn't turned on, follow the steps on the Current Experience tab.

#### [Aktuální zkušenosti](#tab/current-experience/)

To bulk update item prices, such as increase all prices by a percentage, you can fill in the Sales Price Worksheet page by using the following batch jobs:

* **Suggest Sales Price on Wksh.** suggests changes in one of two ways. Either by applying an adjustment factor to existing sales prices, or by copying existing sales price agreements to other customers, customer price groups, or sales campaigns.
* **Suggest Item Price on Wksh.** suggests changes in one of two ways. Either by applying an adjustment factor to existing unit prices on item cards, or by suggesting prices for new combinations of currency, units of measure, and so on. The unit prices on items aren't changed by this batch job.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat<"), zvolte **Sešit prodejní ceny** a poté vyberte související odkaz.
2. Zvolte akci **Navrhnout cenu zboží**.
3. V záložce **Zboží** vyplňte pole **Číslo** nebo **Účto skupina zboží** nebo jiná pole s původními cenami zboží, které chcete aktualizovat.
4. V horní části stránky požadavku vyplňte **Typ prodeje** a **Kód prodeje** typem a názvem, do kterého chcete prodejní ceny zkopírovat.
5. If you want the batch job to automatically adjust suggested item prices, enter the adjustment in **Adjustment Factor** field. Například pokud zadáte 1,15 do **faktoru úpravy** pro 15% zvýšení ceny zboží.
6. If you want the batch job to create new prices, turn on the **Create New Prices** toggle.
7. Choose the **OK** button to fill in the lines on the **Sales Price Worksheet** page with the suggested new prices.
8. To implement the suggestions, use the **Implement Price Changes** action. The batch job creates suggestions but doesn't implement them.

#### [Po novu](#tab/new-experience/)

Chcete-li aktualizovat ceny pro více položek, je nutné vytvořit nový ceník a potom zkopírovat řádky z existujícího ceníku. Při kopírování řádků můžete pomocí filtrů určit, co se má kopírovat, a v poli **Faktor úpravy** můžete zadat celé číslo nebo desetinné číslo pro zvýšení nebo snížení cen. Ceník musí být ve stavu **Koncept.**. V případě potřeby můžete starý ceník deaktivovat.

> [!NOTE]
> You can't have two lines that have the same settings but different prices. Pokud k tomu dojde, zobrazí se při aktivaci ceníku zpráva. Cenu, kterou chcete použít, můžete zvolit otevřením seznamu a odstraněním nesprávné ceny.

---

## Best Price Calculation

After you record special prices and line discounts for sales and purchases, [!INCLUDE[prod_short](includes/prod_short.md)] calculates the best price on sales and purchase documents, and on job and item journal lines.

The best price is the lowest price with the highest line discount allowed on a given date. [!INCLUDE[prod_short](includes/prod_short.md)] calculates best prices when it adds unit prices and the line discount percentages on document and journal lines.

> [!NOTE]  
> The following describes how the best price is calculated for sales. For purchases, the calculation is similar but is based on the available parameters. For example, item discount groups are not supported for purchasing.

1. [!INCLUDE[prod_short](includes/prod_short.md)] checks the combination of the bill-to customer and the item and then calculates the applicable unit price and line discount percentage, using the following criteria:

   * Does the customer have a price/discount agreement, or does the customer belong to a group that does?
   * Is the item or the item discount group on the line included in any of these price/discount agreements?
   * Is the order date (or the posting date for the invoice and credit memo) within the starting and ending date of the price/discount agreement?
   * Is a unit of measure code specified? If so, [!INCLUDE[prod_short](includes/prod_short.md)] checks for prices/discounts with the same unit of measure code, and prices/discounts with no unit of measure code.

2. [!INCLUDE[prod_short](includes/prod_short.md)] checks whether any price/discount agreements apply to information on the document or journal line. It then inserts the applicable unit price and line discount percentage using the following criteria:

   * Is there a minimum quantity requirement in the price/discount agreement that is fulfilled?
   * Is there a currency requirement in the price/discount agreement that is fulfilled? If so, the lowest price and the highest line discount for that currency are inserted, even if local currency would provide a better price. If there's no price/discount agreement for the specified currency code, [!INCLUDE[prod_short](includes/prod_short.md)] inserts the lowest price and the highest line discount in your local currency.

If no special price can be calculated for the item on the line, then either the last direct cost or the unit price from the item card is inserted.

## Sales Invoice Discounts and Service Charges

When you use invoice discounts, the total amount on the invoice determines the size of the discount that is granted. On the **Cust. Invoice Discounts** page, you can also add a service charge to invoices over a certain amount.

Before you can use invoice discounts with sales, you must specify certain information. You must make the following decisions:

* Which customers will be granted this type of discount?
* Which discount percentages you'll use?

If you want invoice discounts to be calculated automatically, on the **Sales & Receivables Setup** page, turn on the **Calc Inv. Discount** toggle.

You can specify whether you'll grant invoice discounts when an invoice meets certain criteria for each customer. For example, when the invoice amount is large enough. Invoice discounts can be in local currency for domestic customers, or in foreign currency for foreign customers.

You link discount percentages to specific invoice amounts on the **Cust. Invoice Discounts** page for each customer. You can enter any number of percentages. Každý zákazník může mít svou vlastní stránku nebo můžete propojit několik zákazníků se stejnou stránkou.

In addition to, or instead of, a discount percentage, you can link a service charge amount to a specific invoice amount.

> [!TIP]  
> Before you enter this information, it is a good idea to prepare an outline of the discount structure that you want to use. This makes it easier to see which customers can be linked to the same invoice discount page. The fewer pages you have to set up, the faster you can enter the basic information.

For training in discounts in sales, see [Set up discounts for your customers](/learn/modules/customer-discounts-dynamics-365-business-central/index) at Microsoft Learn.

### Calculating Invoice Discounts on Sales

[!INCLUDE [sales-invoice-discounts](includes/sales-invoice-discounts.md)]

## Nastavení slevy na prodejní řádek pro zákazníka
Tyto kroky se liší podle toho, zda správce zapnul aktualizaci funkce **Nové prodejní ceny**. If the feature update isn't turned on, follow the steps on the Current Experience tab.

#### [Aktuální zkušenosti](#tab/current-experience/)

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Zákazníci** a poté vyberte související odkaz.
2. Otevřete příslušnou kartu zákazníka a poté zvolte akci **Řádkové slevy**.
3. Vyplňte pole na řádku podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Vyplňte řádek pro každou kombinaci, která zákazníkovi poskytne slevu na prodejní řádek.

> [!NOTE]
> When you open the **Sales Prices** and **Sales Line Discounts** pages from a specific customer, the **Sales Type Filter** and **Sales Code Filter** fields are set for the customer and can't be changed or removed.
>
> Chcete-li nastavit ceny nebo řádkové slevy pro všechny zákazníky, cenovou skupinu zákazníků nebo kampaň, musíte otevřít stránky z karty položky. Alternativně můžete pro prodejní ceny použít stránku **Sešit prodejní ceny**. Další informace naleznete v tématu [Hromadná aktualizace cen zboží](sales-how-record-sales-price-discount-payment-agreements.md#to-bulk-update-item-prices).

#### [Po novu](#tab/new-experience/)

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Zákazníci** a poté vyberte související odkaz.
2. Vyberte zákazníka a poté zvolte akci **Prodejní ceníky**.
3. Otevřete ceník, pro který chcete zadat řádkovou slevu.
4. Vytvořte nový řádek nebo vyberte existující řádek a vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
5. V poli **Definování** zvolte buď **Cena a sleva**, nebo pouze **Sleva**.
6. V poli **Řádková sleva %** zadejte procento slevy.

   > [!TIP]
   > Pokud upravujete existující řádek, můžete filtrovat řádky výběrem příslušné možnosti v poli **Zobrazit sloupce pro**.

   > [!NOTE]  
   > Kódy fakturačních slev jsou reprezentovány existujícími zákaznickými kartami. To vám umožní rychle přiřadit podmínky fakturační slevy zákazníkům výběrem jména jiného zákazníka, který bude mít stejné podmínky. To set up customer-specific invoice discount terms, set the **Invoice Disc. Code** field to the customer's customer code, and then proceed to the next step.

---

## Nastavení fakturační slevy pro zýkazníka
After you decide which customers are eligible for invoice discounts, enter the invoice discount code on the Customer Card pages. Then set up the terms for each code.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Zákazníci** a poté vyberte související odkaz.
2. Otevřete stránku zákazníka pro zákazníka, který bude mít nárok na fakturační slevy.
3. Do pole **Kód fakturační slevy** vyberte kód pro příslušné podmínky fakturační slevy, které se mají použít k výpočtu fakturních slev pro zákazníka. <!--Looks like I can only choose customers in this list-->

> [!NOTE]  
> Kódy fakturačních slev jsou reprezentovány existujícími zákaznickými kartami. To vám umožní rychle přiřadit podmínky fakturační slevy zákazníkům výběrem jména jiného zákazníka, který bude mít stejné podmínky.

Pokračujte nastavením nových podmínek slevy prodejní faktury.

1. Na stránce **Zákazníci** zvolte akci **Fakturační slevy** . Stránka **Fakturační slevy zákazníka** se otevře.
2. Do pole **Kód měny** zadejte kód měny, na kterou se vztahují podmínky slevy na faktuře na řádku. Chcete-li nastavit podmínky fakturační slevy v USD, ponechte pole prázdné.
3. Do pole **Minimální částka** zadejte minimální částku, kterou musí mít faktura nárok na slevu.
4. Do pole **Procento slevy** zadejte fakturační slevu jako procento částky faktury.
5. Opakujte kroky 5 až 7 pro každou měnu, pro kterou zákazník obdrží jinou fakturační slevu.

## Podívejte se na související školení na webu [Microsoft Learn](/learn/modules/manage-sales-prices-dynamics-365-business-central/index)

## Viz také

[Setting Up Sales](sales-setup-sales.md)  
[Sales](sales-manage-sales.md)  
[Setting Up Customer Price Groups](sales-how-to-set-up-customer-price-groups.md)  
[Setting Up Customer Discount Groups](sales-how-to-set-up-customer-discount-groups.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]