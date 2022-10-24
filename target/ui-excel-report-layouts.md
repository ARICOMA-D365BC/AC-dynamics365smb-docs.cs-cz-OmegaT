---
title: Working with Excel Layouts
description: Learn how to create and modify report layouts that are built using Excel.
author: jswymer

ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customized report, document layout, logo, personalize
ms.search.form: 9650, 9652
ms.date: 03/14/2022
ms.author: jswymer
---
# Práce s rozvrženími aplikace Excel

Rozvržení sestav aplikace Excel jsou založeny na sešitech aplikace Microsoft Excel (soubory .xlsx). Umožňují vytvářet sestavy pomocí známých funkcí aplikace Excel pro shrnutí, analýzu a prezentaci dat, pomocí vzorců, kontingenčních tabulek a kontingenčních grafů.

![Zobrauje příklad rozložení aplikace Excel.](media/excel-layout-2.png)

Tento článek vysvětluje některé z nejdůležitějších věcí, které potřebujete vědět, abyste mohli začít s rozvržním aplikace Excel.

## Proč používat rozvržení aplikace Excel?

Zde jsou další výhody používání rozvržení aplikace Excel:

- Vytvářejte interaktivní sestavy pomocí vizualizací, jako jsou průřezy
- Prohlédněte si nezpracovaná data z datové sady sestavy, abyste pochopili, jak sestava funguje a odkud zobrazená data pocházejí
- Pomocí integrovaných funkcí Office můžete provádět následné zpracování vykreslených sestav, například:
   - [Ochrana listů](https://support.microsoft.com/en-us/office/protect-a-worksheet-3179efdb-1285-4d49-a9c3-f4ca36276de6)
   - [Použití popisků citlivosti](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
   - [Přidávání komentářů a poznámek](https://support.microsoft.com/en-us/office/insert-comments-and-notes-in-excel-65f504d8-160b-4a05-ac30-46fbd5227a52)
   - [Prognózy a analýzy](https://support.microsoft.com/en-us/office/introduction-to-what-if-analysis-22bffa5f-e891-4acc-bf7a-e4645c446fb4)
- Používejte nainstalované doplňky a integrace aplikací, jako jsou toky Power Automate nebo OneDrive.

## Začínáme

Při nastavování rozvržení sestav aplikace Excel jsou v zásadě dva úkoly:

1. Vytvořte nový soubor rozvržení aplikace Excel.
2. Přidat do sestavy nové rozvržení.

## Úkol 1: Vytvoření souboru rozvržení aplikace Excel

Existují tři způsoby, jak vytvořit soubor rozvržení sestavy aplikace Excel, jak je vysvětleno v této části

### [Z jakékoli sestavy](#tab/any-report)

Pomocí následujících kroků můžete vytvořit rozvržení sestavy aplikace Excel z libovolné sestavy bez ohledu na aktuální typ rozložení. Rozvržení aplikace Excel bude obsahovat požadovaný **Datový** list a tabulku, list **Metadat sestavy** a nic jiného.

[!INCLUDE[open-report-layouts-page](includes/open-report-layouts-page.md)]
2. V seznamu **Rozvržení sestav** vyberte libovolné rozložení sestavy a pak zvolte akci **Spustit sestavu**.
3. V oknu před tiskem sestavy vyberte **Odeslat do** > **Microsoft Excel (pouze data)** > **OK**.

Tento krok stáhne sešit aplikace Excel, který obsahuje datovou sadu sestavy.
4. Otevřete stažený soubor v Excelu, proveďte změny a pak soubor uložte.

### [Z jiného rozvržení sestavy aplikace Excel](#tab/other-layout)

Pokud již existuje rozvrženísestavy aplikace Excel, použijete existující rozložení jako výchozí bod. Existují dva způsoby, jak získat kopii rozvržení. Existující rozvržení můžete exportovat ze stránky **Rozložení sestavy** nebo stáhnout rozvržení ze stránky před tiskem sestavy. Oběma způsoby stáhněte soubor rozvržení aplikace Excel, který obsahuje všechny listy existujícího souboru. Rozdíl je v tom, že ze stránky požadavku tisku bude rozložení obsahovat skutečná data. Data nejsou vyžadována, ale pomáhají při navrhování rozvržení.

#### Přístup 1: Export rozvržení ze stránky **Rozvržení sestav**

[!INCLUDE[open-report-layouts-page](includes/open-report-layouts-page.md)]
2. Ze seznamu vyberte rozvržení aplikace Excel a pak v horní části stránky vyberte akci **Exportovat rozvržení**.
3. Otevřete soubor v Excelu, proveďte změny a pak soubor uložte.

#### Přístup 2: Stažení rozložení ze stránky požadavku sestavy

[!INCLUDE[open-report-layouts-page](includes/open-report-layouts-page.md)]
2. V seznamu **Rozvržení sestav** vyberte libovolné rozložení sestavy a pak zvolte akci **Spustit sestavu**.
3. Na stránce požadavku na přehled vyberte **Stáhnout**.
4. Otevřete soubor v Excelu, proveďte změny a pak soubor uložte.

### [Z AL kódu](#tab/from-code)

Tento způsob je nejpokročilejší. Vyžaduje znalost AL kódu, takže cílí na programátory. Rozvržení aplikace Excel jsou v tomto případě součástí balíčku rozšíření, který si nainstalujete. Pro více informací navštivte [Vytváření rozvržení sestav v Excelu](/dynamics365/business-central/dev-itpro/developer/devenv-howto-excel-report-layout) v nápovědě Developer a IT Pro.

---

## Úkol 2: Přidání rozvržení sestavy aplikace Excel

Jakmile budete mít soubor rozvržení aplikace Excel, dalším úkolem je přidat jej jako nové rozložení sestavy.

[!INCLUDE[open-report-layouts-page](includes/open-report-layouts-page.md)]
2. Vyberte **Nové rozvržení**.
3. Nastavte **Report ID** sestavy.
4. Vložte název do pole  **Název rozvržení**.
5. Nastavte **Možnost formátu** na **Excel**.
6. Vyberte **OK** > **zvolte** průzkumníka souborů v zařízení.
7. Najděte a vyberte excelový soubor a pak vyberte **Otevřít**.

Vybraný soubor se nahraje do rozvržení a vrátíte se na stránku **Rozvržení Sestav**.
8. Pokud chcete vidět, jak sestava vypadá s novým rozvržením, vyberte rozvržení v seznamu a pak vyberte **Spustit sestavu**.


<!--

**Data** sheet
  - An Excel layout must contain a sheet named **Data**.
  - The **Data** sheet can only include one table named **Data**.

**Data** table
  - The **Data** sheet must include a table that has the name **Data**.
  - The table must have at least one column and can only include columns that are also in report dataset.
  - The table must start in the first cell A1 of the **Data** sheet.

3. Report Metadata
-->

## Principy rozvržení sestav aplikace Excel

Existuje několik věcí, které byste měli vědět nebo zvážit, než začnete vytvářet nebo provádět změny rozvržení aplikace Excel. Každé rozvržení aplikace Excel musí obsahovat dva prvky: **Datový** list a tabulku **Dat**. Tyto prvky tvoří základ rozvržení definováním obchodních dat z Business Central, se kterými můžete pracovat. **Datový** list si můžete představit jako druh smlouvy mezi rozvržením v obchodních datech. Tato data použijete jako zdroj výpočtů a vizualizací, které chcete prezentovat na jiných listech.

Existují některé specifické požadavky na strukturu sešitu aplikace Excel Pokud požadavky nebudou splněny, budete mít problémy s používáním rozvržení. Následující diagram a tabulka popisují prvky rozložení aplikace Excel a požadavky.

[![Zobrazuje různé prvky rozvržení aplikace Excel.](media/excel-layout-callouts-2.png)](media/excel-layout-callouts-2.png#lightbox)

| Čísla. | Element | Popis | Povinný |
|---|-------|----|---|
| 1 | **Datový** list | <ul><li>Musí mít název **Data**</li><li>Může obsahovat pouze jednu tabulku a tabulka musí mít název **Data**</li></ul> | ![Je povinné](media/check.png) |
| 2 | **Data** Tabulka | <ul><li>Musí mít název **Data**</li><li>Musí mít alespoň jeden sloupec.</li><li>Může obsahovat pouze sloupce, které jsou v datové sadě sestavy.</li><li>Musí začínat v první buňce **A1** listu **Data**</li></ul> | ![Je povinné](media/check.png) |
| 3 | Prezentační listy | <ul><li>Používá se k prezentaci dat.</li><li>Údaje pocházejí z **datového** listu. </li></ul> |
| 4 | List **Metadata sestavy** | <ul><li>Automaticky zahrnuto, pokud bylo rozvržení vytvořeno exportem jiné sestavy jako Excel</li><li>Obsahuje obecné informace o sestavě</li><li>Can be deleted</li></ul> |

Shrnutí toho, co můžete a nemůžete dělat na listu **Data**:

- Neměňte název **Datového** listu, Tabulky **Dat** ani sloupců.
- Sloupce můžete odstranit nebo skrýt.
- Nepřidávejte žádné sloupce, pokud nejsou zahrnuty v datové sadě sestavy.
- Listy můžete umístit v libovolném pořadí. Například list **Data** může být první nebo poslední.

## Podívejte se na související školení na webu [Microsoft Learn](/learn/modules/change-documents-dynamics-365-business-central/index)

## Viz také

[Managing Report Layouts](ui-manage-report-layouts.md)  
[Change the Current Report Layout](ui-how-change-layout-currently-used-report.md)  
[Import and Export a Custom Report or Document Layout](ui-how-import-and-export-report-layout.md)  
[Working with Reports, Batch Jobs, and XMLports](ui-work-report.md)  
[Prepare Financial Reporting with Account Schedules and Account Categories](bi-how-work-account-schedule.md)
[Business Intelligence](bi.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Analyzing Report Data with Excel](report-analyze-excel.md).


[!INCLUDE[footer-include](includes/footer-banner.md)]