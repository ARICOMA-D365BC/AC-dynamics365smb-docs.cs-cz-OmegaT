---
title: Set Up Currencies
description: You must set up each currency if you buy or sell in currencies other than your local currency (LCY), or if you record G/L transactions in different currencies.
author: edupont04

ms.topic: conceptual
ms.search.keywords: multiple currencies
ms.search.form: 5, 118
ms.date: 03/15/2022
ms.author: edupont
---
# Nastavit měny  

[!INCLUDE [finance-currencies-def](includes/finance-currencies-def.md)]

Pomocí externí služby můžete získat nejnovější směnné kurzy měn do seznamu **Měny**. Další informace naleznete v části [Nastavení služby směnného kurzu](finance-how-update-currencies.md#to-set-up-a-currency-exchange-rate-service).

[!INCLUDE [finance-currencies-lcy](includes/finance-currencies-lcy-note.md)]

## Měny

Následující tabulka popisuje pole v seznamu **Měny**.

| Pole | Popis |
|---------------------------------|---------------------------------------|  
| Kód | Identifikátor měny. |
| **Popis** | Volný textový popis měny. |
| **Kód ISO** | Mezinárodní třípísmenný kód měny definovaný v ISO 4217. |
| **Číselný kód ISO** | Mezinárodní číselný odkaz na měnu definovanou v ISO 4217. |
| **Datum směnného kurzu** | Poslední aktuální datum směnného kurzu. |
| **HMU Měna** | Určuje, zda je měnou HMU (Hospodářská a měnová unie), například EUR. |
| **Účet realizovaných zisků** | Účet, na kterém bude skutečný zisk zaúčtován při přijímání plateb za pohledávky nebo při registraci skutečného měnového kurzu plateb závazkům. Příklad měnové transakce pohledávky naleznete v příkladu pod touto tabulkou. |
| **Účet realizovaných ztrát** | Účet, na kterém bude zaúčtována skutečná ztráta, když obdržíte platby za pohledávky nebo zaregistrujete skutečný kurz měny u plateb závazků. Příklad měnové transakce pohledávky naleznete v příkladu pod touto tabulkou. |
| **Účet nerealizovaných zisků** | Účet, na kterém bude teoretický zisk zaúčtován při provádění měnové úpravy. |
| **Účet nerealizovaných ztrát** | Účet, na kterém bude zaúčtována teoretická ztráta, když provedete úpravu měny. |
| **Přesnost zaokrouhlení částky** | Některé měny mají pro fakturované částky jiné formáty, než jsou definovány na stránce **Nastavení hlavní knihy**. Pokud změníte přesnost zaokrouhlení částky pro měnu, všechny fakturované částky v této měně budou zaokrouhleny s aktualizovanou přesností. |
| **Desetinná místa v částce** | Některé měny mají pro fakturované částky jiné formáty, než jsou definovány na stránce **Nastavení hlavní knihy**. Pokud změníte částku desetinných míst pro měnu, všechny fakturované částky v měně budou zaokrouhleny aktualizovanými desetinnými místy |
| **Typ zaokrouhlení faktury** | Určuje metodu, která se má použít, pokud musí být částky zaokrouhleny. Možnosti jsou **Nejbližší**, **Nahoru** a **Dolů**. |
| **Přesnost zaokrouhlení jednotkové částky** | Některé měny mají jiné formáty pro jednotkové částky, než jsou definovány na stránce **Nastavení hlavní knihy**. pokud změníte přesnost zaokrouhlení jednotkové částky pro měnu, všechny jednotkové částky v měně budou zaokrouhleny s aktualizovanou přesností. |
| **Desetinná místa v jednotkách** | Některé měny mají jiné formáty pro jednotkové částky, než jsou definovány na stránce **Nastavení hlavní knihy**. Pokud pro měnu změníte desetinná místa částky jednotky, všechny částky jednotky v měně budou zaokrouhleny na aktualizovaná desetinná místa. |
| **Přesnost zaokrouhlení aplikace** | Určuje velikost intervalu, který je povolen jako rozdíl zaokrouhlení při vzájemném použití položek v různých měnách. |
| **Zaokrouhlení převodu LCY. Debetní účet** | Určuje informace o převodu, které musí také obsahovat debetní účet, pokud chcete vložit opravné řádky pro zaokrouhlení rozdílů ve finančních denících pomocí příkazu ** Vložit konv. LCY Rndg. zakázky**. |
| **Konverze LCY Zaokrouhlovací kreditní účet** | Určuje informace o převodu, které musí také obsahovat debetní účet, pokud chcete vložit opravné řádky pro zaokrouhlení rozdílů ve finančních denících pomocí příkazu ** Vložit konv. LCY Rndg. zakázky**. |
| **Poslední datum úpravy** | Datum poslední měnové úpravy. |
| **Datum poslední změny** | Datum změny nastavení měny. |
| **Tolerance platby %** | Maximální tolerance platby % nastavená pro tuto měnu. Další informace naleznete v tématu [ Tolerance platby a Tolerance platební slevy](finance-payment-tolerance-and-payment-discount-tolerance.md). |
| **Max. Částka tolerance platby** | Maximální částka tolerance platby nastavená pro tuto měnu. Další informace naleznete v tématu [ Tolerance platby a Tolerance platební slevy](finance-payment-tolerance-and-payment-discount-tolerance.md). |
| **Měnový faktor** | Určuje vztah mezi měnou a místní měnou pomocí skutečného kurzu měny. |
| **Účet realizovaných zisků hk** | Určuje finanční účet, který se používá k zaúčtování kurzových zisků pro měnové úpravy mezi místní měnou (LCY) a další měnou vykazování. Zisky směnného kurzu se vypočítají při spuštění dávkové úlohy Upravit směnné kurzy pro úpravu účtů hlavní knihy. Toto pole nemusí být ve výchozím nastavení viditelné. Lze jej získat přizpůsobením stránky. |
| **Účet realizovaných hlavních ztrát** | Určuje účet hlavní knihy, který se používá k zaúčtování kurzových ztrát pro měnové úpravy mezi místní měnou (LCY) a další měnou vykazování. Zisky směnného kurzu se vypočítají při spuštění dávkové úlohy Upravit směnné kurzy pro úpravu účtů hlavní knihy. Toto pole nemusí být ve výchozím nastavení viditelné. Lze jej získat přizpůsobením stránky. |
| **Reziduální účet zisků<x2/> | Určuje účet hlavní knihy, který se používá k zaúčtování částek zbytkového zisku (zaokrouhlovacích rozdílů), když je v oblasti aplikace hlavní knihy použita další měna vykazování. Toto pole nemusí být ve výchozím nastavení viditelné. Lze jej získat přizpůsobením stránky. |
| <g1/>Reziduální účet ztrát** | Určuje účet hlavní knihy, který se používá k zaúčtování částek zbytkových ztrát (rozdíly zaokrouhlení), pokud je v oblasti použití hlavní knihy použita další měna vykazování. Toto pole nemusí být ve výchozím nastavení viditelné. Lze jej získat přizpůsobením stránky. |
| **Max. Povolený rozdíl DPH** | Maximální povolená částka pro rozdíly DPH v této měně. Další informace naleznete v tématu [Ruční oprava částek DPH v prodejních a nákupních dokladech](finance-work-with-vat.md#correcting-vat-amounts-manually-in-sales-and-purchase-documents). Toto pole nemusí být ve výchozím nastavení viditelné. Lze jej získat přizpůsobením stránky. |
| **Typ zaokrouhlení DPH** | Určuje metodu zaokrouhlení pro ruční opravu částek DPH v prodejních a nákupních dokladech. Toto pole nemusí být ve výchozím nastavení viditelné. Lze jej získat přizpůsobením stránky. |

### Dostupné měnové funkce

Následující tabulka popisuje klíčové akce na stránce **Měny**.

| Menu | Akce | Popis |
|-------------|--------------|------------------------------|
| **Probíhá** | **Návrh účtů** | Použití účtů z jiných měn. Budou vloženy nejčastěji používané účty. |
|  | **Změna tolerance platby** | Změnit jedno nebo obě: maximální odchylka platby a procentuální odchylka platby a filtry dle měny. Další informace naleznete v tématu [ Tolerance platby a Tolerance platební slevy](finance-payment-tolerance-and-payment-discount-tolerance.md). |
|  | Směnné kurzy | Zobrazit aktualizované směnné kurzy měn, které můžete použít. |
|  | Úprava směnných kurzů | Upravit věcné položky, položky zákazníka, dodavatele a bankovního účtu, aby reflektovaly změnu směnného kurzu od doby, kdy byly položky zaúčtovány. |
|  | **Registr úprav směnných kurzů** | Zobrazit výsledky spuštění dávkové úlohy **Upravit směnné kurzy**. Pro každou měnu nebo každou kombinaci měny a účetní skupiny, která je zahrnuta do úpravy, se vytvoří jeden řádek. |
| **Služba směnných kurzů** | **Služba směnných kurzů** | Zobrazení nebo úprava nastavení služeb, které jsou nastaveny pro načtení aktualizovaných směnných kurzů měn, když zvolíte akci **Aktualizovat směnné kurzy**. |
|  | **Aktualizace směnných kurzů** | Získat nejnovější směnné kurzy měn od poskytovatele služeb. |
| Přehledy | **Zůstatek v cizí měně** | Zobrazení zůstatků pro všechny odběratele a dodavatele v cizích měnách i v místní měně (LCY). Sestava zobrazuje dva zůstatky LCY. Jedním z nich je zůstatek cizí měny převedený na LCY pomocí směnného kurzu v době transakce. Druhým je zůstatek cizí měny převedený na LCY pomocí směnného kurzu pracovního dne. |

## LCY a další měny

[!INCLUDE [finance-currencies-lcy-def](includes/finance-currencies-lcy-def.md)]

## Zaokrouhlení měny

Chcete-li spravovat měny, které nepoužívají desetinná místa, a vyhnout se zbytečným desetinným místům v cizí měně, můžete použít dvě různé funkce zaokrouhlování:

- Zaokrouhlení jednotkové částky

- Zaokrouhlení částky

Tyto funkce mohou pracovat nezávisle nebo v kombinaci. Kromě toho mohou funkce fungovat v souvislosti se zaokrouhlováním faktur.

Na rozdíl od funkcí zaokrouhlování faktur ovlivňují funkce zaokrouhlování částek a jednotkové částky pouze částky v cizí měně – nikoli odpovídající částky v LCY. Tyto dvě funkce nebudou mít za následek žádné zaúčtování na účty hlavní knihy. V důsledku toho není třeba specifikovat žádný účet hlavní knihy na zaúčtovacích skupinách nebo jinde.

### Zaokrouhlení jednotkové částky

Funkce zaokrouhlení jednotkové částky řídí způsob zaokrouhlování prodejních cen položek a zdrojů v cizích měnách na řádcích prodeje a nákupu. Je nutné zadat pravidla pro každou měnu zvlášť v poli **Přesnost zaokrouhlení částky** jednotky v seznamu **Měny**.

Funkce zaokrouhlení jednotkové částky se automaticky použije při každém zadání čísla položky nebo zdroje na prodejní řádek. If the invoice is for a customer with a currency code, the item or resource price is converted into the customer's currency. Cena je zaokrouhlena podle přesnosti zaokrouhlení jednotkové částky pro měnu.

### Zaokrouhlení částky

Funkce zaokrouhlování částek řídí způsob zaokrouhlování částek v cizích měnách na řádcích finančního deníku, řádcích prodeje a řádcích nákupu. Je nutné zadat pravidla pro každou měnu zvlášť v poli **Přesnost zaokrouhlení částky** v seznamu **Měny**.

Částky v cizích měnách jsou zaokrouhleny při vyplňování a zaúčtování řádků finančního deníku, řádků prodeje a řádků nákupu.

## Směnné kurzy

Můžete zaregistrovat směnné kurzy pro každou cizí měnu a určit, od kterých dat jsou směnné kurzy platné. Můžete například zadat denní směnné kurzy, měsíční směnné kurzy nebo čtvrtletní směnné kurzy pro každou cizí měnu.

Historické směnné kurzy můžete zachovat na stránce **Směnné kurzy** měn pro referenční účely. Když potřebujete aktualizovat směnné kurzy, můžete pomocí tlačítka **Aktualizovat směnné kurzy** získat nejnovější směnné kurzy od externího poskytovatele služeb.

## Účty hlavní knihy

Kódy měn nelze propojit s účty hlavní knihy, protože částky na účtech hlavní knihy jsou v LCY. Pokud máte bankovní půjčku v USD a vložíte vklady na bankovní účet v SEK, můžete tyto účty sledovat nastavením bankovních účtů v USD a SEK. Pomocí účetních skupin můžete propojit účty s příslušnými účty hlavní knihy. V hlavní knize je hodnota částek uvedena v LCY.

Můžete zadat kód měny na řádku finančního deníku a zaúčtovat řádek na účet hlavní knihy. Příslušný směnný kurz se používá k převodu částky na LCY před jejím zaúčtováním na účet hlavní knihy.

## Příklad měnové transakce pohledávky

[!INCLUDE [finance-currencies-example](includes/finance-currencies-example.md)]

## Viz také

[Aktualizace směnných kurzů](finance-how-update-currencies.md)    
[Nastavení další vykazovací měny](finance-how-setup-additional-currencies.md)  
