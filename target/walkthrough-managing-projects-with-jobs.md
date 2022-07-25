---
    title: Walkthrough - Managing Projects with Jobs
    description: This walkthrough introduces you to the project management features in jobs which allow you to schedule the usage of your company's resources and more.
    author: SorenGP


    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/24/2021
    ms.author: edupont

---
# Návod: Správa projektů pomocí úloh

<!-- [!INCLUDE[complete_sample_data](includes/complete_sample_data.md)]   -->

Tento návod vás seznámí s funkcemi řízení projektů v úlohách. Úlohy jsou způsob, jak naplánovat využití zdrojů vaší společnosti a sledovat různé náklady spojené se zdroji v konkrétním projektu. Úlohy zahrnují spotřebu hodin zaměstnanců, strojních hodin, skladového zboží a dalších typů využití, které můžete chtít sledovat v průběhu projektu.

Tento návod zahrnuje nastavení nového projektu kromě některých běžných úkolů, jako je zpracování pevných cen, provádění plateb po splátkách, účtování faktur z úloh a kopírování projektů.

## O tomto návodu
Tento návod ukazuje následující úkoly:

### Nastavení projektů
Se strukturou rozpočtu nastavenou pro projekty je jejich vytváření jednoduché. Tento návod zahrnuje následující postupy:

- Nastavení řádků úkolů a plánování.
- Vytváření konkrétních cen pro zboží, zdroje a účty hlavní knihy.
- Fakturace přímo z projektu.

### Zpracování pevných cen
V projektech můžete zpracovat pevné ceny a ceny za služby nebo zboží, které jsou předem dohodnuty se zákazníky. V tomto návodu můžete provést následující:

- Můžete se podívat, jak jsou určeny hodnoty smluv a faktur.
- Můžete povolit další práci v plánu, která nebyla fakturována.

### Kopírování projektu
Tato část návodu se zaměřuje na to, jak kopírovat část nebo celej projekt, aby se snížilo ruční zadávání dat a zlepšila přesnost. Zahrnuje následující:

- Kopírování části projektu do nového projektu.
- Kopírování cen konkrétních projektů.
- Kopírování řádků plánování.

### Provádění plateb podle splátky
Když velký, drahý projekt trvá dlouhou dobu, zákazníci se často dohodnou se společností na zaplacení ve splátkách. Tento scénář ukazuje, jak nastavíte platby na splátky:

- Vytváření plateb na splátky za projekt.
- Fakturace plateb zákazníkům.
- Účtování o využití v projektu nastaveném pro platbu na splátky.

## Role
Tento návod obsahuje úkoly pro následující role:

- Vedoucí projektu
- Člen projektového týmu

## Předpoklady
Před provedením úkolů v návodu je nutné provést následující kroky:

- Install the CRONUS demonstration database.
- Vytvoření ukázkových dat pomocí kroků v následující části.

## Příběh
This walkthrough focuses on CRONUS, a design and consultancy firm that designs and fits new infrastructures, such as conference halls and offices, with furniture, accessories, and storage units. Většina jeho práce je zaměřena na projekt. Prakash je projektový manažer ve společnosti CRONUS. Projekty mu poskytují přehled o každé probíhající úloze, kterou CRONUS zahájil, a také o dokončených úlohách. Obvykle je to ten, kdo uzavírá dohody se zákazníky a vstupuje do jádra úlohy, kterou jsou kromě cen také úkoly a plánování, do [!INCLUDE[prod_short](includes/prod_short.md)]. Zjistil, že vytváření, udržování a kontrola informací je jednoduchá. Prakash má také rád způsob, jakým [!INCLUDE[prod_short](includes/prod_short.md)] umožňuje kopírování úloh a platby na splátky.

Tricia, členka projektového týmu, která se hlásí k Prakashovi, je odpovědná za každodenní sledování práce. Kromě práce techniků na každém úkolu vykonává i svou vlastní práci. Zaznamenává zboží, které použili, a náklady, které jim vznikly.

## Příprava ukázkových dat
Chcete-li se na tento návod připravit, musíte přidat Tricii jako nový zdroj.

### Připravit ukázková data

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Resources**, and then choose the related link.
2. Zvolte akci **Nový** a vytvořte novou kartu zdroje.
3. Na záložce **Obecné** zadejte následující informace:

   - **Číslo**: **Tricia**
   - **Jméno**: **Tricia**
   - **Typ**: **Osoba**

4. Vyberte pole **Základní měrná jednotka** a kliknutím na akci **Nový** otevřete stránku **Měrná jednotka zdroje**. V poli **Kód** vyberte **hodina**.
5. Na záložce **Fakturace** zadejte následující informace:

   - **Nákupní cena**: **5**
   - **Nepřímé náklady %**: **4**
   - **Pořizovací cena**: **10**
   - **Obecná  účto  skupina zboží**: **Služby**
   - **DPH účto  skupina zboží**: **DPH 25**

6. Zavřete stránku.

V dalším postupu vytvoříte list deníku projektu pro Tricii, abyste mohli zaúčtovat její použití.

### Vytvoření listu deníku projektů

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Journals**, and then choose the related link.
2. Na stránce **Deníky projektů** vyberte pole **Název listu**. Otevře se stránka **Listy deníku projektů**.
3. Zvolte akci **Nový** a vytvořte nový řádek s následujícími informacemi:

   - **Jméno**: **Tricia**
   - **Popis**: **Tricia**
   - **Číselná  řada**: **JJNL-GEN**

4. Chcete-li změny uložit, zvolte tlačítko **OK**.

## Nastavení projektů
V tomto scénáři CRONUS získal smlouvu se zákazníkem, Progressive Home Furnishings, na návrh konferenční haly a jídelny. Zákazník má sídlo ve Spojených státech a projekt bude vyžadovat speciální software. Vedoucí projektu dosáhne dohody se zákazníkem a vytvoří projekt, který pokrývá dohodu.

### Nastavení projektu

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.
2. Zvolte akci **Nový** a vytvořte novou kartu.
3. Na záložce **Obecné** zadejte následující informace:

   - **Popis**: **Poradenství při nastavení konferenčního sálu**
   - **Číslo plátce**: **01445544**

4. Na záložce **Účtování** zadejte následující informace:

   - **Stav**: **Plánování**
   - **Účto skupina projektu**: **VYBAVENÍ**
   - **Metoda NV**: **Hodnota nákladů**

5. Na záložce **Trvání** zadejte dnešní datum do polí **Počáteční datum** a **Datum dokončení**. Tato data pomohou při převodu měny při fakturaci projektu.
6. Na záložce **Zahraniční obchod** nastavte kód měny na **USD**. Pokud v poli **Kód měny faktury** vyberete USD, bude úloha fakturována v amerických dolarech a plánována pouze v místní měně systému CRONUS.

Ceny pro zákazníky můžete přizpůsobit podle jednotlivých pracovních míst v závislosti na dohodách, které jste nastavili. V dalším postupu projektový manažer specifikuje náklady na čas Tricie, stanoví cenu požadovaného softwaru a přidá cestovní náklady, které zákazník zaplatil.

### Přizpůsobení cen

1. Na kartě projektu zvolte akci **Zdroj**.
2. Na stránce **Ceny zdrojů projektu** zadejte následující informace:

   - **Kód**: **Tricia**
   - **Jednotková cena**: **20**

3. Zavřete stránku.
4. Vyberte akci **Zboží**.
5. Na stránce **Ceny za zboží projektu** zadejte následující informace a přizpůsobenou cenu:

   1. **Číslo zboží**: **80201 (grafický program)**
   2. **Jednotková cena**: **200**

6. Zavřete stránku.
7. Vyberte akci **Finanční účet**.
8. Na stránce **Ceny fin. účtu projektu** zadejte následující informace a náklady na cestu, se kterými zákazník souhlasil, že je zaplatí, plus 25 procent:

   1. **Finanční účet**: **8430 (Cestování)**
   2. **Faktor pořizovací ceny**: **1,25**

9. Zavřete stránku.

Posledními kroky při nastavování projektu jsou přidání úkolů projektu a řádků plánování, které jsou součástí každého úkolu. Řádky plánování určují, co je fakturováno zákazníkovi.

### Přidání úkolů projektu

1. Na kartě **Projekt** zvolte pro nový úkol akci **Řádky úlohy projektu**.
2. Následující tabulka popisuje informace, které byste měli zadat do polí.

   | Číslo úlohy projektu | Popis | Typ úlohy projektu |
   |------------------|---------------------------------------|-------------------|  
   | 1000 | Poradenství ohledně nastavení haly | Od-součet |
   | 1010 | Konzultační schůzka se zákazníkem | Účtování |
   | 1020 | Rozvoj | Účtování |
   | 1090 | Poradenství celkem | Do-součet |

3. Chcete-li ukázat, že některé úkoly jsou podkategoriemi jiných úkolů, vyberte akci **Odsadit úlohy projektu**.

Řádek plánování může být jedním z následujících typů:

- **Rozpočet**: Přidáno do plánu, ale není fakturováno.
- **Fakturovatelné**: Fakturováno, ale není přidáno do plánu.
- **Plán i Fakturovatelné**: Fakturováno a přidáno do plánu.

V tomto návodu používá projektový manažer možnost **Plán i Fakturovatelné**. Vytvoří tři řádky plánování pro úkol 1010 a dva řádky plánování pro úkol 1020.

### Vytvoření řádků plánování

1. Vyberte řádek 1010 a poté vyberte akci **Řádky plánování projektu**.

2. Vytvořte řádek plánování s následujícími informacemi:

   | Řádek | Typ řádku | Datum plánování | Typ | Ne. | Množství | jednotková cena |
   |------|-----------|----------------|-------------|-------|----------|------------|
   | 1 | Rozpočet i fakturovatelné | (dnešní datum) | Zdroj | Tricia | 40 |     |
   | 2 | Rozpočet i fakturovatelné | (dnešní datum) | Zdroj | Timothy | 40 |     |
   | 3 | Rozpočet i fakturovatelné | (dnešní datum) | Finanční účet | 8430 (cestování) | 2 | 400 |

   Zavřete stránku. Součty se aktualizují na stránce **Řádky úlohy projektu**.
3. Vyberte řádek 1020 a poté vyberte akci **Řádky plánování projektu**. Zadejte následující informace:

   | Řádek | Typ řádku | Datum plánování | Typ | Ne. | Množství | jednotková cena |
   |------|-----------|----------------|-------------|-------|----------|------------|
   | 1 | Rozpočet i fakturovatelné | (dnešní datum) | Zdroj | Tricia | 80 |     |
   | 2 | Rozpočet i fakturovatelné | (dnešní datum) | Zboží | 80201 (grafický program) | 1 |     |

4. Zavřete stránku. Součty se aktualizují na stránce **Řádky úlohy projektu**.

## Výpočet zbývajícího využití
Tricia, členka týmového projektu, na této práci nějakou dobu pracuje a chce si v ní zaregistrovat své hodiny a využití. Nepracovala více hodin, než bylo předem dohodnuto se zákazníkem. K výpočtu zbývajícího využití projektu v deníku projektů používá dávkovou úlohu **Výpočet zbývajícího použití**. Dávková úloha pro každý úkol vypočítá rozdíl mezi plánovanou spotřebou zboží, zdrojů a částkou výdajů v hlavní knize a skutečnou spotřebou zaúčtovanou v položkách projektu. Zbývající využití se poté zobrazí v deníku projektu, odkud jej můžete zaúčtovat.

### Výpočet zbývajícího využití

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Journals**, and then choose the related link.
2. Na stránce  **Deník projektů** v poli **Název listu** otevřete seznam **List deníku projektů**. Vyberte List deníku projektů **Tricia**.
3. Vyberte akci **Výpočet  zbývajícího použití**.
4. Na stránce **Výpočet zbývajícího  použití projektu** na záložce **Úloha projektu** vyberte pole **Číslo projektu** a vyberte příslušné číslo úlohy, obvykle úlohu J00010.
5. Na záložce **Možnosti** zadejte **J00001** do pole **Číslo dokladu**. To usnadňuje budoucí sledování zaúčtování.
6. Zadejte dnešní datum jako zúčtovací datum.
7. Zvolte tlačítko **OK**. Tím se vygenerují řádky deníku projektů odvozené z řádků plánování, které Prakash pro projekt vytvořil.
8. Na potvrzovací stránce klikněte na tlačítko **OK**. Generované řádky jsou přidány do deníku projektů.
9. Ujistěte se, že všechna čísla dokumentu jsou J00001, a poté vyberte akci **Zaúčtovat**. Vyberte **Ano** pro potvrzení odeslání.

Řádky jsou nyní zaúčtovány.

## Vytvoření a zaúčtování prodejní faktury projektu
Dále může Tricia vytvořit novou fakturu pro celý projekt nebo pro část projektu. Může také připojit fakturu k jiné faktuře pro stejného zákazníka za stejnou práci. V tomto případě fakturuje za celou práci, protože projekt je nyní dokončen.

### Vytvoření prodejní faktury projektu

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.
2. Vyberte úlohu, kterou jste vytvořili dříve, a poté vyberte akci **Vytvořit prodejní fakturu projektu**.
3. Na záložce **Úloha projektu** zrušte filtr na **Číslo úlohy projektu**, abyste mohli úlohu fakturovat. V poli **Číslo projektu** vyberte příslušný projekt.
4. Na záložce **Možnosti** vyplňte datum zaúčtování a definujte, zda chcete vytvořit jednu fakturu na úkol nebo jen jednu fakturu pro všechny úkoly.
5. Zvolte tlačítko **OK**, abyste vytvořili fakturu, a klikněte na tlačítko **OK** na stránce s potvrzením.

Poté, co Tricia vytvoří fakturu, má k ní například přístup z Centra role **Zpracovatel prodejních objednávek**.

### Zaúčtování nové prodejní faktury

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Invoices**, and then choose the related link.
2. Otevřete fakturu pro zákazníka č. 01445544. Informace zadané z řádků plánování můžete zobrazit.
3. Vyberte tlačítko **Zaúčtovat**. Vyberte **Ano** pro potvrzení odeslání.

### Zobrazení zaúčtované faktury

1. Otevřete projekt a pak zvolte akci **Řádky plánování projektu**.
2. Vyberte některý z řádků plánování, které byly fakturovány, a pak zvolte akci **Získat prodejní fakturu/dobropis**.
3. Na stránce **Faktury projektu** vyberte akci **Otevřená prodejní faktura/dobropis**.

Tricia má otázku ohledně cen, nákladů a zisků, které jsou relevantní pro tuto konkrétní práci, takže k těmto informacím přistupuje na stránce **Statistika**.

### Otevření stránky Statistika

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.
2. Vyberte akci **Statistika**. Můžete si prohlédnout podrobné informace o cenách pracovních míst, nákladech a ziscích v místní i zahraniční měně.
3. Kliknutím na tlačítko **Zavřít** zavřete stránku **Statistika projektu**.

## Zpracování pevných cen
CRONUS má smlouvu na zřizování konferenčních místností. Jako projektový manažer chce Prakash dobrý přehled o úkolech požadovaných pro daný projekt s přidruženými rozpočty a vzniklými náklady na každou úlohu. Kromě toho chce znát celkovou smluvní cenu práce a částku, která byla fakturována k tomuto bodu. Se zákazníkem se dohodl na pevných cenách práce.

### Správa pevných cen v projektech

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.
2. Vyberte číslo projektu **AB** a poté vyberte akci **Řádky úlohy projektu**.
3. Vyberte řádek 1120 a v poli **Rozpočet (Náklady celkem)** klikněte pravým tlačítkem na částku a vyberte **Přejít k podrobnostem**.

   Přezkoumáním řádků plánování práce Prakash určí, že bude také potřebovat Tricii po dobu 30 hodin pro tuto fázi projektu. Se zákazníkem se dohodne na pevné ceně.

4. Na stránce **Řádky úlohy projektu** vyberte řádek 1120 a poté vyberte akci **Řádky plánování projektu**. Vytvořte řádek plánování s následujícími informacemi:

   | Řádek | Typ řádku | Typ | Ne. | Množství |
   |------|-----------|-------------|-------|----------|
   | 1 | Rozpočet i fakturovatelné | Zdroj | Tricia | 30 |

   Zavřete stránku.
5. V poli **Rozpočet (Náklady celkem)** klikněte na toto pole pravým tlačítkem myši a na stránce **Řádky úlohy projektu** znovu zvolte **Přejít k podrobnostem**. Zobrazí se změny v plánu. Vidíte, že do plánu bylo přidáno 30 hodin.
6. Zavřete stránku.

Poté, co byla Tricia přidána do plánu pro tento řádek úkolu, pracuje v práci 25 hodin. Zadává tyto hodiny do deníku práce.

### Zadání hodin do deníku projektů

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Journals**, and then choose the related link.
2. Na nový řádek zadejte následující informace:

   - **Typ řádku**: **(prázdný)**
   - **Zúčtovací datum**: **(dnešní datum)**
   - **Číslo dokladu**: **J00002**
   - **Číslo projektu**: **AB**
   - **Číslo úlohy projektu**: **1120**
   - **Typ**: **Zdroj**
   - **Číslo**: **Tricia**
   - **Množství**: **25**

3. Vyberte tlačítko **Zaúčtovat**.

   O pár dní později Tricia pracuje dalších 10 hodin v práci. Nyní odpracovala celkem 35 hodin. Vzhledem k tomu, že smlouva se zákazníkem je uzavřena po dobu 30 hodin, bude zákazníkovi účtováno pouze pět z těchto hodin. Tricia ručně přidá dalších pět hodin, které odpracovala, do rozvrhu.

4. Na stránce **Deník projektů** vyberte akci **Výpočet  zbývajícího použití**.
5. Na stránce **Výpočet zbývajícího  použití projektu** na záložce **Možnosti** zadejte následující informace:

   - **Číslo dokladu**: **J00003**
   - **Zúčtovací datum**: **(dnešní datum)**

6. Na záložce **Úloha projektu** zadejte následující informace:

   - **Číslo projektu**: **AB**
   - **Číslo úlohy projektu**: **1120**

7. Výpočet spustíte kliknutím na tlačítko **OK**.

   Tricii zbývá pět hodin práce. Pole **Typ řádku** je prázdné, což znamená, že zbývá zaúčtovat pouze využití, protože práce již byla naplánována.

8. V **Deníku projektů** vytvořte nový řádek s následujícími informacemi. Ujistěte se, že obě čísla projektů jsou sekvenční s čísly, která jste již použili:

   - **Typ řádku**: **Rozpočet**
   - **Číslo projektu**: **AB**
   - **Číslo úlohy projektu**: **1120**
   - **Typ**: **Zdroj**
   - **Číslo**: **Tricia**
   - **Množství**: **5**

   Použitím typu řádku **Rozpočet** existují aktualizace plánovaných nákladů a cen, ale žádné aktualizace smluvních nákladů a cen, které jsou fakturovány zákazníkovi.

9. Vyberte tlačítko **Zaúčtovat**. Stránku zavřete kliknutím na tlačítko **OK**.
10. Otevřete seznam **Projektů**.
11. Vyberte projekt AB a potom v části **Řádky úlohy projektu** vyberte řádek 1120 a v poli **Rozpočet (celkové náklady)** klikněte pravým tlačítkem na částku. Chcete-li zobrazit informace, zvolte **Přejít k podrobnostem**.

   Změny se automaticky zadávají na řádku pro projekt č. 1120. V celkových nákladech na plánovanou práci bylo do plánu přidáno dalších pět hodin práce Tricie.

12. Stránku zavřete kliknutím na tlačítko **Zavřít**.
13. Klikněte pravým tlačítkem na částku v poli **Smlouva (náklady celkem)** a vyberte **Přejít k podrobnostem** pro zobrazení informací.

Do celkové ceny za smlouvu je zahrnuto pouze původních nasmlouvaných 30 hodin, protože to bylo to, co bylo dohodnuto se zákazníkem.

## Kopírování projektu

Prakash dosáhl dohody se zákazníkem, společností Selagorian Ltd, o zřízení 10 konferenčních místností. Dohoda se podobá dřívějšímu projektu. Proto ušetříte čas na zkopíroví dřívějšího projektu.

Na stránce **Kopírovat projekt** můžete vybrat řádky úloh a úkoly, které chcete kopírovat. Můžete také zvolit zkopírování položek zdrojového projektu, která vytváří řádky plánování na základě skutečného využití, nebo můžete zkopírovat řádky plánování zdrojového projektu, které zkopírují původní řádky plánování do nového projektu. Poté můžete zvolit, jaký typ řádku plánování nebo řádku položky chcete zahrnout, a vybrat pouze to, co je relevantní pro tento nový projekt. Nakonec můžete vybrat projekt, do kterého chcete kopírovat, a definovat, zda mají být zkopírovány také ceny a množství.

### Kopírování projektu

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.
2. Vyberte akci **Nový** a vytvořte nový projekt. Zadejte následující informace:

   - **Popis**: **Nastavení 10 konferenčních místností**
   - **Číslo plátce**: **20000**

3. Vyberte akci **Kopírovat úlohy projektu z**.
4. Na stránce **Kopírovat úlohy projektu** zadejte následující:

   - **Číslo projektu**: **AB**
   - **Od čísla úlohy  projektu**: **1000**
   - **Zdroj**: **Řádky plánování projektu**
   - **Zahrnout  Typ řádku plánování**: **Rozpočet + Fakturovatelné**
   - **Projekt č.**: **AB Nastavení 10 konferenčních místností**
   - Vyberte pole **Kopie dimenzí** a **Kopírovat množství**.

5. Kliknutím na tlačítko **OK** zkopírujete projekt a kliknutím na tlačítko **OK** zavřete stránku s potvrzením.

Porovnáním cen, řádků úkolů a řádků plánování úloh pro dva projekty můžete vidět, že informace byla úspěšně zkopírována.

## Provádění plateb podle splátek

CRONUS právě dokončil velký projekt, který bude trvat rok. Vzhledem k tomu, že vyžaduje přidělení mnoha zdrojů, projektový manažer nastaví smlouvu tak, aby zákazník zaplatil část ceny předem, část po dokončení poloviny projektu a konečnou platbu po dokončení celého projektu.

### Nastavení nového účtu

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, and then choose the related link.
2. Na stránce **Účetní osnova** vyberte akci **Nový** a vytvořte novou kartu.
3. Na kartě **Nový finanční účet** zadejte následující informace:

   - **Číslo**: **40255**
   - **Název**: **Platba za projekt**

4. Na záložce **Účtování** v poli **Obecná  účto  skupina zboží** vyberte **Služby**. Zavřete stránku.
5. Na stránce **Účetní osnova** vyberte **Platba za projekt č. 40255** a poté vyberte akci **Odsadit účetní osnovu**. Potvrďte výběrem **Ano**.

Následující postupy ukazují, jak vytvořit novou úlohu, nastavit ceny a pak nastavit platbu podle splátky. V řádcích úloh projektu můžete vytvořit konkrétní řádky věnované platbě ve splátkách. Veškerá práce dokončená na projektu, která je přidána do plánu, bude zadána na řádcích použití. Pro každý řádek platebního úkolu na plánovacích řádcích je typem řádku **Fakturovatelné**, což znamená, že zákazníkovi bude fakturována. Zadejte nový řádek pro zálohu. Na řádku úkolu použití můžete zadat informace o zboží a zdrojích, které byly použity v tomto projektu, což zvýší plán, například hodiny zaměstnanců a zboží použité v projektu.

### Provádění plateb podle splátek

1. Vytvořit nový projekt.
2. Na nové kartľ **Projekt** vyplňte následující informace:

   - **Popis**: **Předělání recepce**
   - **Číslo plátce**: **30000**
   - **Účto skupina projektu**: **Nastavení**
   - **Metoda NV**: **Hodnota nákladů**

3. Na kartě úlohy vyberte akci **Ceny** a poté zvolte akci **Zdroj**. Zadejte následující informace:

   - **Kód**: **Tricia**
   - **Jednotková cena**: **10**

   Zavřete stránku.

4. Na kartě **Projekt** v části **Úlohy** přidejte řádky úloh, jak je popsáno v následující tabulce:

   | Řádek | Číslo úlohy projektu | Popis | Typ úlohy projektu |
   |------|--------------|----------------------|---------------|
   | 1 | 1000 | Platba zálohy | Účtování |
   | 2 | 2000 | Použití | Účtování |
   | 3 | 3000 | Platba - v polovině projektu | Účtování |
   | 4 | 4000 | Platba – dokončení | Účtování |

5. Vyberte úkol 1000 a poté vyberte akci **Řádky plánování projektu**.

6. Vytvořte řádek plánování s následujícími informacemi:

   | Řádek | Typ řádku | Datum plánování | Typ | Ne. | Množství | jednotková cena |
   |------|-----------|----------------|-------------|-------|----------|------------|
   | 1 | Fakturovatelné | (dnešní datum) | Finanční účet | 40255 | 1 | 5000 |

   Zavřete stránku.

7. Vyberte úkol 2000 a poté vyberte akci **Řádky plánování projektu**.

8. Vytvořte řádek plánování s následujícími informacemi:

   | Řádek | Typ řádku | Datum plánování | Typ | Ne. | Množství |
   |------|-----------|----------------|----------|--------|----------|
   | 1 | Rozpočet | (dnešní datum) | Zdroj | Tricia | 120 |
   | 2 | Rozpočet | (dnešní datum) | Zboží | 70104 | 10 |

   Zavřete stránku. Na stránce **Řádky úlohy projektu** můžete vidět, že částky plánu byly aktualizovány.

9. Vyberte úkol 32000 a poté vyberte akci **Řádky plánování projektu**.

10. Vytvořte řádek plánování s následujícími informacemi:

   | Řádek | Typ řádku | Datum plánování | Typ | Ne. | Množství | jednotková cena |
   |------|-----------|-----------------|-------------|-------|----------|------------|
   | 1 | Fakturovatelné | (budoucí datum) | Finanční účet | 40255 | 1 | 5000 |

   Zavřete stránku.

11. Vytvořte podobnou položku řádku plánování pro úkol projektu 4000.

Nyní, když byly zadány řádky úkolu a plánování, Prakash vytvoří fakturu pro první platbu. Udělá to z řádků úkolu projektu, aby se ujistil, že faktura obsahuje pouze řádky pro první platbu. Objednávku odběratele můžete otevřít z plánovacích řádků nebo řádků úkolů.

### Vytvoření faktury

1. Na stránce **Řádky úlohy projektu** vyberte řádek 1000 a poté vyberte akci **Vytvořit prodejní fakturu**.
2. Na stránce **Vytvořit prodejní fakturu** nastavte dnešní datum jako zúčtovací datum, zadejte **Na úkol** a kliknutím na tlačítko **OK** pro vytvoření faktury s výchozími informacemi. Kliknutím na tlačítko **OK** zavřete stránku pro potvrzení.
3. Vyberte akci **Prodejní faktura/dobropis**. Na prodejní faktuře je vidět, že do faktury je zahrnuta pouze záloha. Nyní to můžete zákazníkovi poslat podle dohody.

## Další kroky
Tento návod vás provedl některými základními kroky práce s projekty v [!INCLUDE[prod_short](includes/prod_short.md)]. Naučili jste se, jak vytvořit novou práci, jak kopírovat úlohu a jak zacházet s platbami. Také jste viděli ukázku, jak sledovat hodiny a vytvářet faktury.

## Viz také

[Business Process Walkthroughs](walkthrough-business-process-walkthroughs.md)   
[Setting Up Project Management](projects-setup-projects.md)   
[Use Resources](projects-how-use-resources.md)   
[Monitor Progress and Performance](projects-how-monitor-progress-performance.md)   
[Invoice Jobs](projects-how-invoice-jobs.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]