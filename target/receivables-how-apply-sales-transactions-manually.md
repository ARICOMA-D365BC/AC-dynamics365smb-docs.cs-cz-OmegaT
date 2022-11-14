---
title: Reconcile Customer Payments with the Cash Receipt Journal or from Customer Ledger Entries
description: Describes how to apply customer cash receipts or refunds to one or more open customer ledger entries. This is part of reconciling customer payments.
author: SorenGP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment process, cash receipt
ms.search.form: 25, 255
ms.date: 04/01/2021
ms.author: edupont

---
# Odsouhlaste platby zákazníků s deníkem přijaté hotovosti nebo ze záznamů v položkách zákazníků

Když obdržíte platbu v hotovosti od zákazníka nebo vrátíte hotovost, můžete platbu nebo refundaci použít k uzavření otevřených debetních nebo kreditních položek. Můžete určit částku, kterou chcete použít. Můžete například použít částečné platby na záznamy v položkách zákazníků. Uzavření položek zákazníka udržuje statistiky zákazníka, výpisy z účtu, finanční náklady atd. aktuální.

> [!TIP]  
> Na stránce **Položky zákazníka** červené písmo znamená, že související platba je po datu splatnosti. Pokud se platby po splatnosti stávají problémem, můžeme vám pomoci snížit jejich frekvenci. Můžete povolit rozšíření **Předpovědi opožděných plateb** , které používá prediktivní model, který jsme vytvořili ve službě Azure Machine Learning k předpovědi načasování plateb. Tyto předpovědi vám pomohou snížit neuhrazené pohledávky a vyladit strategii vymáhání pohledávek. Pokud se například předpokládá, že platba bude zpožděna, můžete upravit platební podmínky nebo způsob platby pro zákazníka. Další informace naleznete v tématu [Předpovědi pozdních plateb](ui-extensions-late-payment-prediction.md).

Položky zákazníka můžete použít několika způsoby:

* Zadáním informací na vyhrazené stránky:
   * Stránka **Deník odsouhlasení plateb**. Další informace naleznete v části [Automatické použití plateb a Odsouhlasení bankovních účtů](receivables-apply-payments-auto-reconcile-bank-accounts.md).
   * Stránka **Registrace platby**. Další informace naleznete v tématu [Odsouhlasení plateb odběratele ze seznamu nezaplacených prodejních dokladů](receivables-how-reconcile-customer-payments-list-unpaid-sales-documents.md).
   * **Deník přijaté hotovosti**. Tato možnost je popsána níže.
* Vyplněním **Čísla vyrovnání dokladu. Číslo** na dokladech prodejního dobropisu. Tato možnost je popsána níže.
* Pomocí akce **Nastavit ID** pro položku zákazníka. Tato možnost je popsána níže.
* Pomocí akce **Použít položky** na stránce **Bankovní vklad** a následným zadáním čísla faktury do pole **vztahuje se pro ID**. Další informace naleznete v tématu [Vytváření bankovních vkladů](bank-create-bank-deposits.md).

> [!NOTE]  
> Pokud pole **Metoda vyrovnání** na zákaznické kartě obsahuje **Použít k nejstarším**, platby se použijí na nejstarší otevřený kreditní záznam, pokud ručně neurčíte záznam. Pokud je metoda vyrovnání **Ruční**, vždy aplikujete položky ručně.

## Vyplnění a zaúčtování deníku příjemek hotovosti
Deník pokladních příjmů je typ finančního deníku. Můžete jej použít k zaúčtování transakcí na účty hlavní knihy, banky, zákazníka, dodavatele a dlouhodobého majetku. Platbu můžete použít na jednu nebo více debetních položek při zaúčtování platby. Můžete také požádat ze zaúčtovaných položek později.
1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Deníky přijaté hotovosti** a poté vyberte související odkaz.
2. Vyberte akci **Upravit deník**.
3. Vyberte příslušnou dávku v poli **Název dávky**.
4. Vyplňte pole **Zúčtovací datum**.
5. V poli **Typ dokladu** vyberte **možnost Platba**.

   Pole **Číslo dokladu** je vyplněno číselnou řadou přiřazenou dávkou.
6. Použijte pole **Číslo externího dokladu** k uložení identifikátoru, jako je číslo šeku zákazníka.
7. V poli **Typ účtu** vyberte **možnost Zákazník**.
8. V poli **Číslo účtu** vyberte příslušný finanční účet.
9. Pokud chcete zaúčtovat aplikaci současně se zaúčtováním deníku, proveďte jednu z následujících akcí.
10. V poli **Typ vyrovnávacího účtu** vyberte **Deník finančních účtů** pro hotovostní platby a **Bankovní účet** pro ostatní platby.
11. V poli **Číslo vyrovnávacího účtu** vyberte pokladní účet pro hotovostní platby nebo příslušný bankovní účet pro ostatní platby.
12. Zaúčtujte deník.

## Použití platby na jednu položku zákazníka
1. Vyberte žárovku![, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Deník přijaté hotovosti** a vyberte související odkaz.
2. Vyberte akci **Upravit deník**.
3. Na prvním řádku deníku zadejte příslušné informace o položce, která má být použita.
4. Do pole **Typ dokladu** zadejte **Platba**.
5. Do pole **Typ účtu** zadejte **Zákazník**.
6. V poli **Číslo Typ účtu**, zadejte **Bankovní účet**.
7. V **příslušném dokumentu Číslo** vyberte pole pro otevření stránky **Použít položky zákazníka**.
8. Na stránce **Použít položky zákazníka** vyberte položku, na kterou chcete platbu použít.
9. Do pole **Částka k použití** zadejte částku, kterou chcete na záznam použít. Pokud částku nezadáte, použije se maximální částka.

   V dolní části stránky **Použít položky zákazníků** můžete vidět konkrétní částku v poli **Použitá částka** a také to, zda je aplikace vyrovnaná.
10. Zvolte tlačítko **OK**. **Na stránce Deník přijaté hotovosti** se nyní zobrazuje položka v **Číslo vyrovnání dokladu. Typ** a **Číslo vyrovnání dokladu. Číslo** pole.
11. Zaúčtování deníku přijaté hotovosti.

## Použití platby na více položek zákazníka
1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Deníky přijaté hotovosti** a poté vyberte související odkaz.
2. Vyberte akci **Upravit deník**.
3. Na prvním řádku deníku zadejte příslušné informace o položce, která má být použita.
4. Do pole **Typ dokladu** zadejte **Platba**.
5. Do pole **Typ účtu** zadejte **Zákazník**.
6. V poli **Číslo Typ účtu**, zadejte **Bankovní účet**.
7. V poli **Částka** zadejte celou platbu jako zápornou částku.
8. Chcete-li při zaúčtování použít platbu na více položek zákazníka, vyberte akci **Použít položky**.
9. Vyberte řádky s položkami, na které chcete použít použitou položku, a poté vyberte akci **Nastavit ID**.
10. Na každém řádku v poli **Částka k použití** zadejte částku, kterou chcete použít pro jednotlivou položku. Pokud částku nezadáte, použije se maximální částka.

   V dolní části stránky **Použít položky zákazníků** můžete vidět konkrétní částku v poli **Použitá částka** a také to, zda je aplikace vyrovnaná.
11. Zvolte tlačítko **OK**.
12. Zaúčtování deníku přijaté hotovosti.

## Použití dobropisu na jednu položku zákazníka
1. Vyberte žárovku![, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Prodejní dobropisy** a poté vyberte související odkaz.
2. Otevřete příslušný prodejní dobropis.
3. Chcete-li použít dobropis na jednu položku zákazníka při zaúčtování, v **Číslo vyrovnání dokladu Číslo** vyberte položku, na kterou chcete platbu použít.
4. Na řádku v poli **Částka k použití** zadejte částku, kterou chcete u položky použít.

   Pokud částku nezadáte, aplikace automaticky použije maximální částku. V dolní části stránky **Použít položky zákazníků** můžete vidět konkrétní částku v poli **Použitá částka** a také to, zda je aplikace vyrovnaná.
5. Zvolte tlačítko **OK**. Na stránce **Dobropis prodeje** se nyní zobrazuje položka, kterou jste vybrali a zadali do **Číslo vyrovnání dokladu. Typ** a **Číslo vyrovnání dokladu. Číslo** pole. A částku dobropisu, který má být zaúčtován, upravenou o případné platební slevy.
6. Zaúčtujte dobropis.

## Použití dobropisu na více položek odběratele
1. Vyberte žárovku![, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Prodejní dobropisy** a poté vyberte související odkaz.
2. Otevřete příslušný prodejní dobropis.
3. Chcete-li použít dobropis na více položek zákazníka při zaúčtování, vyberte akci **Použít položky**.
4. Vyberte řádky s položkami, na které chcete použít použitou položku, a poté vyberte akci **Nastavit ID**.
5. Na každém řádku v poli **Částka k použití** zadejte částku, kterou chcete použít pro jednotlivou položku. Pokud částku nezadáte, použije se maximální částka.

   V dolní části stránky **Použít položky zákazníků** můžete vidět konkrétní částku v poli **Použitá částka** a také to, zda je aplikace vyrovnaná.
6. Zvolte tlačítko **OK**. Stránka **Prodejní dobropis** nyní zobrazuje částku dobropisu, který má být zaúčtován, upravenou o případné platební slevy.
7. Zaúčtujte dobropis.

## Použití zaúčtovaných položek zákazníka
1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi.](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Zákazníci** a poté vyberte související odkaz.
2. Otevřete kartu zákazníka s položkami, které chcete použít.
3. Vyberte akci **Položky hlavní knihy** a poté vyberte řádek s položkou, která bude použitou položkou.
4. Vyberte akci **Vyrovnat položky**. The **Apply Customer Entries** page opens showing the open entries for the customer.
5. Vyberte řádky s položkami, na které chcete použít použitou položku, a pak zvolte akci **Nastavit ID**
6. Pro každý řádek v poli **Částka k použití** zadejte částku, kterou chcete použít na jednotlivou položku. Pokud částku nezadáte, použije se maximální částka.

   V dolní části stránky **Použít záznamy zákazníků** můžete v poli **Použitá částka** vidět konkrétní částku.
7. Vyberte akci **Účtovat vyrovnání**. Zobrazí se stránka **Účtovat vyrovnání** s číslem dokumentu žádajícího záznamu a datem zaúčtování záznamu s posledním datem účtování.
8. Kliknutím na tlačítko **OK** zaúčtujete vyrovnání.

   Pokud zaúčtované vyrovnání vyústilo v uzavřené položky zákazníka, pole **Otevřít** je pro tyto položky hlavní knihy vymazáno.
9. Chcete-li zobrazit položky hlavní knihy, vyberte ![Žárovku, která otevře funkci Řekněte mi.](media/ui-search/search_small.png "Řekněte mi, co chcete udělat") ikona, zadejte **Zákazníci**a poté vyberte související odkaz. Přejdete na kartu příslušného zákazníka a zobrazte položky hlavní knihy.

V seznamu položek hlavní knihy na řádku, který obsahuje položku hlavní knihy, která byla plně použita, vidíte, že není zaškrtnuto políčko **Otevřít**.

> [!NOTE]  
> Poté, co vyberete záznam na stránce **Použít záznamy zákazníků** nebo několik záznamů nastavením **Platí pro ID**, pole **Použitá částka** na řádek deníku bude obsahovat součet zbývajících částek pro zaúčtované položky, které jste vybrali, pokud pole již něco neobsahuje. Pokud vyberete **možnost Použít na nejstarší** v poli Metoda vyrovnání na kartě zákazníka, **vyrovnání** proběhne automaticky.

## Chcete-li použít položky zákazníka v různých měnách mezi sebou navzájem, postupujte takto:
Pokud prodáváte zákazníkovi v jedné měně a přijímáte platbu v jiné měně, stále můžete fakturu použít k platbě.

Tady je příklad. Položku 1 použijete v jedné měně na položku 2 v jiné měně. Datum účtování na položce 1 se používá k vyhledání směnného kurzu, který se má použít k převodu částek na položce 2. Směnný kurz najdete na stránce **Směnné kurzy**.

Použití položek zákazníka v různých měnách musí být povoleno. Další informace naleznete v tématu [Povolení použití položek hlavní knihy v různých měnách](finance-how-enable-application-ledger-entries-different-currencies.md).

1. Vyberte žárovku![, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Deník přijaté hotovosti** a poté vyberte související odkaz.
2. Otevřete požadovaný deník a vyplňte první prázdný řádek deníku pomocí kódu měny.
3. Vyberte akci **Vyrovnat položky**.
4. Vyberte řádek s položkou, kterou chcete použít pro položku v deníku přijaté hotovosti, vyberte akci **Nastavit ID použití** a poté vyberte položku, kterou chcete použít.
5. Kliknutím na tlačítko **OK** se vraťte do deníku přijaté hotovosti.
6. Zaúčtujte prodejní deník.

> [!IMPORTANT]  
> Když použijete položky v různých měnách, položky se převedou na USD. I když jsou směnné kurzy pro obě měny pevné, například mezi USD a EUR, při jejich převodu na USD může existovat malá zbytková částka. Tyto malé zbytkové částky jsou zaúčtovány jako zisky a ztráty na účet uvedený v polích **Účet realizovaných zisků** nebo **Účet realizovaných ztrát** na stránce **Měny**. Pole **Částka (USD)** je také upraveno v položkách knihy dodavatelů.

## Chcete-li opravit vyrovnání položek zákazníků
Když opravíte vyrovnání, jsou vytvořeny a zaúčtovány opravné položky pro všechny záznamy. Opravné položky jsou stejné jako originály, ale mají opačné znaménko v poli **Částka**. Opravné položky zahrnují všechny položky hlavní knihy odvozené z vyrovnání Například platební sleva a kurzové zisky/ztráty. Položky, které byly vyrovnáním uzavřeny, se znovu otevřou.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi.](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Zákazníci** a poté vyberte související odkaz.
2. Otevřete příslušnou kartu zákazníka.
3. Vyberte akci **Položky hlavní knihy**.
4. Vyberte příslušnou položku hlavní knihy a poté vyberte akci **Zrušit vyrovnání položek**.
5. Případně vyberte akci **Podrobná položka hlavní knihy**.
6. Vyberte položku aplikace a poté vyberte akci **Zrušit vyrovnání položek**.
7. Vyplňte pole v záhlaví a poté vyberte akci **Zrušit vyrovnání položek**.

> [!IMPORTANT]  
> Pokud byl záznam aplikován více než jedním záznamem aplikace, musíte nejprve zrušit použití posledního záznamu aplikace.

## Viz také
[Správa pohledávek  [  
  Prodej[<x6/>  
[Práce s [!INCLUDE<x7/>prod_short<x8/>]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]