---
title: Setting Up Text-to-Account Mapping for Recurring Payments
description: Link text on payments with specific accounts, so that payments are posted to the accounts when you post the payment reconciliation journal.
author: SorenGP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: account linking, direct payment posting, automatic payment processing, reconcile payment, recurring expense, recurring cash receipt
ms.search.form: 1290, 1294, 1287
ms.date: 04/01/2021
ms.author: edupont

---
# Mapování textu na opakované platby na účty pro automatické odsouhlasení
Na stránce **Mapování textu na účet**, kterou otevřete ze stránky **Deník odsouhlasení plateb**, můžete nastavit mapování mezi textem o platbách a konkrétním debetem, kreditem a vyrovnávací účty, aby se takové platby zaúčtovaly na specifické účty při zaúčtování deníku odsouhlasení plateb.

Podobná funkce existuje pro odsouhlasení přebytečných částek na řádcích deníku odsouhlasení plateb na ad hoc bázi. Další informace naleznete v části [Odsouhlasení plateb, které nelze použít automaticky](receivables-how-reconcile-payments-cannot-apply-auto.md).

Platby zaúčtované na základě mapování textu na účet se nepoužijí na otevřené položky, ale jsou pouze zaúčtovány na zadané účty kromě vytvoření položek bankovního účtu. Mapování textu na účet je proto vhodné pro opakující se hotovostní příjmy nebo výdaje, jako jsou časté nákupy pohonných hmot nebo bankovní poplatky a úroky, které se pravidelně vyskytují na bankovním výpisu a nepotřebují související obchodní dokument. Další informace naleznete v části "Příklad – mapování nákladů na pohonné hmoty z textu na účet" v tomto tématu.

> [!NOTE]  
> Platby na řádcích deníku odsouhlasení jsou nastaveny na zaúčtování podle mapování textu na účet pouze v případě, že funkce automatické aplikace může poskytnout spolehlivost shody pouze **Nízká** nebo **Střední**. Pokud funkce automatické aplikace poskytuje shodu Vysoká, pak se platba automaticky použije na jednu nebo více otevřených položek a platba není zaúčtována na účty uvedené na stránce **Mapování textu na účet**. Jinými slovy, spolehlivost shody **Vysoká** převažuje nad mapováním textu na účet.

Na řádku deníku odsouhlasení plateb, kde byla platba nastavena na zaúčtování podle mapování textu na účet, obsahuje pole **Spolehlivost shody** **hodnotu Vysoká – mapování textu na účet** a pole **Typ účtu** a **Číslo účtu** obsahují mapované účty.

## Mapování textu o opakovaných platbách k účtům pro automatické odsouhlasení
1. Zvolte ![Žárovku, která otevře funkci Řekněte mi.](media/ui-search/search_small.png " Řekněte mi, co chcete udělat"), zadejte **Deníky odsouhlasení plateb** a pak zvolte související odkaz.
2. Otevřete deník odsouhlasení plateb. Pro více informací navštivte [Automatické odsouhlasení plateb<x2/>.
3. Vyberte akci **Mapovat text na účet**. Otevře se stránka **Mapování textu na účet**.
4. Do pole **Text mapování** zadejte libovolný text, který se vyskytuje u plateb, které chcete zaúčtovat na zadané účty, aniž byste se museli vztahovat na otevřenou položku. Můžete zadat až 50 znaků.

   > [!NOTE]  
   > Pokud s příslušným textem mapování neexistují žádné další platby, dojde k mapování textu na účet, i když pouze část textu na platbě existuje jako text mapování.
5. V poli **Číslo dodavatele** zadejte dodavatele, kterému budou platby zaúčtovány.
6. V poli **Číslo V poli Typ zdroje** zadejte, zda bude platba zaúčtována na účet hlavní knihy nebo na účet zákazníka nebo dodavatele.
7. V poli **Číslo V poli Zdroj č.** zadejte účet, na který bude platba zaúčtována, v závislosti na vašem výběru v **Typu zdroje protiúčtu**

   > [!NOTE]
   > Nepoužívejte **Debetní účet č.** a **Kreditní účet. č.** pole v souvislosti s odsouhlasením plateb. Jsou používány pouze pro příchozí dokumenty. Další informace naleznete v části [Použití OCR k přeměně souborů PDF a obrázků na elektronické dokumenty](across-how-use-ocr-pdf-images-files.md).

8. Opakujte kroky 3 až 7 pro veškerý text o platbách, které chcete namapovat na účty pro přímé účtování bez použití.

Při příštím importu souboru bankovního výpisu nebo výběru akce **Použít automaticky** na stránce **Deník odsouhlasení plateb** budou řádky deníku pro platby, které obsahují zadaný text mapování, obsahovat mapované účty v polích **Typ účtu** a **Číslo účtu**. Pole **Spolehlivost shody** bude obsahovat **vysoké mapování textu na účet**. To je za podmínky, že funkce automatické aplikace může poskytnout pouze shodu **spolehlivosti Nízká** nebo **Střední**.

## Příklad: Mapování textu na účet pro bankovní poplatky

Chcete-li vždy účtovat výdaje související s poplatky konkrétní banky, MyBank, na účet hlavní knihy pro bankovní poplatky a poplatky (účet 60400), vyplňte řádek na stránce **Mapování textu na účet** jak následuje.

| Mapování textu | Debetní účet Čísla. | Kreditní účet Čísla. | Typ zdroje protiúčtu | Typ čísla zdroje protiúčtu |
| --- | --- | --- | --- | --- |
| MyBank | Prázdný | 60400 | Finanční účet | Prázdný |

## Viz také

[Správa pohledávek](receivables-manage-receivables.md)    
[Prodej](sales-manage-sales.md)    
[Nastavení služby Envestnet Yodlee Bank Feeds](bank-how-setup-bank-statement-service.md)    
[Přizpůsobení [!INCLUDE[prod_short](includes/prod_short.md)] pomocí rozšíření](ui-extensions.md)  
[Pracovat s [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]