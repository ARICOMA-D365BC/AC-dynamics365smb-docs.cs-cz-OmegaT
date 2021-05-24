---
title: Set Up Value-Added Tax
description: Make sure that you correctly calculate, post, and report on VAT for sales and purchases.
author: bholtorf
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: VAT, posting, tax, value-added tax
ms.date: 04/01/2021
ms.author: bholtorf

---

# Set Up Calculations and Posting Methods for Value-Added Tax

Spotřebitelé a podniky platí daň z přidané hodnoty (DPH) při nákupu zboží nebo služeb. Výše DPH se může lišit v závislosti na několika faktorech. In [!INCLUDE[prod_short](includes/prod_short.md)], you set up VAT to specify the rates to use to calculate tax amounts based on the following:

* Komu prodáváte
* Od koho nakupujete
* Co prodáváte
* Co kupujete

Výpočty DPH můžete nastavit ručně, ale to může být složité a časově náročné. To make it easy, we provide an assisted setup guide named **VAT Setup** that will help you with the steps. K nastavení DPH doporučujeme použít průvodce nastavením.

> [!NOTE]  
> Průvodce můžete použít pouze v případě, že jste vytvořili společnost a neúčtovali jste transakce, které zahrnují DPH. V opačném případě by bylo velmi snadné omylem použít různé sazby DPH a učinit sestavy související s DPH nepřesnými.

Pokud si chcete sami stanovit výpočty DPH nebo se chcete o každém kroku dozvědět, toto téma obsahuje popisy jednotlivých kroků.

## Použití asistovaného průvodce Nastavit DPH k nastavení DPH

We recommend that you use the VAT Setup assisted setup guide to set up VAT in [!INCLUDE[prod_short](includes/prod_short.md)].

Chcete-li spustit průvodce asistovaným nastavením, postupujte takto:

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Assisted Setup**.
2. Choose **Set up VAT** and complete the steps.
3. When you have completed the assisted setup, visit the **Vat Posting Setup** page and check if you have to fill in additional fields according to the local requirements in your version pf [!INCLUDE [prod_short](includes/prod_short.md)]. For more information, see [Local functionality in Business Central](about-localization.md)

## Nastavení DIČ pro vaší zemi nebo oblast

Chcete-li zajistit, aby lidé zadávali platná DIČ, můžete definovat formáty pro DIČ, která se používají v zemích nebo regionech, ve kterých podnikáte. [!INCLUDE[prod_short](includes/prod_short.md)] will display an error message when someone makes a mistake or uses a format that is incorrect for the country or region.

Pro nastavení DIČ postupujte takto:

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Countries/Regions**.
2. Choose the country or region, and then choose the **VAT Reg. Ne.  Formats** action.
3. In the **Formats** field, define the format by entering one or more of the following characters:

* **#** Requires a single-digit number.
* **@** Requires a letter. Na velikosti písmen nezáleží.
* **?** Allows any character.

   > [!Tip]
   > Můžete použít i jiné znaky, pokud jsou ve formátu vybrané země nebo oblasti.. Pokud například potřebujete zahrnout tečku nebo pomlčku mezi sadami čísel, můžete formát definovat jako ##.######## nebo @@@-###-####.

## Nastavení DPH obchodních účto skupin
Obchodní DPH účto skupiny by měly představovat trhy, na kterých obchodujete se zákazníky a prodejci, dále skupiny určijí, jak vypočítat a účtovat DPH na každém trhu. Examples of VAT business posting groups are **Domestic** and **European Union (EU)**.

Use codes that are easy to remember and describe the business posting group, such as **EU**, **Non-EU**, or **Domestic**. Kód musí být jedinečný. Můžete nastavit libovolný počet kódů, ale nemůžete mít stejný kód více než jednou v tabulce.

Pro nastavení DPH obchodních účto skupin postupujte takto:

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Business Posting Group**, and then choose the related link.
2. Podle potřeby vyplňte pole.

Výchozí DPH obchodní účto skupiny nastavíte jejich propojením s obecnými obchodními účto skupinami. [!INCLUDE[prod_short](includes/prod_short.md)] automatically assigns the VAT business posting group when you assign the business posting group to a customer, vendor, or general ledger account.

## Nastavení DPH účto skupin zboží
VAT product posting groups represent the items and resources you buy or sell, and determine how to calculate and post VAT according to the type of item or resource that is being bought or sold.  
It is a good idea to use codes that are easy to remember and describe the rate, such as **NO-VAT** or **Zero**, **VAT10** or **Reduced** for 10% VAT, and **VAT25** or **Standard** for 25%.

Pro nastavení DPH obchodních účto skupin postupujte takto:

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Product Posting Groups**, and then choose the related link.
2. Podle potřeby vyplňte pole.

## Kombinace DPH účto skupin v nastavení účtování DPH
[!INCLUDE[prod_short](includes/prod_short.md)] calculates VAT amounts on sales and purchases based on VAT posting setups, which are combinations of VAT business and product posting groups. Pro každou kombinaci můžete zadat procento DPH, typ výpočtu DPH a účty pro účtování DPH za prodej, nákup a vratky. Můžete také určit, zda se má přepočítat DPH při uplatnění nebo obdržení skonta.

Nastavte tolik kombinací, kolik potřebujete. If you want to group VAT posting setup combinations with similar attributes, you can define a **VAT Identifier** for each group, and assign the identifier to the group members.

Chcete-li kombinovat nastavení účtování DPH, postupujte takto:

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Posting Setup**, and then choose the related link.
2. Podle potřeby vyplňte pole.

## Přiřazení Účto skupin DPH ve výchozím nastavení k více entitám
If you want to apply the same VAT posting groups to multiple entities, you can set up [!INCLUDE[prod_short](includes/prod_short.md)] to do so by default. Existuje několik způsobů, jak to udělat:

* Obchodní účto skupiny DPH můžete přiřadit k obecným obchodním účto skupinám nebo k šablonám zákazníků nebo dodavatelů.
* Můžete přiřadit DPH účto skupiny zboží k obecným účto skupinám zboží.

Dph obchodní nebo účto skupina zboží je přiřazena při výběru obchodní nebo zbožové účto skupině pro zákazníky, dodavatele, zboží nebo zdroj.

## Přiřazení DPH účto skupin k účtům, zákazníkům, dodavatelům, zboží a zdrojům
Následující části popisují, jak přiřadit DPH účto skupiny k jednotlivým subjektům.

### Přiřazení DPH účto skupin k jednotlivým účtům hlavní knihy
1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Účtovní osnova** a poté vyberte související odkaz.
2. Open the **G/L Account** card for the account.
3. Na záložce **Účtování** v poli **Obecná  Posting Type** field, choose either **Sale** or **Purchase**.
5. Zvolte DPH účto skupiny, které chcete použít pro prodejní nebo nákupní účet.

### Přiřazení DPH obchodních účto skupin zákazníkům a dodavatelům
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customer** or **Vendor**, and then choose the related link.
2. On the **Customer** or **Vendor** card, expand the **Invoicing** FastTab.
3. Vyberte DPH obchodní účto skupinu.

### Přiřazení DPH účto skupin zboží k jednotlivému zboží a zdrojům
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item** or **Resource**, and then choose the related link.
2. Proveďte jeden z následujících úkonů:

* On the **Item** card, expand the **Price & Posting** FastTab, and then choose **Show more** to display the **VAT Product Posting Group** field.
* On the **Resource** card, expand the **Invoicing** FastTab.
3. Vyberte DPH účto skupinu zboží.

## Nastavení doložek k vysvětlení osvobození od DPH nebo nestandardních DPH sazeb
Nastavte klauzuli DPH popisující informace o typu DPH, která je použita. Informace mohou být vyžadovány nařízením vlády. Po nastavení klauzule DPH a přidružení k nastavení účtování DPH, se klauzule DPH zobrazí na vytištěných prodejních dokladech, které používají účto skupiny nastavení DPH.

V případě potřeby můžete také určit, jak převést klauzule DPH do jiných jazyků. Potom při vytváření a tisku prodejního dokladu, který obsahuje identifikátor DPH, bude dokument obsahovat přeloženou klauzuli DPH. Kód jazyka uvedený na kartě zákazníka určuje jazyk.

Pokud jsou nestandardní sazby DPH používány v různých typech dokumentů, jako jsou faktury nebo dobropisy, musí společnosti obvykle uvést text osvobození (klauzuli o DPH), v níž je uvedeno, proč byla vypočtena snížená nebo nulová sazba DPH. Můžete definovat různé klauzule DPH, které mají být zahrnuty do obchodních dokladů podle typu dokladu, například faktury nebo dobropisu. You do this on the **VAT Clauses by Doc. Type** page.

Můžete upravit nebo odstranit klauzuli DPH a změny se následně projeví ve vygenerované sestavě. However, [!INCLUDE[prod_short](includes/prod_short.md)] does not keep a history of the change. V sestavě jsou popisy klauzule DPH vytištěny a zobrazeny pro všechny řádky v sestavě vedle částky DPH a základní částky DPH. Pokud nebyla klauzule DPH definována pro žádné řádky v prodejním dokladu, je při tisku sestavy vynechán celý oddíl.

### Nastavení klauzule DPH
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Clauses**, and then choose the related link.
2. On the **VAT Clauses** page, create a new line.
3. In the **Code** field, enter an identifier for the clause. Pomocí tohoto kódu přiřadíte klauzuli skupinám účtování DPH.
4. In the **Description** field, enter the VAT exemption text that you want to display on documents that can include VAT. In the **Description 2** field, enter additional text, if needed. Text se zobrazí na nových řádcích dokumentu.
5. Choose the **Description by Document Type** action.
6. On the **VAT Clauses by Doc. Type** page, fill in the fields to set up which VAT exemption text to display for which document type.
7. Optional: To assign the VAT clause to a VAT posting setup right away, choose **Setup**, and then choose the clause. If you want to wait, you can assign the clause later on the **VAT Posting Setup** page.
8. Optional: To specify how to translate the VAT clause, choose the **Translations** action.

### Přiřazení klauzule DPH k nastavení účtování DPH
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Posting Setup**, and then choose the related link.
2. In the **VAT Clause** column, choose the clause to use for each VAT posting setup it applies to.

### Nastavení překladů pro klauzule DPH
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Clauses**, and then choose the related link.
2. Choose the **Translations** action.
3. In the **Language Code** field, choose the language you are translating to.
4. In the **Description** and **Description 2** fields, enter the translations of the descriptions. Tento text se zobrazí v přeložených dokladech DPH.

## Nastavení účtování DPH pro zpracování importní DPH
Funkce Importní DPH se používá v případě, že potřebujete zaúčtovat doklad, kde je celá částka DPH. Tuto možnost použijete, pokud obdržíte od finančního úřadu fakturu na DPH za dovážené zboží.

Pro nastavení kódů pro importní DPH postupujte takto:
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Product Posting Groups**, and then choose the related link.
2. Na stránce DPH účto skupiny zboží nastavte novou DPH účto skupinu zboží pro importní DPH.
3. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Posting Setup**, and then choose the related link.
4. Na stránce Nastavení účtování DPH vytvořte nový řádek nebo použijte existující DPH obchodní účto skupiny v kombinaci s novou DPH účto skupinou zboží pro importní DPH.
5. In the **VAT Calculation Type** field, choose **Full VAT**.
6. In the **Purchase VAT Account** field, enter the general ledger account to use for posting import VAT. Všechny ostatní účty jsou volitelné.


## Použití vratné DPH pro obchod mezi zeměmi nebo oblastmi EU
Některé společnosti musí při obchodování s jinými společnostmi používat vratnou DPH. Toto pravidlo se například vztahuje na nákupy ze zemí nebo oblastí EU a prodej do zemí nebo oblastí EU.

> [!NOTE]  
> Toto pravidlo platí při obchodování se společnostmi, které jsou registrovány jako plátce DPH v jiné zemi EU. Pokud obchodujete přímo se spotřebiteli v jiných zemích nebo oblastech EU, měli byste se obrátit na svůj daňový úřad s žádostí o příslušná pravidla DPH.

> [!TIP]  
> Ověřením, že společnost je registrována jako plátce DPH v jiné zemi EU, použijte službu ověřování DIČ v EU. The service is available for free in [!INCLUDE[prod_short](includes/prod_short.md)]. For more information, see the section titled _Verify VAT registration numbers_ in this topic.

### Prodej do zemí EU
DPH se nepočítá z prodeje společnostem povinným k DPH v jiných zemích nebo oblastech EU. Hodnotu těchto prodejů musíte nahlásit do zemí EU samostatně ve svém daňovém přiznání.

Chcete-li správně vypočítat DPH z prodeje do zemí nebo oblastí EU, měli byste udělat:

* Založte řádek pro prodej se stejnými informacemi pro nákupy. Pokud jste již nastavili řádky na stránce Nastavení účtování DPH pro nákupy ze zemí nebo oblastí EU, můžete tyto řádky použít také pro prodej.
* Assign the VAT business posting groups in the **VAT Bus. Posting Group** field on the **Invoicing** FastTab of the customer card of each EU customer. You should also enter the customer's VAT registration number in the **VAT Registration No.** field on the **Foreign Trade** FastTab.

Když účtujete prodej zákazníkovi v jiné zemi nebo oblasti EU, vypočítá se částka DPH a položka DPH se vytvoří pomocí informací o přenesené daňové povinnosti DPH a základu DPH, což je částka, která se používá k výpočtu částky DPH. Na účtech DPH nejsou v hlavní knize zaúčtovány žádné položky.

## Principy zaokrouhlení DPH v dokladech
Částky v dokladech, které ještě nejsou zaúčtovány, jsou zaokrouhleny a zobrazeny tak, aby odpovídaly konečnému zaokrouhlení částek, které jsou skutečně zaúčtovány. DPH se vypočítá pro celý doklad, což znamená, že DPH je vypočtena na základě součtu všech řádků se stejnou sazbou DPH v dokladu.




## Viz také
[Setting up VAT Statement Templates and VAT Statement Names](finance-how-setup-vat-statement.md)   
[Setting Up Unrealized Value Added Tax](finance-setup-unrealized-vat.md)      
[Report VAT to a Tax Authority](finance-how-report-vat.md)      
[Work with VAT on Sales and Purchases](finance-work-with-vat.md)    
[Work with the VAT Rate Change Tool](finance-how-use-vat-rate-change-tool.md)    
[Verify VAT registration numbers](finance-how-validate-vat-registration-number.md)  
[Local functionality in Business Central](about-localization.md)

## Zobrazit související školení na webu [Microsoft Learn](/learn/paths/process-vat-dynamics-365-business-central/)


[!INCLUDE[footer-include](includes/footer-banner.md)]