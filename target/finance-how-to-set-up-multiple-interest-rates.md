---
    title: How to Set Up Multiple Interest Rates
    description: You can calculate finance charges with multiple interest rates for a specific period. The interest calculation is similar for all financial charges, with variation only in the rate of interest for a specific period.

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
# Nastavení více úrokových sazeb
Pro zpožděné platby v obchodních transakcích se pro různá období používá více úrokových sazeb. Vláda například specifikuje maximální úrok, který má být pro spotřebitele vybrán. Tato úroková sazba může být změněna dvakrát ročně: 1. ledna a 1. července. Úroková sazba mezi podniky (B2B) je smluvními stranami dohodnuta a pro tuto skupinu zákazníků neexistuje žádný limit. Vyhlášená sazba je obvykle o čtyři procenta vyšší, než je obvyklý bankovní úrok.

Při vytváření podmínek penále a upomínek pro zpožděné platby penále můžete zadat více úrokových sazeb tak, aby se penále počítalo z různých úrokových sazeb v různých obdobích.Pro více informací navštivte <x3/>Evidence nového zákazníka<x4/>. For more information, see [Collect Outstanding Balances](receivables-collect-outstanding-balances.md).

## Nastavení více úrokových sazeb
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Finance Charge Terms**, and then choose the related link.
2. On the **Finance Charge Terms** page, select the required finance term, and then choose the **Interest Rates** action.
3. Podle potřeby vyplňte pole. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Zvolte tlačítko **OK**.
5. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png " Řekněte mi, co chcete dělat") zadejte **Podmínky upomínky** a vyberte související odkaz.
6. On the **Reminder Terms** page, select the required reminder term, and then choose the **Levels** action.
7. On the **Reminder Levels** page, select the **Calculate Interest** field.

Když vydáte penále, zobrazí se finanční poplatky s více úrokovými sazbami pro určité časové období. Penále také obsahuje kontaktní údaje o zákazníkovi, společnosti, která oznámení vydala, další částku a celkovou částku. Úvodní položka v penálích je zobrazena tučně. Finanční poplatky se počítají s více úrokovými sazbami za určité časové období a tisknou se po otevření záznamu.

## Viz také
[Collect Outstanding Balances](receivables-collect-outstanding-balances.md)  
[Setting Up Finance](finance-setup-finance.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]