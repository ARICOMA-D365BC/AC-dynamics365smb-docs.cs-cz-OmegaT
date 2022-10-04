---
title: Work with recurring revenue
description: Learn about the available options to automate sending subscription invoices to your customers and register recurring revenue.
author: AndreiPanko


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: recurring, invoicing, subscription, billing
ms.search.form: 283
ms.reviewer: edupont
ms.date: 04/01/2021
ms.author: andreipa

---
# Práce s periodickými výnosy v [!INCLUDE[prod_short](includes/prod_short.md)]

Mnoho společností přechází od modelu obchodních výnosů, kdy výnosy plynou z jednorázového nákupu zákazníka, k modelu předplatného, kdy výnosy plynou periodicky výměnou za stálý přístup k dodávkám zboží nebo služeb.
[!INCLUDE[prod_short](includes/prod_short.md)] má následující možnosti automatizace zasílání faktur za předplatné zákazníkům a evidence periodických výnosů.

## Evidence výnosů pomocí periodického finančního denníku.

Periodický deník je finanční deník se specifickými poli pro správu transakcí, které často účtujete, s malými nebo žádnými změnami, jako je nájemné, předplatné, elektřina a teplo. Pomocí těchto polí pro periodické transakce můžete účtovat pevné i variabilní částky.
U periodického deníku je třeba položky, které budou zveřejněny pravidelně, psát pouze jednou. To znamená, že účty, dimenze a hodnoty dimenzí atd., které zadáte, zůstanou po zaúčtování v deníku. Pokud jsou nutné úpravy, můžete je provést s každým účtováním.

### Proč používat tuto možnost

Pomocí této možnosti definujete flexibilní fakturační období pomocí [Vzorců dat](ui-enter-date-ranges.md#use-date-formulas).

Při použití této možnosti však nelze tisknout a odesílat faktury ve výchozí verzi [!INCLUDE[prod_short](includes/prod_short.md)].

Pro další informace navštivte [Práce s periodickými deníky](ui-work-general-journals.md#work-with-recurring-journals).

## Tvorba více faktur na základě periodického deníku úloh

Periodický deník úloh je pokročilejší alternativou k finančnímu deníku. Definujete položky, zdroje a účty hlavní knihy, které se musí opakovat pro každou úlohu, a určíte frekvenci periody.

Po zaúčtování periodického deníku úloh můžete vytvořit více faktur pomocí úlohy **Vytvořit prodejní fakturu projektu**. Vytvořené faktury můžete zkontrolovat a zaúčtovat na stránce **Prodejní faktury**.

### Proč používat tuto možnost

S touto možností budete postupovat podle standardního postupu fakturace se všemi jeho výhodami, včetně standardních a zákaznických rozvržení pro předvolby komunikace. Můžete také definovat ceny pro každou úlohu jednotlivě.

Pro každého nového zákazníka je však nutné vytvořit novou úlohu a přidat řádky do periodického deníku.

Další informace naleznete v tématu [Vytvoření řádků deníku projektu](projects-how-record-job-usage.md#to-create-job-journal-lines-manually) a [Vytvoření více prodejních faktur projektu](projects-how-invoice-jobs.md#to-create-multiple-job-sales-invoices).

## Vytvoření více faktur na základě periodických řádků prodeje

Pokud často potřebujete vytvořit prodejní a nákupní řádky s podobnými informacemi, můžete nastavit periodické řádky prodeje, které pak můžete vložit do periodických prodejních a nákupních dokladů, například pro periodické objednávky doplňování. Pomocí dávkové úlohy **Vytvořit periodické prodejní faktury** vytvoříte prodejní faktury podle periodických prodejních řádků, které jsou přiřazeny zákazníkům, a s daty zaúčtování v rámci dat platných od a platných do, která jste zadali u periodických prodejních řádků.

### Proč používat tuto možnost

Pomocí této možnosti můžete přiřadit stejné periodické řádky více zákazníkům. Můžete definovat dobu platnosti pro periodické řádky prodeje pro konkrétního odběratele. Můžete přiřadit více periodických řádků stejnému odběrateli a všechny budou zahrnuty do faktury.

Neexistuje však žádný způsob, jak nastavit pevné ceny položek, protože [! INCLUDE[prod_short](includes/prod_short.md)] použije skutečné ceny a slevu platnou k datu dokladu a pokusí se najít nejlepší kombinaci, která dává nejnižší cenu.

Pro více informací navštivte sekci <g2>Vytvoření periodických prodejních a nákupních řádků</g2>.

## Periodické faktury se servisní smlouvou

Servisní smlouva obsahuje dohody o poskytování služeb mezi vašimi zákazníky a vaší společností. Servisní smlouva zahrnuje dohody o úrovni služeb a položky služeb, které servisujete jako součást smlouvy.

Můžete definovat počáteční datum smlouvy, fakturační období, zda je smlouva předplacená nebo ne, specifikace aktualizace ceny, pokud plánujete změnit ceny, když je smlouva aktivní. Můžete použít jak předměty servisu, tak položky v řádcích servisní smlouvy.
Můžete vytvořit šablony smluv, které definují, jak vytvořit určité typy smluv.

### Proč používat tuto možnost

Pomocí této možnosti využijete část funkcí pokročilé správy služeb, která se neomezuje na vystavování periodických faktur, ale podporuje opravárenské a terénní servisní operace.

Tato možnost však vyžaduje licenci Premium. Nastavení správy služeb a její údržba nemusí v jednodušších scénářích předplatného poskytovat velké výhody.

Další informace naleznete v části [Práce se servisními smlouvami a nabídkami servisních smluv](service-how-to-create-service-contracts-and-service-contract-quotes.md) a [Faktura několika servisních smluv](service-how-create-invoices.md#to-invoice-several-service-contracts).

## Související funkce
Existuje několik souvisejících funkcí v [!INCLUDE[prod_short](includes/prod_short.md)].

### Hromadné prodejní objednávky

Hromadní prodejní objednávka představuje rámec pro dlouhodobou dohodu mezi vaší společností a vaším zákazníkem.
Hromadní objednávka se obvykle provádí, když se zákazník zavázal k nákupu velkého množství, které má být dodáno v několika menších zásilkách po určitou dobu. Časté hromadné objednávky často pokrývají pouze jednu položku s předem stanovenými termíny dodání. Hlavním důvodem pro použití hromadní objednávky spíše než prodejní objednávky je to, že množství zadaná v hromadní objednávce nemají vliv na dostupnost položky, ale lze je použít pro účely plánování.

#### Proč používat tuto možnost

S touto možností použijete předpokládanou poptávku, takže informace jsou brány v úvahu během běžných plánovacích rutin. Další informace naleznete v části [Prognózy poptávky a hromadní objednávky](design-details-central-concepts-of-the-planning-system.md#demand-forecasts-and-blanket-orders).

Výchozí verze však nenabízí přednastavenou možnost hromadného zpracování více hromadních objednávek.

Další informace naleznete v části [Práce s hromadními prodejními objednávkami](sales-how-to-create-blanket-sales-orders.md).

### Periodické objednávky (Norsko)

Periodické objednávky můžete použít k vytvoření šablon hromadních objednávek, aby bylo možné vytvořit prodejní objednávky na základě definovaných časových intervalů. Pokud například dodáváte stejnou prodejní objednávku každé dva týdny, můžete použít hromadní prodejní objednávku a vytvořit periodické objednávky.
You can use recurring groups to define a range of parameters that show how you make the orders. These groups are assigned to blanket orders that have to be created regularly. To create the recurring orders, you will have to periodically run the create recurring orders process.

#### Proč používat tuto možnost

With this option, you can choose between fixed and "best" prices.

However, this is only available in Norway. Validity period can be defined on the recurring group level.

For more information, see [Recurring Orders](LocalFunctionality/Norway/recurring-orders.md).

### Recurring revenue and subscription billing by other providers

At [AppSource.microsoft.com](https://appsource.microsoft.com/), you can get extensions for Business Central. Some extensions are provided by Microsoft, and other extensions are provided by other companies. The list of the extensions by other companies grows each month. So keep an eye out for [AppSource.microsoft.com](https://go.microsoft.com/fwlink/?linkid=2081646) and get apps to help you in your work in Business Central.

## Viz také

[Date Formulas](ui-enter-date-ranges.md#use-date-formulas)  
[Work with Recurring Journals](ui-work-general-journals.md#work-with-recurring-journals)  
[Create job journal lines](projects-how-record-job-usage.md#to-create-job-journal-lines-manually)  
[Create multiple job sales invoices](projects-how-invoice-jobs.md#to-create-multiple-job-sales-invoices)  
[Create Recurring Sales and Purchase Lines](sales-how-work-standard-lines.md)  
[Work with Service Contracts and Service Contract Quotes](service-how-to-create-service-contracts-and-service-contract-quotes.md)  
[Invoice several service contracts](service-how-create-invoices.md#to-invoice-several-service-contracts)  
[Demand Forecasts and Blanket Orders](design-details-central-concepts-of-the-planning-system.md#demand-forecasts-and-blanket-orders)  
[Work with Blanket Sales Orders](sales-how-to-create-blanket-sales-orders.md)  
[Recurring Orders (Norway)](LocalFunctionality/Norway/recurring-orders.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]