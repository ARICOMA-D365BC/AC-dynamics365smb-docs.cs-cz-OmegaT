---
title: Apply Payments to Unpaid Sales Documents
description: You apply amounts paid by customers to related sales documents and post the payment to update the customer, general ledger, and bank ledger entries.
author: SorenGP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment process, cash receipts, customer payment
ms.search.form: 1290, 1294, 1287
ms.date: 04/01/2021
ms.author: edupont

---
# Odsouhlasení plateb zákazníků ze seznamu nezaplacených prodejních dokladů
Když vaši zákazníci provedli platby na váš elektronický bankovní účet, musíte použít každou zaplacenou částku na související prodejní doklad a poté zaúčtovat platbu, abyste aktualizovali odběratele, hlavní knihu a položky bankovní knihy. V závislosti na vašich obchodních potřebách můžete dostat zaplaceno a zaregistrovat tuto platbu různými způsoby: ručně, automaticky a prostřednictvím platebních služeb.

> [!NOTE]  
> Můžete provádět stejné úkoly, včetně plateb dodavatele na stránce **Deník odsouhlasení plateb** pomocí funkcí pro import výpisu z účtu, automatickou aplikaci a odsouhlasení bankovního účtu. Pro více informací navštivte [Automatické odsouhlasení plateb](receivables-how-reconcile-payments-auto-application.md).

Stránka **Registrovat platby zákazníků** je navržena tak, aby vám pomohla při vyrovnávání interních účtů pomocí skutečných peněžních údajů, aby bylo zajištěno, že platby jsou od zákazníků shromažďovány efektivně. Tento nástroj pro zpracování plateb vám umožňuje rychle ověřit a zaúčtovat jednotlivé nebo paušální platby, zpracovat zlevněné platby a najít konkrétní nezaplacené doklady, za které se platí.

Platby pro různé zákazníky, kteří mají různá data plateb, musí být zaúčtovány jako jednotlivé platby. Platby pro stejného zákazníka se stejným datem platby lze zaúčtovat jako paušální platbu. To je užitečné například v případě, že zákazník provedl jednu platbu, která pokrývá více prodejních faktur.

## Nastavení deníku registrace plateb
Protože můžete účtovat různé typy plateb na různé vyrovnávací účty, musíte před zahájením zpracování plateb zákazníků vybrat vyrovnávací účet na stránce **Nastavení registrace plateb**. Pokud vždy účtujete na stejný vyrovnávací účet, můžete tento účet nastavit jako výchozí a vyhnout se tomuto kroku při každém otevření stránky **Registrovat platby zákazníka**.

1. Zvolte ![žárovku, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Nastavení registrace plateb** a pak zvolte související odkaz.

   Případně na stránce **Registrovat platby zákazníka** vyberte akci **Nastavení**.
2. Vyplňte pole na stránce **Nastavení registrace plateb**. Vyberte pole, ve kterém si chcete přečíst krátký popis pole nebo odkaz na související informace.

## Individuální registrace plateb zákazníka

1. Zvolte žárovku![, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Zaregistrovat platby zákazníka** a pak zvolte související odkaz.

   Stránka **Registrovat platby zákazníka** zobrazuje všechny zaúčtované doklady, pro které lze platbu zaregistrovat. Stránku lze také otevřít ze stránek **Zákazníci** a **Karta zákazníka**, kde je automaticky filtrována pro zadaného zákazníka.
2. Zaškrtněte políčko **Platba provedena** na řádku, který představuje zaúčtovaný doklad, pro který byla provedena platba.

   Pokud je na stránce **Nastavení registrace plateb** zaškrtnuto políčko automatické vyplnění Data **pak,**  je pracovní datum zadáno **do pole Datum přijetí**.
3. Do pole **Datum přijetí** zadejte datum, kdy byla platba provedena. Toto datum se může lišit od pracovního data.
4. Do pole **Přijatá částka** zadejte částku, která byla zaplacena.

   U úplných plateb je to stejné jako částka v poli **Zbývající částka** na řádku. U částečných plateb je tato částka nižší než částka v poli **Zbývající částka** na řádku.
5. Opakujte kroky 2 až 4 pro další řádky, které představují zaúčtované doklady, pro které jsou prováděny platby.
6. Vyberte akci **Zaúčtovat platby**.

Informace o platbě jsou zaúčtovány pro doklady reprezentované řádky, kde je zaškrtnuto políčko **Platba provedena**.

Položky plateb jsou zaúčtovány do hlavní knihy, banky a účtů zákazníků. Každá platba se použije na související zaúčtovaný prodejní doklad.

## Odsouhlasení paušálních plateb
1. Zvolte žárovku![, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Platební registrace** a pak zvolte související odkaz.
2. Zaškrtněte políčko **Platba provedena** na řádcích, které představují zaúčtované doklady pro stejného zákazníka, pro kterého byla provedena paušální platba.

   > [!NOTE]  
   > Zákazník v poli **Jméno** musí být stejný na všech řádcích, které budou zaúčtovány jako paušální platba.

   Pokud je na stránce **Nastavení registrace plateb** zaškrtnuto políčko **Datum automatického vyplnění** pak, je pracovní datum vyplněno v poli **Datum přijetí**.
3. Do pole **Datum přijetí** zadejte datum, kdy byla platba provedena. Toto datum se může lišit od pracovního data.

   > [!NOTE]  
   > Toto datum musí být stejné na všech řádcích, které budou zaúčtovány jako paušální platba.
4. V poli **Přijatá částka** zadejte částky na více řádcích, které se sečítají až do paušální částky.

   > [!TIP]  
   > Pokuste se zaúčtovat co nejvíce úplných plateb s paušální částkou. Zadejte částky, které jsou stejné jako částka v poli **Zbývající částka** na co největším počtu řádků.
5. Opakujte kroky 2 až 4 pro další řádky, které představují zaúčtované doklady pro stejného zákazníka, pro kterého byla provedena paušální platba.
6. Vyberte akci **Zaúčtovat jako paušální platbu**. Zadané informace o platbě jsou zaúčtovány pro doklady reprezentované řádky, kde je zaškrtnuto políčko **Platba provedena**.

Položky plateb jsou zaúčtovány do hlavní knihy, banky a účtů odběratelů. Každá platba se použije na související zaúčtovaný prodejní doklad.

Pokud platba v bance není reprezentována řádkem na stránce **Registrace platby**, může to být proto, že související dokument ještě nebyl zaúčtován. V takovém případě můžete pomocí funkce vyhledávání rychle najít dokument a odeslat jej ke zpracování platby. Další informace naleznete v části [Vyhledání specifického prodejního dokladu, který není plně fakturován](receivables-how-reconcile-customer-payments-list-unpaid-sales-documents.md#to-find-a-specific-sales-document-that-is-not-fully-invoiced).

Pokud platba v bance není reprezentována žádným dokumentem v [! INCLUDE[prod_short](includes/prod_short.md)] pak můžete otevřít předvyplněný hlavní deník ze stránky **Registrace platby** a zaúčtovat platbu přímo na vyrovnávací účet bez použití platby na doklad. Případně můžete chtít evidovat platbu v deníku, dokud nebude vyřešen původ platby. Další informace naleznete v části [Zaznamenávání nebo zaúčtování platby bez souvisejícího dokumentu](receivables-how-reconcile-customer-payments-list-unpaid-sales-documents.md#to-record-or-post-a-payment-without-a-related-document).

## Pro ruční zpracování plateb zákazníků se slevami
Pokud jste se se svým zákazníkem dohodli na slevě z platby, pak mohou být částky platby nižší než částky faktury, pokud platba proběhne před dohodnutým datem slevy.

Následující postupy vysvětlují čtyři různé způsoby zaúčtování zlevněných plateb na stránce **Registrace plateb**.

* Částka platby se rovná zbývající diskontované částce a datum platby je před datem slevy. Platbu zaúčtujete tak, jak je.
* Částka platby se rovná zbývající diskontované částce, ale datum platby je po datu slevy. Platbu zaúčtujete jako částečnou. Dokument zůstává otevřen pro vyzvednutí/zaplacení zbývající částky. Případně můžete nastavit datum slevy později, abyste umožnili platbu v plné výši.
* Částka platby je nižší než zbývající diskontovaná částka. Platbu zaúčtujete jako částečnou. Dokument zůstává otevřen pro vyzvednutí/zaplacení zbývající částky.
* Částka platby je vyšší než zbývající diskontovaná částka. Platby zaúčtujete tak, jak jsou. Zaúčtuje se pouze zbývající částka. Dodatečná částka je připsána zákazníkovi.

### Zpracování částky platby, která se rovná diskontované částce a jejíž datum platby je před datem slevy
1. Zvolte žárovku![, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Platební registrace** a pak zvolte související odkaz.
2. Zadejte částku platby do pole **Přijatá částka**. Částka se rovná částce v **zůstatku částky  po slevě**.

   Zaškrtávací políčko **Platba byla provedena** je automaticky zaškrtnuto a pole **Datum přijetí** je vyplněno pracovním datem.
3. Do pole **Datum přijetí** zadejte datum platby. Datum je před datem v **datu. skonta**.
4. Ověřte, zda pole **Zbývající částka** obsahuje nulu (0).
5. Zvolte akci **Zaúčtovat platby** pro zaúčtování úplné platby na hlavní knihu, bankovní účty a účty zákazníků.

### Zpracování částky platby, která se rovná diskontované částce, ale jejíž datum platby je po datu slevy
1. Zvolte žárovku![, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Platební registrace** a pak zvolte související odkaz.
2. Zadejte částku platby do pole **Přijatá částka**. Částka se rovná částce v **zůstatku částky  po slevě**.

   Zaškrtávací políčko **Platba byla provedena** je automaticky zaškrtnuto a pole **Datum přijetí** je vyplněno pracovním datem.
3. Do pole **Datum přijetí** zadejte datum platby, které je po datu v **Platba skonta**. Pole data se změní na červené písmo a v dolní části stránky se zobrazí chybová zpráva.

   > [!TIP]  
   > Pokud chcete udělat výjimku a poskytnout slevu, i když je platba opožděná, postupujte takto:
4. Vyberte akci **Podrobnosti**.
5. Na stránce **Platební údaje** v **datu Skonta** na pevné záložce **Skonto**, zadejte datum, které je po datu do pole **Datum přijetí** na stránce **Registrace platby</g5 > .

   Chybová zpráva a červené písmo zmizí a můžete pokračovat ve zpracování zvýhodněné platby.
6. Ověřte, zda pole **Zbývající částka** obsahuje částku, která zbývá k zaplacení celé fakturované částky.
7. Zvolte akci **Zaúčtovat platby**, chcete-li zaúčtovat částečnou platbu na účty hlavní knihy, banky a odběratele.

Související dokument zůstane otevřený.

### Zpracování platby, která je nižší než zbývající diskontovaná částka
1. Zvolte žárovku![, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Platební registrace** a pak zvolte související odkaz.
2. Zadejte částku platby do pole **Přijatá částka**. Částka je nižší než částka v **zůstatku částky  po slevě**.

   Zaškrtávací políčko **Platba byla provedena** je automaticky zaškrtnuto a pole **Datum přijetí** je vyplněno pracovním datem.
3. Do pole **Datum přijetí** zadejte datum platby. Datum je před datem v **datu. skonta**.
4. Ověřte, zda pole **Zbývající částka** obsahuje částku, která zbývá k zaplacení zlevněné částky.
5. Zvolte akci **Zaúčtovat platby**, chcete-li zaúčtovat částečnou platbu na účty hlavní knihy, banky a odběratele.

Související dokument zůstane otevřený.

### Zpracování platby, která je vyšší než zbývající zlevněná částka
1. Zvolte žárovku![, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Platební registrace** a pak zvolte související odkaz.
2. Zadejte částku platby do pole **Přijatá částka**. Částka je vyšší než částka v **zůstatku částky  po slevě**.

   Zaškrtávací políčko **Platba byla provedena** je automaticky zaškrtnuto a pole **Datum přijetí** je vyplněno pracovním datem.
3. Do pole **Datum přijetí** zadejte datum platby. Datum je před datem v **datu. skonta**.
4. Ověřte, zda pole **Zbývající částka** obsahuje nulu (0).
5. Zvolte akci **Zaúčtovat platby** pro zaúčtování úplné platby na hlavní knihu, bankovní účty a účty zákazníků.

The related document is closed, and the customer is credited the excess payment amount.

## Chcete-li najít specifický prodejní doklad, který není plně fakturován
Stránka **Registrace plateb** vám pomůže v úkolech potřebných k vyrovnání interních účtů se skutečnými hotovostními částkami, aby bylo zajištěno efektivní inkaso od zákazníků. Zobrazuje neuhrazené příchozí platby jako řádky, které představují prodejní doklady, kde je splatná částka.

Obvykle, když byla provedena platba, zaznamenána v bance nebo jinak, související prodejní nebo nákupní doklad je reprezentován jako řádek na stránce **Registrace platby**, protože příslušný dokument čeká na zaúčtování platby proti dlužné částce. Někdy však platba, která byla provedena, není na stránce znázorněna řádkem **Registrace platby** , obvykle proto, že příslušný doklad nebyl zcela zaúčtován.

Na stránce **Hledání dokumentu** můžete vyhledávat mezi dokumenty, které nejsou plně fakturovány. Můžete vyhledávat na základě jednoho nebo více z následujících kritérií:

* Číslo dokladu
* Množství nebo rozsah částek

Následující postup vysvětluje, jak najít konkrétní dokument pomocí obou kritérií vyhledávání.

1. Zvolte žárovku![, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Platební registrace** a pak zvolte související odkaz.
2. S ukazatelem na libovolném řádku zvolte akci **Hledat dokumenty**.
3. Na stránce **Vyhledávání dokumentů** zadejte hledanou hodnotu do pole **Číslo dokumentu**.

   > [!NOTE]  
   > Hodnota, kterou zadáte do tohoto pole, je uzavřena skrytými zástupnými znaky. To znamená, že funkce vyhledá všechna čísla dokumentů, která obsahují zadanou hodnotu.
4. V poli **Částka** zadejte konkrétní částku, která existuje v dokladu, který chcete najít.
5. V poli **Tolerance částky %** zadejte procentuální hodnotu pro definování rozsahu částek, které chcete vyhledat pro otevřený dokument.

   Pokud zadáte hodnotu 10, funkce vyhledá částky v rozsahu mezi deseti procenty nižšími a o deset procent vyššími, než je hodnota v poli **Částka**.
6. Zvolte akci **Hledat**.

Funkce Hledat vyhledává mezi dokumenty, které nejsou plně fakturovány na základě zadaných kritérií.

Pokud kritéria splňuje jeden nebo více dokumentů, otevře se stránka **Výsledek hledání dokumentu**, na které se zobrazí řádky, které tyto dokumenty představují. Každý řádek obsahuje číslo dokladu, popis a částku, abyste mohli snadno najít konkrétní doklad, například na základě informací z vašeho bankovního výpisu.

Pokud platba v bance není reprezentována žádným dokumentem v [! INCLUDE[prod_short](includes/prod_short.md)] pak můžete otevřít předvyplněný hlavní deník ze stránky **Registrace platby** a zaúčtovat platbu přímo na vyrovnávací účet bez použití platby na doklad. Případně můžete chtít evidovat platbu v deníku, dokud nebude vyřešen původ platby.

## Zaznamenání nebo zaúčtování platby bez souvisejícího dokladu
Pokud platba v bance není reprezentována žádným dokumentem v [! INCLUDE[prod_short](includes/prod_short.md)], pak můžete otevřít předvyplněný řádek hlavního deníku ze stránky **Registrace platby** a zaúčtovat platbu přímo na vyrovnávací účet bez použití platby na doklad. Případně můžete chtít zaznamenat platbu do deníku, dokud nebude objasněn původ platby.

1. Zvolte žárovku![, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Platební registrace** a pak zvolte související odkaz.

   Pokračujte v zaznamenávání nezdokumentované platby.
2. Zvolte akci **Hlavní deník**.

   Otevře se stránka **Finanční deník** s jedním řádkem předvyplněným vyrovnávací účtem dávky deníku, který je nastaven na stránce **Nastavení registrace plateb**.
3. Vyplňte zbývající pole na řádku finančního deníku, například částku a číslo zákazníka nebo jiné informace z bankovního výpisu. Další informace naleznete v tématu [Zaúčtování transakcí přímo do hlavní knihy](finance-how-post-transactions-directly.md).

Můžete buď zaúčtovat řádek deníku a aktualizovat součet na vyrovnávacím účtu. Případně můžete nechat řádek deníku nezaúčtovaný a možná k němu připojit poznámku, že platba vyžaduje další analýzu.

Pokud ponecháte řádek deníku nezaúčtovaný, přidá se k hodnotě v poli **Nezaúčtovaný zůstatek** v dolní části stránky **Registrace platby**.

## Viz také
[Správa pohledávek  [  
  Prodej[<x6/>  
[Práce s [!INCLUDE<x7/>prod_short<x8/>]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]