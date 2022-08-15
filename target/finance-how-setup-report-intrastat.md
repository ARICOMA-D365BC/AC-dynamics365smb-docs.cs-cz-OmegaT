---
title: Set Up and Report Intrastat
description: Learn how to set up Intrastat reporting features, and how to report trade with companies in other EU countries.
author: brentholtorf


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: electronic document, Intrastat, trade, EU, European Union
ms.search.form: 308, 309, 310, 311, 325, 326, 327, 328, 405, 406, 8451, 12202, 31077
ms.date: 05/23/2022
ms.author: bholtorf

---
# Nastavení a hlášení Intrastatu

Všechny společnosti v Evropské unii musí hlásit svůj obchod s ostatními zeměmi nebo oblastmi EU. Pohyb zboží musíte nahlásit statistickým úřadům ve vaší zemi / regionu každý měsíc a zpráva musí být doručena daňovým úřadům. Toto se nazývá hlášení Intrastatu. You use the **Intrastat Journal** page to complete periodic Intrastat reports.

## Povinné a volitelné nastavení

> [!IMPORTANT]  
> Customer cards and Vendor cards include a field, **Intrastat Partner Type**, that has the same option values as the **Partner Type** field: *"" (blank)*, *Company*, and *Person*. The **Intrastat Partner Type** field has replaced the **Parter Type** field in Intrastat reporting. **Partner Type** is used in SEPA to define theSEPA Direct Debit Scheme (Core or B2B). **Intrastat Partner Type** is used for Intrastat reporting only. This way, you can specifiy different values for the two fields, if you need to.
>
> However, note that if the **Intrastat Partner Type** field is left blank, the value from the **Partner Type** field is used for Intrastat reporting.

Před použitím deníku Intrastat k vykazování informací o intrastatu je třeba nastavit několik věcí:

* **Intrastat Setup**: Intrastat Setup page is used to enable intrastat reporting and set defaults for it. Můžete určit, zda chcete nahlásit Intrastat ze dodávek (odchozí), příjemek (příchozí) nebo obojí v závislosti na prahových hodnotách stanovených místními předpisy. Můžete také nastavit výchozí typy transakcí pro běžné doklady a doklady vratky, které se používají podle povahy vykazování transakcí.
* **Intrastat journal templates**: You must set up the Intrastat journal templates and batches you will use. Protože je Intrastat hlášen měsíčně, musíte vytvořit 12 deníků založených na stejné šabloně.
* **Commodity codes**: Customs and tax authorities have established numerical codes that classify items and services. Tyto kódy zadáte u zboží.
* **Transaction nature codes**: Countries and regions have different codes for types of Intrastat transactions, such as ordinary purchase and sale, exchange of returned goods, and exchange of non-returned goods. Nastavte všechny kódy, které platí pro vaši zemi nebo oblast. You use these codes on the **Foreign Trade** FastTab on sales and purchase documents, and when you process returns.

   > [!NOTE]
   > Starting in January 2022, Intrastat requires different transaction nature code for dispatches to private individuals or non-VAT registered businesses and VAT registered businesses. To comply with this requirement, we recommend that you review and/or add new transaction nature codes in the **Transaction Types** page accoridng to the requirements in your country. You should also review and update the **Intrastat Partner Type** field to *Person* for private individual or non-VAT registered businesses customers in the relevant **Customer** page. If you are unsure about the correct intrastat partner type or transaction type to use, we recommend that you ask an expert in your country or region.

* **Transport methods**: There are seven, one-digit codes for Intrastat transport methods. **1** for sea, **2** for rail, **3** for road, **4** for air, **5** for post, **7** for fixed installations, and **9** for own propulsion (for eample, transporting a car by driving it). [!INCLUDE[prod_short](includes/prod_short.md)] does not require these codes, however, we recommend that the descriptions provide a similar meaning.
* **Transaction specifications**: Use these to supplement the descriptions from the transaction types.
* **Country of origin**: Use the two-letter ISO Alpha Codes for the country where the good was obtained or produced. If the good was produced in more than one country, the country of origin is the last country where it was significantly processed.
* **VAT identification number of the partner operator in the Member State of import**: This is the VAT-ID number of the partner operator in the Member State of import. The VAT-ID is also used in the exchange of intra-EU-export data among Member States, and allows Member States to allocate the received data to the importing company in their own country. Reporting units must report the VAT-ID of the company that declared the intra-Union acquisition of goods in the Member State of import.

> [!NOTE]
> The business partner VAT-ID to use can differ, depending on the business circumstance. For example, the ID to use differs for scenarios such as chain sales, where a supplier sells a product to another country, and then that company resells the item to another business in the same country, triangular trade, and so on. If you are unsure about the correct VAT-ID to use, we recommend that you ask an expert in your country or region.

Volitelně můžete také nastavit:

* **Areas**: Use these to supplement information about countries and regions.
* **Entry/exit points**: Use these to specify the locations where you ship or receive items to or from other countries. Letiště Heathrow je příkladem vstupního nebo výstupního bodu. You enter entry or exit points on sales and purchase documents on the **Foreign Trade** FastTab. Tyto informace budou také zkopírovány z položek zboží při vytváření deníku Intrastatu.

### Nastavení šablon a listů Intrastat
Dávkové úlohy Intrastat obsahují pouze položky zboží, nikoli finanční položky. Pokud máte položky hlavní knihy, které splňují podmínky pro hlášení Intrastat, musíte je zadat ručně. Pokud například kupujete počítač z jiné země nebo oblasti EU, počítač není uskladněn, ale je zaúčtován přímo na účet hlavní knihy. Tento typ záznamu musíte ručně zadat do deníku Intrastatu.

Položky můžete exportovat do souboru, který můžete odeslat orgánům Intrastatu. Můžete také vytisknout zprávu, ručně zadat informace do formulářů od svých úřadů a poté tyto informace odeslat.

> [!Note]
> We recommended that you set up an Intrastat journal batch for each month.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journal Templates**, and then choose the related link.
2. Vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]. Vytvořte šablonu pro každý formulář Intrastat.
3. To create batches, choose the **Batches** action.
4. Vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]. Vytvořte šablonu pro každý formulář Intrastat.

> [!Note]
> In the **Statistics Period** field, enter the statistics period as a four-digit number, where the first two digits represent the year and the next two digits represent the month. Zadejte například hodnotu 1706 pro červen 2017.

### Nastavení typů přepravy

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transport Methods**, and then choose the related link.
2. Vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

### Nastavení povinných polí v sestavě Intrastatu

V některých zemích, například ve Španělsku a Velké Británii, úřady požadují, aby zprávy Intrastatu zahrnovaly například způsob přepravy nákupů nebo nějaké jiné hodnoty, pokud prodej přesáhne určitou hranici. On the **Intrastat Setup** page, you can select to make **Intrastat Checkist Setup** to set mandatory fields on the **Intrastat Journal** page.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Setup**, and then choose the related link.
2. Choose the **Intrastat Checklist Setup** action.
3. On the **Intrastat Checklist Setup** page, click in the **Field Name** to pick Intrastat report field you want to make mandatory.

### Czechia

Specifically for Czech businesses, you must also set up commodity codes and transaction nature codes.

#### Nastavení čísel sazebníku

Všechny zboží, které nakupujete nebo prodáváte, musí mít kód komodity.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Commodity Codes**, and then choose the related link.
2. Vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. To assign a commodity code to an item, go to the **Item Card** page, expand the **Costs & Posting** FastTab, and then enter the code in the **Commodity Code** field.

### Italy

Specifically for Italian businesses, you must also set up commodity codes and transaction nature codes.

#### Nastavení typů transkací

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transaction Nature Codes**, and then choose the related link.
2. Vyplňte pole podle potřeby. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!Tip]
> If you frequently use a particular transaction nature code, you can make it the default. To do this, go to the **Intrastat Setup** page, and choose the code.

## Hlášení Intrastat

After you fill in the Intrastat journal, you can run the **Checklist report** action to make sure that that all information in the journal is correct. Mandatory fields you have set in **Intrastat Checklist Setup** page that are missing values, will be shown in Errors and warning factbox on **Intrastat Journal** page. Poté můžete vytisknout výkaz Intrastat jako formulář nebo vytvořit soubor, který odešlete finančnímu úřadu ve vaší zemi / regionu.

### Vyplnění deníků Intrastat

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journal** and then choose the related link.
2. On the **Intrastat Journal** page, in the **Batch Name** field, choose the relevant journal batch, and then choose **OK**.
3. Choose the **Suggest Lines** action. The **Starting Date** and **Ending Date** fields will already contain the dates specified for the statistics period on the journal batch.
4. In the **Cost Regulation %** field, you can enter a percentage to cover transport and insurance. If you enter a percentage, the content of the **Statistical Value** field in the journal is proportionally higher.
5. Choose **OK** to start the batch job.

Dávková úloha načte všechny položky zboží v období statistiky a vloží je jako řádky do deníku Intrastat. V případě potřeby můžete řádky upravit.

> [!IMPORTANT]  
> The batch job retrieves only the entries that contain a country/region code for which an Intrastat code has been entered on the **Countries/Regions** page. Proto je nutné zadat kódy Intrastat pro kódy zemí nebo oblastí, pro které budete dávkovou úlohu spouštět. The batch job sets the **Partner VAT ID** field to *QV999999999999* for private individuals or non-VAT registered businesses (customers with the **Intrastat Partner Type** field set to *Person*), and it uses the value of the **Tranaction Type** field on the posted item ledger entry or job ledger entry.

### To modify Intrastat journals lines

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journal**, and then choose the related link.
2. On the **Intrastat Journal** page, in the **Batch Name** field, choose the relevant journal batch, and then choose **OK**.
3. User filter pane to filter Intrastat Jorunal lines based on some criteria. For example, filter on **Partner VAT ID** fields with the value *QV999999999999*.
4. Choose **Share** icon ![Share a page in another app.](media/share-icon.png) and select **Edit in Excel**
5. In Excel, modify the Intrastat journal lines that you filtered out. For example, modify **Transaction Type** field values.
6. Publish the changes that you have made in Excel back to [!INCLUDE[prod_short](includes/prod_short.md)]

> [!Note]
> In [!INCLUDE[prod_short](includes/prod_short.md)] versions that do not support [**Edit in Excel**](across-work-with-excel.md#edit-in-excel) for journals, you can create configuration packages to export and import Intrastat journal lines to Excel. For more information, see [Migrate On-Premises Data to Business Central Online](/dynamics365/business-central/dev-itpro/administration/migrate-data) in the administration content.

### Hlášení Intrastatu ve formuláři nebo souboru

To get the information that is required on the Intrastat form from the statistical authorities, you must print the **Intrastat – Form** report. Než to budete moci provést, musíte připravit deník Intrastat a vyplnit jej. Pokud máte jak prodejní, tak nákupní transakce, musíte pro každý typ vyplnit samostatný formulář, takže musíte sestavu vytisknout dvakrát.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journals**, and then choose the related link.
2. On the **Intrastat Journal** page, choose the relevant journal batch in the **Batch Name** field.
3. If you have not already done this, fill in the journal manually or choose **Suggest Lines** action.
4. Choose the **Prints Intrastat Journal** action.
5. On the **Intrastat Jnl. Line** FastTab, add a **Type** filter and then specify whether this is a **Receipt** or a **Shipment**.
6. Choose **Send to** to print the report.

### Vykazování Intrastat do souboru

You can submit the Intrastat report as a file. Před vytvořením souboru si můžete vytisknout kontrolní seznam, který obsahuje stejné informace, jaké budou v souboru.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journal**, and then choose the related link.
2. On the **Intrastat Journal** page, select the relevant journal batch in the **Batch Name** field.
3. If you have not already done this, fill in the journal manually or by choosing the **Suggest Lines** action.
4. Choose the **Create File** action.
5. On the batch job page, choose the **OK** button.
6. Choose **Save**.
7. Browse to the location where you want to save the file, enter the file name, and then choose **Save**.

> [!NOTE]
> When a line in the Intrastat report has a supplementary unit of measure, the weight of the item will not be shown, since this value is not required.

## Reorganizace deníků Intrastatu

Vzhledem k tomu, že musíte odeslat sestavu Intrastat každý měsíc a vytvořit nový list deníku pro každou sestavu, budete mít nakonec mnoho listů deníku. Řádky deníku nejsou automaticky odstraněny. Možná budete chtít periodicky reorganizovat názvy dávek deníku. To provést odstraněním listů deníků, které již nepotřebujete. Řádky deníku v těchto dávkách jsou také odstraněny.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journals**, and then choose the related link.
2. To view the options, choose the **Batch Name** field.
3. Choose the journal batches to deleted, and then choose the **Delete** button.

## Tariff numbers

In many countries, the customs and tax authorities establish 8-digit item codes for various items. In order for item entries to contain the necessary information when the program imports them to the Intrastat journal line, you must have entered the information about the tariff number in the **Tariff Numbers** page. Find the codes for the items that your company deals with and enter them in the **Tariff Numbers** page.

In the **Tariff Numbers** page, add all the codes that you use. You must enter the codes on the item card before you begin to post. When you have set up the codes, enter them in the **Tariff No.** field on the item card. You must also fill in the **Net Weight** field on the item card.

## Podívejte se na související školení na webu [Microsoft Learn](/learn/modules/process-intrastat-dynamics-365-business-central/index)

## Viz také

[Financial Management](finance.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
