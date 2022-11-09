---
title: Managing OneDrive Integration with Business Central
description: Learn about things you can do to manage an integration between Business Central and OneDrive for Business.
author: jswymer
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: OneDrive, share, browser
ms.date: 02/28/2022
ms.author: jswymer
---
# Správa integrace OneDrive s Business Central

Tento článek poskytuje přehled o tom, co může správce udělat pro řízení integrace OneDrive pro firmy pomocí [!INCLUDE[prod_short](includes/prod_short.md)]. [!INCLUDE[prod_short](includes/prod_short.md)] online zákazníci těží z automatické integrace bez dalšího nastavování pro použití těchto funkcí.

## Minimální požadavky

* Každý uživatel musí mít licenci pro [!INCLUDE[prod_short](includes/prod_short.md)] a OneDrive jako součást plánu Microsoft 365.
* OneDrive musí být nastavený pro každého uživatele.

## Správa

Admin center pro správu SharePointu poskytuje rozsáhlou kontrolu nad zásadami, kterými se řídí používání OneDrive v celé organizaci. Globální správci nebo uživatelé, kteří mají roli správce SharePointu, mohou nastavit zásady, které určují, kdo má přístup k OneDrivu, kde jsou uložena data, životní cyklus obsahu a mnoho dalšího. Následující odkazy poskytují informace o často používaných funkcích a nastaveních, které mohou zlepšit integraci s [! INCLUDE[prod_short](includes/prod_short.md)].

* [Správa nastavení sdílení](/sharepoint/turn-external-sharing-on-or-off)
* [Použití informačních bariér se službou SharePoint](/sharepoint/information-barriers)
* [Zjistěte více o ochraně před ztrátou informací](/microsoft-365/compliance/dlp-learn-about-dlp)
* [Nastavení výchozího úložného prostoru pro uživatele OneDrive](/onedrive/set-default-storage-space)
* [Přidat a odebrat správce pro OneDrive uživatele](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)
* [Zakázat vytváření OneDrive pro některé uživatele](/sharepoint/manage-user-profiles#disable-onedrive-creation-for-some-users)
* [Funkce Multi-Geo na OneDrive a SharePoint Online](/microsoft-365/enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365)

> [!NOTE]
> Některé funkce mohou být dostupné pouze pro konkrétní plány.

## Správa ochrany osobních údajů

Správci a koncoví uživatelé řídí obsah uložený na OneDrive a tato data vlastní výhradně vaše organizace. Pro více informací navštivte [Jak SharePoint a OneDrive chrání vaše data v cloudu](/sharepoint/safeguarding-your-data). Můžete také navštívit naše [Prohlášení o zásadách ochrany osobních údajů společnosti Microsoft](https://privacy.microsoft.com/en-us/privacystatement), které vysvětluje, jaká data společnost Microsoft zpracovává, jak je zpracovává a pro jaké účely.

## Obnovení OneDrive a [!INCLUDE[prod_short](includes/prod_short.md)]

V rámci cvičení zotavení po havárii může být nutné, aby správci obnovili [!INLCUDE[prod_short](includes/prod_short.md)] prostředí do zálohy z doby v minulosti a synchronizovat úložiště OneDrive do stejného bodu v čase. OneDrive k tomu poskytuje různé nástroje, jako je obnovení OneDrive uživatele do dřívější doby, obnovení předchozí verze jednotlivého souboru nebo obnovení smazaných souborů. Další informace naleznete v následujících článcích:

* Pro informace o [! INCLUDE[prod_short](includes/prod_short.md)], navštivte [Obnovení prostředí v Admin centru](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-backup-restore).
* Pro informace o OneDrive, navštivte [Obnovení OneDrive](https://support.microsoft.com/en-us/office/restore-your-onedrive-fa231298-759d-41cf-bcd0-25ac53eb8a15?ui=en-us&rs=en-us&ad=us)

## Konfigurace Business Central On-Premises

Správce musí nastavit připojení mezi [!INCLUDE[prod_short](includes/prod_short.md)] on premises a OneDrive. Na rozdíl od [! INCLUDE[prod_short](includes/prod_short.md)] online, připojení není automatické. Pokud připojení není nakonfigurované, uživatelé nemohou používat funkce pro OneDrive.

[!INCLUDE[prod_short](includes/prod_short.md)] on-premises lze připojit pouze k OneDrive hostovanému společností Microsoft v cloudu. Připojení [!INCLUDE[prod_short](includes/prod_short.md)] k on premises do úložiště osobních webů SharePoint Serveru se nepodporuje.

> [!IMPORTANT]
> Nakonfigurováním této funkce také povolíte starší funkce, které posílají soubory na OneDrive.
>
> * Funkce Otevřít v aplikaci Excel automaticky zkopíruje excelový soubor na OneDrive a pak ho otevře v Excel Online.
> * Při exportu jakékoli sestavy do souboru, se soubor automaticky zkopíruje na OneDrive a pak se otevře v Excel Online, Word Online nebo OneDrive.
> * Další funkce se můžou automaticky otevírat i na OneDrive.

### Abyste připravili [!INCLUDE[prod_short](includes/prod_short.md)] on-premises pro připojení k OneDrive

<!--
1. For the best experience Configure Azure Active Directory (AD) authentication.

   For more information, see [Authenticating Business Central Users with Azure Active Directory](/dynamics365/business-central/dev-itpro/administration/authenticating-users-with-azure-active-directory)-->

Přidejte registrovanou aplikaci pro Business Central do svého tenanta Azure AD vašeho plánu Microsoft 365. Stejně jako ostatní služby Azure, které pracují s Business Central, OneDrive vyžaduje registraci aplikace v Azure Active Directory (Azure AD). Registrace aplikace poskytuje služby ověřování a autorizace mezi Business Central a SharePoint, který používá OneDrive.

Nakonfigurujte registrovanou aplikaci s následujícími delegovanými oprávněními k rozhraní API služby SharePoint:

- AllSites.FullControl
- User.ReadWrite.All

Pro Business Central 2021 vlnu vydání 2 (verze 19), nastavte místo toho tato oprávnění:

- AllSites.Write
- MyFiles.Write
- User.Read.All

Tuto práci provedete v Azure Portal. Nezapomeňte zkopírovat ID aplikace (klienta) a tajný klíč klienta používaný registrovanou aplikací. Tyto informace budete potřebovat v dalším úkolu.

Další informace o registraci aplikace a konfiguraci oprávnění najdete v tématu [Registrace aplikace v Azure Active Directory](/dynamics365/business-central/dev-itpro/administration/register-app-azure#register-an-application-in-azure-active-directory) v nápovědě pro vývojáře a IT profesionály.

> [!TIP]
> Pokud jste již zaregistrovali aplikaci v rámci integrace s jiným produktem společnosti Microsoft, jako je Power BI, můžete tuto registraci aplikace znovu použít. V takovém případě stačí nastavit oprávnění služby SharePoint.

### Nastavení připojení v [!INCLUDE[prod_short](includes/prod_short.md)] on-premises

<!--
> [!NOTE]
> This requires the following types of authentication credentials:
>
> * Windows
> * NavUserPassword
> * Azure Active Directory
-->
1. Vyberte ikonu![Žárovky, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Nastavení připojení k Microsoft SharePoint** a pak zvolte související odkaz.
2. Do pole **Popis**, zadejte popis připojení, například **OneDrive**.
3. Do pole **Složka**, zadejte **Business Central**.
4. Do pole **Umístění**, zadejte adresu URL svého OneDrive.

   Adresa URL OneDrive je obvykle v následujícím formátu: `https://<název tenanta>-my.sharepoint.com`. Další informace najdete v tématu [Adresy URL OneDrive pro uživatele ve vaší organizaci](/onedrive/list-onedrive-urls) v dokumentaci k OneDrive.
5. Do pole ID klienta zadejte **ID klienta** z registrace aplikace.
6. Do pole **Klientský tajný klíč**, zadejte tajný klíč z registrace vaší aplikace.
   <!--
      For information about how to find the URLs, see the following:
      * [How to find your SharePoint server URL]
      * [How to find your OneDrive URL]-->

> [!IMPORTANT]
> Stránka Nastavení připojení SharePoint se používá ke konfiguraci několika starších funkcí. Sekce **Obecné** konfiguruje připojení k OneDrive a sekce **Sdílené dokumenty** místo toho přesměrovává soubory na SharePoint. Starší funkce SharePoint bude v blízké budoucnosti ukončena. Doporučujeme, abyste sekci **Sdílené dokumenty** nekonfigurovali.

## Viz také
[Integrace Business Central a OneDrive pro firmy](across-onedrive-overview.md)    
[Otevírání souborů Business Central na OneDrive](across-share-onedrive.md)    
[Nejčastější dotazy o OneDrive](admin-onedrive-faq.md)  

