---
title: Rules for Automatic Application of Payments
description: Read about how to set Up Rules for the Automatic Application of Payments on the Payment Application Rules page.
author: SorenGP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment process, direct payment posting, reconcile payment, expenses, cash receipts
ms.search.form: 1290, 1294, 1287
ms.date: 06/25/2021
ms.author: edupont

---
# Nastavení pravidel pro automatickou aplikaci plateb

Na stránce **Pravidla aplikace platby** nastavíte pravidla, která určují, jak je text platby (u bankovní transakce) automaticky spárován s textem na souvisejících otevřených (nezaplacených) fakturách, dobropisech nebo jiných položkách při použití **Použít automaticky** funkce na stránce **Deník odsouhlasení plateb**. Pro více informací navštivte **Automatické odsouhlasení plateb**.

Nová pravidla aplikace platby nastavíte tak, že zvolíte, které typy dat na řádku deníku odsouhlasení plateb se musí shodovat s daty o jedné nebo více otevřených položkách, než bude související platba automaticky použita na otevřené položky. Kvalita každé automatické aplikace je zobrazena jako hodnota **Nízká** až **Vysoká** v poli **Spolehlivost shody** na stránce **Deník odsouhlasení plateb** podle použitého pravidla platební aplikace.

Každý řádek na stránce **Pravidla aplikace platby** představuje pravidlo žádosti o platbu. Pravidla se používají v pořadí určeném v poli **Pořadí řazení**. Pokud je současně použito více pravidel, použije se shoda nejvyššího seřazeného pravidla.

Funkce automatické aplikace je založena na prioritních kritériích shody. Nejprve se funkce pokusí v pořadí podle priority porovnat text v pěti polích **Související strana** na řádku deníku s textem na bankovním účtu, jménu nebo adrese zákazníků nebo dodavatelů s nezaplacenými dokumenty představujícími otevřené položky. Poté se funkce pokusí porovnat text v polích **Text transakce** a **Další informace o transakci** na řádku deníku s textem v polích **Číslo externího dokladu** a **Č. dokumentu** u otevřených položek. Nakonec se funkce pokusí porovnat částku v poli **Částka výkazu** na řádku deníku s částkou na otevřených položkách.

> [!NOTE]
> Shoda textu je možná pouze pro text delší než čtyři znaky.

Kromě kritérií pro přiřazování platí pro znaménko částky platby toto:

- U záporných částek je nejprve provedena shoda s otevřenými položkami představujícími faktury odběratele a poté s dobropisy dodavatele.
- U kladných částek je nejprve provedena shoda s otevřenými položkami představujícími faktury dodavatele a poté s dobropisy odběratele.

## Nastavení pravidla žádosti o platbu
1. Vyberte ![ Žárovku, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat") ikona, zadejte **Pravidla žádosti o platbu** a poté vyberte související odkaz.
2. Definujte nové nebo upravené pravidlo platební aplikace vyplněním polí na řádku, jak je popsáno v následující tabulce.

|Pole|Popis|
|-|-|
|**Důvěra shody**|Udává vaši důvěru v pravidlo aplikace, které definujete na řádku. <br /></br>Hodnota, kterou zadáte v tomto poli, se zobrazí v poli **Důvěra shody** na stránce **Deník odsouhlasení plateb** podle kvality automatického žádost o platbu na řádku deníku.|
|**Priorita**|Určuje prioritu pravidla aplikace vzhledem k ostatním pravidlům aplikace, která jsou definována jako řádky na stránce **Pravidla aplikace platby**. 1 představuje nejvyšší prioritu.|
|**Shoda se spřízněnou stranou**|Uvádí, kolik informací o zákazníkovi nebo dodavateli, jako je adresa, název města a číslo bankovního účtu, na řádku deníku odsouhlasení plateb se musí shodovat s informacemi o otevřené položce než bude použito aplikační pravidlo pro automatické připsání platby na otevřený záznam.|
|**Doc. Č./příp. Doc. Č.. Shoda**|Uvádí, zda se text na řádku deníku odsouhlasení plateb musí shodovat s hodnotou v poli **Číslo dokumentu** nebo **Číslo externího dokladu** v otevřeném poli záznam před aplikačním pravidlem bude použit k automatickému uplatnění platby na otevřený záznam.|
|**Částka vč. Odpovídající tolerance**|Uvádí, kolik položek pro zákazníka nebo dodavatele musí odpovídat částce včetně tolerance platby, než bude pravidlo aplikace použito k automatickému použití platby na otevřenou položku.|
|**Vyžadována kontrola**|Uvádí, zda je aplikace pro automatické platby doporučena k manuální kontrole uživatelem před odesláním. Výběrem pole **Řádky ke kontrole** na stránce **Deník platebních aplikací** spustíte řízené prostředí, kde můžete snadno zkontrolovat více žádostí v sekvenci na stránce **Kontrola žádosti o platbu**.|

Následující tabulka popisuje standardní pravidla aplikace platby v [!INCLUDE[prod_short](includes/prod_short.md)].

> [!Important]
> Pravidla žádosti o platbu se mohou ve vaší implementaci [!INCLUDE[prod_short](includes/prod_short.md)] lišit.

| Jistota shody | Priorita | Spřízněná strana se shoduje | Doc. Č./příp. Doc. Č.. Shoda | Částka vč. Odpovídající tolerance |
|------------------|----------|-----------------------|--------------------------------|--------------------------------|
| Vysoká | 1 | Plně | Ano - Více | Jedna shoda |
| Vysoká | 2 | Plně | Ano - Více | Více shod |
| Vysoká | 3 | Plně | Ano | Jedna shoda |
| Vysoká | 4 | Plně | Ano | Více shod |
| Vysoká | 5 | Částečně | Ano - Více | Jedna shoda |
| Vysoká | 6 | Částečně | Ano - Více | Více shod |
| Vysoká | 7 | Částečně | Ano | Jedna shoda |
| Vysoká | 8 | Plně | Ne | Jedna shoda |
| Vysoká | 9 | Ne | Ano - Více | Jedna shoda |
| Vysoká | 10 | Ne | Ano - Více | Více shod |
| Střední | 1 | Plně | Ano - Více | Nezvažuje se |
| Střední | 2 | Plně | Ano | Nezvažuje se |
| Střední | 3 | Plně | Ne | Více shod |
| Střední | 4 | Částečně | Ano - Více | Nezvažuje se |
| Střední | 5 | Částečně | Ano | Nezvažuje se |
| Střední | 6 | Ne | Ano | Jedna shoda |
| Střední | 7 | Ne | Ano - Více | Nezvažuje se |
| Střední | 8 | Částečně | Ne | Jedna shoda |
| Střední | 9 | Ne | Ano | Nezvažuje se |
| Nízký | 1 | Plně | Ne | Žádné shody |
| Nízký | 2 | Částečně | Ne | Více shod |
| Nízký | 3 | Částečně | Ne | Žádné shody |
| Nízký | 4 | Ne | Ne | Jedna shoda |
| Nízký | 5 | Ne | Ne | Více shod |

## Podívejte se na související školení na webu [Microsoft Learn](/learn/modules/reconciliation-journals-dynamics-365-business-central/index)

## Viz také
[Odsouhlasení plateb pomocí automatické aplikace](receivables-how-reconcile-payments-auto-application.md)    
[Správa pohledávek](receivables-manage-receivables.md)    
[Prodej](sales-manage-sales.md)    
[Práce s [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]