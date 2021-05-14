---
    title: How to Create Custom Company Configuration Packages | Microsoft Docs
    description: As you grow your business, you will likely come to rely on a set of company types that you use with most of your customers. You can streamline your implementation process by turning these types into company configuration packages that are available for reuse.
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
# Vytvoření vlastních konfiguračních balíčků společnosti
Při růstu vašeho podniku se pravděpodobně budete spoléhat na sadu typů společností, které používáte u většiny svých zákazníků. Proces implementace můžete zefektivnit tak, že tyto typy změníte do konfiguračních balíčků společnosti, které jsou k dispozici pro opakované použití.

Obecně vytvořte konfigurační balíček pro každou funkční oblast, například balíček pro nastavení výroby. To umožňuje použít a nastavit nové oblasti ve společnosti podle potřeby.

Dalším přístupem by bylo vytvoření balíčku, který bude obsahovat tabulky definující nastavení, například následující:

- Nastavení dlouhodobého majetku
- Nastavení financí
- Nastavení zásob
- Nastavení výroby
- Nastavení nákupů a závazků
- Nastavení marketingu
- Nastavení služby
- Nastavení prodeje a pohledávek
- Nastavení skladu
- Nastavení obecného účtování
- Nastavení účtování DPH
- Nastavení účtování zásob

To see a complete list of setup tables, Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Manual Setup**, and then choose the related link.

> [!IMPORTANT]
> Use caution if you choose tables or fields that have the same temporal name but are differentiated by special characters, such as %, &, <, >, (, and ). For example, table "XYZ" might contain the "Field 1" and "Field 1%" fields.
>
> The XML processor accepts only some special characters, and will remove those it does not. If removing a special character, such as the % sign in "Field 1%," results in two or more tables or fields with the same name an error will occur when you export or import a configuration package.

## Vytvoření vlastního konfiguračního balíčku společnosti
1. Vytvoření nové společnosti. For more information, see [Creating New Companies in Business Central](about-new-company.md).
3. Založte novou společnost tak, jak potřebujete. Vyplňte všechny požadované tabulky nastavení.
4. Otevřete novou společnost.
5. Open the **Configuration Worksheet** page.
6. Přidejte do sešitu tabulky, které chcete přenést do jiné společnosti. Přiřaďte řádky sešitu k balíčku.
7. Vytvořte dotazník pro nejčastěji používané tabulky nastavení.
8. Vytvořte konfigurační šablony, které usnadní vytváření kmenových dat, jako jsou zákazníci nebo zboží.
9. Exportujte balíček jako soubor .rapidstart.

## Viz také
[Setting Up a Company With RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]