---
title: Set Up Marketing Campaigns in Business Central| Microsoft Docs
description: Describes how you can set up and conduct marketing campaigns in Business Central to help you identify and attract prospects and retain customers.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: marketing, campaign, promo, prospect
ms.date: 04/01/2021
ms.author: edupont
---
# Správa marketingových kampaní
Mít silný marketingový plán vám umožní identifikovat, přilákat a udržet si zákazníky. Marketingový plán se skládá z různých kampaní a dalších interakcí v souvislosti s vašimi prodejními a marketingovými aktivitami. Při plánování kampaně se musíte rozhodnout, na které kontakty se chcete zaměřit, na jaký typ kampaně (např. Na veletrhu nebo direct-mail) a na jaké úkoly budou prodejci budou provádět.

Každá kampaň se skládá z různých aktivit nebo úkolů. Můžete kombinovat více činností, například úkoly, z nichž každý představuje krok, v aktivitách. Úkoly aktivity jsou vzájemně propojeny pomocí vzorcem data. Jednotlivé úkoly lze přiřadit pouze prodejcům. Činnosti lze přiřadit příležitostem, prodejcům, skupinám prodejců a kontaktům. For more information, see [Set Up Opportunity Sales Cycles and Cycle Stages](marketing-how-setup-opportunity-sales-cycles-stages.md).

## Definování jednotlivých kampaní
Before you can create a campaign, you must set up *campaign status codes*. Použití těchto kódů vám pomůže spravovat kampaně přiřazením stavu kampani. Při práci ve fázích kampaně můžete zjistit, v jakém kroku se kampaň nachází a jaký krok nastane dále. You set up campaign status codes on the **Campaign Status** page.

Pro každou kampaň, kterou chcete sledovat, můžete vytvořit kartu kampaně. Tyto karty kampaně můžete také prohlížet a zobrazit si obecné informace o kampaních.
Můžete odstranit položky kampaně, například pokud položka zaznamená akci, která byla zrušena. Odstranit lze pouze zrušené kampaně.

### Výběr cílové skupiny
Po vytvoření kampaně můžete začít vytvářet segmenty, které určují cílovou skupinu kampaně. For more information, see [Managing Segments](marketing-segments.md).

### Registrace procent slev
When you have set up your campaign, decided what segments you want the campaign to cover, and set the starting and ending dates, you register the discount percentage that the customer will receive on the individual items on the lines on the **Sales Line Discounts** page. You can also register the sales prices for the individual items on the lines on the **Sales Prices** page. Z karty kampaně máte přístup k oběma stránkám.

Pokud jste nastavili prodejní ceny/řádkové slevy a segmenty na kartě kampaně, musíte je aktivovat, aby se ceny/slevy kampaně projevily na řádcích.

> [!NOTE]  
> In order to activate the sales prices/line discounts, you must specify if the whole segment or only some contacts are targets of the campaign. If the sales prices/line discounts covers all the contacts in the segment, select the **Campaign Target** field on the **Campaign** FastTab of the **Segment** card.

If the sales prices/line discounts are not to be offered to all the contacts in the segment, you can clear the **Campaign Target** field for the relevant contacts. Pokud toto pole nevidíte, můžete jej přidat do svého pohledu. For more information, see [Personalize Your Workspace](ui-personalization-user.md).

## Vedení kampaní
Při spuštění kampaně se zaznamenávají všechny interakce s vašimi kontakty nebo segmentem, abyste získali statistiky a další informace o nákladech a úspěšnosti kampaně.

Kampaně jsou prováděny prodejci a je nutné vytvořit aktivity, které budou reprezentovat jednotlivé úkoly, dále se musí přiřadit příslušným prodejcům. For more information, see [Set Up Opportunity Sales Cycles and Cycle Stages](marketing-how-setup-opportunity-sales-cycles-stages.md).

## Viz také
[Managing Contacts](marketing-contacts.md)  
[Managing Segments](marketing-segments.md)  
[Managing Sales Opportunities](marketing-manage-sales-opportunities.md)  
[Working with Business Central](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]