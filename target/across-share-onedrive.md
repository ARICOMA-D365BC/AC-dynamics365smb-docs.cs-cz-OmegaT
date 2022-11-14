---
title: Opening Business Central Files in OneDrive
description: Learn how you can share Business Central data through OneDrive for Business. 
author: jswymer
ms.topic: conceptual
ms.workload: na
ms.search.keywords:
ms.date: 02/28/2022
ms.author: jswymer

---
# Otevírání a sdílení souborů Business Central na OneDrivu

[!INCLUDE[prod_short](includes/prod_short.md)] usnadňuje ukládání, správu a sdílení souborů s jinými lidmi prostřednictvím OneDrive pro firmy. Na většině stránek, kde jsou dostupné soubory, jako je Doručená pošta sestav nebo soubory připojené k záznamům, najdete akci **Otevřít na OneDrivu** a **Sdílet**.


:::image type="content" source="media/onedrive-overview-report-inbox-w-outline.png" alt-text="Akce Otevřít na OneDrivu a Sdílet pro sestavy":::


:::image type="content" source="media/one-drive-attachments-w-outline.png" alt-text="Akce Otevřít na OneDrivu a Sdílet pro přílohy":::

<!--
:::image type="content" source="media/Open in OneDrive.PNG" alt-text="The Open in OneDrive action":::

 
:::image type="content" source="media/OneDrive attachment.PNG" alt-text="Share file attachments in OneDrive":::
-->

## Otevřít na OneDrivu

Akce **Otevřít na OneDrivu** zkopíruje soubor na OneDrive a otevře ho v jejich online aplikacích, jako je Excel Online, Word Online a PowerPoint Online.

<!--## Working with Different Types of Files-->

Když zvolíte **Otevřít na OneDrivu**, [!INCLUDE[prod_short](includes/prod_short.md)] identifikuje soubory Excel, Word a PowerPoint a otevře je v jejich online aplikacích, tedy Excel online, Word online a PowerPoint online. Můžete přidávat poznámky, upravovat je a spolupracovat s ostatními, aniž byste opustili prohlížeč.

U jiných oblíbených typů souborů, jako jsou PDF, textové soubory a obrázky, nabízí OneDrive prohlížeče souborů, které nabízejí funkce pro tisk, sdílení a další. Pokud soubor nelze zobrazit na OneDrive, můžete být vyzváni ke stažení.

## Sdílet

Akce **Sdílet** zkopíruje soubor do OneDrive a umožní vám sdílet ho s dalšími lidmi a podívat se, s kým jste ho už sdíleli. Když vyberete akci **Sdílet**, otevře se následující stránka.

:::image type="content" source="media/share-to-onedrive-dialog.PNG" alt-text="Sdílet soubor na OneDrivu":::

Pokud OneDrive znáte, možná tu stránku poznáte. Soubor můžete sdílet dvěma způsoby: **Odeslat odkaz** a **Kopírovat odkaz**.

- **Odeslat odkaz** umožňuje sdílet soubory s konkrétními lidmi. Lidé, kterým soubor sdílíte, dostanou e-mail s odkazem na soubor. Soubor se také objeví v sekci **Sdílené** na jejich OneDrivu. Začněte zadáním e-mailových adres nebo jmen kontaktů do **pole Jméno, skupina nebo e-mail**.

- **Kopírovat odkaz** zkopíruje odkaz k souboru na OneDrivu, abyste jej mohli použít na jiných místech, jako je Facebook, Twitter nebo e-maily.

Před odesláním nebo zkopírováním odkazu nastavte oprávnění k souboru, která chcete, aby lidé měli. Aktuální nastavení můžete vidět v části **Odeslat odkaz** a **Kopírovat odkaz**. Ve většině případů to bude **Každý, kdo má odkaz, může upravit a otevřít odkaz.**, v závislosti na nastaveních, která provedl váš administrátor. Chcete-li změnit oprávnění, vyberte odkaz a proveďte změny na stránce **Nastavení odkazu**.

Funkce sdílení v Business Central je založena na OneDrivu. Další informace o sdílení a oprávněních najdete v tématu [Sdílení souborů a složek na OneDrivu](https://support.microsoft.com/en-us/office/share-onedrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07).

> [!NOTE]
> Akce **Sdílet** není v aplikaci Business Central pro mobilní zařízení k dispozici.

## První přihlášení z Business Central

Když poprvé použijete akci **Otevřít na OneDrivu** nebo **Sdílet**, [!INCLUDE[prod_short](includes/prod_short.md)] provede následující akce:

1. Otevře stránku **Přečtěte si smluvní podmínky**. Přečtěte si stránku a pokud souhlasíte s podmínkami a ujednáními, vyberte **Souhlasím** pro pokračování.
2. Otevře stránku **Vyberte účet** nebo **použijte jiný účet**, pokud nevidíte svůj vlastní, tak po zobrazení výzvy zadejte uživatelské jméno a heslo.
3. Vytvoří složku s názvem [!INCLUDE[prod_short](includes/prod_short.md)] na OneDrivu.
4. Ve složce [!INCLUDE[prod_short](includes/prod_short.md)] vytvoří další složku se stejným názvem jako společnost, ve které pracujete. Pokud pracujete ve více než jedné společnosti, vytvoří se složka pro společnost, ve které pracujete, když použijete akce **Otevřít na OneDrivu** a **Sdílet**.
5. Vloží kopii vybraného souboru do složky a potom soubor otevře. Při příštím použití akce pouze zkopíruje a otevře soubor.

## Správa více kopií souboru

Když zvolíte **Otevřít na OneDrivu** nebo **Sdílet**, soubor se zkopíruje z [!INCLUDE[prod_short](includes/prod_short.md)] do vaší složky na OneDrivu. Pokud soubor upravíte na OneDrivu, kopie souboru se budou lišit. Chcete-li aktualizovat [!INCLUDE[prod_short](includes/prod_short.md)] s nejnovějším souborem, odeberte existující soubor z [!INCLUDE[prod_short](includes/prod_short.md)] a pak nahrajte nejnovější kopii.

Pokud soubor se stejným názvem již existuje na OneDrivu, [!INCLUDE[prod_short](includes/prod_short.md)] nabídne možnost buď nahradit soubor, nebo zachovat oba soubory. Pokud se rozhodnete ponechat oba soubory, nový soubor se zkopíruje na OneDrive a bude mu přidělen název souboru s příponou, například „Položky (2).xlsx“. Původní soubor se nezmění.

Pokud se rozhodnete soubor nahradit, bude nový soubor přidán do historie verzí tohoto souboru. Původní soubor se neztratí a můžete zobrazit nebo obnovit předchozí verze souboru.

## O složce Business Central na OneDrivu

Složka a její obsah jsou soukromé, dokud se je nerozhodnete sdílet s ostatními. Můžete se například rozhodnout sdílet obsah s jedním nebo více spolupracovníky nebo dokonce s lidmi mimo vaši organizaci.
Ke svému OneDrivu se dostanete ze stránky **Moje nastavení** výběrem odkazu v poli **Cloudové úložiště**. Pro více informací navštivte [Sdílení souborů a složek na OneDrivu](https://support.microsoft.com/en-us/office/share-onedrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07).

:::image type="content" source="media/my-settings-cloud-storage.PNG" alt-text="Pole Cloud Storage v Moje nastavení":::

<!--## Extending the Connection to OneDrive
You can create an extension and connect it to... For more information, see...-->

## Viz také
[Integrace Business Central a OneDrive](across-onedrive-overview.md)    
[Správa integrace OneDrive s Business Central](admin-onedrive-integration.md)    
[Nejčastější dotazy k OneDrive](admin-onedrive-faq.md)  