---
    title: Tips and Tricks - RapidStart Services | Microsoft Docs
    description: When you configure companies using RapidStart Services, there are some tips and tricks that you can take advantage of to help your implementation go smoothly.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2021
    ms.author: edupont

---
# Tipy a triky: Služby RapidStart

Pokud konfigurujete společnosti pomocí služby RapidStart Services, existuje několik tipů a triků, které můžete využít pro bezproblémovou implementaci.

## Využijte konfiguračních šablon

Konfigurační šablony vám mohou pomoci zefektivnit proces implementace. Jejich použitím můžete zahrnout podobné zákazníky do segmentů a poté vytvořit protokol implementace, který zachází se všemi zákazníky v segmentu podobným způsobem. Tímto způsobem můžete pro každý segment použít úroveň přednastavení a pokračovat v rychlém provádění.

## Konfigurační dotazníky

Chcete-li usnadnit proces vyplňování konfiguračního dotazníku, zvažte vymezení výchozích odpovědí, abyste uvedli osvědčené postupy.

## Dávkové vytvoření řádků deníku

K migraci položek deníku doporučujeme použít dodané nástroje pro migraci dat. V opačném případě, pokud použijete dávkovou úlohu k vytvoření řádků deníku, který má omezený rozsah a také generuje pouze předvolená pole do deníku. Zbytek deníku pak musí být vyplněn ručně.

## Migrace transakcí

Doporučujeme migrovat počáteční zůstatky v následujícím pořadí. <!--Be aware that you cannot insert ledger entries directly. Instead you must use journals to post the journal lines-->

1. Přeneste počáteční zůstatky hlavní knihy bez použití účetních položek finančního účtu. Použijte specifické protiúčty počátečního stavu, které jsou nastaveny pro každou dílčí knihu. Chcete-li povolit přímé účtování, nastavte vyrovnávací účty.
2. Migrujte položky zákazníků.  <!--work on these-->
3. Migrujte položky zboží.
4. Migrovat položky dlouhodobého majetku

## Make each package manageable

When you use configuration packages to migrate data, separate the data into separate packages for easier portability. For example, if you want to migrate 20 years of ledger entries, the import might take many hours and days. Instead, split the data up so that each package becomes more manageable. Currently, there are no firm rules for what makes a package performant, but if you see problems importing or exporting a package, try making it smaller and see if that helps.

## Viz také

[Setting Up a Company With RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]