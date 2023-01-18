---
title: Set Up FA User-Defined Depreciation Method
description: In Business Central, you can apply a user-defined depreciation method for defining your asset's depreciation method on the Fixed Asset Card page.
author: jill-kotel-andersson


ms.reviewer: edupont
ms.topic: conceptual
ms.search.keywords: user-depreciation
ms.date: 07/05/2021
ms.author: edupont
---

# Nastavení dlouhodobého majetku s uživatelsky definovanými odpisovými metodami

Můžete použít [! INCLUDE[prod_short](includes/prod_short.md)] pro nastavení uživatelem definovaných odpisových metod, jak je popsáno zde.

Pro každou uživatelsky definovanou metodu používáte stránku **Tabulky odpisů**, kde musíte zadat procento odpisů pro každé období (měsíc, čtvrtletí, rok nebo účetní období). Když pak přiřadíte knihu odpisů s uživatelem definovanou metodou k dlouhodobému majetku, musíte nastavit **První uživatelem definované prohlášení. Pole Datum** a **Datum zahájení odpisů ** na stránce ** Knihy odpisů DM**  pro konkrétní dlouhodobý majetek.

Vzorec pro výpočet odpisových částek je:

*Částka odpisu = (Odpis % x Počet dnů odepisování x Základ odpisu) / (100 x 360)*


> [!NOTE]  
> Zatím co datum v poli **První uživ.definované datum. Datum** se používá k určení časových intervalů, je to **Datum zahájení odpisování**, které se používá k určení počtu dnů odepisování. Pokud **První uživ.definované datum. Datum** je dřívější než **Datum zahájení odpisování**, procento pro první období v odpisové tabulce bude použito pouze částečně, když program vypočítá první odpis. To znamená, že majetek nebude do konce posledního období zcela odepsán.

## Přiřazení knihy odpisů k dlouhodobému majetku pomocí uživatelem definované metody odpisování

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png " Řekněte mi, co chcete dělat") zadejte **Dlouhodobý majetek<x5/> a vyberte související odkaz.
2. Vyberte dlouhodobý majetek, pro který chcete nastavit knihu odpisů dlouhodobého majetku.
3. Zvolte akci **Související** a poté zvolte **Dlouhodobý majetek** a poté **Knihy odpisů**. Otevře se stránka **Knihy odpisů DM.**

   Ve výchozím nastavení jsou některá pole, která je třeba vyplnit podle níže uvedených pokynů skrytá, takže je musíte zobrazit. Chcete-li to provést, musíte stránku přizpůsobit. Další informace naleznete v tématu <g6>Přizpůsobení stránky pomocí pásu Přizpůsobení</g6>.
4. V poli **Metoda odpisování** vyberte **Definováno uživatelem**.
5. V poli **Kód odpisové tabulky** vyberte **Tabulku odpisů**, kterou chcete použít.
6. V poli **Počáteční datum odpisu** vyberte počáteční datum pro výpočet odpisů.
7. Použijete-li metodu definovanou uživatelem, **První uživ. definované období Pole Datum** musí být nastaveno na datum, které je stejné nebo dřívější než pole **Počáteční datum odpisů**. Pokud jste vybrali hodnotu v poli **Délka období** v odpisové tabulce, datum v poli **První uživatelem definované období. Datum** musí být počátečním datem účetního období.
8. Buď vyplňte pole **č. odpisových roků** nebo pole **Datum ukončení odpisů**. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## Nastavení uživatelských metod odpisování

Na stránce **Tabulka odpisů** můžete nastavit uživatelem definované metody odpisování. Například můžete nastavit odpis podle počtu jednotek.

1. Vyberte ![Žárovku, která otevře funkci Řekněte mi.](media/ui-search/search_small.png "Řekněte mi, co chcete udělat") ikona, zadejte **Tabulky odpisů**a poté vyberte související odkaz.
2. Na stránce **Seznam odpisové tabulky** vyberte akci **Nový**.
3. Na stránce **Karta odpisové tabulky** vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!TIP]
> Pomocí funkce **Vytvořit tabulku součtu číslic** definujte odpisovou tabulku založenou na metodě *Součet číslic*.

Pokud je u metody *Součet číslic* dlouhodobý majetek odepisován po dobu 4 let, pak se odpisy za každý rok vypočítají následujícím způsobem:

Součet číslic = 1 + 2 + 3 + 4 = 10
Amortizace:

* Rok 1 = 4/10:
* Rok 2 = 3/10:
* Rok 3 = 2/10:
* Rok 4 = 1/10:

### Odpisy založené na počtu jednotek

Tuto uživatelsky definovanou metodu lze také použít k odpisování na základě počtu jednotek, například v případě výrobních strojů se stanovenou životností. Na stránce **Odpisové tabulky** můžete zadat počet jednotek, které lze vyrobit v každém období (měsíc, čtvrtletí, rok nebo účetní období).

### Příklad - Odpisy definované uživatelem

Používáte metodu odpisování, která vám umožňuje rychleji odpisovat majetek pro účely daně z příjmů.

Pro dlouhodobý majetek s tříletou životností pro daňové účely byste použili následující odpisové sazby:

* Rok 1: 25 %
* Rok 2: 38 %
* Rok 3: 37%

Pořizovací cena činí 100 000 LM a odpisovatelná životnost je pět let. [přibližně]Odpisy se vypočítají ročně.

| Datum | Typ zaúčtování DM | Dny | Částka | Účetní hodnota |
| --- | --- | --- | --- | --- |
| 01.01.20 | Pořizovací cena | (Datum zahájení odpisování) | 100 000,00 | 100 000,00 |
| 31.12.20 | Odpisy | 360 | -25,000.00 | 75 000,00 |
| 31.12.21 | Odpisy | 360 | -38,000.00 | 37,000.00 |
| 31.12.22 | Odpisy | 360 | -37,000.00 | 0 |
| 31,12.23 | Odpisy | Žádné | Žádné | 0 |
| 31.12.24 | Odpisy | Žádné | Žádné | 0 |

V předchozím příkladu bylo provedeno **První uživatelem definované období. Pole** Datum a **Datum zahájení odpisů** budou nastavena na 01/01/20 na stránce **Knihy odpisů FA** pro konkrétní dlouhodobý majetek. Pokud však **První uživatelem definované období. Pole Datum obsahuje 01/01/20 a pole Datum zahájení odpisování obsahuje 04/01/20, výsledek bude:

| Datum | Typ zaúčtování DM | Dny | Částka | Účetní hodnota |
| --- | --- | --- | --- | --- |
| 01.01.20 | Pořizovací cena | (Datum zahájení odpisování) | 100 000,00 | 100 000,00 |
| 31.12.20 | Odpisy | 270 | -18,750.00 | 81 250,00 |
| 31.12.21 | Odpisy | 360 | -38,000.00 | 42,250.00 |
| 31.12.22 | Odpisy | 360 | -37,000.00 | 6 250,00 |
| 31,12.23 | Odpisy | 90 | -6 250,00 | 0 |
| 31.12.24 | Odpisy | Žádné | Žádné | 0 |


## Viz také
[Nastavení dlouhodobého majetku](fa-setup.md)   
[Dlouhodobá aktiva](fa-manage.md)   
[Nastavení odpisů dlouhodobého majetku](fa-how-setup-depreciation.md)   
[Metody odpisování dlouhodobého majetku](fa-depreciation-methods.md) 

[!INCLUDE[footer-include](includes/footer-banner.md)]
