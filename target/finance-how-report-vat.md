---
title: Submit VAT Reports to Tax Authorities
description: Learn how to prepare reports that lists VAT from sales during a period, or from sales and purchases, and submit the report to a tax authority.
author: brentholtorf


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: VAT, tax, report, EC sales list, statement
ms.search.form: 321, 322, 323, 474, 475, 739, 740, 741, 742, 743, 744, 745, 746, 747, 748, 9401
ms.date: 01/31/2022
ms.author: bholtorf

---

# Výkaz DPH Finančnímu úřadu

Toto téma popisuje sestavy v [!INCLUDE[prod_short](includes/prod_short.md)] které můžete použít k odeslání informací o částkách daně z přidané hodnoty (DPH) za prodeje a nákupy daňovým úřadům ve vaší zemi. V závislosti na konkrétní zemi mohou sestavy obsahovat specifické informace nebo mohou existovat další sestavy, které musíte odesílat. Podívejte se na další články pro vaši zemi v sekci [Lokální funkcionality](about-localization.md).

Můžete použít následující integrované sestavy:

* Sestava **Přehled prodeje v EU**

   V sestavě Přehled prodeje v EU jsou uvedeny částky daně z přidané hodnoty (DPH), které jste vybrali za prodeje zákazníkům registrovaným k DPH v zemích Evropské unie (EU).
* Sestava **Přiznání k DPH** report

   Přehled přiznání k DPH zahrnuje DPH za prodeje a nákupy zákazníkům a od dodavatelů ve všech zemích, které používají DPH.

V obou případech se DPH vypočítá na základě nastavení účtování DPH a nastavených účto skupin DPH.

Pokud chcete zobrazit úplnou historii položek DPH, každé zaúčtování, které zahrnuje DPH, vytvoří položku na stránce **Položky DPH**. Tyto záznamy slouží k výpočtu částky pro vypořádání DPH, jako je platba a vrácení za určité období. Chcete-li tyto položky zobrazit, vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Položky DPH** a poté vyberte související odkaz.

> [!NOTE]
> Každé prostředí  [!INCLUDE[prod_short](includes/prod_short.md)] je určeno ke zpracování regulačních sestav v jedné zemi. Například holandská verze [!INCLUDE[prod_short](includes/prod_short.md)] zpracovává vykazování DPH v Nizozemsku, ale ne v jiných zemích. Podobně i americká verze [!INCLUDE[prod_short](includes/prod_short.md)] zpracovává hlášení 1099 ve Spojených státech a nepodporuje nárokování na vykazování DPH v jiných zemích, pokud není podáno rozšířením dodaným naším partnerským systémem nebo specifickou úpravou pro zákazníka.

## <a name="ecsaleslist"></a>o sestavě Přehledu prodeje v EU

V Evropské unii (EU) a ve Spojeném království musí všechny společnosti, které prodávají zboží a služby zákazníkům registrovaným k DPH, včetně zákazníků v jiných zemích Evropské unie (EU), předložit elektronickou verzi hlášení souhrnného hlášení Evropského společenství (ES) svým celním a daňovým úřadům. **Přehled prodeje v EU** funguje pouze pro země v EU.

Sestava obsahuje jeden řádek pro každý typ transakce se zákazníkem a zobrazuje celkovou částku pro každý typ transakcí. Přehled může zahrnovat tři typy transakcí:

* B2B zboží
* B2B služby
* B2B triangulace zboží

Zboží a služby*B2B* určují, zda jste prodali zboží nebo službu, a řídí se nastavením **Služba EU** v nastavení účtování DPH. *B2B triangulované zboží* uvádí, zda jste obchodovali s třetí stranou a zda je řízeno nastavením **EU 3-Party Trade** na prodejních dokladech, jako jsou prodejní objednávky, faktury, dobropisy a tak dále.

Poté, co finanční úřad zkontroluje váš výkaz, zašle e-mail kontaktní osobě vaší společnosti. V [!INCLUDE[prod_short](includes/prod_short.md)], je kontaktní osoba uvedena na stránce **Informace o společnosti**. Před odesláním výkazu se ujistěte, že je vybrána kontaktní osoba.

### Odeslání Přehledu prodeje v EU

[!INCLUDE [finance-ecsaleslist](includes/finance-ecsaleslist.md)]

## <a name="vatreturn"></a>O Přehledu přiznání k DPH

Tuto sestavu použijte k odeslání DPH za prodejní a nákupní doklady, jako jsou nákupní a prodejní objednávky, faktury a dobropisy. Informace v sestavě jsou ve stejném formátu jako ve formuláři prohlášení celních a daňových orgánů.

Pro přiznání k DPH můžete zadat položky, které mají být zahrnuty:

* Odesílejte pouze otevřené transakce nebo otevřené a uzavřené transakce. To je užitečné například při přípravě konečného ročního přiznání k DPH.
* Předložte pouze položky ze zadaných období, nebo zahrňte i položky z předchozích období. To je užitečné pro aktualizaci přiznání k DPH, které jste již odeslali, například pokud vám dodavatel zašle pozdě fakturu.

## Připojení k webové službě finančního úřadu
[!INCLUDE[prod_short](includes/prod_short.md)] poskytuje připojení k webovým stránkám daňových úřadů. Pokud se například nacházíte ve Spojeném království, můžete povolit připojení služby **GovTalk** k elektronickému odesílání Sestavy Přehledu prodeje v EU a přiznání k DPH. Pokud chcete hlášení odeslat ručně, například zadáním svých údajů na webových stránkách finančního úřadu, není to nutné.

Chcete-li daňovému úřadu oznámit DPH elektronicky, musíte se připojit [!INCLUDE[prod_short](includes/prod_short.md)] do webové služby finančního úřadu. To vyžaduje, abyste si zřídili účet u svého daňového úřadu. Pokud máte účet, můžete povolit připojení ke službě, které poskytujeme v [!INCLUDE[prod_short](includes/prod_short.md)].

1. Vyberte ikonu ![Žárovka, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zvolte **Připojení Služby** a poté vyberte související odkaz.
2. Vyplňte požadovaná pole. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

   > [!NOTE]  
   > Připojení je vhodné otestovat. Chcete-li to provést, zaškrtněte políčko **Testovací režim** a poté připravte a odešlete hlášení DPH, jak je popsáno v části [Příprava a odeslání hlášení DPH](#to-prepare-and-submit-a-vat-report). V testovacím režimu služba testuje, zda daňový úřad může vaše hlášení přijmout, a stav hlášení uvádí, zda bylo testovací podání úspěšné. Je důležité si uvědomit, že se nejedná o skutečné podání. Chcete-li zprávu odeslat skutečně, musíte zrušit zaškrtnutí políčka **Testovací režim** a poté proces odeslání zopakovat.

## Nastavení hlášení DPH v nabídce [!INCLUDE[prod_short](includes/prod_short.md)]

[!INCLUDE [vat-report-setup](includes/vat-report-setup.md)]

### Nastavení období pro přiznání DPH

Pokud se vaše firma nenachází ve Spojeném království, použijte stránku **Období přiznání k DPH** k nastavení plánovaných přiznání k DPH. Pokud se vaše firma nachází ve Velké Británii, přečtěte si téma [Digitální daň ve Spojeném království](LocalFunctionality/UnitedKingdom/making-tax-digital-submit-vat-return.md).

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png " Řekněte mi, co chcete dělat") zadejte **Období přiznání k DPH** a vyberte související odkaz.
2. Na stránce **Období přiznání k DPH** vyplňte pole pro nastavení prvního období. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)].
3. Opakujte krok 2 pro všechna další období, která chcete přidat.

Nyní, až nastane čas pro podání hlášení DPH za období, vyberte období na stránce **Období přiznání DPH** a poté zvolte akci **Vytvořit DPH přiznání **. Poté na kartě **Přehled přiznání k DPH** vyberte akci **Navrhnout řádky**, jak je popsáno v kroku 3 v následujícím postupu.

## Příprava a podání hlášení o DPH

1. Vyberte ikonu ![Žárovky, která otevře funkci Řekněte mi](media/ui-search/search_small.png "Řekněte mi, co chcete dělat"), zadejte **Přehled prodeje v EU** nebo **Přehled přiznání k DPH**a poté zvolte související odkaz.
2. Zvolte **Nový** a vyplňte požadovaná pole. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Chcete-li vygenerovat obsah sestavy, vyberte akci **Navrhnout řádky**.

   > [!NOTE]  
   > U sestavy Přehled prodeje v EU můžete před odesláním výkazu zkontrolovat transakce zahrnuté do řádků sestavy. Chcete-li to provést, zvolte řádek a poté zvolte akci **Zobrazit položky DPH**.

4. Chcete-li ověřit a připravit sestavu k odeslání, vyberte akci **Vydat**.

   > [!NOTE]  
   > [!INCLUDE[prod_short](includes/prod_short.md)] ověří, zda je sestava nastavena správně. Pokud se ověření nezdaří, chyby se zobrazí v části **Chyby a upozornění, abyste** věděli, co opravit. Obvykle, pokud je zpráva o chybějícím nastavení v [!INCLUDE[prod_short](includes/prod_short.md)], můžete klepnutím na zprávu otevřít stránku obsahující informace, které chcete opravit.
5. Chcete-li zprávu odeslat, vyberte akci **Odeslat**.

Po odeslání sestavy [!INCLUDE[prod_short](includes/prod_short.md)] sleduje službu a uchovává záznamy o vaší komunikaci. Pole **Stav** označuje, v jakém stavu se sestava v průběhu procesu. Když například úřady zpracují váš výkaz, stav sestavy se změní na **Úspěšný**. Pokud finanční úřad zjistí chyby v hlášení, které jste odeslali, stav hlášení bude **Neúspěšný**. Chyby si můžete prohlédnout v části **Chyby a varování**, opravit je a poté zprávu odeslat znovu Chcete-li zobrazit seznam všech sestav Přehled prodeje v EU, přejděte na stránku **Sestavy Přehledu prodeje v EU**.

## Zobrazení komunikace s finančním úřadem
V některých zemích si při odesílání hlášení vyměňujete zprávy s finančním úřadem. You can view the first and the last message you sent or received by choosing the **Download Submission Message** and **Download Response Message** actions.

## Submitting VAT reports manually
If you use another method to submit the report, for example by exporting the XML and uploading it to a tax authority website, afterward you can choose **Mark as Submitted** to close the reporting period. When you mark the report as released, it becomes non-editable. If you must change the report after you mark it as released, you must reopen it.

## VAT settlement
Periodically, you must remit the net VAT to the tax authorities. If you need to settle VAT frequently, you can run the **Calc. and Post VAT Settlement** batch job to close the open VAT entries and transfer purchase and sales VAT amounts to the VAT settlement account.

When you transfer VAT amounts to the settlement account, the purchase VAT account is credited, and the sales VAT account is debited with the amounts calculated for the specified period. The net amount is credited or debited, if the purchase VAT amount is larger, to the VAT settlement account. You can post the settlement immediately or print a test report first.

> [!Note]
> When you use the **Calc. and Post VAT Settlement** batch job, if you do not specify a **VAT Bus. Posting Group** and a **VAT Prod. Posting group**, entries with all business posting groups and product posting group codes are included.

## Configuring your own VAT reports

You can use the **EC Sales List** report out-of-the-box. However, you can also create your own reports, if you have a development license so that you can create codeunits. If you need assistance, contact a Microsoft Partner.

The following table describes the codeunits that you must create for your report.

| Codeunita | What it must do |
|----|-----|
| Suggest Lines | Fetch information from the **VAT Entries** table, and display it in lines on the VAT report. |
| Content | Control the format of the report. For example, whether it is XML or JSON. The format to use depends on the requirements of your tax authority's web service. |
| Submission | Control how, and when, you submit the report based on the requirements of your tax authority. |
| Response Handler | Handle the return from the tax authority. For example, it might send an email message to your company's contact person. |
| Cancel | Send a cancellation of a VAT report that was submitted earlier to your tax authority. |

> [!Note]
> When you create codeunits for the report, pay attention to the value in the **VAT Report Version** field. This field must reflect the version of the report that is, or was, required by the tax authority. For example, you might enter **2021** in the field to indicate that the report conforms to the requirements that were in place that year. To find the current version, contact your tax authority.

## Viz související školení na webu [Microsoft Learn](/learn/paths/process-vat-dynamics-365-business-central/)

## Viz také

[Set Up Calculations and Posting Methods for Value-Added Tax](finance-setup-vat.md)  
[Work with VAT on Sales and Purchases](finance-work-with-vat.md)  
[Set Up Sales](sales-setup-sales.md)  
[Invoice Sales](sales-how-invoice-sales.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]