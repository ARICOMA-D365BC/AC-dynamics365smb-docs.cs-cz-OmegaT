---
    title: Change the Annual Amount on Service Contracts or Contract Quotes
    description: You can change the amount that will be invoiced annually on service contracts or service contract quotes.
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2021
    ms.author: bholtorf

---
# <g1>Změna roční částky na servisních smlouvách a nabídkách smluv.</g1>
Chcete-li opravit částku, která bude každoročně fakturována, můžete změnit roční částku servisní smlouvy nebo nabídky smlouvy.

## Pro změnu roční částky servisní smlouvy nebo nabídky smlouvy

1. Vyberte  <x1 />Žárovka, která otevře funkci Řekněte mi <x2 /> Řekněte mi, co chcete udělat <x3 />, zadejte **Servisní smlouvy** nebo **Nabídky servisních smlouv </ g5 > a poté vyberte související odkaz.
2. Vyberte smlouvu nebo nabídku smlouvy.
3. Zvolte akci **Otevřít smlouvu** a otevřete smlouvu nebo nabídku smlouvy pro úpravy.
4. Zaškrtněte políčko **Povolit nevyrovnané částky**, pokud chcete změnit roční částku a ručně rozdělit roční částku na řádcích smlouvy. V opačném případě zrušte zaškrtnutí políčka, abyste po změně roční částky automaticky rozdělili roční rozdíl částek na řádky smlouvy.
5. Změňte obsah pole **Roční částka**. Nemůžete podepsat, to znamená převést na servisní smlouvu, pokud pracujete na nabídce smlouvy, nebo uzamknout servisní smlouvu, která má zápornou roční částku. Pokud nastavíte roční částku na nulu, musí být obsah pole **Období fakturace** **Žádné** při podpisu nebo uzamčení servisní smlouvy
6. V závislosti na tom, zda je zaškrtnuto políčko **Povolit nevyrovnané částky**, spusťte manuální nebo automatické rozdělení ročního rozdílu částky. Řádky smlouvy budou aktualizovány, takže hodnota pole**Vypočítaná roční částka** se rovná nové roční částce.

## Rozdělení rozdílů mezi novými a vypočítanými ročními částkami
Pokud změníte roční částku servisní smlouvy nebo nabídky smlouvy, možná budete chtít rozdělit rozdíl mezi její novou a vypočítanou roční částkou na řádcích smlouvy. Existují tři způsoby, jak rozdělit částky:

* Rovnoměrné rozdělení
* Rozdělení na základě částek řádku
* Rozdělení založené na zisku

### Rovnoměrné rozdělení
Pokud změníte roční částku servisní smlouvy nebo nabídky smlouvy, možná budete chtít rozdělit rozdíl mezi její novou a vypočítanou roční částkou na řádcích smlouvy. Rovnoměrné rozdělení je jednou z metod automatické distribuce, která vám může pomoci rovnoměrně rozdělit rozdíl mezi novými a vypočítanými ročními částkami mezi řádkovými částkami na řádcích smlouvy. Následující seznam kroků postupu rozdělení popisuje hlavní myšlenku této metody:

1. Rozdíl mezi novou **Roční částkou** a hodnotami pole**Vypočítaná  roční částka** se vydělí počtem řádků smlouvy v servisní smlouvě nebo v nabídce smlouvy.
2. Hodnota pole **Částka řádku** se aktualizuje přidáním výsledku předchozí operace.
3. Obsah polí **Částka řádkové slevy**, **% řádkové slevy**a **Zisk** se aktualizuje s ohledem na novou hodnotu v poli **Částka na řádku** následujícím způsobem:
   * Částka řádkové slevy = Hodnota řádku - Částka řádku.
   * % řádkové slevy = Částka řádkové slevy / Hodnota řádku * 100.
   * Zisk = Částka na řádku - Náklady na řádku.

Kroky se opakují pro každý řádek smlouvy.

#### Příklad
V servisní smlouvě, která obsahuje tři řádky smlouvy s takovými informacemi, není zaškrtnuto políčko **Povolit nerovnané částky**.

| Zboží | Náklady na řádku | Hodnota na řádku | % řádkové slevy | Částka řádkové slevy | Částka na řádku | Zisk |
|----------|---------------|----------------|---------------------|--------------------------|-----------------|------------|  
| Zboží 1 | 30.00 | 40,00 | 0.00 | 0.00 | 40,00 | 10,00 |
| Zboží 2 | 40,00 | 50.00 | 10,00 | 5.00 | 45.00 | 5.00 |
| Zboží 3 | 50.00 | 70.00 | 10,00 | 7.00 | 63.00 | 13.00 |

Hodnota pole **Roční částka** se rovná obsahu pole**Vypočítaná roční částka**, které je vždy nastaveno na součet částek řádků. V tomto případě se rovná následujícímu: 40 + 45 + 63 = 148.

Pokud změníte **roční částku** na 139, vypočítá se částka, která by měla být přidána ke každé hodnotě pole **Částka na řádku**. Tato částka se vypočítá odečtením **Vypočítané roční částky** z nové hodnoty pole **Roční částka** a vydělením výsledku počtem řádků smlouvy ve servisní smlouvě. V tomto případě se bude rovnat následujícímu: (139 - 148) / 3 = -3. Poté se ke každé hodnotě pole **Částka na řádku**,**% řádkové slevy** a **Částka řádkové slevy**  přidá poslední vypočítaný údaj, a hodnoty polí **Zisk** se aktualizují pomocí vzorců v postupu popsaném výše.

Nakonec budou řádky smlouvy obsahovat tyto údaje.

| Zboží | Náklady na řádku | Hodnota na řádku | % řádkové slevy | Částka řádkové slevy | Částka na řádku | Zisk |
|----------|---------------|----------------|---------------------|--------------------------|-----------------|------------|  
| Zboží 1 | 30.00 | 40,00 | 7.50 | 3.00 | 37.00 | 7.00 |
| Zboží 2 | 40,00 | 50.00 | 16.00 | 8,00 | 42.00 | 2,00 |
| Zboží 3 | 50.00 | 70.00 | 14.29 | 10,00 | 60.00 | 10,00 |

### Rozdělení na základě Částky na řádku
Pokud změníte roční částku servisní smlouvy nebo nabídky smlouvy, možná budete chtít rozdělit rozdíl mezi její novou a vypočítanou roční částkou na řádcích smlouvy. Rozdělení založené na částce na řádku je automatická metoda, která vám může pomoci rozložit rozdíl mezi novými a vypočítanými ročními částkami mezi částky řádků na řádcích smlouvy. Toto rozdělení bude provedeno úměrně jejich podílům na častkách řádku ve vypočítané roční částce. Následující seznam kroků postupu rozdělení pro každý řádek smlouvy popisuje hlavní myšlenku této metody:

1. Procentní podíl částky řádku se počítá takto: obsah pole **Částka na řádku** se vydělí hodnotami polí **Vypočítaná. roční částka** na všech řádcích smlouvy.
2. Hodnota pole **Částka na řádku** se aktualizuje přidáním rozdílu mezi novou a vypočítanou roční částkou, který se vynásobí procentním příspěvkem částky řádku.
3. Obsah polí **Částka řádkové slevy**, **% řádkové slevy**a **Zisk** se aktualizuje s ohledem na novou hodnotu v poli **>Částka řádkové slevy** následujícím způsobem:

   * Částka řádkové slevy = Hodnota řádku - Částka řádku.
   * % řádkové slevy = Částka řádkové slevy / Hodnota řádku * 100.
   * Zisk = Částka na řádku - Náklady na řádku.

Kroky se opakují pro každý řádek smlouvy.

#### Příklad
V servisní smlouvě, která obsahuje tři řádky smlouvy s takovými informacemi, není zaškrtnuto políčko **Povolit nerovnané částky**.

| Zboží | Náklady na řádku | Hodnota na řádku | % řádkové slevy | Částka řádkové slevy | Částka na řádku | Zisk |
|----------|---------------|----------------|---------------------|--------------------------|-----------------|------------|  
| Zboží 1 | 15.00 | 17.00 | 3.00 | 0.51 | 25.00 | 1.49 |
| Zboží 2 | 20,00 | 23.00 | Žádné | 0.00 | 55.10 | 3.00 |
| Zboží 3 | 24.00 | 27.00 | 3.00 | 0.81 | 112.70 | 2.19 |

Hodnota pole **Roční částka** se rovná obsahu pole**Vypočítaná roční částka**, které je vždy nastaveno na součet částek řádků. V tomto případě se rovná následujícímu: 16,49 + 23,00 + 26,19 = 65,68.

Pokud změníte **Roční částku** na 60, vypočítají se procentní podíly na zisku pro každý řádek smlouvy:

* Zboží 1 - 5 / (5 + 5,1 +12,7) = 0,2193%
* Zboží 2 - 5,1 / (5 + 5,1 + 12,7) = 0,2237
* Zboží 3 - 12,7 / (5 + 5,1 + 12,7) = 0,557

Hodnota pole **Částka na řádku** se aktualizuje na každém řádku smlouvy pomocí následujícího vzorce: Částka na řádku = Částka na řádku + rozdíl mezi novou a vypočítanou roční částkou * Procentní podíl. Poté se hodnoty polí **Částka řádkové slevy**, **% řádková sleva**a **Zisk** aktualizují pomocí vzorců popsaných výše.

Nakonec budou řádky smlouvy obsahovat tyto údaje.

| Zboží | Náklady na řádku | Hodnota na řádku | % řádkové slevy | Částka řádkové slevy | Částka na řádku | Zisk |
|----------|---------------|----------------|---------------------|--------------------------|-----------------|------------|  
| Zboží 1 | 15.00 | 17.00 | 11.41 | 1.94 | 15.06 | 0.06 |
| Zboží 2 | 20,00 | 23.00 | 8.65 | 1.99 | 21.01 | 1.01 |
| Zboží 3 | 24.00 | 27.00 | 11.37 | 3.07 | 23.93 | -0.07 |

### Rozdělení založené na zisku
Pokud změníte roční částku servisní smlouvy nebo nabídky smlouvy, možná budete chtít rozdělit rozdíl mezi její novou a vypočítanou roční částkou na řádcích smlouvy. Rozdělení založené na zisku je jedna z  automatických metod, které vám mohou pomoci rozložit rozdíl mezi novými a vypočítanými ročními částkami mezi částky řádků na řádcích smlouvy. Toto rozdělení se provede úměrně jejich podílům na zisku na celkovém zisku ze smlouvy nebo z nabídky smlouvy. Následující seznam kroků postupu rozdělení pro každý řádek smlouvy popisuje hlavní myšlenku této metody:

1. Procentní podíl na zisku se vypočítá takto: obsah pole **Zisk** se vydělí součtem hodnot polí **Zisk** na všech řádcích smlouvy.
2. Hodnota pole **Částka na řádku** se aktualizuje přidáním rozdílu mezi novou a vypočítanou roční částkou, který se vynásobí procentním podílem částky řádku.
3. Obsah polí **Částka řádkové slevy**, <g2>% řádkové slevy</g2>a <g3>Zisk</g3> se aktualizuje s ohledem na novou hodnotu v poli <g4>Částka na řádku</g4> následujícím způsobem:

   * Částka řádkové slevy = Hodnota řádku - Částka řádku.
   * % řádkové slevy = Částka řádkové slevy / Hodnota řádku * 100.
   * Zisk = Částka na řádku - Náklady na řádku.

#### Příklad
V servisní smlouvě, která obsahuje tři řádky smlouvy s takovými informacemi, není zaškrtnuto políčko **Povolit nerovnané částky**.

| Zboží | Náklady na řádku | Hodnota na řádku | % řádkové slevy | Částka řádkové slevy | Částka na řádku | Zisk |
|----------|---------------|----------------|---------------------|--------------------------|-----------------|------------|  
| Zboží 1 | 20,00 | 25.00 | 0.00 | 0.00 | 25.00 | 5.00 |
| Zboží 2 | 50.00 | 58.00 | 5.00 | 2.90 | 55.10 | 5.10 |
| Zboží 3 | 100,00 | 115.00 | 2,00 | 2.30 | 112.70 | 12.70 |

Hodnota pole **Roční částka** se rovná obsahu pole**Vypočítaná roční částka**, které je vždy nastaveno na součet částek řádků. V tomto případě se rovná následujícímu: 25,00 + 55,10 + 112,70 = 192,80.

Pokud změníte **Roční částku** na 180, vypočítají se procentní podíly na zisku pro každý řádek smlouvy:

* Zboží 1 - 5 / (5 + 5,1 +1 2,7) = 0,2193%
* Zboží 2 - 5,1 / (5 + 5,1 + 12,7) = 0,2237
* Zboží 3 - 12,7 / (5 + 5,1 + 12,7) = 0,557

Hodnota pole **Částka na řádku** se aktualizuje na každém řádku smlouvy pomocí následujícího vzorce: Částka na řádku = Částka na řádku + rozdíl mezi novou a vypočítanou roční částkou * Procentní podíl. Poté se hodnoty polí **Částka řádkové slevy**, **% řádkové slevy**a **Zisk** aktualizují pomocí vzorců v 3. kroce vzorce popsaného výše.

Nakonec budou řádky smlouvy obsahovat tyto údaje.

| Zboží | Náklady na řádku | Hodnota na řádku | % řádkové slevy | Částka řádkové slevy | Částka na řádku | Zisk |
|----------|---------------|----------------|---------------------|--------------------------|-----------------|------------|  
| Zboží 1 | 20,00 | 25.00 | 11.24 | 2.81 | 22.19 | 2.19 |
| Zboží 2 | 50.00 | 58.00 | 9.93 | 5.76 | 52.24 | 2.24 |
| Zboží 3 | 100,00 | 115.00 | 8.20 | 9.43 | 105.57 | 5.57 |

## Viz také
[Vytváření servisní smlouvy a nabídky servisních smluv  ](service-how-to-create-service-contracts-and-service-contract-quotes.md)
[Nastavení Správy servisu](service-setup-service.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]