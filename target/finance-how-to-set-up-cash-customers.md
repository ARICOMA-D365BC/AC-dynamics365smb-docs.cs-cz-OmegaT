---
    title: How to Set Up Cash Customers | Microsoft Docs
    description: This topic describes the steps to set up customer who pays in cash.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2021
    ms.author: edupont

---
# Nastavení zákazníků platících hotovostí
Fakturu nelze vytvořit bez čísla zákazníka. To platí, i když provedete hotovostní prodej a nemáte co zaznamenávání na účtu zákazníka.

## Nastavení zákazníka platícího hotovostí
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customer**, and then choose the related link.
2. Create a new **Customer** card. For more information, see [Register New Customers](sales-how-register-new-customers.md).
3. In the **No.** field, enter **Cash**, for example.
4. In the **Name** field, enter **Cash Sale**, for example.
5. On the **Invoicing** FastTab, fill in the **Customer Posting Group** and the **Gen. účto  Posting Group** fields.

Nyní jste vytvořili zákazníka, který obsahuje dostatečné informace pro fakturaci.

> [!NOTE]  
> You may have chosen a posting group that is also used for domestic credit sales. Pokud si chcete zachovat samostatné údaje o hotovostním prodeji, například se zvláštním účtem prodeje nebo pohledávek, můžete pro tento účel zřídit zvláštní účtovací skupinu.
>
> Musíte zadat číslo účtu pohledávek pro účtovací skupinu, i když zůstatek na tomto účtu bude po odeslání faktury vždy 0.

## Viz také
[Managing Receivables](receivables-manage-receivables.md)  
[Register New Customers](sales-how-register-new-customers.md)    
[Finance](finance.md)



[!INCLUDE[footer-include](includes/footer-banner.md)]