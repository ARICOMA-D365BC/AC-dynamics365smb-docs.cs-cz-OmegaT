---
    title: Set Up Base Calendars
    description: You can assign a base calendar to your company and its business partners, to calculate delivery and receipt dates according to the specified working days.
    author: SorenGP

    
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.form: 7600, 7601, 7602, 5703
    ms.date: 06/11/2021
    ms.author: edupont

---
# Nastavení základních kalendářů

Společnosti a jejím obchodním partnerům, jako jsou zákazníci, dodavatelé nebo lokace, můžete přiřadit základní kalendář. Data dodání a příjmu na budoucí prodejní objednávce, nákupní objednávce, objednávce transferu a řádcích výrobní zakázky se počítají podle určených pracovních dnů kalendáře. Hlavním úkolem při nastavování nového základního kalendáře je určení a definování nepracovních dnů, které chcete použít.

## Nastavení základního kalendáře

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Base Calendar**, and then choose the related link.
2. Vyberte akci **Nový**.
3. Fill in the **Code** field.
4. Choose the **Maintain Base Calendar Changes** action.
5. On the **Base Calendar Changes** page, use the **Recurring System** field to mark a particular date or day as a recurring nonworking day. You can select either the **Annual Recurring** or **Weekly Recurring** option.

   If you select **Annual Recurring**, you must also enter the relevant date in the **Date** field.

   If you select **Weekly Recurring**, you must also select the relevant day of the week in the **Day** field. If you leave the field empty, you must fill in the **Date** field. The **Day** field is filled in automatically.

When you make an entry, the **Nonworking** field is selected. You can choose to clear the check mark to make it a working day.  
When you return to the base calendar card, you will observe that the nonworking day entries that you made have been updated. These entries now appear in red and the **Nonworking** field is selected.

> [!NOTE]  
> When setting up a new base calendar, you can select and copy lines from an existing calendar. You do this in the relevant **Base Calendar Changes** page.

> [!IMPORTANT]  
> Any base calendar defined for the vendor or the location affects how the dates are calculated and rounded to working days.
> Určuje vzorec data pro čas potřebný k doplnění zboží. It is used to calculate the **Planned Receipt Date** field, if calculating forward, and **Order Date** field, if calculating backwards. See [Lead Time Calculation](across-how-to-assign-base-calendars.md#lead-time-calculation).

## Výpočet průběžné doby

Jakýkoli základní kalendář definovaný pro dodavatele nebo místo ovlivňuje způsob výpočtu dat a zaokrouhlování na pracovní dny. Proto jsou dvě pole data na řádcích nákupní objednávky vypočtena následujícím způsobem za různých podmínek.

| Směr výpočtu | Kalendář dodavatele definován | Kalendář dodavatele není definován |
|---------------------|-----------------------|---------------------------|
| Dopředu | plánované datum přijetí = datum objednávky + dodací lhůta dodavatele (podle kalendáře dodavatele a zaokrouhleno na další pracovní den nejprve v kalendáři dodavatele a poté v kalendáři lokace) | plánované datum přijetí = datum objednávky + dodací lhůta dodavatele (podle místního kalendáře) |
| Zpětně | datum objednávky = plánované datum přijetí - dodací lhůta dodavatele (podle kalendáře dodavatele a zaokrouhlena na předchozí pracovní den nejprve v kalendáři dodavatele a poté v kalendáři lokace) | datum objednávky = plánované datum přijetí - dodací lhůta dodavatele (podle místního kalendáře) |

> [!NOTE]
> In addition to the lead time calculation that affects the planned receipt date and order date, as shown in the above table, warehouse handling time and safety lead time may be added to the formulas to make up the value in the **Expected Receipt Date** field, as follows: Planned Receipt Date + Safety Lead Time + Inbound Warehouse Handling Time = Expected Receipt Date.

> [!Important]
> If your location uses a significantly different calendar than your vendors do, then it is important that you set up specific calendars for those vendors, to calculate optimal vendor lead times. For information about how to set up vendor calendars, see [To assign a base calendar](across-how-to-assign-base-calendars.md#to-assign-a-base-calendar).

The contents of the **Lead Time Calculation** field is copied from either the item card or the SKU card, if the lead time is defined for the item, or on the **Item Vendor Catalog** page, if the lead time is defined for the vendor.

## Přizpůsobení kalendáře
Hlavním úkolem při přizpůsobení základního kalendáře pro vaši společnost nebo jednoho z jejích obchodních partnerů je zadání změn stavu pracovního a nepracovního dne.

Zatímco například základní kalendář obvykle uvádí všechny soboty jako nepracovní dny, přizpůsobený kalendář pro určité umístění může uvádět všechny soboty v měsících listopadu a prosinci, které se zadjí být jako prázninové, tak mohou být jako pracovní dny.

Následující postup používá případ lokace jako příklad. Všimněte si, že v tomto okamžiku jste již k lokaci přiřadili základní kalendář.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Lokace** a poté vyberte související odkaz.
2. Open the location that you want to update, and then select the **Customized Calendar** field. Note that a calendar must be selected in the **Base Calendar Code** field.
3. On the **Customized Calendar Entries** page opens, choose the **Maintain Customized Calendar Changes** action.
4. In the **Customized Calendar Changes**, add lines for customized calendar entries.

   When you enter a line, the **Nonworking** check box is selected. Pokud chcete změnit stav na pracovní den, můžete toto políčko zrušit.

   You can use the **Recurring System** field to set a particular date or day as a recurring nonworking day. You can select either the **Annual Recurring** or **Weekly Recurring** option.

   If you select **Annual Recurring**, you must also enter the relevant date in the **Date** field. If you select **Weekly Recurring**, you must also select the relevant day of the week in the **Day** field. If you leave the field empty, you must fill in the **Date** field. The **Day** field is then filled in automatically. To může být užitečné, pokud chcete označit jednotlivé datum jako nepracovní nebo pracovní den.

5. Zvolte tlačítko **OK**.

On the **Customized Calendar Entries** page, you will observe that the date entries are updated with the changes that you made.

On the Location card, you will observe that the **Customized Calendar** field contains **Yes**, indicating that a customized calendar has been set up.

> [!Important]
> If you do not fill in the **Location Code** field on an order line, your company’s calendar is used.


If you do not fill in the **Shipping Agent Code** field on the order line, your company’s calendar is used.

> [!NOTE]  
> If you make changes to a base calendar for which customized calendar changes exist, all existing customized calendars are updated automatically.

## Přiřazení základního kalendáře
Následující postup ukáže příklad jak naplánovat datum dodání na řádcích prodejních objednávek pro určitého zákazníka.

Základní kalendáře jsou přiřazeny k vaší vlastní společnosti, zákazníkům, prodejcům, lokacím a přepravcům takto:

- On the **Company Information** and **Customer** cards, the base calendar is assigned on the **Shipping** FastTab.
- On the **Vendor** card, the base calendar is assigned on the **Receiving** FastTab.
- On the **Location** card, the base calendar is assigned on the **Warehouse** FastTab.
- On the **Shipping Agents** page, the base calendar is assigned on the **Shipping Agent Services** page.

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi.](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Zákazníci** a poté vyberte související odkaz.
2. Open the **Customer** card for whom you will assign a base calendar.
3. On the **Shipping** FastTab, in the **Base Calendar Code** field, select the base calendar that you want to assign.

> [!IMPORTANT]
> - Pokud společnosti nepřiřadíte základní kalendář, všechna data se počítají jako pracovní dny.
> - Pokud na řádku objednávky zadáte prázdné místo, všechna data se počítají jako pracovní dny.
> - Jakýkoli základní kalendář definovaný pro dodavatele nebo místo ovlivňuje způsob výpočtu dat a zaokrouhlování na pracovní dny.

> [!NOTE]  
> Before you can make customized calendar entries, you must first assign a base calendar to the company.

## Viz také
[Purchasing](purchasing-manage-purchasing.md)  
[Manufacturing](production-manage-manufacturing.md)    
[Inventory](inventory-manage-inventory.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]