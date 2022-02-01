---
    title: Walkthrough Conducting a Sales Campaign
    description: This walkthrough gives a detailed overview of all the tasks involved in conducting a sales campaign in Business Central.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/24/2021
    ms.author: edupont

---
# Walkthrough Conducting a Sales Campaign

Kampaň je jakýkoli druh aktivity, který zahrnuje několik kontaktů. Důležitou součástí nastavení kampaně je výběr cílové skupiny pro vaši kampaň. Z tohoto důvodu v [!INCLUDE[prod_short](includes/prod_short.md)] vytvoříte pomocí filtrů segment nebo skupinu kontaktů.

Tyto funkce v oblasti Prodeje a marketingu používáte k pečlivému plánování svých marketingových aktivit a ke správě svých interakcí s kontakty a zákazníky. Můžete vytvářet kampaně a nastavovat segmenty kontaktů pro korespondenci a další typy interakcí s kontakty a potenciálními zákazníky.

Funkce Kampaně a segmentu s automatizovanými procesy umožňují plánovat, organizovat a sledovat vaše marketingové aktivity. Tím se zvýší šance na získání nových zákazníků a udržení stávajících zákazníků.

## O tomto návodu

Tento návod ukazuje proces sledování veletrhu a cílení na potenciální zákazníky (kontakty) v následné kampani.

Návod představuje funkci správy kampaní a segmentů v oddělení prodeje a marketingu. Tento návod ilustruje následující úkoly:

- Preparing the data.
- Nastavení kampaně.
- Výběr cílové skupiny.
- Dolování dat.
- Odesílání dopisů kontaktům.
- Registrace odpovědí na kampaň.

## Role

Tento návod ukazuje úkoly, které jsou prováděny následujícími uživatelskými rolemi:

- Marketingový manažer nebo Manažer prodeje
- Marketingový pracovník

## Předpoklady

Než budete moci provést úkoly v tomto návodu, musíte si nainstalovat [!INCLUDE[prod_short](includes/prod_short.md)].

## Příběh

Marketingový manažer v obchodním oddělení CRONUS je zodpovědný za plánování kampaní a jejich provádění. Rovněž rozhoduje o tom, kterých veletrhů se má účastnit, a hodnotí postup kampaně.

Pracovník marketingu v marketingovém oddělení zpracovává produkci, distribuci a umisťování marketingových materiálů.

The company has just launched a new product called the Rome Guest Chair. The product was recently promoted at a trade show, Office Futurus. Many customers expressed great interest in the product, and as part of a promotional effort, customers who bought Rome Guest Chair during a campaign period were offered a special campaign price.

Jedním z úkolů marketingového pracovníka po veletrhu je zadat všechny potenciální zákazníky jako kontakty.

Marketingový manažer nastaví kampaň, vytvoří segment, který obsahuje všechny nové kontakty, a poté vytěží kontaktní údaje, aby vybral cílové publikum pro kampaň.

Pracovník pomáhá rozesílat děkovné dopisy všem kontaktům, které zanechaly své karty zaměstnancům ve stánku, a nakonec manažer zaznamená všechny odpovědi, které obdrží od potenciálních zákazníků.

## Nastavení kampaně

Jakmile zaměstnanec vstoupí do vizitek přijatých na veletrhu, marketingový manažer nastaví kartu kampaně pro správu aktivit zapojených do kampaně.

### Nastavení kampaně

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Campaigns**, and then choose the related link.
2. Chcete-li vytvořit novou kampaň, vyberte akci **Nový**. On the campaign card, press **Enter** to have a campaign number automatically inserted.
3. In the **Description** field, enter a description for the campaign, for example, **Office Futurus trade show**.
4. Choose the **Status Code** field, and select the status code "1-PLAN".
5. Podle potřeby vyplňte pole **Počáteční datum** a **Koncové datum** kampaně.

## Výběr Cílové skupiny.

The marketing manager creates a segment to select the contacts that they want to interact with.

When you create a segment, you can use a variety of criteria to select the contacts that must be targets for the segment. For example, you can select contact persons who work at a customer site or a prospective customer site who are responsible for purchases at their company. Pomocí filtrů přidáváte kontakty podle kritérií, která nejlépe vyhovují vašim účelům. Můžete například filtrovat podle pracovní odpovědnosti kontaktní osoby nebo obchodního vztahu nebo odvětví kontaktní společnosti. For this walkthrough, we'll choose the **Job Responsibility** filter to select contacts.

### Vytvoření segmentu s příslušnými kontakty

1. Choose the **Navigate** action, and then choose **Segments**.
2. Vyberte akci **Nový** a vytvořte nový segment. On the segment card, select **Enter** to have a segment number automatically inserted.
3. On the **General** FastTab, in the **Description** field, enter, for example, *Visitors at the Office Futurus trade show*.
4. Choose the **Add Contacts** action to open the **Add Contacts** filter.
5. Scroll down to the **Contact Job Responsibility** FastTab, select the **Purchase** filter as the **Job Responsibility Code** and choose the **OK** button.

Stránka **Segment** nyní obsahuje seznam kontaktů na základě vámi zadaného filtru. Na záložce **Obecné** v poli **Počet  řádků** můžete na první pohled vidět počet kontaktů, které splňují tato kritéria.

> [!NOTE]  
> You can save your segmentation criteria to be reused at a later stage.

### To save your segmentation criteria

1. On the **Segment** page, choose **Actions**.
2. Choose **Functions**, then **Segment**, and then choose the **Save Criteria** action.
3. Na stránce **Uložit kritéria segmentu** zadejte kód segmentu. Do pole **Popis** zadejte popis kritérií segmentu.
4. Zvolte tlačítko **OK**.

## Dolování dat

Marketingový manažer se blíže podívá na segmentovaný seznam kontaktů a uvědomí si, že seznam je příliš velký. Rozhodne se snížit seznam na základě skutečných potenciálních zákazníků, aby se ujistil, že se zaměřuje na správnou cílovou skupinu. Tento proces rafinace a snížení dat se také označuje jako dolování dat.

### Odebrání kontaktů ze segmentu

1. On the **Segment** page, choose **Actions**.
2. In the menu bar below, choose **Functions**, choose **Contacts**, and the choose **Reduce Contacts**.

This opens the **Remove Contacts – Reduce** dialog.  
4. On the **Contact Business Relation** FastTab, select the **CUST** filter as the **Business Relation Code**, and choose the **OK** button.

Stránka **Segment** nyní obsahuje omezený seznam kontaktů a v poli **Počet  řádků** můžete vidět počet kontaktů, které nyní splňují tato nová kritéria.

> [!NOTE]  
> If you have to reverse this removal of a group of contacts, you can do this using the **Go Back** function. Jinými slovy, můžete vrátit zpět poslední segmentaci.

### To bring back the removed contacts

1. On the **Segment** page, choose the **Segment** action.
2. Choose the **Go Back** action.

Kontakty, které jste právě odebrali, se přidají zpět do seznamu kontaktů.

## Propojení segmentu s kampaní

The marketing manager decides that the reduced list is the final list of contacts that they want to be part of the campaign. They therefore link this segment to the campaign FUTURUS trade show.

### Propojení segmentu s kampaní

1. Na stránce **Segment** na záložce **Campaň** vyberte pole **Číslo kampaně** a vyberte kampaň, ke které chcete segment připojit, například: **CP0001**.
2. Select **Yes**.
3. Since this segment is the target of the campaign, select the **Campaign Target** check box and choose **Yes**.

## Odesílání dopisů a e-mailových zpráv kontaktům

The marketing staffer helps the marketing manager send out correspondence to the prospective customers, in which they thank them for visiting the trade show.

### Odeslání dopisu kontaktu pomocí segmentu

> [!NOTE]  
> In this procedure you have to attach a Word document. You can add attachments in any language.

> [!NOTE]  
> If needed click on the **Edit Pencil** icon to open the page in edit mode.

1. Otevřete kartu **Segment** pro **návštěvníky veletrhu FUTURUS**.
2. On the **Interaction** FastTab, in the **Interaction Template Code** field, select the Business Letter template code **BUS** and select **Yes**.
3. Vyberte pole **Kód jazyka (výchozí)** a otevřete stránku **Jazyky segmentu interakce**. Select a **Language Code** and then choose the **OK** button.
4. Make sure that the **Correspondence Type (Default)** is set to **Hard Copy**.
5. In the **Attachment** field select the **Ellipsis** box. This opens the Import Attachment dialog.
   1. Select the **Choose** button to choose your file.
   1. Find the file and select the **Open** button to attach it.
6. Do pole **Předmět (výchozí)** zadejte následující ukázkový text: **Děkujeme vám za návštěvu veletrhu**. Press the Tab key to leave the field, and select the **Yes** button.
7. Slide the **Send Word Docs as Attmt** to on and select the **Yes** button.
8. Choose the action **Log**. In the Log Segment pop-up window enable:
   **Create Follow-up Segment**
9. Choose the **OK** button to start the **Log Segment batch job**.

Přílohy jsou odeslány. Po dokončení procesu vyberte tlačítko **OK**, které uvádí, že segment byl zaznamenán.

Listy se automaticky vytisknou a segment se zaprotokoluje. Protože segment byl zaprotokolován, již není v seznamu segmentů, ale je přesunut do seznamu protokolovaných segmentů. To see that list, Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Logged Segments**, and then choose the related link.

Po zaprotokolování segmentu je každý odeslaný list zaznamenán jako interakce, kterou můžete zobrazit v protokolu.

Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Interaction Log Entries**, and then choose the related link. Pro každý odeslaný dopis je k dispozici položka.

### Odeslání e-mailové zprávy kontaktu

1. Na záložce **Interakce** v poli **Kód šablony interakce** vyberte šablonu Business Letter, kód **BUS**.
2. Do pole **Předmět (výchozí)** zadejte následující ukázkový text: **Děkujeme vám za návštěvu veletrhu**.
3. V poli **Typ korespondence** vyberte možnost **E-mail**.
4. Specify language settings, and attach a Word document, as in the previous procedure.
5. Vyberte akci **Protokol**. Otevře se stránka **Protokolovat segment**.
6. Zaškrtněte políčko **Poslat přílohy**, aby se přílohy odesílaly e-mailem.
7. Zaškrtněte políčko **Vytvořit segment sledování**.
8. Zvolte tlačítko **OK**.

Dopisy jsou automaticky odesílány e-mailem a segment je zaprotokolován. Protože segment byl zaprotokolován, již není v seznamu segmentů, ale je uložen v seznamu protokolovaných segmentů. To see that list, Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Logged Segments**, and then choose the related link.

## Registrace odpovědí na kampaň

Během příštích několika týdnů budou potenciální zákazníci na dopis reagovat. Marketingový manažer chce sledovat odpovědi a zaznamenávat tyto interakce.

Za tímto účelem vytvořte segment pro kontakty, které na dopis odpověděly.

### Registrace odpovědí na kampaň

1. On the **Segment** page, on the **Interaction** FastTab, choose the **Interaction Template Code** field.

Neexistuje žádná šablona interakce pro zaznamenávání odpovědí na kampaně. Proto vytvořte novou šablonu.

2. On the **Interaction Templates** dropdown, choose the **New** action.
3. Do pole **Kód** zadejte **RESP** a do pole **Popis** field, zadejte **Odpovědi kampaně**.
4. Zvolte tlačítko **OK**.
5. Choose **Yes** to confirm that you want to apply this interaction template code to all segment lines.
6. On the **Campaign** FastTab, select the **Campaign Response** field. Choose **Yes** to confirm the message *You have modified Campaign Response*.
7. Na stránce **Segment** vyberte akci **Protokol**.
8. On the **Log Segment** page, clear the **Send Attachments** check box. Then choose the **OK** button to confirm the message that the segment has been logged.

## Viz také
[Řízení vztahů](marketing-relationship-management.md)    
[Návody obchodních procesů](walkthrough-business-process-walkthroughs.md)    
[Práce s [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
