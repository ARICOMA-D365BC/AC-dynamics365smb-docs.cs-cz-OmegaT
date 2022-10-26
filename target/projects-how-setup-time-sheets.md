---
title: Set Up Time Sheets and Their Approval
description: You set up time sheets to track the time used on tasks and projects, helping you with project management, staffing, and capacity
author: SorenGP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: project management, capacity, staff, resource, time sheet
ms.search.form: 977, 462, 76, 77
ms.date: 12/13/2021
ms.author: edupont

---
# Nastavení pracovních výkazů

Pracovní výkazy v [!INCLUDE[prod_short](includes/prod_short.md)] zpracovává časovou registraci v týdenních přírůstcích po sedmi dnech. Můžete je použít ke sledování času použitého na projektech a můžete je použít k zaznamenání jednoduché registrace času zdroje. Před použitím pracovních výkazů je nutné určit, kteří uživatelé budou pracovní výkazy odesílat a jak chcete pracovní výkazy konfigurovat.

> [!TIP]
> V [!INCLUDE [prod_short](includes/prod_short.md)] jsou uživatelé časových výkazů *zdroje*. Tímto způsobem můžete použít pracovní výkazy například ke sledování práce nezaměstnanců. Chcete-li sledovat práci vlastních zaměstnanců nebo používat pracovní výkazy ke sledování nepřítomnosti zaměstnanců, je nutné přidružit *zaměstnance* ke *zdrojům* v průvodci nastavením.

Volitelně zadejte, zda a jak se schvalují časové výkazy. V závislosti na potřebách vaší organizace můžete určit:

* Jednoho nebo více uživatelů jako správce pracovního výkazu a schvalovatele všech pracovních výkazů.
* Schvalovatel pracovního výkazu pro každý zdroj.

Po nastavení časových výkazů můžete vytvořit časové rozvrhy pro zdroje a zdroje mohou zaúčtovat řádky pracovního výkazu. Volitelně můžete přiřadit pracovní výkazy k řádkům plánování úloh. Pro více informací navštivte [Použití pracovních výkazů](projects-how-use-time-sheets.md).

## Nastavení časových výkazů pomocí průvodce asistovaným nastavením

[!INCLUDE [2021_releasewave2](includes/2021_releasewave2.md)]

Počínaje vlnou 2 vydanou v roce 2021 můžete použít průvodce nastavením, který vám pomůže nastavit pracovní výkazy.

> [!TIP]
> Chcete-li tuto funkci používat, musíte na stránce [Správa funkcí](https://businesscentral.dynamics.com/?page=2610) povolit funkci **Aktualizace funkcí: Nové pracovní výkazy**.
>
> Stejná funkce také usnadňuje správu pracovních výkazů na mobilním zařízení.

Otevřete průvodce asistovaným nastavením **Nastavení časových výkazů** ze stránky [Asistované nastavení](https://businesscentral.dynamics.com/?page=1801).

Průvodce asistovaným nastavením vás provede následujícími kroky:

1. Nastavení účastníků v procesech časového rozvrhu

   První stránka v průvodci vám ukáže počet uživatelů ve vašem [!INCLUDE [prod_short](includes/prod_short.md)]. Zobrazuje také další povinné a volitelné informace.
2. Určení prvního dne pracovního týdne v této organizaci

   První den pracovního týdne bude výchozím prvním dnem pro všechny pracovní výkazy.
3. Určete osobu, která spravuje pracovní výkazy

   Tato osoba může upravovat a mazat všechny časové výkazy. Volitelně můžete přidat stejnou roli ostatním lidem na stránce **Nastavení uživatele**.
4. Nastavení zdrojů, které budou používat pracovní výkazy, a osob, které budou pracovní výkazy schvalovat

Na konci průvodce nastavením se můžete rozhodnout nechat [!INCLUDE [prod_short](includes/prod_short.md)] vytvářet pracovní výkazy na základě vaší konfigurace. Prohlédněte si nové časové výkazy na stránce **Časové výkazy**, kterou můžete otevřít [zde](https://businesscentral.dynamics.com/?page=951). Případně spusťte průvodce asistovanou instalací znovu nebo dokončete nastavení ručně.

## Ruční nastavení pracovních výkazů

Následující části popisují, jak nastavit pracovní výkazy, pokud nepoužíváte průvodce asistovaným **Nastavením pracovních výkazů**.

### Ruční nastavení obecných informací pro pracovní výkazy

1. Zvolte ![žárovku, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Nastavení zdrojů** a pak zvolte související odkaz.
2. Vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. V poli **Schválení pracovního výkazu** vyberte jednu z následujících možností.

| Možnost | Popis |
| --- | --- |
| Nikdy | Uživatel v poli **ID schvalovatele pracovního výkazu** na kartě zdroje schvaluje pracovní výkaz. |
| Vždy | Uživatel v poli **Zodpovědně osoba** na kartě projektu schvaluje pracovní výkaz. |
| Pouze počítač | Pokud je pracovní výkaz stroje spojen s projektem, schválí pracovní výkaz uživatel v poli **Zodpovědná osoba** na kartě projektu. Pokud je časový rozvrh stroje spojen se zdrojem, pak pracovní výkaz schválí uživatel v poli **ID schvalovatele pracovního výkazu** na kartě zdroje. |

### Chcete-li ručně přiřadit správce časového rozvrhu

1. Vyberte ikonu ![Žárovky, která otevře ikonu Řekněte mi](media/ui-search/search_small.png "Řeknete mi, co chcete dělat"), zadejte **Nastavení uživatelů** a poté vyberte související odkaz.
2. Přidejte nového uživatele, pokud seznam uživatelů nezahrnuje osobu, kterou chcete mít jako administrátora pracovního výkazu. Další informace o oprávněních naleznete v tématu [Přiřazení práv uživatelům a uživatelským skupinám](ui-define-granular-permissions.md).
3. Vyberte uživatele, který má být správcem pracovního výkazu a zaškrtněte políčko **Správce pracovního výkazu**.

> [!TIP]  
> Doporučuje se určit pouze jednoho uživatele, který bude správcem pracovního výkazu pro společnost. V následujícím postupu nastavíte vlastníka pracovního výkazu a schvalovatele, kde schvalovatel je přiřazen ke každému zdroji.

### Ruční přiřazení vlastníka a schvalovatele pracovních výkazů

1. Vyberte ikonu ![Žárovky, která otevře funkci Řeknete mi.](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Zdroje** a poté vyberte související odkaz.
2. Vyberte zdroj, pro který chcete nastavit možnost používat pracovní výkazy, a zaškrtněte políčko **Použít pracovní výkaz**.
3. Do pole **ID vlastníka pracovního výkazu** zadejte ID vlastníka pracovního výkazu. Vlastník může zadat využití času do časového výkazu a odeslat jej ke schválení. Obecně platí, že pokud je zdrojem osoba, je tato osoba také vlastníkem.
4. Do pole **ID schvalovatele pracovního výkazu** zadejte ID schvalovatele pracovního výkazu. Schvalovatel může schválit, odmítnout nebo znovu otevřít pracovní výkaz.

> [!NOTE]  
> ID schvalovatele pracovního výkazu nemůžete změnit, pokud existují pracovní výkazy, které ještě nebyly zpracovány a mají stav **Odesláno** nebo **Otevřeno**.

## Viz také

[Používejte pracovní výkazy pro projekty](projects-how-use-time-sheets.md)    
[Vytvoření časových výkazů](projects-how-use-time-sheets.md#to-create-time-sheets)    
[Zaznamenejte spotřebu nebo využití zdrojů pro projekty](projects-how-record-job-usage.md)    
[Nastavení projektového řízení](projects-setup-projects.md)    
[Správa projektu](projects-manage-projects.md)    
[Finance](finance.md)    
[Nákup](purchasing-manage-purchasing.md)    
[Prodej](sales-manage-sales.md)    
[Práce s [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]