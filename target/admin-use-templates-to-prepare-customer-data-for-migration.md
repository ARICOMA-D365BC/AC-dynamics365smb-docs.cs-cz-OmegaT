---
    title: Prepare Customer Data Migration with Templates
    description: Learn how to use configuration templates to structure existing customer data before you migrate the master data to the new company in Business Central.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/14/2021
    ms.author: edupont

---
# Prepare to Migrate Customer Data with Templates

After you import and apply setup data in the new database, you can start migrating the customer's existing master data, such as item and customer numbers and names. Chcete-li se ujistit, že se tato data v nové společnosti vytvářejí rychle a přesně, měli byste je strukturovat pomocí šablon.

Obvykle vytvoříte datové šablony pro následující tabulky hlavních dat:

- **Contact**
- **Zákazník**
- **Zboží**
- **Vendor**

However, you can create a template structure for and apply it to any table in [!INCLUDE[prod_short](includes/prod_short.md)].

> [!TIP]  
> You can also use data templates for daily operations to create new records that are based on templates. Tyto datové šablony fungují pouze pro podporované tabulky hlavních dat. For more information, see, for example, [Register New Items](inventory-how-register-new-items.md).

Při importu zákaznických dat, například u zboží, ze souboru jsou povinná pole, která jste zadali, převzata z propojené datové šablony. Když vytvoříte nové zboží, zadáte pouze obecné informace, jako je název, popis a cena, a poté shromáždíte zbývající data povinného pole z vybrané datové šablony.

Při vytváření nového záznamu kmenových dat, například zákaznické karty, jsou některá pole povinná a musí být vyplněna. Můžete seskupovat většinu povinných polí, jako jsou například účto skupiny a platební podmínky, aby bylo vytváření záznamů hlavních dat snazší a stabilnější. For example, you can group mandatory fields for table 18, **Customer**, as **Domestic**, **Foreign**, or **Export** types.

> [!NOTE]
> Fields of type Blob cannot be exported/imported using Excel.

## Výběr datové šablony

Když vyberete existující datovou šablonu, musíte posoudit, zda šablony, které jste vytvořili pro novou společnost, jsou pro zákazníka dostačující. Zkontrolujte poskytnutá pole a hodnoty a určete, které šablony jsou vhodné pro novou společnost.

> [!TIP]  
> You can also use data templates to create new records quickly. Používejte je k rychlejšímu a přesnějšímu vytváření dat. Pro více informací navštivte [Evidence nového zboží](inventory-how-register-new-items.md).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Configuration Templates**, and then choose the related link.
2. On the **Configuration Templates** page, select a data template from the list, and then choose the **Edit** action.

Pokud výchozí šablony nesplňují vaše potřeby, můžete vytvořit nové šablony nebo přidat pole do existující šablony. Pokud jsou výchozí šablony dostatečné, můžete je použít k vytvoření záznamů na základě šablon kmenových dat.

## Vytvoření nové datové šablony

Pokud výchozí šablony neodpovídají potřebám nové společnosti, můžete vytvořit novou datovou šablonu.

> [!TIP]
> If you are creating more than one, you may find it useful to adopt a naming convention for the **Code** field.

Each template consists of a header and a line for each field to include in the template. Když vytvoříte šablonu, můžete určit, která pole mají být vždy použita pro data určitého typu. Můžete například vytvořit různé šablony zákazníků, které se použijí na různé typy zákazníků. Když vytvoříte zákazníka pomocí šablony, můžete použít data šablony k předběžnému vyplnění určitých polí.

### Kopírování existující datové šablony

Novou šablonu dat můžete rychle vytvořit zkopírováním informací z existující šablony dat, kterou potom upravíte.

1. Open the **Configuration Templates** page.
2. Vyberte akci **Nový**.
3. Fill in the **Code** field.
4. Choose the **Copy Config. Template** action.
5. On the **Configuration Templates** page, select an existing template to copy, and then choose the **OK** button.

ID tabulky, název tabulky a řádky existující šablony dat jsou vloženy do nové šablony.

### Ruční vytvoření záhlaví šablony dat

1. Open the **Configuration Templates** page.
2. Vyberte akci **Nový**.
3. Fill in the **Code** field.
4. In the **Table ID** field, enter the table to which this template applies. The **Table Name** field is automatically filled in when the **Table ID** field is set.

### Ruční vytvoření řádku šablony dat

1. On the first line, select the **Field Name** field. The **Field List** page displays the list of fields in the table.
2. Select a field, and then choose the **OK** button. The **Field Caption** field is filled in with the field name.
3. In the **Default Value** field, enter an appropriate value. V některých případech je vhodné použít hodnotu, která není hodnotou dostupnou v databázi. In that case, you can select the **Skip Relation Check** check box, to make it possible to apply data without error.

   > [!TIP]  
   > Since the **Default Value** field does not have a look up to the corresponding [!INCLUDE[prod_short](includes/prod_short.md)] field options, you copy and paste the value that you want from the related page into the template.

4. Select the **Mandatory** check box if users must fill in the field in question.

   > [!NOTE]
   > The check box is informational only. Není vynucena žádná obchodní logika. Například uživatelé nemohou zaúčtovat fakturu, pokud nebyly vytvořeny účto skupny. You can select the **Mandatory** check box for those fields to have the user fill them in and thereby avoid a posting error later.
5. In the **Reference** field, enter information about the field as needed.
6. Zvolte tlačítko **OK**.

## Export do šablony do aplikace Excel

Můžete vytvořit sešit aplikace Excel, který bude sloužit jako šablona, která se rychle zakládá na struktuře existující databázové tabulky. You can then use the template to gather together customer data in a consistent format for later import into [!INCLUDE[prod_short](includes/prod_short.md)].

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Configuration Worksheet**, and then choose the related link.
2. Přidejte tabulku do seznamu nebo vyberte existující tabulku. For more information, see [Manage Company Configuration in a Worksheet](admin-how-to-manage-company-configuration-in-a-worksheet.md).
3. Choose the **Shows Fields** action to define the fields from the table that you want to include in the template.
4. Choose the **Export to Template** action.
5. Pojmenujte a uložte soubor aplikace Excel. Sešit aplikace Excel se automaticky otevře.

Nyní můžete zadat údaje o zákaznících do sešitu aplikace Excel. Pokud jste exportovali více tabulek, bude každá tabulka na samostatném listu. Před dalším postupem uložte sešit.

> [!NOTE]  
> You may encounter the following error when you run an English version of Excel, but have your regional settings configured for a non-English language: "Old format or invalid type library." To fix this error, make sure that the language pack for the non-English language is installed.

## Import ze šablony v aplikaci Excel

1. On the **Configuration Worksheet** page, and then choose the **Import from Template** action.
2. Navigate to the template worksheet that you have created, and then choose the **Open** action.
3. To add the collected customer data to the database, choose the **Apply Data** action.

Použijete-li data ze šablony aplikace Excel do tabulky, ve které je také Šablona konfigurace s touto šablonou propojena v konfiguračním balíčku, budou použity také výchozí hodnoty polí z šablony konfigurace.

Každý záznam, jehož data jsou použita tímto způsobem, je úplný, protože se skládá z dat zadaných uživatelem v Excelu plus výchozích hodnot určených konfigurační šablonou.

> [!NOTE]
> If the data in the tables in the configuration package contains dates, for example, posting dates on invoices, the dates are considered in the time zone specified in [!INCLUDE[prod_short](includes/prod_short.md)].


## Vytvoření záznamu z konfigurační šablony

Strukturu dat obsaženou v šablonách dat můžete použít k převedení informací na záznamy v databázi, jeden po jednom. To do so, you use the **Create Instance** function. Jedná se o miniaturní verzi procesu migrace dat, která může být užitečná při vytváření prototypů nebo zpracování menších úloh vytvoření dat.

Následující kroky popisují, jak vytvořit kartu zboží z šablony zboží. Stejným postupem můžete vytvořit záznam z libovolné datové šablony.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Configuration Templates**, and then choose the related link.
2. Select the **Item** template, and then choose the **Edit** action. For more information, see [To create a data template](admin-use-templates-to-prepare-customer-data-for-migration.md#to-create-a-new-data-template).
3. Choose the **Create Instance** action. Vytvoří se karta zboží.
4. Zvolte tlačítko **OK**.
5. To review the new item card, choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.
6. Otevřete novou kartu zboží.
7. Rozbalte záložky s náhledem a ověřte, zda byly informace na nich správně vytvořeny.

## To use conversion templates

You can convert contacts into customers, vendors and employees.

### To convert a contact into a customer, vendor or employee
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Contacts**, and then select the correct contact.
2. On the Contact Card select **Actions**, then **Functions** and then select **Create as Customer, Vendor, Bank, or Employee**.


## Použití konfigurační šablony na záznamu

You can apply a data template to any record that is in [!INCLUDE[prod_short](includes/prod_short.md)] and use this technique to change or modify a record. Když to však uděláte, přepíšete stávající hodnoty v záznamu hodnotami šablony. Proto byste měli být opatrní při použití šablony nad existujícími záznamy.

> [!WARNING]  
> The **Apply Template** function overwrites existing data in a record. Pokud je tato funkce použita při migraci kmenových dat, přepíše importovaná data při vytváření záznamů.

Následující postup je založen na nové kartě zákazníka.

1. Vytvoření zákazníka. Pro více informací navštivte <x3/>Evidence nového zákazníka<x4/>.
2. On the **Customer Card** page, choose the **Apply Template** action.
3. On the **Customer Templates** page, select one of the templates, and then choose the **OK** button.

Výchozí hodnoty z vybrané zákaznické šablony jsou vloženy na kartu zákazníka.

> [!NOTE]
> You cannot use Apply Template to blank out fields on customers, suppliers, and the like. Instead you need to use the **Edit in Excel** functionality. For more information, see [Edit in Excel](across-work-with-excel.md#edit-in-excel).

## Viz také

[Setting Up a Company With RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)  
[Register New Customers](sales-how-register-new-customers.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]