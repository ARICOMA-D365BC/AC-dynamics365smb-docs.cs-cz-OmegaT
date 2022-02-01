---
    title: How to Block Sales to Customers
    description: If needed, you can block a customer from being included on sales documents and other sales transactions.
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
# Blokace zákazníků
Zákazníka můžete zablokovat například z důvodu platební neschopnosti, aby jej nebylo možné přidat do prodejních dokladů nebo na zákazníka nemohly být zaúčtovány žádné transakce.

Kromě blokování zákazníka můžete nastavit transakce pohledávek, aby byl zákazník v souvislosti s upomínkami pozastaven. For more information, see [Collect Outstanding Balances](receivables-collect-outstanding-balances.md).

Následující tabulka popisuje možnosti blokování zákazníků.

| Možnost | Popis |
|--------------------|------------|  
| **Blank** | Transakce jsou pro tohoto zákazníka povoleny. |
| **Ship** | Pro tohoto zákazníka nelze vytvořit nové objednávky ani nové dodávky. Existující dodávky, které ještě nebyly fakturovány, lze fakturovat. |
| **Invoice** | Pro tohoto zákazníka nelze vytvořit nové objednávky, nové dodávky ani nové faktury. Existující dodávky, které ještě nebyly fakturovány, nelze fakturovat. Zákazníkovi můžete stále posílat upomínky a penále. |
| **All** | Pro tohoto zákazníka není povolena žádná transakce, včetně plateb. |

## Zablokování zákazníka
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Select a customer, and then choose the **Edit** action.
3. In the **Blocked** field, choose what to block, as described in the table above.

## Viz také
[Register New Customers](sales-how-register-new-customers.md)  
[Collect Outstanding Balances](receivables-collect-outstanding-balances.md)  
[Managing Receivables](receivables-manage-receivables.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]