---
title: Collect Outstanding Balances
description: Learn how to remind your customers of outstanding payments. Send a customer statement, issue a reminder, or send a finance charge memo.
author: SorenGP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment due, debt, overdue, fee, charge, reminder
ms.search.form: 6, 25, 440, 443, 448, 452
ms.date: 02/09/2022
ms.author: edupont

---
# Inkaso nevyrovnaných zůstatků

Správa pohledávek zahrnuje kontrolu, zda jsou dlužné částky hrazeny včas. Pokud mají zákazníci platby po splatnosti, můžete jim odeslat sestavu **Výkaz zákazníka** jako připomínku. Případně můžete vydávat upomínky.

Pomocí upomínek můžete zákazníkům připomenout částky po splatnosti. Upomínky můžete také použít k výpočtu finančních poplatků, jako jsou úroky nebo poplatky, které je možné zahrnout do upomínky. Chcete-li zákazníkům strhnout úroky nebo poplatky, aniž byste jim připomínali částky po splatnosti, použijte vyúčtování finančních poplatků.

## Výpisy

Z karty zákazníka můžete vytvořit výpis transakcí mezi vámi a zákazníkem. Poté odešlete zákazníkovi vygenerovaný soubor PDF. Případně můžete pomocí sestavy **Výkaz zákazníka** poslat zákazníkům přehled o jejich podnikání s vámi. Výkaz zákazníka lze odeslat do Excelu k dalšímu zpracování.

### Odeslání sestavy Výkaz zákazníka

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi ](media/ui-search/search_small.png "Řekněte mi, co chcete dělat") zadejte **Výkaz zákazníka <x5/> a vyberte související odkaz..
2. Vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. V části **Možnosti výstupu** vyberte způsob odeslání sestavy odběrateli.

> [!NOTE]
> Pokud používáte více měn, sestava Výkaz zákazníka se vytiskne v  měně zákazníka. Poslední datum v období výkazu se také používá jako datum výkazu a datum splatnosti, pokud je zahrnuto sledování splatnosti.

## Upomínky

[!INCLUDE [receivables-reminders](includes/receivables-reminders.md)]

## Finanční poplatky

Když zákazník nezaplatí do data splatnosti, můžete si nechat automaticky vypočítat penále a přidat je k částkám po splatnosti na účtu zákazníka. Zákazníky můžete informovat o přidaných penálích zasláním oznámení o penáli.

> [!NOTE]  
> K výpočtu úroků a finančních poplatků a k informování zákazníků o úrocích a finančních poplatcích bez upomínání o opožděných platbách používáte upomínky o penálích. Alternativně můžete vypočítat úroky z plateb po splatnosti při vytváření upomínek.

Než budete moci vytvořit penále, musíte nastavit podmínky. Pro více informací navštivte [Nastavení podmínek pro finanční poplatky](finance-setup-finance-charges.md).

Můžete ručně vytvořit penále pro jednotlivého odběratele a automaticky vyplnit řádky. Můžete taky použít funkční úlohu **Vytvořit poznámky finančních nákladů** k vytvoření poznámek o penálích pro všechny nebo vybrané odběratele se zůstatky po splatnosti.

Po vytvoření penálích je můžete upravovat. Text, který se zobrazí na začátku a na konci penále, je určen podmínkami finančního poplatku a lze jej zobrazit ve sloupci **Popis** na řádcích. Pokud byla vypočítaná částka automaticky vložena do počátečního nebo koncového textu, text se při smazání řádků neupraví. Pak musíte použít funkci **Aktualizovat text finančních nákladů**.

Po vytvoření penále a provedení potřebných úprav můžete buď vytisknout zkušební sestavy, nebo vydat poznámky o penálích, obvykle jako e-mail.

### Ruční vytvoření penále

Penále je podobné faktuře. Záhlaví můžete vyplnit ručně a nechat řádky vyplnit za vás, nebo můžete automaticky vytvořit poznámky o penálích pro všechny zákazníky.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi 2.](media/ui-search/search_small.png "Řekněte mi, co chcete udělat"), zadejte **Penále **a poté vyberte související odkaz .
2. Zvolte tlačítko ** Nový<x2/> a vyplňte pole dle potřeby.
3. Zvolte **Navrhnout Fin. Řádky penále**
4. Na stránce **Navrhnout řádky penále** nastavte filtr v **Cust. Záložka ** Položka hlavní knihy, pokud chcete vytvořit finanční doklady pouze pro konkrétní položky.

   > [!NOTE]
   > Přestože jsou uvedeny, výběr filtrů **Platba** a **Dobropis** jako **Typ dokumentu** nebude mít žádný účinek, protože funkce **Navrhnout řádky oznámení o penále ** zpracovává pouze kladné částky.
5. Zvolte tlačítko **OK** pro spuštění dávkové úlohy.

### Aktualizace textů penále
V některých případech můžete upravit počáteční a koncový text, který jste nastavili pro podmínky penále. Pokud tak učiníte v době, kdy jste vytvořili, ale ještě nevydali, poznámky o penálích, můžete je aktualizovat upraveným textem.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi 3.](media/ui-search/search_small.png "Řekněte mi, co chcete udělat"), zadejte **Penále**a poté vyberte související odkaz .
2. otevřete záznam o penále, jehož text chcete změnit, a poté zvolte akci **Aktualizovat text penále**.
3. Na stránce **Aktualizovat text penále** můžete nastavit filtr, pokud chcete aktualizovat několik poznámek.
4. Zvolte tlačítko **OK** pro aktualizaci počátečních a koncových textů.

### Vystavení penále
Po vytvoření poznámek o penále a provedení potřebných úprav můžete buď vytisknout zkušební zprávy, nebo vydat penále.

Po vystavení připomenutí jsou položky zveřejněny podle vašich specifikací na stránce **Podmínky penále**. Tato specifikace určuje, zda jsou úroky a/nebo další poplatky zaúčtovány na účet zákazníka a do hlavní knihy. Nastavení na stránce **Účto skupiny zákazníka** určuje, do kterých účtů jsou zaúčtovány.

Pro každou položku knihy odběratelů v poznámce o penále je vytvořena položka na **Upomínky/Fin. Účtované položky**

Pokud jsou na stránce **Podmínky penále** zaškrtnuta políčka **Zaúčtovat úrok** nebo **Zaúčtovat dodatečný poplatek**, vytvoří se také následující položky:

- Jedna položka na stránce **Zák. Položky hlavní knihy**
- Jeden záznam pohledávky na příslušný účet hlavní knihy
- Jeden úrok a/nebo jeden dodatečný poplatek na příslušném účtu hlavní knihy

Kromě toho může vydání penále vést k zaúčtování DPH.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi 4.](media/ui-search/search_small.png "Řekněte mi, co chcete udělat"), zadejte **Penále**a poté vyberte související odkaz .
2. Vyberte příslušné penále a poté vyberte akci **Vydat**.
3. Na stránce **Vydat penále** vyplňte pole podle potřeby.
4. Zvolte tlačítko **OK**.

Poznámka o penále je vytištěna pro odeslání na zadaný e-mail jako příloha PDF.

### Zrušení vydaného penále
Pokud byly penále vystaveny omylem, můžete je zrušit před jejich odesláním. Můžete to udělat buď jeden po druhém, nebo jako dávku.
1. Na stránce **Vydané penále** vyberte jeden nebo více řádků pro vydané penále, které chcete zrušit, a pak zvolte akci **Zrušit**.
2. Na stránce**Zrušení vydaného penále. Na stránce účtované položky** vyplňte pole podle potřeby a poté stiskněte tlačítko **OK**.

### Zobrazení položek upomínek a penále
Když vydáte připomenutí, vytvoří se záznam připomenutí na **Upomínka /Fin. Stránka Položky penále** pro každý řádek připomenutí, který obsahuje položku odběratele. Následně můžete získat přehled o vytvořených záznamech upomínek pro konkrétního zákazníka.
1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi.](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Zákazníci** a poté vyberte související odkaz.
2. Otevřete příslušnou kartu zákazníka a poté zvolte akci **Položky hlavní knihy**.
3. Na stránce **Položky zákazníka** vyberte řádek s položkou hlavní knihy, pro kterou chcete zobrazit položky připomenutí, a pak zvolte **Připomenutí/Fin. Účtované položky**.

## Více úrokových sazeb

[!INCLUDE [multiple-interest-rates-def](includes/multiple-interest-rates-def.md)] For more information, see [Set Up Multiple Interest Rates](finance-how-to-set-up-multiple-interest-rates.md).

## Podívejte se na související školení na webu [Microsoft Learn](/learn/paths/process-financial-periodic-activities-dynamics-365-business-central/)

## Viz také

 [Set Up Reminder Terms and Levels ](finance-setup-reminders.md)  
[Set Up Finance Charge Terms](finance-setup-finance-charges.md)  
[Managing Receivables](receivables-manage-receivables.md)  
[Sales](sales-manage-sales.md)  
[Práce s[!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]