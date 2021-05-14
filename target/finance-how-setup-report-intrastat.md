---
title: Set Up and Report Intrastat| Microsoft Docs
description: Learn how to set up Intrastat reporting features, and how to report trade with companies in other EU countries.
services: project-madeira
documentationcenter: ''
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: electronic document, Intrastat, trade, EU, European Union
ms.date: 04/01/2021
ms.author: bholtorf

---
# Nastavení a hlášení Intrastatu
Všechny společnosti v Evropské unii musí hlásit svůj obchod s ostatními zeměmi nebo oblastmi EU. Pohyb zboží musíte nahlásit statistickým úřadům ve vaší zemi / regionu každý měsíc a zpráva musí být doručena daňovým úřadům. Toto se nazývá hlášení Intrastatu. You use the **Intrastat Journal** page to complete periodic Intrastat reports.

## Povinné a volitelné nastavení
Před použitím deníku Intrastat k vykazování informací o intrastatu je třeba nastavit několik věcí:

* **Intrastat Setup**: Intrastat Setup page is used to enable intrastat reporting and set defaults for it. Můžete určit, zda chcete nahlásit Intrastat ze dodávek (odchozí), příjemek (příchozí) nebo obojí v závislosti na prahových hodnotách stanovených místními předpisy. Můžete také nastavit výchozí typy transakcí pro běžné doklady a doklady vratky, které se používají podle povahy vykazování transakcí.
* **Intrastat journal templates**: You must set up the Intrastat journal templates and batches you will use. Protože je Intrastat hlášen měsíčně, musíte vytvořit 12 deníků založených na stejné šabloně.
* **Commodity codes**: Customs and tax authorities have established numerical codes that classify items and services. Tyto kódy zadáte u zboží.
* **Transaction nature codes**: Countries and regions have different codes for types of Intrastat transactions, such as ordinary purchase and sale, exchange of returned goods, and exchange of non-returned goods. Nastavte všechny kódy, které platí pro vaši zemi nebo oblast. Tyto kódy se používají v prodejních a nákupních dokladech a při zpracování vratek.
* **Transport methods**: There are seven, one-digit codes for Intrastat transport methods. **1** for sea, **2** for rail, **3** for road, **4** for air, **5** for post, **7** for fixed installations, and **9** for own propulsion (for eample, transporting a car by driving it). [!INCLUDE[prod_short](includes/prod_short.md)] does not require these codes, however, we recommend that the descriptions provide a similar meaning.

Volitelně můžete také nastavit:

* **Transaction specifications**: Use these to supplement the descriptions from the transaction types.
* **Areas**: Use these to supplement information about countries and regions.
* **Entry/exit points**: Use these to specify the locations where you ship or receive items to or from other countries. Letiště Heathrow je příkladem vstupního nebo výstupního bodu. You enter entry or exit points on sales and purchase documents on the **Foreign Trade** FastTab. Tyto informace budou také zkopírovány z položek zboží při vytváření deníku Intrastatu.

### Nastavení šablon a listů Intrastat
Dávkové úlohy Intrastat obsahují pouze položky zboží, nikoli finanční položky. Pokud máte položky hlavní knihy, které splňují podmínky pro hlášení Intrastat, musíte je zadat ručně. Pokud například kupujete počítač z jiné země nebo oblasti EU, počítač není uskladněn, ale je zaúčtován přímo na účet hlavní knihy. Tento typ záznamu musíte ručně zadat do deníku Intrastatu.

Položky můžete exportovat do souboru, který můžete odeslat orgánům Intrastatu. Můžete také vytisknout zprávu, ručně zadat informace do formulářů od svých úřadů a poté tyto informace odeslat.

> [!Note]
> Doporučujeme nastavit dávkovou úlohu instrastatu každý měsíc..

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journal Templates**, and then choose the related link.
2. Podle potřeby vyplňte pole. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]. Vytvořte šablonu pro každý formulář Intrastat.
3. To create batches, choose the **Batches** action.
4. Podle potřeby vyplňte pole. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]. Vytvořte šablonu pro každý formulář Intrastat.

> [!Note]
> In the **Statistics Period** field, enter the statistics period as a four-digit number, where the first two digits represent the year and the next two digits represent the month. Zadejte například hodnotu 1706 pro červen 2017.

### Nastavení čísel sazebníku
Všechny zboží, které nakupujete nebo prodáváte, musí mít kód komodity.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Commodity Codes**, and then choose the related link.
2. Podle potřeby vyplňte pole. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. To assign a commodity code to an item, go to the **Item Card** page, expand the **Costs & Posting** FastTab, and then enter the code in the **Commodity Code** field.

### Nastavení typů transkací
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transaction Nature Codes**, and then choose the related link.
2. Podle potřeby vyplňte pole. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!Tip]
> Pokud často používáte určitý kód povahy transakce, můžete jej nastavit jako výchozí. To do this, go to the **Intrastat Setup** page, and choose the code.

### Nastavení typů přepravy
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transport Methods**, and then choose the related link.
2. Podle potřeby vyplňte pole. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

### Nastavení povinných polí v sestavě Intrastatu
V některých zemích, například ve Španělsku a Velké Británii, úřady požadují, aby zprávy Intrastatu zahrnovaly například způsob přepravy nákupů nebo nějaké jiné hodnoty, pokud prodej přesáhne určitou hranici. On the **Intrastat Setup** page, you can select to make **Intrastat Checkist Setup** to set mandatory fields on the **Intrastat Journal** page.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Setup**, and then choose the related link.
2. Chooes the **Intrastat Checklist Setup** action.
3. On the **Intrastat Checklist Setup** page, click in the **Field Name** to pick Intrastat report field you want to make mandatory.

## Hlášení Intrastat
After you fill in the Intrastat journal, you can run the **Checklist report** action to make sure that that all information in the journal is correct. Mandatory fields you have set in **Intrastat Checklist Setup** page that are missing values, will be shown in Errors and warning factbox on **Intrastat Journal** page. Poté můžete vytisknout výkaz Intrastat jako formulář nebo vytvořit soubor, který odešlete finančnímu úřadu ve vaší zemi / regionu.

### Vyplnění deníků Intrastat
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journal** and then choose the related link.
2. On the **Intrastat Journal** page, in the **Batch Name** field, choose the relevant journal batch, and then choose **OK**.
3. Choose the **Suggest Lines** action. The **Starting Date** and **Ending Date** fields will already contain the dates specified for the statistics period on the journal batch.
4. In the **Cost Regulation %** field, you can enter a percentage to cover transport and insurance. If you enter a percentage, the content of the **Statistical Value** field in the journal is proportionally higher.
5. Choose **OK** to start the batch job.

Dávková úloha načte všechny položky zboží v období statistiky a vloží je jako řádky do deníku Intrastat. V případě potřeby můžete řádky upravit.

> [!IMPORTANT]  
> The batch job retrieves only the entries that contain a country/region code for which an Intrastat code has been entered on the **Countries/Regions** page. Proto je nutné zadat kódy Intrastat pro kódy zemí nebo oblastí, pro které budete dávkovou úlohu spouštět.

### Hlášení Intrastatu ve formuláři nebo souboru
To get the information that is required on the Intrastat form from the statistical authorities, you must print the **Intrastat – Form** report. Než to budete moci provést, musíte připravit deník Intrastat a vyplnit jej. Pokud máte jak prodejní, tak nákupní transakce, musíte pro každý typ vyplnit samostatný formulář, takže musíte sestavu vytisknout dvakrát.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journals**, and then choose the related link.
2. On the **Intrastat Journal** page, choose the relevant journal batch in the **Batch Name** field.
3. If you have not already done this, fill in the journal manually or choose **Suggest Lines** action.
4. Choose the **Prints Intrastat Journal** action.
5. On the **Intrastat Jnl. Line** FastTab, add a **Type** filter and then specify whether this is a **Receipt** or a **Shipment**.
6. Choose **Send to** to print the report.

### Vykazování Intrastat do souboru
You can submit the Intrastat report as a file. Před vytvořením souboru si můžete vytisknout kontrolní seznam, který obsahuje stejné informace, jaké budou v souboru.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journal**, and then choose the related link.
2. On the **Intrastat Journal** page, select the relevant journal batch in the **Batch Name** field.
3. If you have not already done this, fill in the journal manually or by choosing the **Suggest Lines** action.
4. Choose the **Create File** action.
5. On the batch job page, choose the **OK** button.
6. Choose **Save**.
7. Browse to the location where you want to save the file, enter the file name, and then choose **Save**.

## Reorganizace deníků Intrastatu
Vzhledem k tomu, že musíte odeslat sestavu Intrastat každý měsíc a vytvořit nový list deníku pro každou sestavu, budete mít nakonec mnoho listů deníku. Řádky deníku nejsou automaticky odstraněny. Možná budete chtít periodicky reorganizovat názvy dávek deníku. To provést odstraněním listů deníků, které již nepotřebujete. Řádky deníku v těchto dávkách jsou také odstraněny.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journals**, and then choose the related link.
2. To view the options, choose the **Batch Name** field.
3. Choose the journal batches to deleted, and then choose the **Delete** button.

## Tariff numbers

In many countries, the customs and tax authorities establish 8-digit item codes for various items. In order for item entries to contain the necessary information when the program imports them to the Intrastat journal line, you must have entered the information about the tariff number in the **Tariff Numbers** page. Find the codes for the items that your company deals with and enter them in the **Tariff Numbers** page.

In the **Tariff Numbers** page, add all the codes that you use. You must enter the codes on the item card before you begin to post. When you have set up the codes, enter them in the **Tariff No.** field on the item card. You must also fill in the **Net Weight** field on the item card.

## Zobrazit související školení na webu [Microsoft Learn](/learn/modules/process-intrastat-dynamics-365-business-central/index)

## Viz také
[Financial Management](finance.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]