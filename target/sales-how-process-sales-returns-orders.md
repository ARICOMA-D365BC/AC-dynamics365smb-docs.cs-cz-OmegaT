---
title: Process Sales Return Orders
description: Describes how to create a sales return order to process a return, cancellation, or reimbursement for items or services you have been received payment for.
author: SorenGP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: undo, credit memo, return, order
ms.search.form: 44, 134, 144, 6629, 6630, 6633, 6662, 9302, 9304, Report_6646
ms.date: 09/08/2021
ms.author: edupont

---
# Zpracování prodejních vratek

Pokud potřebujete větší kontrolu nad procesem vracení tržeb, jako jsou skladové doklady pro manipulaci se zbožím, nebo lepší přehled při příjmu zboží z více prodejních dokladů s jednou prodejní vratkou, můžete vytvořit prodejní vratku objednávky. Vrácení prodejní objednávky automaticky vydá související prodejní dobropis a další doklady související s vrácením, například náhradní prodejní objednávku, v případě potřeby.

Kromě původní zaúčtované prodejní faktury můžete použít prodejní dobropis nebo prodejní vratku na jiné prodejní doklady, například na jinou zaúčtovanou prodejní fakturu, protože odběratel také vrací zboží dodané s touto fakturou.

## Vytvoření prodejní vratky na základě jednoho nebo více zaúčtovaných prodejních dokladů

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **vratky prodejních objednávek** a pak zvolte související odkaz.
2. Vyberte akci **Nový**.
3. Vyplňte pole na pevné záložce **Obecné** podle potřeby.
4. Na pevné záložce **Řádky** vyplňte řádky ručně nebo zkopírujte informace z jiných dokumentů, abyste řádky vyplnili automaticky:

   - Pomocí funkce **Získat řádky zaúčtovaného dokladu k obrácení** zkopírujte jeden nebo více řádků zaúčtovaného dokladu z jednoho nebo více zaúčtovaných dokladů. Tato funkce vždy přesně obrátí náklady z řádku zaúčtovaného dokladu. Tato funkce je popsána v následujících krocích.
   - Pomocí funkce **Kopírovat z dokumentu** zkopírujte existující dokument k vrácení objednávky. Tato funkce slouží ke zkopírování celého dokumentu. Může to být buď zaúčtovaný dokument, nebo dokument, který ještě není zaúčtován. Tato funkce umožňuje přesné obrácení nákladů pouze v případě, že je zaškrtnuto políčko **Povinné přesné vrácení nákladů** na stránce **Nastavení prodeje a pohledávek**.  

5. Vyberte akci **Zpracovat** a pak zvolte akci **Získat řádky zaúčtovaného dokladu pro obrácení**.
6. V horní části stránky **Řádky zaúčtovaných prodejních dokladů** zaškrtněte políčko **Zobrazit pouze vratné řádky**, chcete-li vidět pouze řádky, které mají množství, která ještě nebyla vrácena. Pokud například již bylo vráceno množství zaúčtované prodejní faktury, možná nebudete chtít toto množství vrátit na novém prodejním dokladu.

   > [!NOTE]  
   > Toto pole funguje pouze pro zaúčtované zásilky a řádky zaúčtované faktury, nikoli pro řádky zaúčtované vratky nebo zaúčtované řádky dobropisu.

   Na levé straně stránky jsou uvedeny různé typy dokumentů a číslo v závorkách ukazuje počet dokumentů dostupných pro každý typ dokumentu.

7. V poli **Filtr typu dokumentu** vyberte typ řádků zaúčtovaného dokladu, který chcete použít.
8. Vyberte řádky, které chcete zkopírovat do nového dokumentu.

   > [!NOTE]  
   > Pokud použijete Ctrl+A k výběru všech řádků, zkopírují se všechny řádky v rámci filtru, který jste nastavili, ale filtr **Zobrazit pouze reverzibilní množství** bude ignorován. Předpokládejme například, že jste filtrovali řádky na konkrétní číslo dokumentu se dvěma řádky, z nichž jeden již byl vrácen. I když je vybráno pole **Zobrazit pouze reverzibilní množství**, pokud stisknete Ctrl+A pro zkopírování všech řádků, zkopírují se oba řádky, namísto pouze jednoho, který ještě nebyl obrácen.

9. Kliknutím na tlačítko **OK** zkopírujte řádky do nového dokumentu.

   Dochází k následujícím procesům:

   - Pro řádky zaúčtovaného dokladu typu **Zboží** je vytvořen nový řádek dokladu, který je kopií řádku zaúčtovaného dokladu s množstvím, které ještě nebylo obráceno. Pole **Aplikační formulář pro zadání zboží** je vyplněno podle potřeby číslem zboží hlavní knihy řádku zaúčtovaného dokladu.

   - Pro řádky zaúčtovaného dokladu, které nejsou typu **Zboží**, například náklady na zboží, je vytvořen nový řádek dokladu, který je kopií původního řádku zaúčtovaného dokladu.

   - Vypočítá pole **Jednotkové náklady (LCY)** na novém řádku z nákladů na odpovídajících záznamech knihy zboží.

   - Pokud je zkopírovaným dokladem zaúčtovaná zásilka, zaúčtovaná účtenka, zaúčtovaná vratka nebo zaúčtovaná zpětná zásilka, jednotková cena se vypočítá automaticky z karty zboží.

   - Pokud je zkopírovaný doklad zaúčtovaná faktura nebo dobropis, zkopíruje se jednotková cena, fakturační slevy a řádkové slevy z řádku zaúčtovaného dokladu.

   - Pokud řádek zaúčtovaného dokladu obsahuje řádky sledování zboží, pole **Aplikační formulář pro zadání zboží** na řádcích sledování zboží je vyplněno příslušnými čísly zboží hlavní knihy z řádků sledování zaúčtovaného zboží.

   Když kopírujete ze zaúčtované faktury nebo zaúčtované dobropisy, aplikace zkopíruje všechny relevantní fakturační slevy a řádkové slevy jako platné v době zaúčtování tohoto dokladu z řádku zaúčtovaného dokladu do nového řádku dokladu. Uvědomte si však, že pokud možnost **Calc. Nák. sleva** je aktivována na stránce **Nastavení prodeje a pohledávek**, poté bude fakturační sleva nově vypočtena při zaúčtování nového řádku dokladu. Částka řádku pro nový řádek se tedy může lišit od částky řádku pro řádek zaúčtovaného dokladu v závislosti na novém výpočtu slevy faktury.

   > [!NOTE]  
   > Pokud již byla část množství řádku účtovaného dokladu stornována nebo prodána nebo spotřebována, vytvoří se řádek pouze pro množství, které zůstalo na skladě nebo které nebylo vráceno. Pokud již bylo stornováno celé množství řádku zaúčtovaného dokladu, nový řádek dokladu se nevytvoří.
   >
   > Pokud je tok zboží v zaúčtovaném dokladu stejný jako tok zboží v novém dokladu, vytvoří se kopie řádku původního zaúčtovaného dokladu v novém dokladu. Pole **Aplikační formulář pro zadání zboží** není vyplněno, protože v tomto případě není možné přesné vrácení nákladů. Pokud například použijete funkci **Získat zaúčtované řádky dokladu k obrácení** k získání zaúčtovaného řádku prodejního dobropisu pro nový prodejní dobropis, zkopíruje se do nového dobropisu pouze původní zaúčtovaný řádek dobropisu.

10. Na stránce **Objednávka prodejní vratky** v poli **Kód příčiny vracení** na každém řádku vyberte důvod vrácení.
11. Vyberte tlačítko **Zaúčtovat**.

## Chcete-li vytvořit náhradní prodejní objednávku z prodejní objednávky
Můžete se rozhodnout odškodnit zákazníka za zboží, které jste mu prodali, výměnou zboží. Můžete provést náhradu za stejné nebo jiné zboží. K této situaci může dojít, pokud jste například omylem odeslali zákazníkovi nesprávné zboží.

1. Na stránce **Objednávka prodejní vratky** pro aktivní proces vrácení proveďte na prázdném řádku záporný záznam pro náhradní zboží vložením záporné částky do pole **Množství**.
2. Vyberte akci **Přesunout záporné čáry**.
3. Na stránce **Přesunout záporné řádky prodeje** vyplňte pole podle potřeby.
4. Zvolte tlačítko **OK**. Záporný řádek pro náhradní zboží je odstraněn z prodejní objednávky a vložen na novou stránku **Prodejní objednávka**. Pro více informací navštivte [Prodej zboží](sales-how-sell-products.md).

## Chcete-li vytvořit dokumenty související s vrácením z prodejní objednávky
Během procesu vracení prodeje můžete automaticky vytvořit náhradní prodejní objednávky, nákupní objednávky pro vrácení a náhradní nákupní objednávky. To je užitečné například v situacích, kdy chcete manipulovat se zárukami zboží poskytovanými prodejci.

1. Na stránce **Objednávky prodejní vratky** pro aktivní proces vrácení vyberte akci **Vytvořit doklady související s vrácením**.
2. V poli **Číslo dodavatele** zadejte číslo dodavatele, pokud chcete automaticky vytvořit dokumenty dodavatele.
3. Pokud musí být vrácené zboží vráceno dodavateli, vyberte zaškrtávací políčko **Vytvořit objednávku nákupní vratky**.
4. Pokud musí být vrácené zboží objednáno od dodavatele, zaškrtněte políčko **Vytvořit nákupní objednávku**.
5. Pokud musí být vytvořena náhradní prodejní objednávka, zaškrtněte políčko **Vytvořit prodejní objednávku**.

## Vytvoření dodatečného naskladnění
Můžete se rozhodnout účtovat zákazníkovi poplatek za doplnění zásob, který pokryje fyzické manipulační náklady na vrácení zboží. K tomu může dojít, pokud si zákazník například omylem objednal špatné zboží nebo si to rozmyslel poté, co obdržel zboží, které jste mu prodali.

Tyto zvýšené náklady můžete zaúčtovat jako poplatek za zboží v dobropisu nebo objednávce vrácení a přiřadit je k zaúčtované zásilce. Následující text je popsán pro prodejní objednávku vrácení, ale stejné kroky platí pro prodejní dobropis.

1. Otevřete stránku **Objednávka prodejní vratky** pro aktivní proces vrácení.
2. Na novém řádku do pole **Typ** vyberte **Poplatek (zboží)**.
3. Vyplňte pole jako u jakéhokoli řádku poplatku za zboží. Další informace [naleznete v tématu Použití poplatků za položku k účtování dodatečných obchodních nákladů](payables-how-assign-item-charges.md).

Při zaúčtování prodejní vratky se náklady na doplnění přidají k příslušné částce položky prodeje. Tímto způsobem můžete udržovat přesné ocenění zásob.

## Podívejte se na související školení na webu [Microsoft Learn](/learn/paths/return-items-dynamics-365-business-central/)

## Viz také

[Prodej](sales-manage-sales.md)  
[Nastavení prodeje](sales-setup-sales.md)  
[Správa závazků](payables-manage-payables.md)  
[Odesílání dokladů e-mailem](ui-how-send-documents-email.md)  
[Zpracování nebo zrušení nákupní vratky](purchasing-how-process-purchase-returns-cancellations.md)  
[Práce s [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
