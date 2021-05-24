---
title: Managing VAT Rate changes | Microsoft Docs
description: learn how to sue the VAT Rate Change tool for Dynamics 365 Business Central.
author: andregu
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.reviewer: edupont
ms.workload: na
ms.search.keywords: VAT, VAT rate, posting, tax, value-added tax
ms.date: 04/01/2021
ms.author: andregu

---

# Správa změn sazeb DPH

Sazby DPH se mohou měnit v závislosti na místní legislativě. Any change in VAT impacts your data in [!INCLUDE[prod_short](includes/prod_short.md)] whether or not the VAT rate is lowered, raised, or removed. VAT is connected to many entities in [!INCLUDE[prod_short](includes/prod_short.md)], such as customers, vendors, items, resources, item charges, and general ledger accounts. Ke změnám sazeb DPH obvykle dochází k určitému datu, od kterého okamžiku budete muset změnit nastavení DPH, účto skupiny atd., pro ujištětní, že nové prodejní objednávky a nákupní objednávky jsou vytvořeny s novou sazbou DPH.

## Změna sazeb DPH

Optimálním přístupem ke správě změny sazby DPH je úplné zaúčtování a uzavření otevřených objednávek a dalších dokladů před datem změny sazby DPH, aby se zajistilo, že tyto dokumenty nebudou změnou ovlivněny. Jedná se o nejčistší přístup, který vám umožní spustit nové objednávky a dokumenty s novou sazbou DPH.

Pro změnu sazby DPH se navrhuje následující přístup

1. Plně zaúčtovat a uzavřít otevřené objednávky, deníky a další doklady před datem přechodu. Můžete počkat až po datu změny, dokud nepřidáte nové řádky a ujistěte se, že datum účinnosti bude před datem přepnutí.
2. Vytvořte nové nastavení DPH.
3. Přepněte DPH na entity (příslušné zákazníky, dodavatele, zboží atd.).
4. K datu přepnutí sazby DPH vytvoříte nové doklady, které budou používat novou sazbu.


> [!NOTE]  
> We are currently updating the VAT Rate Change tool. Níže uvedené funkce nemusí odpovídat funkcím ve vašem prostředí. Aktualizace proběhne do 1.7.2020 a nebude pravidelnou měsíční aktualizací. Místo toho budou všechna prostředí aktualizována automaticky (oprava hotfix). Po dokončení této aktualizace se tato zpráva již nezobrazí.

## Nástroj pro změnu sazby DPH

Nástroj změna sazby DPH může do určité míry pomoci s převodem sazeb DPH na hlavních datech, denících a objednávkách. To je užitečné, pokud chcete snadněji převést DPH na kmenových datech nebo pokud máte objednávky, které nelze uzavřít před datem přechodu a budou zpracovány po delším časovým obdobím, čímž překročíte datum přechodu sazby DPH. V nástroji pro změnu sazby DPH, která platí, existují určitá omezení a omezení.

## Principy procesu a omezení převodu sazby DPH

Nástroj Změna sazby DPH provádí převody sazby DPH pro hlavní data, deníky a objednávky různými způsoby. Vybraná hlavní data a deníky budou aktualizovány novou obecnou účto skupinou zboží nebo DPH účto skupiny zboží. Pokud byla objednávka zcela nebo částečně dodána, bude dodané zboží udržovat aktuální obecnou účto skupinu zboží nebo DPH účto skupinu zboží. Bude vytvořen nový řádek objednávky pro nedodané položky a bude aktualizován tak, aby odpovídal současným a novým  účto skupinám DPH nebo DPH účto skupinám zboží. Kromě toho budou odpovídajícím způsobem aktualizovány přiřazení poplatky zboží, rezervace a informace o sledování zboží.

Na řádcích objednávky bude jednotková cena aktualizována pro všechny řádky typu Zboží a Zdroj, pokud použijete ceny včetně DPH. U ostatních typů řádku je možné rozhodnout, zda má být jednotková cena aktualizována.

Existuje několik věcí, které nástroj nepřevádí:

* Prodejní nebo nákupní objednávky a faktury, kde byly zaúčtovány dodávky. Tyto doklady jsou zaúčtovány pomocí aktuální sazby DPH.
* Doklady, které zaúčtovali jako zálohové faktury. Například jste odeslali nebo obdrželi zálohové faktury, které nebyly dokončeny před použitím nástroje pro změnu sazby DPH. V takovém případě bude rozdíl mezi splatnou DPH a DPH, která byla zaplacena v zálohách po dokončení faktury. Nástroj pro změnu sazby DPH tyto doklady přeskočí a budete je muset ručně aktualizovat.
* Prodejní nebo nákupní objednávky s integrací skladu, pokud jsou částečně dodány nebo přijaty.
* Přímá dodávka.
* Speciální dodávka.
* Montážní zakázky.
* Servisní smlouvy.
* Dobropisy.
* Objednávka vratky.
* Ceny zboží (master data)
* Prodejní ceny (master data)
* Obchodní účto skupiny pro zákazníky a dodavatele.

### Příprava převodu změny sazby DPH

Před nastavením nástroje pro změnu sazby DPH je nutné provést následující.

* Pokud máte transakce, které používají různé sazby, musí být rozděleny do různých skupin buď vytvořením nových účtů hlavní knihy pro každou sazbu, nebo pomocí filtrů dat pro seskupení transakcí podle sazby.
* Pokud vytvoříte nové finanční účty, musíte vytvořit nové obecné účto skupiny.
* Chcete-li snížit počet převedených dokladů, zveřejněte co nejvíce dokladů a zmenšete počet neodeslaných dokladů na minimum.
* Zálohovat data.

### Nastavení nástroje pro změnu sazby DPH

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Rate Change Setup**, and then choose the related link.
2. On the **Master Data**, **Journals**, and **Documents** FastTabs, choose a posting group value from the option list for needed fields. Pro každou skupinu můžete zvolit, zda chcete převést DPH účto skupiny zboží nebo obecné účto skupiny zboží, nebo převést obě hodnoty, pokud jsou k dispozici v položce kmenových dat. U některých oblastí můžete také nastavit filtr pro převod pouze podmnožiny hodnot, například finanční účty.
3. On the **Prices Incl. VAT** FastTab, choose which line types on orders for which you want to update unit prices. Jednotkové ceny na řádcích typu Zboží a Zdroj budou vždy aktualizovány.

### Nastavení převodu účto skupiny účto skupiny zboží

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Rate Change Setup**, and then choose the related link.
2. On the **VAT Rate Change Setup** page, choose either the **VAT Prod. Posting Group Conv.** or **Gen Prod. Posting Group Conv.** action.
3. In the **From Code** field, enter the current posting group.
4. In the **To Code** field, enter the new posting group.

### Provedení převodu změny sazby DPH

Nástroj pro změnu sazby DPH slouží ke správě změn základní sazby DPH. Provádění převodů DPH a obecné účto skupiny, slouží ke změně sazby DPH a udržování přesné vykazování DPH. V závislosti na nastavení jsou provedeny následující změny:

* DPH a obecné účto skupiny jsou převedeny.
* Změny jsou implementovány do účtů hlavní knihy, zákazníků, dodavatelů, otevřených dokladů, řádků deníku atd.

> [!IMPORTANT]  
> Before you perform VAT rate change conversion, you can test the conversion. To do so, follow the steps below, but make sure to clear the **Perform Conversion** and **VAT Rate Change Tool Completed** check boxes. During test conversion, the **Converted** field in the **VAT Rate Change Log Entry** table is cleared and the **Converted Date** field in the **VAT Rate Change Log Entry** table is blank. After the conversion is complete, choose **VAT Rate Change Log Entries** to view the results of the test conversion. Před provedením převodu ověřte každou položku. Ověřte zejména transakce, které používají starou sazbu DPH.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Rate Change**, and then choose the **VAT Rate Change Setup** link.
2. Ověřte, zda jste již nastavili převod DPH účto skupiny zboží nebo převod obecné účto skupiny zboží.
3. Choose the **Perform Conversion** check box.

   > [!IMPORTANT]  
   > Clear the **VAT Rate Change Tool Completed** check box. Toto políčko je automaticky zaškrtnuto po dokončení převodu změny sazby DPH.

4. Choose the **Convert** action.
5. After the conversion is complete, choose the **VAT Rate Change Log Entries** action to view the results of the conversion.

> [!IMPORTANT]  
> After the conversion, the **Converted** field in the **VAT Rate Change Log Entry** table is chosen and the **Converted Date** field in the **VAT Rate Change Log Entry** table displays the conversion date.

## Viz také

[Set Up Value-Added Tax](finance-setup-vat.md)  
[Setting Up Unrealized Value Added Tax](finance-setup-unrealized-vat.md)  
[Report VAT to a Tax Authority](finance-how-report-vat.md)  
[Work with VAT on Sales and Purchases](finance-work-with-vat.md)  
[Local functionality in Business Central](about-localization.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]