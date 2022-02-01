---
title: "Handling Missing Option Values"
description: Learn how to prevent full synchronization from failing because the options differ in mapped fields. This processes require the help of a developer.
author: bholtorf

ms.author: bholtorf
ms.custom: na
ms.reviewer: na
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.date: 06/14/2021
---

# Zpracování chybějících hodnot možností
[!INCLUDE[prod_short](includes/cc_data_platform_banner.md)]

This topic is intended for a technical audience. The processes it describes require the help of a developer.

[!INCLUDE[prod_short](includes/cds_long_md.md)] contains three option set fields that contain values that you can map to [!INCLUDE[prod_short](includes/prod_short.md)] fields of the Option type for automated synchronization. During synchronization, non-mapped options are ignored and the missing options are appended to the related [!INCLUDE[prod_short](includes/prod_short.md)] table and added to the **Dataverse Option Mapping** system table to handle manually later. Například přidáním chybějících možností v obou produktech a aktualizací mapování.

The **Integration Table Mapping** page contains three fields that contain one or more mapped option values. After a full synchronization, the **Dataverse Option Mapping** page contains the non-mapped options in the three fields.

| Záznam | Hodnota možnosti | Titulek hodnoty možnosti |
|----------------------------|--------------|----------------------|
| Platební podmínky: NET30 | 1 | Netto 30 |
| Platební podmínky: 2%10NET30 | 2 | 2% 10; Netto 30 |
| Platební podmínky: NET45 | 3 | Netto 45 |
| Payment Terms: NET60 | 4 | Netto 60 |
| Způsob dodávky: FOB | 1 | FOB |
| Způsoby dodávky: BEZPOPLATKU | 2 | Bez poplatku |
| Přepravce: VZDUCEHM | 1 | VZDUCHEM |
| Přepravce: DHL | 2 | DHL |
| Přepravce: FEDEX | 3 | FedEx |
| Přepravce: UPS | 4 | UPS |
| Přepravce: POŠTA | 5 | Poštovní zásilky |
| Přepravce: FULLLOAD | 6 | Plně naložen |
| Přepravce: BUDEVOLAT | 7 | Bude telefonovat |

The content of the **Dataverse Option Mapping** page is based on enum values in the **CRM Account** table. In [!INCLUDE[prod_short](includes/cds_long_md.md)], the following fields on the account table are mapped to fields on the customer and vendor records:

- **Address 1: Freight Terms** of data type Enum, where values are defined as follow:

```
enum 5335 "CDS Shipment Method Code"
{
    Extensible = true;
    value(0; " ") { Caption = ' '; }
    value(1; "FOB") { Caption = 'FOB'; }
    value(2; "NoCharge") { Caption = 'No Charge'; }
}
```

- **Address 1: Shipping Method** of data type Enum, where values are defined as follows:

```
enum 5336 "CDS Shipping Agent Code"
{
    Extensible = true;
    value(0; " ") { Caption = ' '; }
    value(1; "Airborne") { Caption = 'Airborne'; }
    value(2; "DHL") { Caption = 'DHL'; }
    value(3; "FedEx") { Caption = 'FedEx'; }
    value(4; "UPS") { Caption = 'UPS'; }
    value(5; "PostalMail") { Caption = 'Postal Mail'; }
    value(6; "FullLoad") { Caption = 'Full Load'; }
    value(7; "WillCall") { Caption = 'Will Call'; }
}
```

- **Payment Terms** of data type Enum, where values are defined as follows:

```
enum 5334 "CDS Payment Terms Code"
{
    Extensible = true;
    value(0; " ") { Caption = ' '; }
    value(1; "Net30") { Caption = 'Net 30'; }
    value(2; "2%10Net30") { Caption = '2% 10; Net 30'; }
    value(3; "Net45") { Caption = 'Net 45'; }
    value(4; "Net60") { Caption = 'Net 60'; }
}
```

All of the [!INCLUDE[prod_short](includes/prod_short.md)] enums above are mapped to option sets in [!INCLUDE[prod_short](includes/cds_long_md.md)].

### Extending Option Sets in [!INCLUDE[prod_short](includes/prod_short.md)]
1. Vytvořte nové AL rozšíření.

2. Přidejte rozšíření Enum pro možnosti, které chcete rozšířit. Ujistěte se, že používáte stejnou hodnotu.

```
enumextension 50100 "CDS Payment Terms Code Extension" extends "CDS Payment Terms Code"
{
    value(779800001; "Cash Payment") { Caption = 'Cash Payment'; }
    value(779800002; "Transfer") { Caption = 'Transfer'; }
}
```

> [!IMPORTANT]  
> You must use the same option ID values from [!INCLUDE[prod_short](includes/cds_long_md.md)] when you extend the [!INCLUDE[prod_short](includes/prod_short.md)] enum. V opačném případě se synchronizace nezdaří.

> [!IMPORTANT]  
> Do not use the ","  character in the enum values and captions. This is currently not supported by the [!INCLUDE[prod_short](includes/prod_short.md)] runtime.

> [!NOTE]
> The first ten characters of the new option value names and captions must be unique. Například dvě možnosti s názvem "Převod 20 pracovních dnů" a "Převod 20 kalendářních dnů" způsobí chybu, protože obě mají stejné první 10 znaků, "Transfer 2". Pojmenujte je například "TRF20 WD" a "TRF20 CD."

### Update [!INCLUDE[prod_short](includes/cds_long_md.md)] Option Mapping
Now you can recreate the mapping between [!INCLUDE[prod_short](includes/cds_long_md.md)] options and [!INCLUDE[prod_short](includes/prod_short.md)] records.

On the **Integration Table Mapping** page, choose the line for the **Payment Terms** map, and then choose the **Synchronize Modified Records** action. The **Dataverse Option Mapping** page is updated with the additional records below.

| Záznam | Hodnota možnosti | Titulek hodnoty možnosti |
|--------------------------------|----------------|----------------------|
| Platební podmínky: NET30 | 1 | Netto 30 |
| Platební podmínky: 2%10NET30 | 2 | 2% 10; Netto 30 |
| Platební podmínky: NET45 | 3 | Netto 45 |
| Payment Terms: NET60 | 4 | Netto 60 |
| **Payment Terms: CASH PAYME** | **779800001** | **Cash Payment** |
| **Payment Terms: TRANSFER** | **779800002** | **Transfer** |

The **Payment Terms** table in [!INCLUDE[prod_short](includes/prod_short.md)] will then have new records for the [!INCLUDE[prod_short](includes/cds_long_md.md)] options. V následující tabulce jsou nové možnosti tučným písmem . Řádky kurzívou představují všechny možnosti, které lze nyní synchronizovat. Zbývající řádky představují možnosti, nejsou používány a budou ignorovány během synchronizace. You can remove them or extend Dataverse options with the same names.)

| Kód | Výpočet splatnosti | Výpočet skonto data | Sleva % | Výp.  Platba skonta v dobropisu | Popis |
|------------|----------------------|---------------------------|------------|-------------------------------|-------------------|
| 10 DNY | 10D |                           | 0. | NEPRAVDA | Čistých 10 dní |
| 14 DNY | 14D |                           | 0. | NEPRAVDA | Čistých 14 dní |
| 15 DNY | 15D |                           | 0. | NEPRAVDA | Čistých 15 dní |
| 1M(8D) | 1M | 8D | 2. | NEPRAVDA | 1 Měsíc/2% 8 dnů |
| 2 DNY | 2D |                           | 0. | NEPRAVDA | Čisté 2 dny |
| *2%10NET30* |                      |                           | 0. | NEPRAVDA |                   |
| 21 DNY | 21D |                           | 0. | NEPRAVDA | Čistý 21 dní |
| 30 DNY | 30D |                           | 0. | NEPRAVDA | Čistých 30 dní |
| 60 DNY | 60D |                           | 0. | NEPRAVDA | Čistých 60 dní |
| 7 DNU | 7D |                           | 0. | NEPRAVDA | Čistých 7 dní |
| ***CASH PAYME*** |                      |                           | 0. | NEPRAVDA |                   |
| CM | CM |                           | 0. | NEPRAVDA | Aktuální měsíc |
| COD | 0D |                           | 0. | NEPRAVDA | Dobírka |
| *NET30* |                      |                           | 0. | NEPRAVDA |                   |
| *NET45* |                      |                           | 0. | NEPRAVDA |                   |
| *NET60* |                      |                           | 0. | NEPRAVDA |                   |
| ***TRANSFER*** |                      |                           | 0. | NEPRAVDA |                   |

## Viz také
[Mapping the Tables and Fields to Synchronize](admin-how-to-modify-table-mappings-for-synchronization.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]