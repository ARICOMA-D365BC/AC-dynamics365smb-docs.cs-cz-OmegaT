---
    title: How to Subcontract Manufacturing | Microsoft Docs
    description: When the purchase order has been created from the subcontractor worksheet, then it can be posted.
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
# Subdodavatelská výroba
V mnoha výrobních společnostech je subdodavatelská výroba dodavateli běžná. Subdodávky mohou být vzácným jevem nebo mohou být nedílnou součástí všech výrobních procesů.

[!INCLUDE[prod_short](includes/prod_short.md)] provides several tools for managing subcontract work:

- Pracovní centra s přiřazeným dodavatelem: Tato funkce umožňuje nastavit pracovní centrum, které je spojeno s dodavatelem (subdodavatelem). Toto centrum se nazývá subdodavateléské pracovní středisko. Můžete zadat subdodavatelské pracovní středisko při TNG operaci, což vám umožní snadno zpracovat subdodavatelskou činnost. Kromě toho mohou být náklady na operaci určeny na úrovni TNG postupu nebo pracovního centra.
- Náklady pracovního centra na základě jednotek nebo času: Tato funkce umožňuje určit, zda jsou náklady spojené s pracovním střediskem založeny na době výroby nebo na paušálním poplatku za jednotku. Although subcontractors commonly use a flat charge per unit to charge for their services, the application can handle both options (production time and flat charge per unit).
- Sešity subdodavatelů: Tato funkce vám umožní najít výrobní zakázky s materiálem připraveným k odeslání subdodavateli a automaticky vytvořit objednávky pro subdodavatelské operace z výrobních zakázek. The application automatically posts the purchase order charges to the production order during the posting of the purchase order. Do sešitu subdodavatelů lze přistupovat a používat pouze výrobní zakázky se stavem Vydaná.

## Subdodavatelská pracovní centra
Subdodavatelská pracovní centra jsou zřízena stejně jako běžná pracovní centra s dalšími informacemi. Jsou přiřazeny k TNG postupům stejným způsobem jako ostatní pracovní centra.

### Pole subdodavatelských pracovních středisek
This **Subcontractor No.** field designates the work center as a subcontract work center. Můžete zadat číslo subdodavatele, který zásobuje pracovní centrum. Toto pole lze použít ke správě pracovních středisek, která nejsou interní, ale provádějí zpracování na základě smlouvy.

If you subcontract with the vendor for a different rate for each process, then select the **Specific Unit Cost** field. To vám umožní nastavit náklady na každém řádku technologického postupu a ušetřit čas pro opětovné zadávání jednotlivých nákupních objednávek. Náklady na řádku TNG postupu se používají při zpracování místo nákladů na pole nákladů pracovního centra. Selecting the **Specific Unit Cost** field calculates costs for the vendor by the routing operation.

If you subcontract at a single rate per vendor, leave the **Specific Unit Cost** field blank. The costs will be set up by filling in **Direct Unit Cost**, **Indirect Cost %**, and **Overhead Rate** fields.

### TNG postupy, které používají Subdodavatelská pracovní centra
Pracovní centra subdodávek lze použít pro operace v TNG postupech stejným způsobem jako běžná pracovní centra.

Můžete nastavit TNG postup, který používá externí pracovní středisko jako standardní operační krok. Alternativně můžete upravit TNG postup určité výrobní zakázky tak, aby zahrnoval vnější operaci. To může být nutné v případě nouze, jako je například server, který nepracuje správně, nebo během přechodného období vyšší poptávky, kde musí být práce, která je obvykle prováděna interně, zaslána subdodavateli.

For more information, see [Create Routings](production-how-to-create-routings.md).

## Výpočet sešitů subdodavatelů a vytvoření nákupních objednávek subdodávek
Po výpočtu sešitu subdodavatelů se vytvoří příslušný doklad, v tomto případě nákupní objednávka.

The **Subcontracting Worksheet** page functions like the **Planning Worksheet** by calculating the needed supply, in this case purchase orders, which you review in the worksheet and then create with the **Carry Out Action Message** function.

> [!NOTE]  
> Only production orders with status **Released** can be accessed and used from a subcontracting worksheet.

### Výpočet sešitu subdodavatelů
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Subcontracting Worksheet**, and then choose the related link.
2. To calculate the worksheet, choose the **Calculate Subcontracts** action.
3. On the **Calculate Subcontracts** page, set filters for the subcontracted operations, or the work centers where they are performed, to calculate only the relevant production orders.
4. Zvolte tlačítko **OK**.

   Review the lines on the **Subcontracting Worksheet** page. Informace v tomto sešitě pocházejí z výrobní zakázky a řádků TNG postupu výrobní zakázky a načíta se do nákupní objednávky při vytvoření tohoto dokladu. Řádek můžete odstranit zesešitu bez ovlivnění původních informací, stejně jako u ostatních sešitů. The information will reappear the next time you run the **Calculate Subcontracts** function.

### Vytvoření nákupní objednávky subdodávky
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Subcontracting Worksheet**, and then choose the related link.
2. Vyberte akci **Provést hlášené akce**.
3. Select the **Print Orders** field to print the purchase order as it is created.
4. Zvolte tlačítko **OK**.

Pokud jsou všechny subdodavatelské operace odeslány do stejné lokace dodavatele, je vytvořena pouze jedna objednávka.

Řádek sešitu, který byl převeden na objednávku, je z listu odstraněn. Jakmile je nákupní objednávka vytvořena, již se v sešitě neobjeví.

## Účtování nákupních objednávek subdodávek
Jakmile byly vytvořeny nákupní objednávky subdodavatele, lze je zaúčtovat. Přijetí objednávky zaúčtuje záznam výrobní kapacity do výrobní zakázky a fakturace objednávky zaúčtuje přímé náklady na objednávku do výrobní zakázky.

## Zaúčtování nákupní objednávky subdodávek
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then select the related link.
2. Otevřete nákupní objednávku vytvořenou ze sešitu subdodavatelů.

   Na řádcích objednávek se zobrazují stejné informace jako v sešitu. The **Prod. Order No.**, **Prod. Order Line No.**, **Operation No.**, and **Work Center No.** fields are filled in with the information from the source production order.

3. Vyberte akci **Zaúčtovat**.

Když je nákup zaúčtován tak, jak byl přijat, je výstupní položka deníku automaticky zaúčtována pro výrobní zakázku. Toto platí pouze v případě, že operace subdodávek je poslední operací na TNG postupu výrobní zakázky.

> [!CAUTION]  
> Posting output automatically for an ongoing production order when subcontracted items are received may not be desired. Důvodem může být, že očekávané výstupní množství, které je zaúčtováno, může být odlišné od skutečného množství a že zúčtovací datum automatického výstupu je zavádějící.
>
> Aby se předešlo tomu, že očekávaný výstup výrobní zakázky bude zaúčtován při přijetí subdodavatelských nákupů, ujistěte se, že operace subdodavatele není poslední. Alternativně vložte novou poslední operaci pro konečné výstupní množství.

Když je nákupní objednávka zaúčtována jako fakturovaná, jsou přímé náklady nákupní objednávky zaúčtovány do výroby.

## Viz také
[Manufacturing](production-manage-manufacturing.md)    
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)      
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]