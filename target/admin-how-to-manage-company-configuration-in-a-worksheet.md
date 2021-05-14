---
    title: How to Manage Company Configuration in a Worksheet | Microsoft Docs
    description: The configuration worksheet is the central location in which you can plan, track, and perform your configuration work. You can create a worksheet for each company that you are working with or create a standard configuration worksheet that can be used for configuring multiple identical companies.
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
# Správa společnosti v Sešitu konfigurace
Sešit konfigurace je centrální umístění, ve kterém můžete plánovat, sledovat a provádět konfiguraci. Pro každou společnost, se kterou pracujete, můžete vytvořit pracovní sešit nebo vytvořit standardní konfigurační pracovní sešit, který lze použít pro konfiguraci více identických společností.

Prvním krokem při přípravě konfiguračního balíčku je výběr společnosti, kterou jste již nastavili a upravili tak, aby vyhovovala většině vašich potřeb řešení. Tato společnost slouží jako základ pro vaši konfigurační práci na nových společnostech. V sešitu určíte tabulky, které má vaše konfigurace kontrolovat a zpracovávat. Since most tables in [!INCLUDE[prod_short](includes/prod_short.md)] have relationships and dependencies to other tables, you should also include those related tables as necessary. Společně budou tyto tabulky sloužit jako struktura, kolem které vytvoříte novou firmu. Následující kroky vám pomohou s vytvořením baličku a nasazením vaší konfigurace.

To aide you in tracking and reviewing your work, use the **Config. Package Table** FactBox to see information about records. Use the **Config. Related Tables** FactBox to monitor table relationships.

Následující postupy ukazují, jak přidat a upravit informace o tabulce pro vaši konfiguraci.

## Otevření konfiguračního sešitu
1. In [!INCLUDE[prod_short](includes/prod_short.md)], open the company that is the baseline for configuration, and then open its RapidStart Services Implementer Role Center.
2. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Configuration Worksheet**, and then choose the related link.

## Přidání tabulky do sešitu
1. On the **Config. Worksheet** page, choose the **Edit List** action.
2. On the first line, in the **Line Type** field, select **Table**.
4. In the **Table ID** field, select the table that you want to add to your configuration.
5. In the **Page ID** field, enter the ID of the page that is associated with the table. U standardních tabulek je tato hodnota automaticky vyplněna. U vlastních tabulek musíte uvést ID.
6. In the **Reference** field, enter the URL of a documentation page, for example in Help, that provides best-practice information or instructions o setting up the table.
7. To add related tables, choose the **Get Related Tables** action.

   > [!NOTE]  
   > Related tables will not be added with the **Get Related Tables** action if either of the following is true:
   > - The relation is conditional.  
   >    Example: If you get related tables for the **Customer** table, then the **Location** table will not be added, since it is only conditionally related to the **Customer** table, namely if the **Location Code** field in the **Customer** table is filled in.
   > - The related table is filtered.  
   >    Example: A field in the related table has a WHERE clause. The reason for this is that the involved relations information is stored in the **Field** system table, which is not fully accessible to the application.  
   >    You must add such types of tables manually by following step 4 in this procedure.

8. To modify the resulting list of tables, select a table that you want to remove, and then choose the **Delete** action.
9. Opakujte kroky pro každou tabulku, kterou chcete přidat do konfigurace.
10. To remove duplicate table information that can result from using the **Get Related Tables** action, choose the **Delete Duplicate Lines** action. Tím se odstraní duplicitní tabulky, které mají stejný kód balíčku.

## Přidání více tabulek do konfiguračního sešitu
1. Choose the **Get Tables** action. The **Get Config. Tables** batch job page opens.
2. On the **Options** FastTab, specify the types of tables that you want to add to the configuration, as described in the following table.

   | Možnost | Popis |
   |----------------------------------|---------------------------------------|  
   | **Include with Data Only** | Zaškrtnutím políčka zahrnete pouze tabulky obsahující data. Můžete například přidat tabulku, která již definuje typické platební podmínky, které vaše řešení podporuje. |
   | **Include Related Tables** | Zaškrtněte políčko, chcete-li zahrnout všechny související tabulky. Chcete-li přidat podmnožinu souvisejících tabulek, viz krok 3 v tomto postupu. |
   | **Include Dimension Tables** | Zaškrtněte políčko, chcete-li zahrnout tabulky dimenzí. |
   | **Include Licensed Tables Only** | Zaškrtněte políčko, chcete-li zahrnout pouze tabulky, ke kterým vám umožňuje přístup k licenci, pod kterou vytváříte sešit. |

3. On the **Object** FastTab, set filters as appropriate to specify the types of tables you want to include or exclude.
4. Zvolte tlačítko **OK**. [!INCLUDE[prod_short](includes/prod_short.md)] tables are added to the worksheet. Each entry in the list has a line of type **Table**.
5. To remove duplicate table information that can result from using the **Get Tables** action, choose the **Delete Duplicate Lines** action. Tím se odstraní duplicitní tabulky, které mají stejný kód balíčku.
6. Do sešitu můžete přidat tabulky, které souvisejí s vybranou tabulkou. Review the information in the **Related Tables** FactBox to see whether there are missing tables. To add related tables for a specific table, select the table in the list, and then choose the **Get Related Tables** action.

   > [!NOTE]  
   > Related tables will not be added with the **Get Related Tables** action if either of the following is true:
   > - The relation is conditional.  
   >    Example: If you get related tables for the **Customer** table, then the **Location** table will not be added, since it is only conditionally related to the **Customer** table, namely if the **Location Code** field in the **Customer** table is filled in.
   > - The related table is filtered.  
   >    Example: A field in the related table has a WHERE clause. The reason for this is that the involved relations information is stored in the **Field** virtual table and is not available in pages such as the configuration worksheet for performance reasons.  
   >    You must add related tables with such complex relationships manually by following step 4 in [To add a table to the worksheet](admin-how-to-manage-company-configuration-in-a-worksheet.md#to-add-a-table-to-the-worksheet).

7. To delete tables in the resulting list of tables, select a table to remove, and then choose the **Delete** action.

Pomocí následujícího postupu určete, která pole tabulky mají být zahrnuta. Po provedení této specifikace můžete exportovat tabulku do Excelu a strukturu tabulky použít jako šablonu pro shromažďování zákaznických dat. For more information, see [Prepare to Migrate Customer Data](admin-use-templates-to-prepare-customer-data-for-migration.md).

## Určení sady polí a záznamů pro konfigurační tabulku
1. Select a table in the list of configuration tables, and then chose the **Edit List** action.
2. Select a table for which you want to specify field information, and then choose the **Fields** action.
3. To select just the fields that you want to include, choose the **Clear Included** action. To add all fields, choose the **Set Included** action.
4. o specify that the field data should not be validated, clear the **Validate Field** check box for the field.
5. Zvolte tlačítko **OK**.
6. To filter to a certain set of records to include in the configuration worksheet, choose the **Filters** action, and then specify the appropriate filter values.

Můžete vytvořit oblasti funkčnosti a skupin tabulek v sešitu, aby bylo možné podobné funkce umístit společně. Například při nastavování účetní osnovy pro vaši konfiguraci se můžete rozhodnout vytvořit skupinu účtovacích tabulek. Obvykle se oblasti používají k seskupení sady tabulek, které odpovídají funkční oblasti. Každá oblast může obsahovat skupiny. Skupinu lze použít k uspořádání tabulek, které mají společný význam.

Následující postup popisuje, jak přidat označení oblastí a skupin poté, co jste vytvořili počáteční seznam tabulek. Po přidání těchto kategorií můžete pokračovat v přidávání a úpravách seznamu tabulek.

## Zařazení a seskupení funkcionalit v sešitu
1. Na začátku oblasti vložte do sešitu nový řádek.
2. In the **Line Type** field, choose **Area**. In the **Name** field, enter a name for the area.
3. Na začátku seskupování tabulek vložte do Sešitu nový řádek.
4. In the **Line Type** field, choose **Group**. In the **Name** field, enter a name for the area. Název skupiny je automaticky odsazen.
5. To move tables to the appropriate category, select a table to move, and then choose the **Move Up** or **Move Down** action. Případně můžete odstranit řádek Sešitu a tabulku znovu vložit na požadované místo.

Some [!INCLUDE[prod_short](includes/prod_short.md)] tables are standard and the data in these is not likely to change from implementation to implementation. V důsledku toho můžete tyto tabulky po zahrnutí do konfiguračního balíčku odstranit ze sešitu. Po přidání jsou tabulky součástí konfiguračního balíčku.

## Odebrání standardní tabulky v sešitu
Po přidání všech nezbytných tabulek do konfiguračního balíčku určete, které tabulky nebudou vyžadovat pozornost zákazníka.
1. Select the tables, and then delete them by choosing the **Delete** action.

   > [!NOTE]  
   > The tables remain in the package even though they are deleted from the worksheet.

## Kontrola a přizpůsobení existujících databázových dat
Při vytváření konfiguračního balíčku pro řešení si můžete prohlížet a přizpůsobovat dostupná databázová data podle svých potřeb. Databázová tabulka musí mít přidruženou stránku.

## Přizpůsobení dat v databázi

1. On the **Configuration Worksheet** page, identify the tables whose data that you want to view or customize.

   > [!NOTE]  
   > Make sure that each table has a page ID assigned to it. For standard [!INCLUDE[prod_short](includes/prod_short.md)] tables, this value is automatically filled in. U vlastních tabulek musíte uvést ID.

2. Choose the **Database Data** action.

   The [!INCLUDE[prod_short](includes/prod_short.md)] page for the page opens.

3. Kontrola dostupných informací. Upravte data podle potřeby odstraněním záznamů, které nejsou relevantní, nebo přidáním nových.

## Viz také
[Set Up Company Configuration](admin-set-up-company-configuration.md)  
[Setting Up a Company With RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]