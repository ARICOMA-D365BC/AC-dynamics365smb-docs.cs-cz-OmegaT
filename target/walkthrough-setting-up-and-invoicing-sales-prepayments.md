---
    title: Setting Up and Invoicing Sales Prepayments
    description: Prepayments are payments that are invoiced and posted to a sales or purchase prepayment order before final invoicing.
    author: SorenGP


    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 12/03/2021
    ms.author: edupont

---
# Návod: Nastavení a fakturace prodejních záloh

This walkthrough takes you through the process of setting up and using prepayments in [!INCLUDE [prod_short](includes/prod_short.md)]. [!INCLUDE [prepayment_def](includes/prepayment_def.md)]

[!INCLUDE [prepayment_req](includes/prepayment_req.md)]

Můžete například poslat další zálohové faktury, pokud jsou k objednávce přidány další položky.

## O tomto návodu

Tento návod vás provede následujícími scénáři:

- Nastavení záloh
- Vytvoření objednávky, která vyžaduje zálohu
- Vytvoření zálohové faktury
- Oprava požadavků na zálohu u objednávky
- Uplatňování záloh na objednávku
- Fakturace konečné částky za objednávku se zálohou

### Role

Tento návod obsahuje úkoly pro následující role:

- Hlavní účetní (Phyllis)
- Zpracovatel objednávek (Susan)
- Správce pohledávek (Arnie)

## Příběh

Phyllis je hlavní účetní. Před výrobou nebo odesláním zboží rozhoduje o tom, kteří zákazníci jsou povinni zaplatit zálohu. Phyllis nastavuje [!INCLUDE[prod_short](includes/prod_short.md)] k automatickému výpočtu záloh.

Susan je zpracovatelka prodejní objednávky. Když zákazník zavolá a zadá objednávku, Susan zadá objednávku do systému, když je zákazník na telefonu. Tímto způsobem může okamžitě ověřit ceny a platební podmínky se zákazníkem a během jednání se zákazníkem může provádět úpravy objednávky.

Arnie pracuje v oddělení pohledávek, kde zaúčtuje faktury a platby.

V tomto scénáři Phyllis nastaví požadavky na zálohu pro zákazníka Selangorian, na základě jejich úvěrové historie, a dává Susan pokyny, jak zacházet s jejich objednávkami.

Když zákazník zavolá, Susan vyjednáva se zákazníkem, dokud nedosáhnou dohody. Poté se může rozhodnout vypočítat zálohu několika různými způsoby.

Poté, co Susan odešle zálohovou fakturu, zákazník si objedná další zboží. Susan aktualizuje objednávku a vytvoří druhou zálohovou fakturu.

Arnie zaregistruje platbu zákazníka a použije ji na faktury a poté odešle konečnou fakturu.

## Nastavení záloh

Phyllis nastavuje systém pro zpracování záloh pro zákazníky.

- Phyllis se rozhodne mít stejnou číselnou řadu pro zálohy jako ta, která se používá pro prodejní fakturaci.
- Phyllis nastaví aplikaci, aby zkontrolovala, zda jsou před konečnou fakturací objednávky vyžadovány zálohy.
- Phyllis nastavuje výchozí hodnoty pro požadované procento zálohy pro konkrétní položky a zákazníky.

Následující postupy popisují, jak splnit úkoly Phyllis:

### Nastavení číselných řad pro zálohy

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Nastavení prodeje a pohledávek** a poté vyberte související odkaz.
2. On the **Sales & Receivables Setup** page, expand the **Number Series** FastTab.
3. Ověřte, že číselná řada pro zaúčtované zálohové faktury v poli **Čísla účtovaných  Zásoby faktur** je stejná jako u zaúčtovaných prodejních faktur (**Čísla zaúčtovaných faktur**) a číselné řady zaúčtovaných dobropisů zálohy (**Čísla účtovaných  zál.  dobropisů**) je stejné jako u zaúčtovaných dobropisů (**Čísla zaúčtovaných dobropisů**).

### Blokování zásilek pro nezaplacenou zálohu

1. Na stránce **Nastavení prodeje a pohledávek** na záložce **Obecné** zaškrtněte políčko **Zkontrolovat zálohu při účtování**.

Nyní nemůžete odeslat ani fakturovat objednávku, která má nezaplacenou částku zálohy.

Ve výchozím nastavení vyžaduje Phyllis fakturaci zákazníkovi 20 000 na zálohu 30% na všechny objednávky. Proto zadá výchozí procento zálohy na kartě zákazníka.

Phyllis requires all customers to be invoiced a 20% deposit for item 1896-S. Zákazník 20000 má špatnou platební historii. Therefore, she requires a 40% prepayment from customer 20000 for item 1896-S. Následující postup znázorňuje, jak nastavit výchozí procenta záloh.

### Přiřazení výchozích procent záloh zákazníkům a zboží

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi.](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Zákazníci** a poté vyberte související odkaz.
2. Open the card for customer 20000 (Trey Research).
3. On the **Payments** FastTab, in the **Prepayment %** field, enter **30**.
4. Choose the **Related** action, select the **Sales** menu item, and then choose the **Prepayment Percentages** menu item.
5. Vyplňte dva řádky na stránce **Procentní části prodejní zálohy**.

   | **Typ prodeje** | **Kód prodeje** | **Číslo zboží** | **Záloha %** |
   |--------------------|--------------------|------------------|----------------------|  
   | **Zákazník** | **20000** | **1896-S** | **40** |
   | **Zákazník** | **20000** | **1900-S** | **30** |

   > [!TIP]
   > Depending on your country/region, you must also specify a tax group code on the **Costs & Posting** FastTab for item 1896-S. When you use the demonstration company, this field is already set.

6. Zavřete všechny stránky.

### Určení účtu pro prodejní zálohy v nastavení obecného účtování

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Nastavení obecného účtování** a poté vyberte související odkaz.
2. Vyberte řádek, kde je pole **Obecná  účto  Posting Group** field is set to **DOMESTIC**, and the **Gen. účto  Posting Group** field is set to **RETAIL**.
3. In the **Sales Prepayments Account** field, specify the relevant account. Your selection is automatically saved.

> [!TIP]
> If you cannot see the field in the **General Posting Setup** page, then use the horizontal scroll bar at the bottom of the page to scroll to the right.

## Vytvoření objednávky, která vyžaduje zálohu

V následujícím scénáři Susan, zpracovatel objednávek, vytvoří objednávku při rozhovoru se zákazníkem. Zboží, které zákazník objednává, vyžaduje zálohu a zákazník v minulosti provedl některé opožděné platby. Therefore, Susan has been instructed to require a fixed amount of **800** as a prepayment on the order.

Zákazník požaduje, aby mohl platit 35%, s čím může Susan souhlasit. Proto mění pořadí.

Susan vytvoří zálohovou fakturu a odešle ji zákazníkovi.

### Vytvoření prodejní objednávky se zálohou

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Prodejní objednávky** a poté zvolte související odkaz.
2. Vyberte akci **Nový**.
3. In the **Customer Name** field, choose **Trey Research**.
4. Close the overdue balance warning that is displayed.
5. Vyplňte dva prodejní řádky následujícími informacemi.

   | **Typ** | **Číslo** | **Množství** |
   |--------------|-------------|------------------|  
   | **Zboží** | **1896-S** | **1** |
   | **Zboží** | **1900-S** | **1** |

   Ve výchozím nastavení jsou pole zálohy na prodejním řádku skrytá, takže je nutné je zobrazit. To do this you need to personalize the page. For more information, see [To start personalizing a page through the Personalizing banner](ui-personalization-user.md#to-start-personalizing-a-page-through-the-personalizing-banner).

6. Verify that the **Prepayment %** field on the line with item **1900-S** contains **30**. Výchozí hodnota byla převzata z prodejní hlavičky, která byla vyplněna z karty zákazníka.

   The **Prepayment %** field on the line with item **1896-S** contains **40**. This is the percentage you entered on the **Sales Prepayment Percentages** page for item **1896-S** and customer **20000**.

   Pro více informací navštivte [Nastavení záloh](finance-set-up-prepayments.md).
7. In the **Order** action, choose  **Statistics**.
8. On the **Prepayment** FastTab, the **Prepayment Amount Excl. VAT** field contains **458.16**. Pokud nyní pro objednávku vytvoříte zálohovou fakturu, pak se jedná o částku, která se zobrazí na faktuře.

   In this scenario, Susan has been instructed to suggest a total prepayment of **800** for the order.

   > [!IMPORTANT]  
   > Depending on your country/region, the following step might not apply.
9. Změňte částku v poli **Částka  Amount Excl. Tax** field to **800** and then close the page.
10. Verify the **Prepayment %** field on the sales lines, and you will see that it has been recalculated to **67.02438** and **67.02282**.

   Přepočet zahrnuje všechny řádky, které mají procento platby předem větší než 0.

   Nyní se zákazník zeptá, zda je možné nastavit procento zálohy na 35%. Susanina nadřízená změnu schvaluje.
11. On the **Sales Order** page, on the **Prepayment** FastTab in the **Prepayment %** field, enter **35**.
12. V zobrazeném varování klikněte na tlačítko **Ano**. Jako procento platby pro celou objednávku bude použita sazba 35%.
13. Ověřte, zda byly řádky odpovídajícím způsobem aktualizovány.

## Vytvoření zálohové faktury

Po zadání správných hodnot zálohy na objednávce vytvoří Susan zálohovou fakturu a odešle ji zákazníkovi.

### Vytvoření zálohové faktury

1. On the **Sales Order** page, choose **Actions**, then **Posting**, then **Prepayment** and then select **Post and Print Prepayment Invoice**
2. Choose the **Yes** button to post the invoice.

> [!NOTE]  
> Susan would now send the invoice to the customer.

## Vytvoření dodatečné zálohové faktury

Následující den zákazník zavolá Susan a provede změny v objednávce. The customer wants two of item 1896-S. Susan znovu otevře a aktualizuje objednávku a pak vytvoří druhou zálohovou fakturu na objednávce a odešle ji zákazníkovi.

### Vytvoření dodatečné zálohové faktury

1. On the **Sales Order** page, choose the **Release** action, and then **Reopen**.
2. On the line for item **1896-S**, in the **Quantity** field, enter **2**.

   In the **Order** action, choose **Statistics**. The **Prepayment Amount Excl. VAT** field now contains **768.04**, and the **Prepmt. částka  Zásoby bez  VAT** field contains **417.76**. To ukazuje, že existuje další částka zálohy, která ještě nebyla fakturována.
3. To post an invoice for the additional prepayment amount, choose **Actions**, then **Posting**, then **Prepayment** and then select **Post and Print Prepayment Invoice**
4. Choose the **Yes** button to post the invoice.

## Uplatnění záloh

Zákazník zaplatí částku zálohy a Arnie, která pracuje v účetním oddělení, zaregistruje platbu a použije ji na zálohové faktury.

### Použití platby na zálohové faktury

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cash Receipt Journals**, and then choose the related link.
2. Vyplňte řádek deníku následujícími informacemi.

   | Název pole | Zadejte |
   |----------------|-----------|  
   | **Typ dokladu** | **Platba** |
   | **Typ účtu** | **Zákazník** |
   | **Číslo účtu** | **20000** |
3. Choose the **Process** action, and then **Apply Entries**.
4. On the **Apply Customer Entries** page, select the first prepayment invoice, and then choose the **Process** action, and then choose the **Set Applies-to ID** action.
5. Opakujte předchozí krok pro druhou zálohu.
6. Zvolte tlačítko **OK**.

   The **Amount** fields have now been filled in with the sum of the two prepayment invoices.

7. To post the journal, choose the **Post/Print** action, then select **Post**.
8. Vyberte tlačítko **Ano**.

## Fakturace zbývající částky

Nyní byla Arnie informována, že položky v objednávce byly odeslány a že objednávka je připravena k fakturaci. Arnie vytvoří fakturu za objednávku.

### Fakturace zbývající částky

1. Otevřete prodejní objednávku.
2. Choose the **Posting** action, then **Post**.
3. Select **Ship and Invoice**, and then choose the **OK** button.
4. If you want to preview the invoice, choose the **Yes** button.

   > [!NOTE]  
   > Normally, the shipping department would have already posted the shipment.

   Arnie může zobrazit historii a ověřit, zda byla prodejní faktura vytvořena tak, jak bylo zamýšleno.

5. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Sales Invoices**, and then choose the related link.

## Další kroky

Tento návod vás provedl kroky k nastavení [!INCLUDE[prod_short](includes/prod_short.md)] pro zpracování záloh. Nastavili jste výchozí procenta předplacení u zákazníků a položek a také jste použili různé metody pro výpočet zálohy u objednávky. Pokusili jste se přiřadit jednu celkovú částku zálohy k objednávce a nechali jste si částku zálohy vypočítat jako procento z celé objednávky.

Zaúčtovali jste také zálohovou fakturu, vytvořili jste druhou zálohovou fakturu, když se změnila objednávka, a zaúčtovali jste konečnou fakturu pro zbývající částku.

Funkce záloh v [!INCLUDE[prod_short](includes/prod_short.md)] usnadňuje nastavení a vynucení pravidel záloh pro zákazníky a zboží a umožňuje zaúčtovat každou platbu na fakturu.

## Viz také

[Invoicing Prepayments](finance-invoice-prepayments.md)  
[Finance](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Business Process Walkthroughs](walkthrough-business-process-walkthroughs.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
