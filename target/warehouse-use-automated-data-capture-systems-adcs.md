---
title: Use Automated Data Capture Systems (ADCS)
description: You can use your automatic data capture system (ADCS) to register the movement of items in the warehouse and to register some journal activities.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: barcode
ms.search.form: 7700, 7703, 7704, 7706, 7707, 7710
ms.date: 06/25/2021
ms.author: edupont

---
# Použití automatizovaných systémů pro sběr dat (ADCS)

> [!NOTE]
> The Automated Data Capture System (ADCS) solution provides a way for [!INCLUDE[prod_short](includes/prod_short.md)] to communicate with handheld devices through web services. You must work with a Microsoft partner who can provide the link between the web service and the specific handheld device.

Pomocí automatického systému sběru dat (ASSD) můžete evidovat pohyb položek ve skladu a evidovat některé činnosti deníku, jako je například úprava množství v deníku zboží skladu a fyzických inventur. ADCS typically involves scanning a barcode.

Chcete-li použít ASSD, musíte každému uloženému zboží ve skladu zadat identifikátor. Musíte také nastavit miniformuláře, ruční funkce, výměny dat a zadat nastavení pro pole, která ovládají ASSD. Určíte, zda se má použít ASSD na kartě lokace.

Na základě potřeb vašeho skladu definujete množství informací zobrazených v nastavení miniformuláře pro konkrétní ruční zařízení. Níže jsou uvedeny příklady informací, které můžete zobrazit:

- Data from tables within [!INCLUDE[prod_short](includes/prod_short.md)], such as a list of pick documents from which the user can select.
- Textové informace.
- Zprávy, které zobrazují potvrzení nebo chyby týkající se činností prováděných a evidovaných uživatelem ručního zařízení.

## To enable Web Services for ADCS
To use Automated Data Capture System, you must enable the ADCS web service.

## To enable and publish the ADCS web service

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Web Services**, and then choose the related link.
2. Vyberte akci **Nový**.
3. On the **Web Services** page, enter the following information on a new line:

   | Pole | Hodnota |
   |---------------------------------|-----------|  
   | **Object Type** | Codeunit |
   | **Object ID** | 7714 |
   | **Service Name** | ADCS **Important:** It is required that you name the service **ADCS**. |

5. Select the **Published** check box.
6. Zvolte tlačítko **OK**.

## Nastavení skladu pro použití ASSD
Chcete-li používat ASSD, musíte určit, které lokace technologii budou používat.

> [!NOTE]  
> We recommend that you do not set up a warehouse to use ADCS if the warehouse also has a bin capacity policy.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and choose the related link.
2. Select a warehouse from the list for which you want to enable ADCS, and then choose the **Edit** action.
3. On the **Location Card** page, select the **Use ADCS** check box.

## Určení zboží pro použití ASSD
Každému zboží skladu, které chcete použít s ASSD, musí být přiřazen identifikační kód, který jej propojí s číslem zboží. Jako kód identifikátoru můžete například použít čárový kód zboží. Zboží může mít také více identifikačních kódů. To může být užitečné v případě, kdy je zboží k dispozici v různých měrných jednotkách, například v kusech a paletách. V takovém případě každému přiřaďte identifikační kód.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat") zadejte **Zboží** a poté vyberte související odkaz.
2. Select an item from the list that is part of your ADCS solution, and then choose the **Edit** action.
3. On the **Item Card** page, choose the **Identifiers** action.
4. On the **Item Identifiers** page, choose the **New** action.
5. In the **Code** field, specify the identifier for the item. Například identifikátor může být číslo čárového kódu zboží.

   You can also enter a **Variant Code** and a **Unit of Measure** code.

6. V případě potřeby zadejte pro každé zboží více kódů.
7. Zvolte tlačítko **OK**.
8. To review the information, choose the **Identifier Code** field to open the **Item Identifiers** page.

## Přidání uživatele ASSD
Jako uživatele automatizovaného systému pro sběr dat (ASSD) můžete přidat libovolného uživatele. Pokud to uděláte, musí uživatel zadat také heslo. Volitelně můžete také poskytnout připojení, které identifikuje uživatele ASSD jako zaměstnance skladu. Heslo uživatele ASSD se může lišit od přihlašovacího hesla uživatele systému Windows. For more information, see [Assign Permissions to Users and Groups](ui-define-granular-permissions.md).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **ADCS Users**, and then choose the related link.
2. Vyberte akci **Nový**.
3. In the **Name** field, enter a name for the user. Název nesmí obsahovat více než 20 znaků včetně mezer.
4. In the **Password** field, enter a password. Heslo je maskováno.

### Určení, který zaměstnanec skladu je uživatel ADCS (ASSD)
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Employees**, and then choose the related link.
2. V případě potřeby přidejte nového zaměstnance skladu. For more information, see [Set Up Warehouse Employees](warehouse-how-to-set-up-warehouse-employees.md).
3. Choose the **Edit List** action.
4. Ze seznamu vyberte zaměstnance skladu. In the **ADCS User** field, choose the drop-down arrow, and then select the name of an ADCS user from the list.

> [!NOTE]  
> The default warehouse for the employee must be one that uses ADCS.

## Vytvoření a přizpůsobení miniformulářů
Miniformuláře se používají k popisu informací, které chcete prezentovat na kapesním zařízení. Můžete například vytvořit miniformuláře, které podpoří aktivitu skladu vyskladňování zboží. Po vytvoření miniformuláře do něj můžete přidat funkce pro běžné akce, které uživatel přebírá s kapesními zařízeními, jako je například přesunutí na řádku nahoru nebo dolů.

> [!NOTE]
> To implement or change the functionality of a miniform function, you must create a new codeunit for the **Handling Codeunit** field to perform the required action or response. You can learn more about ADCS functionality by examining codeunits, such as 7705, 7706, 7712, and 7713.

### Vytvoření miniformiuláře pro ADCS
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Miniforms**, and then choose the related link.
2. Vyberte akci **Nový**.
3. In the **Code** field, enter a code for the miniform. Volitelně zadejte hodnoty do všech ostatních polí.

   Select the **Start Miniform** check box to indicate that the miniform is the first form that the user sees at logon.

4. On the **Lines** FastTab, define the fields that appear on the miniform. Pořadí, ve kterém zadáváte řádky, je pořadí, ve kterém se řádky objevují na kapesním zařízení.

Pokud jste vytvořili miniformulář, další kroky slouží k vytvoření funkcí a k přidružení funkčnosti pro různé vstupy klávesnice.

### Přizpůsobené funkcí miniformuláře
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Miniforms**, and then choose the related link.
2. Select a miniform from the list, and then choose the **Edit** action.
3. Choose the **Functions** action.
4. In the **Function Code** drop-down list, select a code to represent the function that you want to associate with the miniform. Můžete například vybrat ESC, které spojuje funkčnost s stisknutím klávesy ESC.

## Viz také
[Správa skladu](warehouse-manage-warehouse.md)    
[Zásoby](inventory-manage-inventory.md)    
[Nastavení správy skladu](warehouse-setup-warehouse.md)       
[Správa montáže](assembly-assemble-items.md)      
[Detaily návrhu: Správa skladu](design-details-warehouse-management.md)    
[Práce s [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]