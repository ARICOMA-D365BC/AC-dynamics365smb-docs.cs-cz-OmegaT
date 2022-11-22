---
title: Transfer Bank Funds
description: You can transfer amounts from one bank account to another, including different currencies, by posting the transaction in the general journal.
author: SorenGP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: bank account transfer, multiple currencies
ms.search.form: 39
ms.date: 04/29/2021
ms.author: edupont

---
# Převod bankovních prostředků

Někdy možná budete muset převést částku z jednoho bankovního účtu [!INCLUDE[prod_short](includes/prod_short.md)] na jiný. Chcete-li to provést, musíte zaúčtovat transakci na stránce **Finanční deník**. Úloha se liší v závislosti na tom, zda bankovní účty používají stejné nebo různé měny.

## Zaúčtování převodu mezi bankovními účty se stejným kódem měny

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat") zadejte **Finanční deníky** související odkaz.
2. Na řádku deníku vyplňte pole **Datum zaúčtování** a **Číslo dokladu**.
3. V poli **Typ účtu** vyberte **Bankovní účet**.
4. V poli **Číslo účtu** vyberte banku, ze které chcete převést prostředky.
5. V poli **Částka** zadejte částku, která má být převedena.

   Dále musíte specifikovat vyrovnávací účet. Pokud příslušná pole nevidíte, výběrem akce **Zobrazit další sloupce** zobrazte všechna dostupná pole.
6. V poli **Číslo Vyrovnávacího účtu**, vyberte možnost **Bankovní účet**.
7. V poli **Číslo Vyrovnávacího účtu** vyberte bankovní účet, na který chcete prostředky převést.
8. Zaúčtujte deník.

## Zaúčtování převodu mezi bankovními účty s různými kódy měny

Chcete-li převést prostředky mezi bankovními účty, které používají různé měny, je nutné zaúčtovat dva řádky finančního deníku.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat") zadejte **Finanční deníky** související odkaz.
2. Vytvořte dva řádky deníku a vyplňte pole **Datum zaúčtování** a **Číslo dokladu**.
3. Na prvním řádku deníku v poli **Typ** vyberte **Bankovní účet**.
4. V poli **Číslo účtu** vyberte bankovní účet, ze kterého chcete prostředky převést.
5. V poli **Částka** zadejte částku v měně bankovního účtu se znaménkem minus nebo bez něj.

   > [!TIP]
   > Částka bez znaménka je debit a částka se znaménkem mínus je kredit.

   > [!NOTE]
   > Některé společnosti preferují převody mezi účty na samostatných řádcích deníku. Jiné společnosti dávají přednost zaúčtování všeho na jeden řádek deníku pomocí vyrovnávacího účtu. Pokud si nejste jisti, co dělat, obraťte se na místního odborníka.
   >
   > Pokud vaše společnost dává přednost použití vyrovnávacího účtu, nastavte **Typ Vyrovnávací účtu** na **Bankovní účet** a nastavte **Číslo Vyrovnávacího účtu** na bankovní účet, na který chcete prostředky převést. Poté pokračujte krokem 9 nebo 10.
   >
   > Pokud vaše společnost dává přednost použití samostatného řádku deníku, přejděte k dalšímu kroku.
6. Na druhém řádku deníku v poli **Typ** vyberte Možnost **Bankovní účet**.
7. V poli **Číslo účtu** vyberte bankovní účet, na který chcete prostředky převést.
8. V poli **Částka** zadejte částku v měně bankovního účtu se znaménkem minus nebo bez něj.

   > [!TIP]
   > Částka bez znaménka je debit a částka se znaménkem mínus je kredit.
9. Pokud se směnné kurzy použité v deníku liší od směnných kurzů na stránce **Směnné kurzy měn**, zadejte nový řádek deníku pro zisk nebo ztrátu směnného kurzu.

   1. Do pole **Typ účtu** zadejte **Účet hlavní knihy**.

   2. Do pole **Číslo účtu** zadejte číslo účtu pro kurzový zisk nebo ztrátu.

   3. Zadejte zisk nebo ztrátu směnného kurzu do pole **Částka** se znaménkem minus nebo bez něj.

   > [!TIP]
   > Částka bez znaménka je debit a částka se znaménkem mínus je kredit.
10. Zaúčtujte deník.

## Viz také

[Odsouhlasení bankovních účtů](bank-manage-bank-accounts.md)    
[Nastavení bankovních účtů](bank-setup-banking.md)    
[Použití front úloh k plánování úkolů](ui-work-general-journals.md)    
[Práce s [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]