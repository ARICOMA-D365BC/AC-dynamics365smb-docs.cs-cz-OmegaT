---
    title: Create Bank Deposits
    description: You can make deposits to maintain a transaction record that contains information that can be applied to outstanding invoices and credit memos.
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.search.form: 10140, 10141, 10143, 10144, 10146, 10147, 10148, 36646
    ms.date: 04/01/2021
    ms.author: bholtorf

---
# Vytváření bankovních vkladů
> [!NOTE]
> Možnost vytvářet bankovní vklady je novinkou ve vlně 1 vydání Business Central 2022 pro mnoho verzí pro jednotlivé země. Pokud jste před tímto vydáním používali Business Central ve Spojených státech, Kanadě nebo Mexiku, možná používáte dřívější funkce. Můžete pokračovat, ale nové funkce nahradí staré v budoucí verzi. Chcete-li začít používat nové funkce popsané v tomto článku, může správce přejít na stránku **Správa funkcí** a zapnout možnost **Aktualizace funkcí: Standardizované odsouhlasení banky a vklady**.

Použijte stránku **Bankovní vklady** k registraci vkladů jako jednoho dokumentu, který zaúčtuje jeden nebo více záznamů na bankovní účet. Bankovní vklady se obvykle používají k registraci hotovostních vkladů. Stránka Bankovní vklady je k dispozici v nabídce **Správa hotovosti** v Centru rolí manažera a dalších pracovních plochách rolí, které se zabývají správou hotovosti.

Částky na bankovních vkladech mohou pocházet z několika zdrojů:

* Prodeje, použití finančního účtu pro výnosy.
* Platby zákazníků.
* Vrácení hotovosti od prodejců nebo hotovostní platby na ně.

Řádky bankovních vkladů obsahují informace o jednotlivých vkladech, například šeky od zákazníků. The total of the amounts on the lines must add up to the total amount of the deposit.

Po vyplnění informací o vkladu a řádků je musíte zaúčtovat. Zaúčtováním se aktualizují příslušné účetní knihy. Tyto knihy zahrnují hlavní knihu a knihy bank, zákazníka a dodavatele. Zaúčtované vklady jsou uloženy pro budoucí použití na stránce **Zaúčtované bankovní vklady**.

Přehled **Bankovní vklad** zobrazuje vklady zákazníků a dodavatelů s původní částkou vkladu, částkou vkladu, která zůstává otevřená, a použitou částkou. Přehled také zobrazuje celkovou zaúčtovanou částku vkladu, kterou je třeba odsouhlasit.

## Než začnete
Než budete moci používat bankovní vklady, musíte nastavit několik věcí. Musíte mít připravenou číselnou řadu a šablonu finančního deníku. Měli byste také určit, zda chcete zaúčtovat částky bankovního vkladu jako paušální částku. To znamená jako součet všech částek na depozitních řádcích. V opačném případě je každý řádek zaúčtován jako samostatná položka. Zaúčtování vkladu jako jedné položky bankovní knihy může usnadnit odsouhlasení banky.

### Číselné řady a paušální vklady
Musíte nastavit číselnou řadu pro bankovní vklady a poté zadat řadu v poli **Čísla bankovních vkladů** na stránce **Nastavení prodeje a pohledávek**. Pro další informace se podívejte na [Vytvořit číselné řady](ui-create-number-series.md).

Také na stránce **Nastavení prodeje a pohledávek**, pokud chcete zaúčtovat vklady jako paušální částky a ne jako jednotlivé řádky, zapněte přepínač **Účtovat bankovní vklady jako paušální částku**. Posting a deposit as a lump sum, which creates one bank ledger entry for the full amount of the deposit, can make it easier to do bank reconciliation.

### Šablony finančních deníků pro bankovní vklady
Musíte také vytvořit šablonu finančního deníku pro vklady. Hlavní deníky používáte k zaúčtování položek na účty bank, zákazníků, dodavatelů, dlouhodobého majetku a hlavní knihy. Šablony deníku navrhují hlavní deník tak, aby vyhovoval účelu vaší práce. To znamená, že pole v šabloně deníku jsou přesně ta, která potřebujete.

Vklady budou hotovostní příjmy, takže možná budete chtít znovu použít číselné řady pro deníky příjmů hotovosti. Případně, pokud potřebujete rozlišovat mezi položkami bankovního vkladu a deníku přijaté hotovosti, použijte jinou číselnou řadu.

Budete také muset vytvořit dávkovou úlohu pro šablonu. Chcete-li vytvořit dávkovou úlohu, na stránce **Šablony finančního deníku** vyberte akci **Dávky**. Další informace naleznete v tématu [Použití šablon deníku a dávek](ui-work-general-journals.md#use-journal-templates-and-batches).

## Dimenze na řádcíh bankovních vkladů
Řádky bankovního vkladu automaticky použijí výchozí dimenze, které jste zadali v polích **Kód oddělení** a **Kód skupiny zákazníků**. Když v poli **Typ účtu** vyberete **Zákazník** nebo **Dodavatel**, výchozí hodnoty nahradí dimenze zadané pro zákazníka nebo dodavatele. V případě potřeby můžete změnit dimenze na řádcích.

> [!TIP]
> Dimenze na řádcích jsou nastaveny podle výchozích priorit dimenzí. Dimenze rádků mají přednost před dimenzemi záhlaví. Chcete-li se vyhnout konfliktům, můžete vytvořit pravidla, která upřednostňují, kdy použít dimenzi v závislosti na zdroji. Chcete-li změnit způsob stanovení priority dimenzí, můžete změnit jejich pořadí na stránce **Výchozí priority dimenzí**. Další informace naleznete v tématu [Nastavení výchozích priorit dimenzí](finance-dimensions.md#to-set-up-default-dimension-priorities).

## Vytvoření bankovního vkladu
1. Vyberte žárovku![, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Bankovní vklady** a poté vyberte související odkaz.
2. Zvolte **Nový** a otevřete stránku **Bankovní vklad**.
3. Vyberte šablonu finančního deníku, kterou jste vytvořili pro bankovní vklady.

   > [!NOTE]
   > Pokud má šablona finančního deníku více než jednu dávku, budete vyzváni k výběru jedné.

4. V poli **Číslo bankovního účtu** vyberte bankovní účet, na který chcete provést vklad.

   > [!TIP]
   > Pomocí akcí **Karta účtu** a **Položky účtu** můžete znovu zkontrolovat, zda provádíte vklad na správný účet, a vyhledat položky pro vybraný bankovní účet. Například zjistit, zda byly na účet provedeny podobné vklady.

5. V poli **Celková částka vkladu** zadejte celkovou částku vkladu. Tento součet musí být součtem částek na všech řádcích.
6. Podle potřeby vyplňte zbývající pole. [!INCLUDE [tooltip-inline-tip_md](../archive/SetupAndAdministration/includes/tooltip-inline-tip_md.md)]

   Datum v poli **Zúčtovací datum** a dimenze v polích **Kód oddělení** a **Kód skupiny zákazníků** budou přiřazeny k řádkům, které vytvoříte pro bankovní vklad. V případě potřeby je můžete změnit.

7. V závislosti na tom, zda chcete zaúčtovat bankovní vklad jako jednorázovou částku nebo každý řádek jednotlivě do hlavní knihy banky, zapněte nebo vypněte přepínač **Zaúčtovat jako jednorázovou částku**. Výchozí nastavení pochází ze stejného přepínače na stránce **Nastavení prodeje a pohledávek**.

   > [!NOTE]
   > Pole **Kód měny** zobrazuje měnu, která je určena pro bankovní účet, který jste vybrali. Nemůžete si vybrat jinou měnu.

8. Na pevné záložce **Řádky** vytvořte nový řádek pro každou hotovostní platbu, kterou chcete vložit.
9. V poli **Typ účtu** určete, odkud platba pochází. U bankovních vkladů je typ obvykle **Zákazník** nebo **Dodavatel**.

   > [!NOTE]
   > Můžete také zaregistrovat hotovostní platbu dodavateli. Chcete-li to provést, zvolte **Dodavatel** a poté zadejte částku platby jako záporné číslo do pole **Částka Dal** na řádku.

10. Do pole **Číslo dokladu** zadejte číslo dokladu faktury, ze které dobropisová částka pochází. Můžete použít číslo dokumentu pro každý řádek nebo stejné číslo pro všechny řádky.

   > [!TIP]
   > Pro finanční záznamy obvykle nemusíte vyplňovat pole **Typ dokumentu**. Pokud například vkládáte hotovost z denního prodeje, ponecháte pole prázdné. Pokud vkládáte hotovost z platby zákazníka, zvolíte **Platba**.

11. Pokud vkládáte hotovostní platbu za konkrétní fakturu zákazníka, zvolte akci **Použít záznamy** a poté zadejte číslo faktury do pole **Platí pro ID**.
12. Pokud jste připraveni zaúčtovat bankovní vklad, vyberte akci **Zaúčtovat**.

   > [!TIP]
   > Před odesláním vkladu můžete pomocí akce **Testovací zpráva** zkontrolovat svá data. Sestava ukáže, zda existují nějaké problémy, například chybějící data, které zabrání zaúčtování.

## Vyhledání zaúčtovaných bankovních vkladů
Na stránce **Zaúčtované bankovní vklady** jsou uvedeny předchozí vklady vaší společnosti. V seznamu si můžete prohlédnout komentáře a dimenze, které byly zadány pro vklady. Můžete otevřít bankovní vklad a zobrazit další podrobnosti a odtud můžete dále zkoumat. Můžete například zvolit akci Najít položky pro zobrazení zaúčtovaných položek banky. Ze záznamu položky bankovní knihy můžete najít odpovídající zaúčtovanou položku hlavní knihy.

Chcete-li vyhledat všechny položky hlavní knihy pro zaúčtované řádky vkladu, přejděte na stránku **Finanční žurnál** a použijte akci **Hlavní kniha**. Zde najdete všechny položky hlavní knihy, včetně položek pro zákazníky a dodavatele.

## Zrušení zaúčtovaného bankovního vkladu
Chcete-li zrušit zaúčtovaný vklad, přejděte na stránku **Finanční žurnál**, vyhledejte registr vkladu a poté vyberte akci **Stornovat žurnál.**

> [!NOTE]
> Stornovat lze pouze žurnál, který obsahuje jeden typ položky. To znamená, že žurnál musí obsahovat pouze položky zákazníka nebo položky dodavatele, ale ne obojí. Pokud žurnál obsahuje obojí, musíte vklad ručně zrušit.

## Viz také
[Finance](finance.md)    
[Nastavení financí](finance.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]



