---
title: Set Up Special Sales Prices and Discounts for Customers | Microsoft Docs
description: Describes how to define the alternate pricing and discount agreements that you want to apply to sales documents when selling to different customers.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: special price, alternate price, pricing
ms.date: 04/01/2021
ms.author: bholtorf

---
# Record Special Sales Prices and Discounts
> [!NOTE]
> In 2020 release wave 2 we released streamlined processes for setting up and managing prices and discounts. Pokud jste nový zákazník a používáte tuto verzi, používáte nové prostředí. If you're an existing customer, whether you are using the new experience depends on whether your administrator has enabled the **New sales pricing experience** feature update in **Feature Management**. Další informace naleznete v tématu [Povolení nadcházejících funkcí s předstihem](/dynamics365/business-central/dev-itpro/administration/feature-management).

The price and discount agreements that apply when selling to customers must be defined so that the agreed rules and values are applied to sales documents.

When you have recorded special prices and line discounts for sales and purchases, [!INCLUDE[prod_short](includes/prod_short.md)] ensures that your profit on item trade is always optimal by automatically calculating the best price on sales and purchase documents and on job and item journal lines. Pro více informací navštivte [Výpočet nejlepší ceny](sales-how-record-sales-price-discount-payment-agreements.md#best-price-calculation).

Concerning prices, you can have a special sales price inserted on sales lines if a certain combination of customer, item, minimum quantity, unit of measure, or starting/ending date exists. For more information, see the [To set up a sales price for a customer](#to-set-up-a-sales-price-for-a-customer) and [Best Price Calculation](#best-price-calculation) sections.

Concerning discounts, you can set up and use two types of sales discounts:

| Typ slevy | Popis |
| --- | --- |
| **Sales Line Discount** | An amount discount that is inserted on sales lines if a certain combination of customer, item, minimum quantity, unit of measure, or starting/ending date exists. This works in the same way as for sales prices. |
| **Fakturační sleva** | A discount percentage that is subtracted from the sales document total if the sum of all lines on the document exceeds a certain minimum. |

Protože prodejní ceny a slevy na prodejních položkách jsou založeny na kombinaci položky a zákazníka, můžete tuto konfiguraci provést také na stránce položky, kde se pravidla a hodnoty použijí.

> [!TIP]  
> Pokud by zboží nemělo být nikdy prodáváno se slevou, ponechte pole pro slevu na stránce položky prázdné a nezařazujte zboží do žádných nastavení řádkových slev.

The **Applies-to Type** and **Applies-to No.** fields let you choose what this price list will apply to, such as customer or customer price group. Using **View Columns for**, you can show or hide columns relevant for setting prices, discounts or prices and discounts.

You can set up price list lines manually or you can use, for example, the **Suggest Lines** action to create new prices for selected items, item discount groups, resources, and other product types. If you choose Suggest Lines, the Price Lines - Create New page allows you to set filters to select products for which you want to create new price list lines. Můžete také určit, zda se má při výpočtu cen vzít v úvahu minimální množství, faktor úpravy, který se má použít pro nové řádky ceníku, a metoda zaokrouhlení, která se má použít pro ceny. The **Copy Lines** action allows you to copy existing price list lines between price lists.

By default, the status of new price lists is Draft. When you're done adding lines and want the price calculation engine to include it, you can change the status to Active.

To review price lists and prices that apply for specific customers or vendors, on the **Customer** page, choose **Sales Price Lists** or, on the **Vendor** page, choose **Purchase Price Lists**. You can view price list lines in various price lists by choosing **Sales Prices** or **Purchase Prices** from the **Item** and **Resource** pages.

## To set up a sales price for a customer

Tyto kroky se liší podle toho, zda správce zapnul aktualizaci funkce **Nové prodejní ceny**.

#### [Aktuální zkušenosti](#tab/current-experience/)

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Zákazníci** a poté vyberte související odkaz.
2. Vyberte zákazníka a poté vyberte akci **Ceny**.
3. Vyplňte pole na řádku podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Vyplňte řádek pro každou kombinaci, která zákazníkovi poskytne speciální prodejní cenu.

#### [Po novu](#tab/new-experience/)

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Zákazníci** a poté vyberte související odkaz.
2. Vyberte zákazníka a poté zvolte akci **Prodejní ceníky**.
3. Chcete-li vytvořit nový prodejní ceník, zvolte **Nový**.
4. Na záložkáck **Obecné** a **Daň** vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
5. Chcete-li přidat zboží do seznamu, proveďte jednu z následujících akcí:
   * Chcete-li přidat více položek, vyberte možnost **Navrhnout řádky** a poté zadejte kritéria filtru, abyste určili typy položek, které chcete přidat. Volitelně můžete také zadat některá další nastavení položek, která jsou specifická pro daný ceník. V případě potřeby je můžete později změnit.
   * Chcete-li zkopírovat položky z jiného ceníku, zvolte **Kopírovat řádky** a poté vyberte ceník, který chcete zkopírovat.
   * To add items manually, in the grid, in the **Product Type** field, choose the type of product that the price list is for. V závislosti na výběru vyplňte zbývající pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
6. Chcete-li ceník začít používat, vyberte v poli **Stav** možnost **Aktivní**.

---

## Sales Invoice Discounts and Service Charges
When you use invoice discounts the total amount on the invoice determines the size of the discount that is granted. On the **Cust. Invoice Discounts** page, you can also add a service charge to invoices over a certain amount.

Before you can use invoice discounts with sales, you must specify certain information. You must decide the following:

- Which customers will be granted this type of discount
- Which discount percentages you will use

If you want invoice discounts to be calculated automatically, you can specify this on the **Sales & Receivables Setup** page.

U každého zákazníka můžete zadat, zda při splnění požadavku (tj. při dostatečně vysoké fakturované částce) poskytnete slevu na faktuře. Podmínky fakturační slevy můžete definovat v místní měně pro tuzemské zákazníky a v cizí měně pro zahraniční zákazníky.

You link discount percentages to specific invoice amounts in the **Cust. Invoice Discounts** page for each customer. You can enter any number of percentages. Each customer can have its own page, or you can link several customers to the same page.

Kromě (nebo namísto) procenta slevy můžete propojit částku poplatku za službu s určitou částkou faktury.

> [!TIP]  
> Before you start entering this information, it is a good idea to prepare an outline of the discount structure that you want to use. This makes it easier to see which customers can be linked to the same invoice discount page. The fewer pages you have to set up, the faster you can enter the basic information.

For training in discounts in sales, see [Set up discounts for your customers](/learn/modules/customer-discounts-dynamics-365-business-central/index) at Microsoft Learn.

### Calculating Invoice Discounts on Sales

[!INCLUDE [sales-invoice-discounts](includes/sales-invoice-discounts.md)]

## Nastavení slevy na prodejní řádek pro zákazníka
Tyto kroky se liší podle toho, zda správce zapnul aktualizaci funkce **Nové prodejní ceny**.

#### [Aktuální zkušenosti](#tab/current-experience/)

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Zákazníci** a poté vyberte související odkaz.
2. Otevřete příslušnou kartu zákazníka a poté zvolte akci **Řádkové slevy**.
3. Vyplňte pole na řádku podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Vyplňte řádek pro každou kombinaci, která zákazníkovi poskytne slevu na prodejní řádek.

> [!Note]
> Při otevření stránek **Prodejní ceny** a **Prodejní řádkové slevy** od konkrétního zákazníka jsou pole **Filtr typu prodeje** a **Filtr kódu prodejního** nastavena pro daného zákazníka a nelze je změnit ani odstranit.
>
> Chcete-li nastavit ceny nebo řádkové slevy pro všechny zákazníky, cenovou skupinu zákazníků nebo kampaň, musíte otevřít stránky z karty položky. Alternativně můžete pro prodejní ceny použít stránku **Sešit prodejní ceny**. Další informace naleznete v tématu [Hromadná aktualizace cen zboží](sales-how-record-sales-price-discount-payment-agreements.md#to-bulk-update-item-prices).

#### [Po novu](#tab/new-experience/)

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Zákazníci** a poté vyberte související odkaz.
2. Vyberte zákazníka a poté zvolte akci **Prodejní ceníky**.
3. Otevřete ceník, pro který chcete zadat řádkovou slevu.
4. Zapněte přepínač **Povolit řádkovou slevu**.
5. Vytvořte nový řádek nebo vyberte existující řádek a vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
6. V poli **Definování** zvolte buď **Cena a sleva**, nebo pouze **Sleva**.
7. V poli **Řádková sleva %** zadejte procento slevy.

   > [!TIP]
   > Pokud upravujete existující řádek, můžete filtrovat řádky výběrem příslušné možnosti v poli **Zobrazit sloupce pro**.

   > [!NOTE]  
   > Kódy fakturačních slev jsou reprezentovány existujícími zákaznickými kartami. To vám umožní rychle přiřadit podmínky fakturační slevy zákazníkům výběrem jména jiného zákazníka, který bude mít stejné podmínky. To set up customer-specific invoice discount terms, set the **Invoice Disc. Code** field to the customer's customer code, and then proceed to the next step.

8. On the **Customer Card** page, choose the **Invoice Discounts** action. Stránka **Fakturační slevy zákazníka** se otevře.
9. Do pole **Kód měny** zadejte kód měny, na kterou se vztahují podmínky slevy na faktuře na řádku. Chcete-li nastavit podmínky fakturační slevy v USD, ponechte pole prázdné.
10. Optionally, in the **Minimum Amount** field, enter the minimum amount that an invoice must have to be eligible for the discount.
11. Do pole **Procento slevy** zadejte fakturační slevu jako procento částky faktury.
12. Opakujte kroky 5 až 7 pro každou měnu, pro kterou zákazník obdrží jinou fakturační slevu.

The invoice discount is now set up and assigned to the customer. Když vyberete kód zákazníka v poli **Kód fakturační slevy** na jiných kartách zákazníka, je těmto zákazníkům přiřazena stejná fakturační sleva.

---

## Nastavení fakturační slevy pro zýkazníka
When you have decided which customers are eligible for invoice discounts, enter the invoice discount code on the customer cards and set up the terms for each code.

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

## Kopírování prodejních cen
Tyto kroky se liší podle toho, zda správce zapnul aktualizaci funkce **Nové prodejní ceny**.

#### [Aktuální zkušenosti](#tab/current-experience/)

Chcete-li kopírovat prodejní ceny, například prodejní ceny jednotlivých zákazníků, které chcete použít pro cenovou skupinu zákazníka, je nutné spustit dávkovou úlohu **Navrhnout cenu z ceny** v sešitu **Sešit prodejní ceny**.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat<"), zvolte **Sešit prodejní ceny** a poté vyberte související odkaz.
2. Vyberte akci **Navrhnout cenu z ceny**.
3. V záložce **Prodejní ceny** vyplňte pole **Typ prodeje** a **Kód prodeje** původními prodejními cenami, které chcete zkopírovat.
4. V horní části stránky požadavku vyplňte pole **Typ prodeje** a **Kód prodeje** typem a názvem, do které chcete zkopírovat prodejní ceny.
5. Pokud chcete, aby dávková úloha vytvářela nové ceny, zaškrtněte políčko **Vytvořit nové ceny**.
6. Vyberte tlačítko **OK** pro vyplnění řádků na stránce **Sešitu prodejní ceny** navrhovanými cenami, které označují, že jsou platné pro vybraný typ prodeje.

   > [!NOTE]  
   > Tato dávková úloha vytváří pouze návrhy a neimplementuje navrhované změny. Pokud jste s návrhy spokojeni a chcete je implementovat, to znamená vložit je na stránku **Prodejní ceny**, zvolte akci **Provést změnu ceny** na stránce **Sešit prodejní ceny**.

#### [Po novu](#tab/new-experience/)

Stav ceníku musí být **Koncept**.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat<"), zvolte **Sešit prodejní ceny** a poté vyberte související odkaz.
2. Vyberte ceník, který chcete zkopírovat, a poté zvolte **Kopírovat řádky**.
3. Podle potřeby vyplňte pole. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

   > [!NOTE]
   > Nemůžete mít dva řádky, které mají stejné nastavení, ale různé ceny. Pokud k tomu dojde, zobrazí se při aktivaci ceníku zpráva. Cenu, kterou chcete použít, můžete zvolit otevřením seznamu a odstraněním nesprávné ceny.

---

## Hromadná aktualizace cen zboží
Tyto kroky se liší podle toho, zda správce zapnul aktualizaci funkce **Nové prodejní ceny**.

#### [Aktuální zkušenosti](#tab/current-experience/)

Chcete-li hromadně aktualizovat ceny zboží, například zvýšit všechny ceny zboží o určité procento, je nutné spustit dávkovou úlohu **Navrhnout cenu ze zboží**. Odkaz na dávkovou úlohu najdete na stránce **Sešit prodejní ceny**.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat<"), zvolte **Sešit prodejní ceny** a poté vyberte související odkaz.
2. Zvolte akci **Navrhnout cenu zboží**.
3. V záložce **Zboží** vyplňte pole **Číslo** nebo **Účto skupina zboží** nebo jiná pole s původními cenami zboží, které chcete aktualizovat.
4. V horní části stránky požadavku vyplňte **Typ prodeje** a **Kód prodeje** typem a názvem, do kterého chcete prodejní ceny zkopírovat.
5. Pokud chcete, aby dávková úloha automaticky zpravovala ceny navrhovaných položek, zadejte úpravu do pole **Faktor úpravy**. Například pokud zadáte 1,15 do **faktoru úpravy** pro 15% zvýšení ceny zboží.
6. Pokud chcete, aby dávková úloha vytvořila nové ceny, vyberte pole **Vytvořit nové ceny**.
7. Vyberte tlačítko **OK** pro vyplnění řádků na stránce **Sešitu prodejní ceny** navrhovanými cenami, které označují, že jsou platné pro vybrané **Zboží**

> [!NOTE]
> Tato dávková úloha vytváří pouze návrhy a neimplementuje navrhované změny. Pokud jste s návrhy spokojeni a chcete je implementovat, to znamená vložit je do tabulky **Prodejní ceny**, můžete použít dávkovou úlohu **Provést změnu ceny**, která se nachází na ve skupině **Akce** v záložce **Funkce** na stránce **Sešit prodejní ceny**.

#### [Po novu](#tab/new-experience/)

Chcete-li aktualizovat ceny pro více položek, je nutné vytvořit nový ceník a potom zkopírovat řádky z existujícího ceníku. Při kopírování řádků můžete pomocí filtrů určit, co se má kopírovat, a v poli **Faktor úpravy** můžete zadat celé číslo nebo desetinné číslo pro zvýšení nebo snížení cen. Ceník musí být ve stavu **Koncept.**. V případě potřeby můžete starý ceník deaktivovat.

> [!NOTE]
> Nemůžete mít dva řádky, které mají stejné nastavení, ale různé ceny. Pokud k tomu dojde, zobrazí se při aktivaci ceníku zpráva. Cenu, kterou chcete použít, můžete zvolit otevřením seznamu a odstraněním nesprávné ceny.

---

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