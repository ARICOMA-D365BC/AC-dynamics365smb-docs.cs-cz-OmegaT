---
    title: Design Details - Table Structure | Microsoft Docs
    description: To understand how the dimension entry storing and posting is redesigned, it is important to understand the table structure.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/08/2021
    ms.author: edupont

---
# Detaily návrhu:  Struktura tabulky
Chcete-li pochopit, jak jsou položky dimenzí uloženy a zaúčtovány, je důležité porozumět struktuře tabulky.

## Tabulka 480, Položka sady dimenzí
Tuto tabulku nelze změnit. Po zapsání dat do tabulky není možné data odstranit ani upravit.

| Číslo pole. | Název pole | Datový typ | Komentář |
|---------------|----------------|---------------|-------------|  
| 1 | **ID** | Integer | >0,0 je rezervováno pro prázdnou sadu dimenzí. Odkazuje na pole 3 v tabulce 481. |
| 2 | **Dimension Code** | Code 20 | Vztah tabulky k tabulce 348. |
| 3 | **Dimension Value Code** | Code 20 | Vztah tabulky k tabulce 349. |
| 4 | **Dimension Value ID** | Integer | Odkazuje na pole 12 v tabulce 349. Jedná se o sekundární klíč, který se používá při procházení tabulky 481. |
| 5 | **Dimension Name** | Text 30 | CalcField. Lookup do tabulky 348. |
| 6 | **Dimension Value Name** | Text 30 | CalcField. Lookup do tabulky 349. |

## Tabulka, Uzel stromu sady dimenzí
Tuto tabulku nelze změnit. Používá se k vyhledání sady dimenzí. Pokud sada dimenzí není nalezena, vytvoří se nová sada.

| Číslo pole. | Název pole | Datový typ | Komentář |
|---------------|----------------|---------------|-------------|  
| 1 | **Parent Dimension Set ID** | Integer | 0 pro uzel nejvyšší úrovně. |
| 2 | **Dimension Value ID** | Integer | Vztah tabulky k poli 12 v tabulce 349. |
| 3 | **Dimension Set ID** | Integer | AutoIncrement. Používá se v poli 1 v tabulce 480. |
| 4 | **In Use** | Boolean | False, pokud se nepoužívá. |

## Tabulka 482 Zásobník přeřazení sady dimenzí
This table is used when you change a dimension value code, for example, on an item ledger entry by using the **Item Reclassification Journal** page.

| Číslo pole. | Název pole | Datový typ | Komentář |
|---------------|----------------|---------------|-------------|  
| 1 | **Dimension Code** | Code 20 | Vztah tabulky k tabulce 348. |
| 2 | **Dimension Value Code** | Code 20 | Vztah tabulky k tabulce 349. |
| 3 | **Dimension Value ID** | Integer | Odkazuje na pole 12 v tabulce 349. |
| 4 | **New Dimension Value Code** | Code 20 | Vztah tabulky k tabulce 349. |
| 5 | **New Dimension Value ID** | Integer | Odkazuje na pole 12 v tabulce 349. |
| 6 | **Dimension Name** | Text 30 | CalcField. Lookup do tabulky 348. |
| 7 | **Dimension Value Name** | Text 30 | CalcField. Lookup do tabulky 349. |
| 8 | **New Dimension Value Name** | Text 30 | CalcField. Lookup do tabulky 349. |

## Tabulky transakcí a rozpočtu
Kromě dalších polí dimenzí v tabulce je toto pole důležité:

| Číslo pole. | Název pole | Datový typ | Komentář |
|---------------|----------------|---------------|-------------|  
| 480 | **Dimension Set ID** | Integer | Odkazuje na pole 1 v tabulce 480. |

### Tabulka 83, Řádky deníku zboží
Kromě dalších polí dimenzí v tabulce jsou tato pole důležitá.

| Číslo pole. | Název pole | Datový typ | Komentář |
|---------------|----------------|---------------|-------------|  
| 480 | **Dimension Set ID** | Integer | Odkazuje na pole 1 v tabulce 480. |
| 481 | **New Dimension Set ID** | Integer | Odkazuje na pole 1 v tabulce 480. |

### Table 349, Dimension Value
Kromě dalších polí dimenzí v tabulce jsou tato pole důležitá.

| Číslo pole. | Název pole | Datový typ | Komentář |
|---------------|----------------|---------------|-------------|  
| 12 | **Dimension Value ID** | Integer | AutoIncrement. Používá se pro odkaz v tabulce 480 a 481. |

### Tabulky, které obsahují pole ID sady dimenzí
The **Dimension Set ID** field (480) exists in the following tables. U tabulek, které ukládají zaúčtovaná data, pole poskytuje pouze neupravitelné zobrazení dimenzí, které je označeno jako přechod k podrobnostem. U tabulek, které ukládají pracovní doklady, je pole upravitelné. Tabulky vyrovnávací paměti, které se používají interně, nepotřebují upravitelné nebo needitovatelné možnosti.

Pole 480 nelze upravovat v následujících tabulkách.

| Číslo tabulky | Název tabulky |
|---------------|----------------|  
| 17 | **G/L Entry** |
| 21 | **Cust. Ledger Entry** |
| 25 | **Vendor Ledger Entry** |
| 32 | **Item Ledger Entry** |
| 110 | **Sales Shipment Header** |
| 111 | **Sales Shipment Line** |
| 112 | **Sales Invoice Header** |
| 113 | **Sales Invoice Line** |
| 114 | **Sales Cr.Memo Header** |
| 115 | **Sales Cr.Memo Line** |
| 120 | **Nákupní  Rcpt. Header** |
| 121 | **Nákupní  Rcpt. Line** |
| 122 | **Nákupní  Zásoby Header** |
| 123 | **Nákupní  Zásoby Line** |
| 124 | **Nákupní  zál.  Memo Hdr.** |
| 125 | **Nákupní  zál.  Memo Line** |
| 169 | **Job Ledger Entry** |
| 203 | **Res. Ledger Entry** |
| 271 | **Bank Account Ledger Entry** |
| 281 | **Phys. Inventory Ledger Entry** |
| 297 | **Issued Reminder Header** |
| 304 | **Issued Fin. Charge Memo Header** |
| 5107 | **Sales Header Archive** |
| 5108 | **Sales Line Archive** |
| 5109 | **Purchase Header Archive** |
| 5110 | **Purchase Line Archive** |
| 5601 | **FA Ledger Entry** |
| 5625 | **Maintenance Ledger Entry** |
| 5629 | **Ins. Coverage Ledger Entry** |
| 5744 | **Transfer Shipment Header** |
| 5745 | **Transfer Shipment Line** |
| 5746 | **Transfer Receipt Header** |
| 5747 | **Transfer Receipt Line** |
| 5802 | **Value Entry** |
| 5832 | **Capacity Ledger Entry** |
| 5907 | **Service Ledger Entry** |
| 5908 | **Service Header** |
| 5933 | **Service Order Posting Buffer** |
| 5970 | **Filed Service Contract Header** |
| 5990 | **Service Shipment Header** |
| 5991 | **Service Shipment Line** |
| 5992 | **Service Invoice Header** |
| 5993 | **Service Invoice Line** |
| 5994 | **Service Cr. Memo Header** |
| 5995 | **Service Cr. Memo Line** |
| 6650 | **Return Shipment Header** |
| 6651 | **Return Shipment Line** |
| 6660 | **Return Receipt Header** |
| 6661 | **Return Receipt Line** |

Pole 480 je editovatelné v následujících tabulkách.

| Číslo tabulky | Název tabulky |
|---------------|----------------|  
| 36 | **Sales Header** |
| 37 | **Sales Line** |
| 38 | **Purchase Header** |
| 39 | **Purchase Line** |
| 81 | **Obecná  Journal Line** |
| 83 | **Item Journal Line** |
| 89 | **BOM Journal Line** |
| 96 | **G/L Budget Entry** |
| 207 | **Res. Journal Line** |
| 210 | **Job Journal Line** |
| 221 | **Obecná  Jnl. Allocation** |
| 246 | **Requisition Line** |
| 295 | **Reminder Header** |
| 302 | **Finance Charge Memo Header** |
| 5405 | **Production Order** |
| 5406 | **Výr. Order Line** |
| 5407 | **Výr. Order Component** |
| 5615 | **FA Allocation** |
| 5621 | **FA Journal Line** |
| 5635 | **Insurance Journal Line** |
| 5740 | **Transfer Header** |
| 5741 | **Transfer Line** |
| 5900 | **Service Header** |
| 5901 | **Service Item Line** |
| 5902 | **Service Line** |
| 5965 | **Service Contract Header** |
| 5997 | **Standard Service Line** |
| 7134 | **Item Budget Entry** |
| 99000829 | **Planning Component** |

Pole 480 existuje v následujících tabulkách vyrovnávací paměti.

| Číslo tabulky | Název tabulky |
|---------------|----------------|  
| 49 | **Invoice Post. Buffer** |
| 212 | **Job Posting Buffer** |
| 372 | **Payment Buffer** |
| 382 | **CV Ledger Entry Buffer** |
| 461 | **Prepayment Inv. Line Buffer** |
| 5637 | **FA G/L Posting Buffer** |
| 7136 | **Item Budget Buffer** |

## Viz také

[Dimension Set Entries Overview](design-details-dimension-set-entries-overview.md)  
[Design Details: Searching for Dimension Combinations](design-details-searching-for-dimension-combinations.md)
