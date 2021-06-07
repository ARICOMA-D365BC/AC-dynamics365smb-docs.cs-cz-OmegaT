---
title: Using the C5 Data Migration Extension | Microsoft Docs
description: Use this extension to migrate customers, vendors, items, and general ledger accounts from Microsoft Dynamics C5 2012 to Business Central.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms. search.keywords: extension, migrate, data, C5, import
ms.date: 04/01/2021
ms.author: bholtorf

---

# Rozšíření C5 Data Migration

Toto rozšíření usnadňuje migraci zákazníků, dodavatelů, položek a účtů hlavní knihy z Microsoft Dynamcis C5 2012 do [!INCLUDE[prod_short](includes/prod_short.md)]. Lze také migrovat historické položky pro účty hlavní knihy.

> [!Note]
> Společnost v [!INCLUDE[prod_short](includes/prod_short.md)] nesmí obsahovat žádná data. Zároveň po spuštění migrace nevytvářejte zákazníky, dodavatele, položky nebo účty, dokud migrace neskončí.

## Jaká data jsou migrována ?
Pro každou entitu se migrují následující data:

### Zákazníci

* Kontakty
* Lokace
* Země
* Dimenze zákazníka (oddělení, středisko, účel)
* Způsob dodávky
* Prodejce
* Platební podmínky
* Způsob platby
* Cenová skupina zákazníka
* Fakturační sleva zákazníka

Pokud migrujete účty, migrují se také následující data:

* Nastavení účto skupiny zákazníka
* List finančního deníku
* Otevřené transakce (položky zákazníka)

### Dodavatelé

* Kontakty
* Lokace
* Země
* Dimenze dodavatele (oddělení, středisko, účel)
* Fakturační sleva
* Způsob dodávky
* Nákupčí
* Platební podmínky
* Způsob platby
* Fakturační sleva dodavatele

Pokud migrujete účty, migrují se také následující data:

* Nastavení účto skupiny dodavatele
* List finančního deníku
* Otevřené transakce (položky dodavatele)

### Zboží

* Lokace
* Země
* Dimenze položky (oddělení, středisko, účel)
* Prodejní řádkové slevy
* Skupina slev zákazníka
* Skupina slev zboží
* Prodejní cena
* Číslo tarifu
* Měrné jednotky
* Kód sledování zboží
* Cenová skupina zákazníka
* Kusovníky montáže

Pokud migrujete účty, migrují se také následující data:

* Nastavení účtování zásob
* Nastavení obecného účtování
* List deníku zboží
* Otevřené transakce (položky Položky)

> [!Note]
> Pokud existují otevřené transakce, které používají cizí měny, migrují se také směnné kurzy pro tyto měny. Ostatní směnné kurzy migrovány nejsou.

### Účetní osnova

* Standardní dimenze: Středisko, Nákladové středisko, Účel
* Historické finanční transakce

> [!Note]
> S historickými finančními transakcemi se zachází trochu jinak. Při migraci dat nastavíte parametr **Aktuální období**. Tento parametr určuje, jak zpracovat finanční transakce. Transakce po tomto datu se migrují jednotlivě. Transakce před tímto datem jsou agregovány na jeden účet a migrovány jako jedna částka. Řekněme například, že existují transakce v letech 2015, 2016, 2017, 2018 a do pole Aktuální období zadáte 01.01.2017. Pro každý finanční účet budou částky za transakce k 31. prosinci 2106 nebo dříve sloučeny do jediného řádku finančního deníku. Všechny transakce po tomto datu budou migrovány jednotlivě.

## Požadavky na velikost souboru

Největší velikost souboru, který můžete nahrát do [!INCLUDE[prod_short](includes/prod_short.md)] je 150 MB. Pokud je soubor exportovaný z C5 větší, zvažte migraci dat pomocí více souborů. Například exportujte jeden nebo dva typy entit z C5, jako jsou například zákazníci a dodavatelé, do jednoho souboru, a poté exportujte položky do jiného souboru atd. Soubory můžete v [!INCLUDE[prod_short](includes/prod_short.md)] importovat jednotlivě.

## Migrace dat

Je třeba učinit jen několik kroků k exportu dat z C5 a jejich importu do [!INCLUDE[prod_short](includes/prod_short.md)]:

1. V C5 exportujte data pomocí funkce **Export databáze**. Poté odešlete exportovanou složku do komprimované (zip) složky.
2. V [ vyberte ikonu ](includes/prod_short.md)Žárovky, která otevře funkci Řekněte mi![](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Migrace Dat** a poté zvolte **Migrace Dat**.
3. Proveďte kroky v průvodci asistovanou instalaci. Ujistěte se, že jako zdroj dat jste zvolili **Import z Microsoft Dynamcis C5 2012**.

## Zobrazení stavu migrace

Na stránce **Přehled migrace dat** můžete sledovat úspěšnost migrace. Stránka zobrazuje informace, jako je počet entit, které bude migrace zahrnovat, stav migrace a počet položek, které byly migrovány, a zda byly jejich migrace úspěšné. Ukazuje také počet chyb, umožňuje vám zjistit, co se pokazilo, a pokud je to možné, usnadňuje přístup k entitě a řešení jejích problémů. Další informace naleznete v další části tohoto tématu.

> [!Note]
> Zatímco čekáte na výsledky migrace, musíte stránku aktualizovat, aby se zobrazily výsledky.

## Jak se vyhnout dvojímu účtování

Abychom se vyhnuli dvojímu účtování do hlavní knihy, pro otevřené transakce se používají následující rozvahové účty:

* Pro dodavatele používáme A/P  účet z účto skupiny dodavatelů.
* Pro zákazníky používáme A/R  účet z účto skupiny zákazníků.
* U položek vytváříme nastavení obecného účtování tam, kde účet adjustace je účet určený jako účet inventáře v nastavení účtování zásob.

## Opravy chyb

Pokud se něco pokazí a dojde k chybě, v poli **Stav** se zobrazí **Dokončeno s chybami** a v poli **Počet chyb** se zobrazí jejich počet. Chcete-li zobrazit seznam chyb, můžete otevřít stránku **Chyby dat migrace** výběrem:

* Číslo v poli **Počet chyb** pro entitu.
* Zvolením entity a potom akce **Zobrazit chyby**.

Na stránce **Chyby dat migrace** můžete opravit chybu tak, že si vyberete chybovou zprávu a poté zvolíte **Upravit záznam**, čímž se zobrazí migrovaná data pro entitu. Pokud máte několik chyb k opravě, můžete použít možnost **Hromadné opravy chyb** a upravit entity v seznamu. Stále však musíte otevírat jednotlivé záznamy, pokud byla chyba způsobena související položkou. Například dodavatel nebude migrován, pokud má e-mailová adresa jednoho z jeho kontaktů neplatný formát.

Po opravě jedné nebo více chyb můžete zvolit **Migrovat** a migrovat pouze entity, které jste opravili, aniž byste museli migraci úplně restartovat.

> [!Tip]
> Pokud jste opravili více než jednu chybu, můžete pomocí funkce **Vybrat více** vybrat více řádků pro migraci.. Alternativně, pokud existují chyby, u kterých oprava není důležitá, můžete je vybrat a poté zvolit **Přeskočit výběr**.

> [!Note]
> Pokud máte položky, které jsou součástí kusovníku, možná je budete muset migrovat více než jednou, pokud původní položka není vytvořena před variantami, které na ni odkazují. Pokud je varianta položky vytvořena jako první, může odkaz na původní položku způsobit chybovou zprávu.

## Ověření dat po migraci

Jedním ze způsobů, jak ověřit, zda vaše data byla správně migrována, je podívat se na následující stránky v C5 a [!INCLUDE[prod_short](includes/prod_short.md)].

| Microsoft Dynamcis C5 2012 | Microsoft Dynamics 365 Business Central | Dávkové úlohy k použití |
|---------------------------|------------------------------|------------------|
| Položky zákazníka | Finanční deníky | CUSTMIGR |
| Položky dodavatele | Finanční deníky | VENDMIGR |
| Položky zboží | Deníky zboží | ITEMMIGR |
| Věcné položky | Finanční deníky | GLACMIGR |

## Zastavení migrace dat

Migraci dat můžete zastavit výběrem **Zastavit všechny migrace**. Pokud tak učiníte, zastaví se také všechny čekající migrace.

## Viz také

[Úprava [!INCLUDE[prod_short](includes/prod_short.md)] pomocí rozšíření](ui-extensions.md)  
[Příprava na podnikání](ui-get-ready-business.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]