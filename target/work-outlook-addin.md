---
title: Using Business Central with Outlook
description: This service has deep integration with Microsoft 365 enabling you to manage all your business interactions and mail with customers and vendors directly in Outlook.
author: jswymer

ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: SMTP, mail, Microsoft 365
ms.date: 04/21/2022
ms.author: jswymer

---
# Use Business Central as your Business Inbox in Outlook

[!INCLUDE[prod_short](includes/prod_short.md)] abízí doplněk, který umožňuje spravovat obchodní interakce se zákazníky a dodavateli přímo v aplikaci Microsoft Outlook.. S doplňkem [!INCLUDE[prod_short](includes/prod_short.md)] pro aplikaci Outlook můžete zobrazit finanční údaje související se zákazníky a dodavateli a vytvářet a odesílat finanční doklady, jako jsou nabídky a faktury.

Doplněk [!INCLUDE[prod_short](includes/prod_short.md)] se skládá ze dvou samostatných doplňků, které poskytují následující možnosti:

- Kontaktní informace

   Tento doplněk vám umožňuje vyhledat [!INCLUDE[prod_short](includes/prod_short.md)] informace o zákaznících nebo dodavatelích v e-mailech aplikace Outlook a schůzkách v kalendáři. Umožňuje také vytvářet a odesílat [!INCLUDE[prod_short](includes/prod_short.md)] obchodní doklady, například prodejní nabídku nebo fakturu kontaktu.

- Zobrazení dokladů

   Když je obchodní doklad odeslán pomocí e-mailu, doplněk poskytuje přímý odkaz z e-mailu na skutečný obchodní doklad v [!INCLUDE[prod_short](includes/prod_short.md)].

## Začínáme

1. První věc, kterou musíte udělat, je nainstalovat doplněk [!INCLUDE[prod_short](includes/prod_short.md)] do aplikace Outlook. Je možné, že váš správce již doplněk pro Vás nainstaloval. Pokud si tedy nejste jisti, obraťte se na správce nebo v dalším kroku ověřte, zda je nainstalován.

   Pokud doplněk nebyl již nainstalován, přečtěte si článek [Instalace doplňku pro vlastní použití](admin-outlook.md#install).

2. S nainstalovaným doplňkem máte přístup k **[!INCLUDE[prod_short](includes/prod_short.md)]** z jakékoli nové nebo existující e-mailové zprávy nebo události kalendáře v aplikaci Outlook.

   Začněte tím, že se přihlásíte do Outlooku a otevřete e-mailovou zprávu. Pokud používáte aplikaci Outlook, přejděte na pás karet a vyhledejte **[!INCLUDE[prod_short](includes/prod_short.md)]**.  Nebo pokud používáte Outlook na webu, v horní nebo dolní části e-mailové zprávy vyhledejte ikonu doplňku ![Business Central v aplikaci Outlook](media/outlook-business-central-icon.png) nebo přejděte na další akce ![Zobrazit další akce pro e-mail v aplikaci Outlook](media/outlook-more-actions-button.png).

   ![Přístup k doplňkům Business Central v aplikaci Outlook](media/outlook-business-central-addin.png)

   Pokud jste si doplněk nainstalovali sami a rozhodli jste se dostat vzorový e-mail, zkontrolujte, zda jste ve své doručené poště nenašli uvítací e-mail. Tento e-mail obsahuje informace, které vám pomůžou začít.

Při prvním použití doplňku v [!INCLUDE[prod_short](includes/prod_short.md)] můžete být vyzváni k přihlášení. V takovém případě zvolte **Přihlásit se nyní** a podle pokynů na obrazovce se přihlaste k Business Central pomocí svého účtu.

> [!TIP]
> Pokud používáte nový Outlook na webu, můžete připnout **[!INCLUDE[prod_short](includes/prod_short.md)]**, aby byl vždy okamžitě viditelný, místo toho, abyste museli přecházet na tlačítko Další akcí, což umožňuje pohodlné zobrazení informací o kontaktech při procházení různých e-mailů.

For more information, see [Use add-ins in Outlook on the web](https://support.office.com/article/using-add-ins-in-outlook-on-the-web-8f2ce816-5df4-44a5-958c-f7f9d6dabdce?ns=OLWAO365B&version=16).

## Práce s kontakty a doklady pomocí doplňku Contact Insights

Řekněme, že dostanete e-mail od zákazníka, který chce získat nabídku na některé zboží. Directly in Outlook, you open the [!INCLUDE[prod_short](includes/prod_short.md)] add-in, which recognizes the sender as a customer, and opens the customer card for that company. From this dashboard, you see overview information for the customer, and drill down for more detail on specific documents. Můžete také nahlédnout do historie prodeje pro zákazníka. Pokud se jedná o nový kontakt, můžete jej vytvořit jako nového zákazníka v [!INCLUDE[prod_short](includes/prod_short.md)] bez opuštění aplikace Outlook.

V doplňku můžete vytvořit prodejní nabídku a odeslat ji zpět tomuto zákazníkovi, aniž byste opustili aplikaci Outlook. Všechny informace, které potřebujete k odeslání nabídky, jsou k dispozici ve vaší schránce v aplikaci Outlook. Jakmile zadáte data, zaúčtujete nabídku a odešlete ji e-mailem. [!INCLUDE[prod_short](includes/prod_short.md)] vygeneruje .PDF soubor s prodejní nabídkou a připojí jej k e-mailové zprávě, kterou jste napsali v doplňku.

Podobně, pokud dostanete e-mail od dodavatele, můžete tento doplněk použít pro práci s dodavateli a nákupními fakturami.

Někdy chcete zobrazit více polí, než je v doplňku možné zobrazit, například když chcete vyplnit řádky faktury. Chcete-li mít více místa pro práci, můžete tento doplněk vložit na samostatnou stránku. Stále je součástí aplikace Outlook, ale máte více místa. Při zadávání dat ve vyskakovacím okně se změny automaticky ukládají.
Následující části vás provedou některými základními úkoly, které vám poskytnou obecné znalosti o tom, jak je používat.

> [!TIP]
> Úkoly vysvětlují, jak používat doplněk z e-mailové zprávy. To stejné můžete udělat z události kalendáře v aplikaci Outlook.

### Vyhledání obchodního kontaktu při psaní e-mailu

1. Vytvoření nové e-mailové zprávy.
2. Na pásu karet přejděte na **[!INCLUDE[prod_short](includes/prod_short.md)]** a vyberte **Contact Insights**. Nebo pokud používáte webovou aplikaci Outlooku, přejděte do dolní části zprávy a vyberte ikonu ![doplněk Business Central v Outlooku](media/outlook-business-central-icon.png) > **Contact Insights**.
3. V **[!INCLUDE[prod_short](includes/prod_short.md)]** podoknu doplňku, které se otevře, vyhledejte a vyberte požadovaný kontakt.

   Přehled kontaktu se zobrazí v podokně a kontakt se přidá do řádku **Komu** v e-mailu.

### Zobrazení a změna kontaktních údajů nebo změna společnosti

Panel akcí v horní části podokna doplňku [!INCLUDE[prod_short](includes/prod_short.md)] obsahuje několik akcí, které vám umožní nahlédnout hlouběji do podrobností o kontaktu a změnit věci.

![Panel akcí doplňku Business Central v aplikaci Outlook](media/outlook-addin-action-bar.png)

Můžete například otevřít úplné kontaktní údaje tak, jak byste je viděli v [!INCLUDE[prod_short](includes/prod_short.md)]. Pokud pracujete s více než [!INCLUDE[prod_short](includes/prod_short.md)] společností, můžete mezi nimi snadno přepínat.

### Sledování došlých dokladů

Možná využíváte přehled **Došlé doklady** v [!INCLUDE[prod_short](includes/prod_short.md)] ke sledování dokladů, které vám dodavatelé zasílají, například nákupní fakturu, kterou je třeba zaplatit. Pokud funkcionalitu používate, můžete snadno vytvořit záznamy Došlých dokladů z doplňku Outlook a zahrnout e-mailové přílohy.

1. Když obdržíte e-mail od dodavatele, který má přílohu, vyberte ![Ikona doplňku Business Central v aplikaci Outlook](media/outlook-business-central-icon.png) **[!INCLUDE[prod_short](includes/prod_short.md)]**  > **Contact Insights**.

2. In the action bar of the add-in, choose **Show more actions**, then choose the **Send to Incoming Documents…** action.

### Vytvoření a odeslání nového dokladu kontaktu

1. Na pásu karet nebo v dolní části e-mailové zprávy vyberte ![Ikona doplňku Business Central v aplikaci Outlook](media/outlook-business-central-icon.png) **[!INCLUDE[prod_short](includes/prod_short.md)]** > **Nový**a poté vyberte typ dokumentu, který chcete vytvořit, například **Prodejní nabídku**.
2. Udělejte změny v dokladu v podokně doplňku **[!INCLUDE[prod_short](includes/prod_short.md)]**.
3. Jakmile bude doklad nachystaný k odeslání kontaktu, na panelu akcí vyberte **Zobrazit další akce**, a pak vyberte **Odeslat e-mailem**.

### Attach files to records

Your email inbox often serves as a source of incoming files that initiate or unblock workflows. Files can include things like PDF invoice payments, photos of goods, or requirements in a Word document. When working in Outlook with Business Central records like vendors, customers, purchase invoices, or sales orders, you can attach these files to the records.

There's a couple ways you can attach files. One way is to upload files from your device. The other way is upload files that are attached to an email. For example, suppose you get an email with files from a contact. The add-in will automatically display the contact record that matches the email sender. From there, you can navigate to a document for the contact, like the latest sales order. Once you've identified the order that the email relates to, you quickly upload the files from the email to that order.

![Shows how to add attachments from an email to records in Business Central.](media/outlook-attach-files.png)

After attaching a file, coworkers can instantly download and view the file from the **Attachments** FactBox in any of their Business Central clients. Or, they can open the file in OneDrive to share and collaborate with their department.

#### How to attach a file

1. Open the email, choose ![Business Central add-in icon in Outlook.](media/outlook-business-central-icon.png) **[!INCLUDE[prod_short](includes/prod_short.md)]**  > **Contact Insights**.
2. In the action bar of the add-in, choose **Show more actions** > **Attachments**.

   The **Attached Documents** page opens to list any documents that are already attached to the record.
3. Choose **Attached File(s)...**, then choose one of the following options:

   - Choose **Attach from email** to upload all or selected files that are attached to the email.
   - Choose **Upload from file** to upload one or files from your device.

> [!NOTE]
> You can't attach files to all records. This feature is available for records that use the **Attachments** FactBox, such as a vendor, customer, purchase invoice, or sales order.

## Zobrazení dokladu z e-mailu pomocí doplňku Zobrazení Dokladu

Ať už se jedná o e-mail, který jste odeslali nebo přijali, můžete přímo v aplikaci Outlook zobrazit jakýkoli doklad [!INCLUDE[prod_short](includes/prod_short.md)] například prodejní nabídku. Odtud můžete provádět změny a přecházet na související informace - stejně jako v [!INCLUDE[prod_short](includes/prod_short.md)].

Pokud používáte aplikaci Outlook, stačí v horní části e-mailové zprávy vybrat **Odkaz na dokument**. V případě webové aplikace Outlook vyhledejte v e-mailové zprávě odkaz na doklad. Text odkazu bude obsahovat číslo dokladu, které je založeno na číselné řadě použité v [!INCLUDE[prod_short](includes/prod_short.md)]. Například odkaz na prodejní nabídku by mohl vypadat jako **Prodejní nabídka S-QUO1000**.

> [!TIP]
> Starting in 2022 release wave 1, documents open in a new browser window with all the capabilities that you know from [!INCLUDE [prod_short](includes/prod_short.md)]. You can navigate from a document to a list and back again, open lists in Excel, send documents to be printed, and run or preview related reports. You also have all of the familiar keyboard shortcuts right there when you open documents from Outlook.


## Podívejte se na související školení na webu [Microsoft Learn](/learn/modules/alternative-interfaces-dynamics-365-business-central/index)

## Viz také

[Příprava obchodování](ui-get-ready-business.md)    
[Získání Business Central pro mobilním zařízení](install-mobile-app.md)    
[Odesílání dokladů e-mailem](ui-how-send-documents-email.md)    
[Finance](finance.md)    
[Prodej](sales-manage-sales.md)    
[Nákup](purchasing-manage-purchasing.md)    
[Minimální požadavky na Outlook](product-requirements.md#outlook)    
[Pouižtí add-inů ve vebové aplikaci Outlooku](https://support.office.com/article/Using-Add-ins-in-Outlook-on-the-web-8f2ce816-5df4-44a5-958c-f7f9d6dabdce?appver=OWB150)


[!INCLUDE[footer-include](includes/footer-banner.md)]