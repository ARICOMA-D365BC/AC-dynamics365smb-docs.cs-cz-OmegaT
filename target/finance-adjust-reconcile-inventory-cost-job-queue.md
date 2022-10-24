---
title: Schedule Jobs for Adjusting & Reconciling Inventory Cost
description: Learn how you can use the job queue to move the tasks for adjusting inventory cost or reconciling it with the general ledger to the background. For example, if your company runs many tasks or processes many transactions.
author: AndreiPanko


ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.reviewer: edupont
ms.search.form: 461
ms.date: 09/23/2021
ms.author: andreipa

---
# Plánování úloh pro úpravu a odsouhlasení nákladů na zásoby s hlavní knihou

Pro optimalizaci prostředí jsou ve výchozím nastavení zapnuty automatické úpravy nákladů a účtování do hlavní knihy. Jak se však data v průběhu času hromadí, může to ovlivnit výkon. Chcete-li snížit zatížení aplikace, je často užitečné použít fronty úloh k přesunutí běhu úlohy na pozadí.

## Přesunutí úlohy úpravy nákladů na zboží do pozadí pomocí asistovaného nastavení

Vytvoření položek fronty úloh může být složité, a to i pro zkušeného konzultanta, takže máme asistovaného průvodce nastavením, který usnadňuje proces úpravy nákladů na zboží.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Nastavení zásob** a poté vyberte související odkaz.
2. Na stránce **Nastavení zásob** přepněte pole **Automatické zaúčtování nákladů** nebo zadejte **Nikdy** v poli **Automatická úprava nákladů**.
3. V oznámení, které se nyní zobrazuje v horní části stránky, vyberte odkaz **Naplánovat záznam do fronty úloh**. Otevře se průvodce asistovaným nastavením **Úpravy nákladů a zaúčtování**.
4. Zvolte úlohu, kterou chcete naplánovat.

> [!NOTE]
> Nemůžete vytvořit novou položku fronty úloh, pokud již položka fronty úloh pro zadanou úlohu existuje.

5. Chcete-li zkontrolovat a upravit nastavení, vyberte pole **Po dokončení zobrazit záznamy fronty úloh**. Pro více informací navštivte [Použití fronty úloh na plánování úloh](admin-job-queues-schedule-tasks.md)

## Vytvoření položky fronty úloh pro ruční úpravu a odsouhlasení nákladů na zásoby

Případně můžete položky fronty úloh vytvořit ručně. Následující postup ukazuje, jak nastavit dávkovou úlohu **Upravit náklady – položky zboží** tak, aby se automaticky spouštěla denně, ale stejné kroky platí pro dávkovou úlohu **Zaúčtování nákladů na hlavní knihu**.

1. Vyberte ikonu ![Žárovky, která otevře funkci](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Položky fronty úloh** a poté vyberte související odkaz.
2. Vyberte akci **Nový**.
3. V poli **Typ objektu ke spuštění** zvolte *Sestava*.
4. V poli **ID objektu ke spuštění** zvolte *možnost 795*, **Upravit náklady - položky položky**.
5. Do pole **Vzorec data dalšího spuštění** zadejte *1D*.
6. Do pole **Počáteční čas** zadejte *2:00*.
7. Zvolte akci **Nastavit stav na Připraveno**.

Nyní budou náklady na zásoby aktualizovány každou noc.

Chcete-li naplánovat úlohu pro odsouhlasení zásob s hlavní knihou, zvolte Kódovou jednotku 2846 **Zaúčtovat náklady zásob do hlavní knihy**.

> [!TIP]
> Abyste se vyhnuli uzamčení, neplánujte úlohy pro dávkovou úlohu **Úprava nákladů – položky položek**, proceduru **Zaúčtování nákladů zásob do hlavní knihy** a úlohy pro účtování prodejních nebo nákupních transakcí ve stejnou dobu. Také se ujistěte, že používají stejnou kategorii fronty úloh.

## Viz také

[Úprava nákladu zboží](inventory-how-adjust-item-costs.md)  
[Odsouhlasení nákladů na zboží s financemi](finance-how-to-post-inventory-costs-to-the-general-ledger.md)  
[Použití front úloh k plánování úkolů](admin-job-queues-schedule-tasks.md)  
[Hledání funkcí a informací](ui-search.md)  
[Work with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
