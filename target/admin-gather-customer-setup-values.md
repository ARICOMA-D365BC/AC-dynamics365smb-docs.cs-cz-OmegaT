---
    title: Gather Customer Setup Values | Microsoft Docs
    description: You use the configuration questionnaire to help reduce your implementation workload by streamlining the task of setting up the new company. You can generate the configuration questionnaire in Business Central and then provide it to your customer as an Excel (.xlsx) or XML file.
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
# Shromážďování dat nastavení zákazníka
Pomocí konfiguračního dotazníku můžete snížit pracovní zatížení implementace pomocá zjednodušení úlohy založení nové společnosti. You can generate the configuration questionnaire in [!INCLUDE[prod_short](includes/prod_short.md)] and then provide it to your customer as an Excel or XML file.

Všechny výchozí hodnoty v dotazníku můžete změnit tak, aby lépe odpovídaly potřebám zákazníků.

> [!TIP]  
> For more information about defining setup values in supply planning fields, see [Setup Best Practices: Supply Planning](setup-best-practices-supply-planning.md).

When your customer completes the questionnaire, you import the file into the customer's new [!INCLUDE[prod_short](includes/prod_short.md)] company. Vy a váš zákazník ověříte odpovědi dotazníku před jejich nasazením do společnosti.

## Vytvoření konfiguračního dotazníku
Pomocí dotazníku můžete určit rozsah a potřeby konfigurace. Můžete vytvořit nový dotazník nebo upravit existující dotazník přidáním nových otázek nebo oblastí otázek.

<!-- A configuration questionnaire has the following structure
* The name of the questionnaire itself
* Question Areas that group questions about a similar subject. For example, you might create a question area that focuses on entering company informtion. Typically, configuration questionnaires have many question groups
* Questions that are closed ended, meaning that the customer must choose an answer, and can choose only one. -->

Dotazníky lze vytvořit pouze pro nastavovací tabulky Tento nástroj můžete použít například k poskytnutí informací na následujících stránkách:

- Informace o společnosti
- Nastavení dlouhodobého majetku
- Nastavení financí
- Nastavení zásob
- Nastavení montáže
- Nastavení výroby
- Nastavení nákupů a závazků
- Nastavení marketingu
- Nastavení služby
- Nastavení prodeje a pohledávek
- Nastavení skladu

> [!NOTE]  
> To see a complete list of setup tables, choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Setup**, and then choose the related link. K určení rozsahu migrace dat záznamů použijte funkci migrace. For more information, see [Migrating Customer Data](admin-migrate-customer-data.md).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Configuration Questionnaire**, and choose the related link.
2. Vyberte akci **Nový**.
3. On the **Configuration Questionnaire** page, in the **Code** field, enter...
<!--4. In the **Name** field, enter...
5. Choose the **Question Areas** action. .
6. On the **Config. Question Areas** page, in the **Code** field, enter...
  
    > [!Note]  
    > The code is alphanumeric, and must start with a letter of the alphabet.
7. In the Table ID field, choose the table to which to apply the answer to the question. Your selection will determine the fields that are available for the questions, and thereby the answer selections.
  
    > [!Tip]
    > The list of table objects is long. If you know the name of the table, use **Search** in the upper left to find it in the list.
8. In the **Description** field, enter text that indicates the subject of the question group.
9. In the **No.** field, enter a number to define where the question appears in the sequence of questions.
10. In the **Field ID** field, choose the field the the customer's answer will be applied to. You can choose from the fields on the table you chose in the **Table ID** field.
  
    When you choose a field, [!INCLUDE[prod_short](includes/prod_short.md)] provides a suggestion in the **Question** field. You can edit the question if needed.
11. To add more questions to the questionnaire, repeat steps seven through 10.

> [!Tip]
> If at some point you change a question, or add a new one, choose the **Update Questions** action to update the list.

-->

3. Choose the **Questions Areas** action. The **Question Areas** page opens.
4. Vyberte akci **Nový**. The **Config. Question Area** page opens.
5. In the **Table ID** field, choose the ID of the table for which you want to collect information. The **Table Name** field is automatically filled in.
6. Choose the **Update Questions** action. Každé pole v tabulce je přidáno do dotazníku s otazníkem následujícím po jeho popisku.

Označení můžete změnit tak, aby bylo jasné, jak má být otázka zodpovězena. Pokud se například pole nazývá „Název“, můžete jej upravit tak, že uvedete „Jaký je  <data being collected>." You can also provide guidance in the **Reference** field, including a URL to a page that provides additional information.

Můžete také odstranit všechny otázky, které nechcete do dotazníku zahrnout.

> [!NOTE]  
> The **Answer Option** field describes the type and format of the answer of the data that is appropriate. The **Answer** field contains user-supplied information.
>
> As needed, you can also define default answers in the **Answer** field. Tyto hodnoty jsou ve výchozím nastavení použity pro vlastní nastavení. Osoba vyplňující dotazník však může odpověď upravit a aktualizovat.

## Dokončení konfiguračního dotazníku
Pomocí konfiguračního dotazníku můžete strukturovat a dokumentovat podrobnou diskusi o konkrétních potřebách zákazníka. You also use it to collect setup data from the customer to configure the relevant [!INCLUDE[prod_short](includes/prod_short.md)] setup tables, such as the general ledger, inventory, and customers.

> [!NOTE]  
> You can also create your own configuration questionnaire to meet your needs.

1. Otevřete společnost, pro kterou chcete vyplnit dotazník.
2. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Configuration Questionnaire**, and then choose the related link.
3. Select the questionnaire for the company, and then choose the **Export to Excel** action, optionally the **Export to XML** action.
4. Nechte zákazníka vyplnit konfigurační dotazník zadáním odpovědí do sešitu Excel. Pro každou oblast otázek, které byly pro dotazník vytvořeny, existují sešity.
5. Save the Excel workbook as *XML Data*. Choose the **Import from XML** action, and select the .xml file with the customer's answers.
6. Choose the **Question Areas** action to begin the process of validating and applying the answers to the configuration questionnaire.

## Vyplnění dotazníku z konfiguračního sešitu
Následující postup poskytuje alternativní způsob přístupu ke konfiguračním dotazníkům. Předpokládá, že konfigurační balíček, který jste poskytli, obsahuje dotazníky.

1. Po importu konfiguračního balíčku otevřete sešit konfigurace.
2. For each table for which there is a question area, choose the **Questions** action. Otevře se stránka dotazníku.
3. Answer the questions, and then choose the **Apply Answers** action.
4. Choose the **OK** button to close the questionnaire.

## Ověření konfiguračního dotazníku
It is important to validate the configuration questionnaire before you apply it to the [!INCLUDE[prod_short](includes/prod_short.md)] format. Je to také způsob, jak zajistit, že formátování dat bude zachováno během importu z Excelu.

Běžným úkolem ověření je zkontrolovat, zda nejsou textové řetězce zadány do datových polí. This review process is necessary because the format of the answer in the questionnaire is not validated automatically when you run the **Apply Answers** function.

> [!NOTE]  
> In general, validation of the configuration questionnaire is a manual process. Existují však kontroly nesrovnalostí v regionálním formátování. In addition, you will get errors if the structure of your [!INCLUDE[prod_short](includes/prod_short.md)] database does not match the structure of the migration database.

1. On the **Configuration Questionnaire** page, select the relevant questionnaire, and then choose the **Question Areas** action.
2. Otevření příslušné oblasti otázek.
3. For each question, validate that the value in the **Answer** field corresponds to the format provided in the **Answer Option** field. Ověřte například, zda je adresa společnosti v textovém formátu.
4. Pokud zjistíte chyby, můžete vyřešit a provést opravy v Excelu exportováním dotazníku a následným importem. Alternatively, you can correct errors directly in [!INCLUDE[prod_short](includes/prod_short.md)] as you review the answers on the **Config. Question Area** page.
5. Tyto kroky opakujte pro každou oblast otázek.

Po dokončení ověřování jsou data připravena k použití v databázi.

## Použití odpovědí z konfiguračního dotazníku
After you have imported and validated information from a configuration questionnaire, you can transfer, or apply the setup data to the corresponding tables in the [!INCLUDE[prod_short](includes/prod_short.md)] database.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Configuration Questionnaire**, and then choose the related link. The **Config. Questionnaire** page opens.
2. Select a configuration questionnaire from the list, and then choose the **Edit List** action.
3. Odpovědi můžete použít jedním ze dvou způsobů.

- To apply the whole questionnaire, choose the **Apply Answers** action.
- To apply answers for a specific **Question Area** only, choose the **Question Areas** action, select a **Question Area** in the list, and then choose the **Apply Answers** action.

### Ověření úspěšného použití odpovědí
1. Check setup pages for the various functional areas of [!INCLUDE[prod_short](includes/prod_short.md)]. To locate the page, choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter the name of the setup page, and then choose the related link.
2. Ověřte, zda byla pole naplněna správnými údaji z různých oblastí otázek v konfiguračním dotazníku.

Nyní jste nakonfigurovali nastavení s obchodními informacemi a pravidly zákazníka.

## Viz také
[Setting Up a Company With RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]