---
    title: Design Details - Outbound Warehouse Flow | Microsoft Docs
    description: The outbound flow in the warehouse begins with a request from released source documents to bring the items out of the warehouse location, either to be shipped to an external party or to another company location. From the storage area, warehouse activities are performed at different complexity levels to bring the items out to the shipping docks.
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
# Detaily návrhu: Výstupní procesy skladu

Výstupní tok ve skladu začíná požadavkem vydaných zdrojových dokladů na vydání zboží ze skladu, které má být dodáno externí straně nebo do jiného skladu společnosti. Z oblasti skladování se různé skladové činnosti provádějí na jistých úrovních složitosti, aby se zboží dostalo do přepravních doků.

Každé zboží je identifikováno a spárováno s odpovídajícím vstupním zdrojovým dokladem. Existují následující výstupní zdrojové doklady:

- Prodejní objednávka
- Výstupní objednávka transferu
- Objednávka nákupní vratky
- Servisní zakázka

Kromě toho existují následující interní zdrojové doklady, které fungují jako výstupní zdroje:

- Výrobní zakázka s potřebou komponent
- Montážní zakázka s potřebou komponent

Poslední dva doklady představují odchozí toky ze skladu do interních provozních oblastí. Další informace o manipulaci se sklady pro interní příchozí a odchozí procesy najdete v [Detaily návrhu: Interní procesy skladu](design-details-internal-warehouse-flows.md).

Procesy a doklady uživatelského rozhraní v odchozích tocích skladu se liší pro základní a pokročilé nastavení skladu. Hlavním rozdílem je, že aktivity jsou zpracovány po objednávkách v základních konfiguracích skladu a jsou konsolidovány pro více objednávek v pokročilých konfiguracích skladu. Další informace o různých úrovních složitosti skladu najdete v [Detaily návrhu: Přehled skladu](design-details-warehouse-setup.md).

In [!INCLUDE[prod_short](includes/prod_short.md)], the outbound processes of picking and shipping can be performed in four ways using different functionalities depending on the warehouse complexity level.

| Metoda | Odchozí proces | Přihrádky | Vyskladnění | Dodávky | Úroveň složitosti (Viz [Detaily návrhu: Nastavení skladu](design-details-warehouse-setup.md)) |
|------|----------------|----|-----|---------|-------------------------------------------------------------------------------------|  
| A | Zaúčtování vyskladnění a dodávky z řádku objednávky | X | 2 |
| B | Zaúčtování vyskladnění a dodávky z dokladu vyskladnění zásob | X | 3 |
| C | Zaúčtování vyskladnění a dodávky z dokladu dodávky ze skladu | X | 4/5/6 |
| D | Zaúčtování vyskladnění z dokladu vyskladnění a zaúčtování dodávky z dokladu dodávky ze skladu | X | X | 4/5/6 |

Výběr přístupu závisí na přijatých postupech společnosti a na úrovni jejich organizační složitosti. V prostředí zpracování objednávek po objednávce s přímočarými procesy a jednoduchou strukturou přihrádek je vhodná metoda A, vychystávání a dodávka z řádku objednávky. V jiných společnostech typu „objednávka po objednávce“, kde zboží pro jeden řádek objednávky může pocházet z více než jedné přihrádky nebo kde pracovníci skladu nemohou pracovat s doklady objednávky, je vhodné použít samostatné doklady vyskladnění, metoda B. Pokud procesy vyskladnění a expedice společnosti zahrnují více zpracování objednávek, a proto vyžadují větší kontrolu a přehled, může se společnost rozhodnout použít doklady dodávky ze skladu a vyskladnění k oddělení výdejních a dodacích úkolů, metod C a Dodávky ze skladu.

V metodách A, B a C jsou akce vyskladnění a dodávky kombinovány v jednom kroku při zaúčtování odpovídajícího dokladu jako dodaný. V metodě D je vyskladnění nejprve zapsáno a poté je dodávka zaúčtována z jiného dokladu.

## Základní konfigurace skladu

Následující diagram znázorňuje výstupní toky ze skladu podle typu dokladu v základním nastavení skladu. Čísla v diagramu odpovídají krokům v následujících částech diagramu.

![Výstupní tok v základním nastavení skladu](media/design_details_warehouse_management_outbound_basic_flow.png "Čísla v diagramu odpovídají krokům v následujících částech diagramu.")

### 1: Vydání zdrojového dokladu / Vytvoření vyskladění nebo přesunu

Pokud je uživatel, který je zodpovědný za zdrojové doklady, například zpracovatel prodejních objednávek nebo plánovač výroby, připraven na výstupního aktivitu skladu, vydá zdrojový doklad, aby dal pracovníkům skladu signál, že prodané zboží nebo komponenty lze vyskladní a umístit do zadaných přihrádek. Alternativně uživatel vytvoří doklady vyskladnění nebo přesunu zásob pro jednotlivé řádky objednávky nabízeným způsobem na základě zadaných přihrádek a množství, která mají být zpracovávána.

> [!NOTE]  
> Inventory movements are used to move items to internal operation areas in basic warehouse configurations, based on source documents or on an ad hoc basis.

### 2: Vytvoření odchozího požadavku

Po vydání výstupního zdrojového dokladu je automaticky vytvořen výstupní požadavek skladu. Obsahuje odkazy na typ a číslo zdrojového dokladu a není pro uživatele viditelný.

### 3: Vytvoření vyskaladnění nebo přesunu

In the **Inventory Pick** or **Inventory Movement** page, the warehouse worker retrieves, in a pull fashion, the pending source document lines based on outbound warehouse requests. Případně jsou řádky vyskladnění zásob již vytvořené uživatelem, který je zodpovědný za zdrojový doklad.

### 4: Zápis vyskladnění nebo zaevidování Přesunu zásob

On each line for items that have been picked or moved, partially or fully, the warehouse worker fills in the **Quantity** field, and then posts the inventory pick or registers the inventory movement. Zdrojové doklady související s vyskladněním zásob jsou zaúčtovány jako dodané nebo spotřebované. Zdrojové doklady související s přesuny zásob nejsou zaúčtovány.

Pro vyskladnění zásob jsou vytvořeny záporné položky zboží, vytvořeny položky skladu a odstraněn požadavek na vyskladnění, pokud je plně zpracován. For example, the **Quantity Shipped** field on the outbound source document line is updated. Vytvoří se zaúčtovaný doklad dodávky, který odráží například prodejní objednávku a dodané zboží.

## Pokročílé nastavení skladu

Následující diagram znázorňuje výstupní tok ze skladu podle typu dokladu při pokročilém nastavení skladu. Čísla v diagramu odpovídají krokům v následujících částech diagramu.

![Výstupní tok v pokročilém nastavení skladu](media/design_details_warehouse_management_outbound_advanced_flow.png "Výstupní tok v pokročilém nastavení skladu")

### 1: Vydání zdrojového dokladu

Pokud je uživatel, který je zodpovědný za zdrojové doklady, například zpracovatel prodejních objednávek nebo plánovač výroby, připraven na výstupního aktivitu skladu, vydá zdrojový doklad, aby dal pracovníkům skladu signál, že prodané zboží nebo komponenty lze vyskladní a umístit do zadaných přihrádek.

### 2: Vytvoření výstupního požadavku (2)

Po vydání výstupního zdrojového dokladu je automaticky vytvořen výstupní požadavek skladu. Obsahuje odkazy na typ a číslo zdrojového dokladu a není pro uživatele viditelný.

### 3: Vytvoření dodávky ze skladu

On the **Warehouse Shipment** page, the shipping worker who is responsible retrieves pending source document lines based on the outbound warehouse request. Několik řádků zdrojového dokladu lze kombinovat v jednom dokladu dodávky ze skladu.

### 4: Vydání dodávky ze skladu / Vytvoření vyskladnění

Odpovědný pracovník expedice vydá dodávku ze skladu, aby pracovníci skladu mohli vytvořit nebo koordinovat vyskladnění pro příslušnou dodávku.

Alternativně může uživatel vytvořit doklad vyskladnění pro jednotlivé řádky dodávky nabízeným způsobem na základě zadaných přihrádek a množství, které má být zpracováno.

### 5: Vydání interní operace / Vytvoření vyskladnění

Uživatel odpovědný za interní operace vydá interní zdrojový doklad, například výrobní a montážní zakázku, aby pracovníci skladu mohli vytvářet nebo koordinovat vyskladnění pro interní operaci.

Alternativně uživatel vytvoří doklady vyskladnění pro jednotlivé výrobní nebo montážní zakázky nabízeným způsobem na základě zadaných přihrádek a množství, která mají být zpracována.

### 6: Vytvoření požadavku vyskladnění

Po vydání výstupního zdrojového dokladu se automaticky vytvoří požadavek na vyskladnění. Obsahuje odkazy na typ a číslo zdrojového dokladu a není pro uživatele viditelný. V závislosti na nastavení se vytvoří spotřeba z výrobní a montážní zakázky a také požadavek na vyskladnění potřebných komponent ze skladu.

### 7: Generování řádků sešitu vyskladnění

The user who is responsible for coordinating picks, retrieves warehouse pick lines in the **Pick Worksheet** based on pick requests from warehouse shipments or internal operations with component consumption. Uživatel vybere řádky, které mají být vyskladněné a připraví vyskladnění určením přihrádek, ze kterých se má odebírat a vkládat a kolik jednotek má být manipulováno. Přihrádky mohou být předdefinovány nastavením skladu nebo zdroje.

Uživatel určuje metody vyskladnění pro optimalizované zpracování skladu a potom pomocí funkce vytvoří odpovídající doklady vyskladnění, které jsou přiřazeny různým pracovníkům skladu, kteří provádějí vyskladnění. When the warehouse picks are fully assigned, the lines in the **Pick Worksheet** are deleted.

### 8: Vytvoření dokladů vyskladnění

Pracovník skladu, který provádí vyskladnění, vytvoří doklad vyskladnění na základě vydaméjp zdrojové dokladu. Alternativně je doklad vyskladnění vytvořen a přiřazen pracovníkovi skladu nabízeným způsobem.

### 9: Zápis vyskladnění

On each line for items that have been picked, partially or fully, the warehouse worker fills in the **Quantity** field on the **Warehouse Pick** page and then registers the warehouse pick.

Položky skladu jsou vytvořeny a řádky vyskladnění jsou odstraněny, pokud jsou plně zpracovány. Doklad vyskladnění zůstane otevřený, dokud není zapsáno celé množství související dodávky ze skladu. **Množství Picked** field on the warehouse shipment lines is updated accordingly.

### 10: Účtování dodávky ze skladu

Když jsou všechny položky v dokladu dodávky ze skladu zapsané jako vyskladněné do určených přihrádek, pracovník, který je zodpovědný za zaúčtování dodávky ze skladu dodávku zaúčtuje. Vytvoří se záporné položky zboží. For example, the **Quantity Shipped** field on the outbound source document line is updated.

## Viz také

[Detaily návrhu: Správa skladu](design-details-warehouse-management.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]