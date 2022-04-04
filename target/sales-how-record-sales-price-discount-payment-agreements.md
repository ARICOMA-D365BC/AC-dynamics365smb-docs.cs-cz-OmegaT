---
title: Set Up Sales Prices and Discounts for Customers | Microsoft Docs
description: Describes how to set up and apply pricing and discount agreements for sales documents.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: special price, alternate price, pricing
ms.search.form: 1345, 7002, 7007, 7015, 7016, 7023
ms.date: 04/01/2021
ms.author: bholtorf

---
# Record Sales Prices and Discounts
> [!NOTE]
> In 2020 release wave 2 we released streamlined processes for setting up and managing prices and discounts. Pokud jste nový zákazník a používáte tuto verzi, používáte nové prostředí. If you're an existing customer, whether you are using the new experience depends on whether your administrator has enabled the **New sales pricing experience** feature update in **Feature Management**. Další informace naleznete v tématu [Povolení nadcházejících funkcí s předstihem](/dynamics365/business-central/dev-itpro/administration/feature-management).

[!INCLUDE[prod_short](includes/prod_short.md)] supports various pricing strategies, ranging from one-price-fits-all models where an item is always sold at the same price, to special price agreements with specific customers, groups of customers, or special offers when you're running a sales campaign. For example, you might offer a special price on a sales order under the following conditions:

* When it's for a minimum quantity
* It's for a certain type of item
* If it's created during a specific period of time

To use a basic pricing model, you only need to specify a unit price for an item or resource. That price will always be used on sales documents. For more advanced models, for example, when you are running a sales campaign and want to offer special prices, you can specify criteria for that on the **Sales Prices** page. You can offer special prices based on combinations of the following:

* Zákazník
* Zboží
* Unit of measure
* Minimum quantity
* Date ranges that define when the prices are valid

Additionally, after you set up special prices, [!INCLUDE[prod_short](includes/prod_short.md)] can automatically calculate the best price on sales and purchase documents and on job and item journal lines. Pro více informací navštivte [Výpočet nejlepší ceny](sales-how-record-sales-price-discount-payment-agreements.md#best-price-calculation).

For sales discounts, you can set up and use the following types:

| Typ slevy | Popis |
| --- | --- |
| **Sales Line Discount** | An amount that is used on sales lines if a certain combination of customer, item, minimum quantity, unit of measure, or starting and ending dates exists. These combinations work in the same way as for sales prices. |
| **Fakturační sleva** | A discount percentage that is subtracted from the sales document total if the sum of all lines on the document exceeds a certain minimum. |

> [!TIP]  
> Pokud by zboží nemělo být nikdy prodáváno se slevou, ponechte pole pro slevu na stránce položky prázdné a nezařazujte zboží do žádných nastavení řádkových slev.

## To set up a sales price for a customer

Tyto kroky se liší podle toho, zda správce zapnul aktualizaci funkce **Nové prodejní ceny**. If the feature update is not turned on, follow the steps on the Current Experience tab.

## [Aktuální zkušenosti](#tab/current-experience)

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Zákazníci** a poté vyberte související odkaz.
2. Vyberte zákazníka a poté vyberte akci **Ceny**.
3. Vyplňte pole na řádku podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Vyplňte řádek pro každou kombinaci, která zákazníkovi poskytne speciální prodejní cenu.

## [Po novu](#tab/new-experience)
By default, the status of new price lists is Draft. Draft price lists are not included in price calculations. When you're done adding lines and want to start using the prices, change the status to Active.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Zákazníci** a poté vyberte související odkaz.
2. Vyberte zákazníka a poté zvolte akci **Prodejní ceníky**.
3. Chcete-li vytvořit nový prodejní ceník, zvolte **Nový**.
4. Na záložkáck **Obecné** a **Daň** vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
5. You can add items to the list in the following ways:
   * Chcete-li přidat více položek, vyberte možnost **Navrhnout řádky** a poté zadejte kritéria filtru, abyste určili typy položek, které chcete přidat. Optionally, you can enter other settings for the items. These settings are specific to the price list. You can change them later, if needed.
   * Chcete-li zkopírovat položky z jiného ceníku, zvolte **Kopírovat řádky** a poté vyberte ceník, který chcete zkopírovat.
   * To add items manually, in the **Product Type** field on a line, choose the type of product that the price list is for. V závislosti na výběru vyplňte zbývající pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
6. Chcete-li ceník začít používat, vyberte v poli **Stav** možnost **Aktivní**.

---

## Using Sales and Purchase Price Lists
> [!NOTE]
> Using price lists requires that your administrator has enabled the **New sales pricing experience** feature update in **Feature Management**. Další informace naleznete v tématu [Povolení nadcházejících funkcí s předstihem](/dynamics365/business-central/dev-itpro/administration/feature-management).

The **Applies-to Type** and **Applies-to No.** fields let you choose what a price list will apply to, such as customer or customer price group. Use the **View Columns for** field to show columns that are relevant only for prices, discounts, or prices and discounts.

### Converting Existing Prices When You Turn On the Pricing Feature Update
When you enable the **New sales pricing experience** feature update on the **Feature Management** page, the **Feature Data Update** guide opens. Use the **Use default prices** toggle as follows:

* If you want to work with all prices on a single page, turn it on. Existing prices are converted to one default price list for each of the following:

   * Prodej
   * Purchases
   * Job sales
   * Job purchases

   Afterward, you can edit all prices for these areas on the **Prices Worksheet** page. The default price lists are set on the **Sales & Receivables Setup**, **Purchases & Payables Setup**, and **Jobs Setup** pages.

   > [!NOTE]
   > If prices are set only on item or resource cards, default price lists will not be filled in with those prices during data update. However, you can open any of default price lists or the Price Worksheet page and use the **Suggest Lines** action to add the prices set on item or resource cards.

* To use sales price lists, turn it off. Existing prices will be converted to a new price list for each combination of customer, customer group, or campaign, and the starting and ending dates and currencies. If you have many combinations, you will have many price lists.

If you have already enabled the New Pricing Experience, you can create default price lists manually or specify an existing price list as the default. To set an existing price list as default, turn on the **Allow Updating Defaults** toggle on the price list. Then, on the **Sales & Receivables Setup**, **Purchase & Payables** or **Jobs Setup** pages, set the price list as the default.

## Editing Active Price Lists
To allow people to edit prices on active price lists for items, resources, customers, vendors, or other entities that use pricing, turn on the **Allow Editing Active Price** toggle on the **Sales & Receivables Setup** and **Purchase & Payables Setup** pages.

When the **Allow Editing Active Price** toggle is turned off, to update prices in a price list you must change the status of the price list to **Draft**, make your change, and then reactivate the price list.

The **Prices Overview** page provides an overview of all prices across price lists. You can set filters to narrow down the list. After you change prices, you must use the **Verify Lines** action to verify the prices against other price list lines. For example, verifying the prices helps avoid duplicate or conflicting prices.

> [!NOTE]
> When you edit a line in an active price list the status of the line becomes Draft, and the line will not be included in price calculations until you use the **Verify lines** action. After you verify the price, the line's status becomes Active and it will be used in price calculations.

To add new prices, on the **Prices Overview** page, use the **Add New Lines** action. The **Prices Worksheet** page opens, where you add price lines in the following ways:

* By suggesting them based on criteria
* Copying them from other price lists
* Manually entering them.

Afterward, you can use the **Implement Price Change** action to compare the new prices with other price lists to avoid duplicates.

## Kopírování prodejních cen
Tyto kroky se liší podle toho, zda správce zapnul aktualizaci funkce **Nové prodejní ceny**. If the feature update is not turned on, follow the steps on the Current Experience tab.

## [Aktuální zkušenosti](#tab/current-experience)

Chcete-li kopírovat prodejní ceny, například prodejní ceny jednotlivých zákazníků, které chcete použít pro cenovou skupinu zákazníka, je nutné spustit dávkovou úlohu **Navrhnout cenu z ceny** v sešitu **Sešit prodejní ceny**.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Price Worksheet**, and then choose the related link.
2. Vyberte akci **Navrhnout cenu z ceny**.
3. V záložce **Prodejní ceny** vyplňte pole **Typ prodeje** a **Kód prodeje** původními prodejními cenami, které chcete zkopírovat.
4. V horní části stránky požadavku vyplňte pole **Typ prodeje** a **Kód prodeje** typem a názvem, do které chcete zkopírovat prodejní ceny.
5. Pokud chcete, aby dávková úloha vytvářela nové ceny, zaškrtněte políčko **Vytvořit nové ceny**.
6. Vyberte tlačítko **OK** pro vyplnění řádků na stránce **Sešitu prodejní ceny** navrhovanými cenami, které označují, že jsou platné pro vybraný typ prodeje.

   > [!NOTE]  
   > Tato dávková úloha vytváří pouze návrhy a neimplementuje navrhované změny. Pokud jste s návrhy spokojeni a chcete je implementovat, to znamená vložit je na stránku **Prodejní ceny**, zvolte akci **Provést změnu ceny** na stránce **Sešit prodejní ceny**.

## [Po novu](#tab/new-experience)

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Price Lists**, and then choose the related link.
2. Vyberte ceník, který chcete zkopírovat, a poté zvolte **Kopírovat řádky**.
3. Podle potřeby vyplňte pole. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

   > [!NOTE]
   > Nemůžete mít dva řádky, které mají stejné nastavení, ale různé ceny. Pokud k tomu dojde, zobrazí se při aktivaci ceníku zpráva. Cenu, kterou chcete použít, můžete zvolit otevřením seznamu a odstraněním nesprávné ceny.

---

## Hromadná aktualizace cen zboží
Tyto kroky se liší podle toho, zda správce zapnul aktualizaci funkce **Nové prodejní ceny**. If the feature update is not turned on, follow the steps on the Current Experience tab.

### [Aktuální zkušenosti](#tab/current-experience)

If you want to bulk update item prices, such as increase all item prices by some percentage, you can fill in the **Sales Price Worksheet** by using the following batch jobs:

* **Suggest Item Price on Wksh.** suggests changes by applying an adjustment factor to existing sales prices, or by copying existing sales price agreements to other customer, customer price groups, or sales campaigns.
* **Suggest Item Price on Wksh.** suggests changes by applying an adjustment factor to existing unit prices on item cards, or by suggesting prices for new combinations of currency, units of measure, and so on. The unit prices on items are not changed.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Price Worksheet**, and then choose the related link.
2. Zvolte akci **Navrhnout cenu zboží**.
3. V záložce **Zboží** vyplňte pole **Číslo** nebo **Účto skupina zboží** nebo jiná pole s původními cenami zboží, které chcete aktualizovat.
4. V horní části stránky požadavku vyplňte **Typ prodeje** a **Kód prodeje** typem a názvem, do kterého chcete prodejní ceny zkopírovat.
5. If you want the batch job to automatically adjust suggested item prices, enter the adjustment in **Adjustment Factor** field. For example, you would enter **1.15** in the **Adjustment Factor** for a **15%** increase in the item price.
6. If you want the batch job to create new prices, turn on the **Create New Prices** toggle.
7. Choose **OK** to fill in the lines on the **Sales Price Worksheet** page with the suggested new prices.
8. To implement the suggestions, use the **Implement Price Changes** action. The batch job creates suggestions but does not implement them.

## [Po novu](#tab/new-experience)

Chcete-li aktualizovat ceny pro více položek, je nutné vytvořit nový ceník a potom zkopírovat řádky z existujícího ceníku. Při kopírování řádků můžete pomocí filtrů určit, co se má kopírovat, a v poli **Faktor úpravy** můžete zadat celé číslo nebo desetinné číslo pro zvýšení nebo snížení cen. Ceník musí být ve stavu **Koncept.**. V případě potřeby můžete starý ceník deaktivovat.

> [!NOTE]
> Nemůžete mít dva řádky, které mají stejné nastavení, ale různé ceny. Pokud k tomu dojde, zobrazí se při aktivaci ceníku zpráva. Cenu, kterou chcete použít, můžete zvolit otevřením seznamu a odstraněním nesprávné ceny.

---

## Sales Invoice Discounts and Service Charges
When you use invoice discounts, the total amount on the invoice determines the size of the discount that is granted. On the **Cust. Invoice Discounts** page, you can also add a service charge to invoices over a certain amount.

If you want invoice discounts to be calculated automatically, on the **Sales & Receivables Setup** page, turn on the **Calc Inv. Discount** toggle.

For each customer, you can specify whether you will offer invoice discounts if the criteria are met. For example, if the invoice amount is large enough. Podmínky fakturační slevy můžete definovat v místní měně pro tuzemské zákazníky a v cizí měně pro zahraniční zákazníky.

You link discount percentages to specific invoice amounts in the **Cust. Invoice Discounts** page for each customer. You can enter any number of percentages. Každý zákazník může mít svou vlastní stránku nebo můžete propojit několik zákazníků se stejnou stránkou.

In addition to, or instead of, a discount percentage, you can link a service charge amount to a specific invoice amount.

For training in discounts in sales, see [Set up discounts for your customers](/learn/modules/customer-discounts-dynamics-365-business-central/index) at Microsoft Learn.

### Calculating Invoice Discounts on Sales

[!INCLUDE [sales-invoice-discounts](includes/sales-invoice-discounts.md)]

## Nastavení slevy na prodejní řádek pro zákazníka
Tyto kroky se liší podle toho, zda správce zapnul aktualizaci funkce **Nové prodejní ceny**. If the feature update is not turned on, follow the steps on the Current Experience tab.

## [Aktuální zkušenosti](#tab/current-experience)

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Zákazníci** a poté vyberte související odkaz.
2. Otevřete příslušnou kartu zákazníka a poté zvolte akci **Řádkové slevy**.
3. Vyplňte pole na řádku podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Vyplňte řádek pro každou kombinaci, která zákazníkovi poskytne slevu na prodejní řádek.

> [!Note]
> Při otevření stránek **Prodejní ceny** a **Prodejní řádkové slevy** od konkrétního zákazníka jsou pole **Filtr typu prodeje** a **Filtr kódu prodejního** nastavena pro daného zákazníka a nelze je změnit ani odstranit.
>
> Chcete-li nastavit ceny nebo řádkové slevy pro všechny zákazníky, cenovou skupinu zákazníků nebo kampaň, musíte otevřít stránky z karty položky. Alternativně můžete pro prodejní ceny použít stránku **Sešit prodejní ceny**. Další informace naleznete v tématu [Hromadná aktualizace cen zboží](sales-how-record-sales-price-discount-payment-agreements.md#to-bulk-update-item-prices).

## [Po novu](#tab/new-experience)

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Zákazníci** a poté vyberte související odkaz.
2. Vyberte zákazníka a poté zvolte akci **Prodejní ceníky**.
3. Otevřete ceník, pro který chcete zadat řádkovou slevu.
4. Vytvořte nový řádek nebo vyberte existující řádek a vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
5. V poli **Definování** zvolte buď **Cena a sleva**, nebo pouze **Sleva**.
6. V poli **Řádková sleva %** zadejte procento slevy.

   > [!TIP]
   > You can filter the lines by choosing the appropriate option in the **View Columns for** field.

   > [!NOTE]
   > Invoice discount codes are represented by existing customer cards. Using customer names as codes enables you to quickly assign invoice discount terms to customers by picking the name of another customer who will have the same terms. To set up customer-specific invoice discount terms, set the **Invoice Disc. Code** field to the customer's customer code, and then proceed to the next step.

---

## Nastavení fakturační slevy pro zýkazníka
When you have decided which customers are eligible for invoice discounts, enter the invoice discount code on the customer cards and set up the terms for each code.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Zákazníci** a poté vyberte související odkaz.
2. Otevřete stránku zákazníka pro zákazníka, který bude mít nárok na fakturační slevy.
3. Do pole **Kód fakturační slevy** vyberte kód pro příslušné podmínky fakturační slevy, které se mají použít k výpočtu fakturních slev pro zákazníka.

> [!NOTE]  
> Kódy fakturačních slev jsou reprezentovány existujícími zákaznickými kartami. Using customer names as codes lets you to quickly assign invoice discount terms to customers by picking the name of another customer who will have the same terms.

Now set up the sales invoice discount terms.

1. Na stránce **Zákazníci** zvolte akci **Fakturační slevy** . Stránka **Fakturační slevy zákazníka** se otevře.
2. Do pole **Kód měny** zadejte kód měny, na kterou se vztahují podmínky slevy na faktuře na řádku. Chcete-li nastavit podmínky fakturační slevy v USD, ponechte pole prázdné.
3. Do pole **Minimální částka** zadejte minimální částku, kterou musí mít faktura nárok na slevu.
4. Do pole **Procento slevy** zadejte fakturační slevu jako procento částky faktury.
5. Opakujte kroky 5 až 7 pro každou měnu, pro kterou zákazník obdrží jinou fakturační slevu.

## Best Price Calculation
When you have recorded special prices and line discounts for sales and purchases, [!INCLUDE[d365fin](includes/d365fin_md.md)] ensures that your profit on item trade is always optimal by automatically calculating the best price on sales and purchase documents and on job and item journal lines.

The best price is the lowest permissible price with the highest permissible line discount on a given date. [!INCLUDE[d365fin](includes/d365fin_md.md)] automatically calculates this when it inserts the unit price and the line discount percentage for items on new document and journal lines.

> [!NOTE]  
> The following describes how the best price is calculated for sales. The calculation is the same for purchases.

1. [!INCLUDE[d365fin](includes/d365fin_md.md)] checks the combination of the bill-to customer and the item and then calculates the applicable unit price and line discount percentage, using the following criteria:

   - Does the customer have a price/discount agreement, or does the customer belong to a group that does?
   - Is the item or the item discount group on the line included in any of these price/discount agreements?
   - Is the order date (or the posting date for the invoice and credit memo) within the starting and ending date of the price/discount agreement?
   - Is a unit of measure code specified? If so, [!INCLUDE[d365fin](includes/d365fin_md.md)] checks for prices/discounts with the same unit of measure code, and prices/discounts with no unit of measure code.

2. [!INCLUDE[d365fin](includes/d365fin_md.md)] checks whether any price/discount agreements apply to information on the document or journal line, and then inserts the applicable unit price and line discount percentage using the following criteria:

   - Is there a minimum quantity requirement in the price/discount agreement that is fulfilled?
   - Is there a currency requirement in the price/discount agreement that is fulfilled? If so, the lowest price and the highest line discount for that currency are inserted, even if local currency would provide a better price. If there is no price/discount agreement for the specified currency code, [!INCLUDE[d365fin](includes/d365fin_md.md)] inserts the lowest price and the highest line discount in your local currency.

If no special price can be calculated for the item on the line, then either the last direct cost or the unit price from the item card is inserted.

## Zobrazit související školení na webu [Microsoft Learn](/learn/modules/manage-sales-prices-dynamics-365-business-central/index)

## Viz také

[Setting Up Sales](sales-setup-sales.md)  
[Sales](sales-manage-sales.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]