---
title: "Reklamace"
author: Autocont
ms.custom: na
ms.date: 02/26/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: dynamics-nav-2018
ms.translationtype: Human Translation
ms.sourcegitcommit: 
ms.openlocfilehash: 
ms.contentlocale: cs-cz
ms.lasthandoff: 02/26/2018

---

# <a name="ac-pp-complaints-management.md"></a>Reklamace

Modul reklamace slouží k evidenci reklamací zboží prodaného i nakoupeného. Také umožňuje evidovat reklamace interní. Umožňuje sledovat proces řešení reklamace od založení reklamace, evidenci různých stavů reklamací, vytváření navazujících dokladů, podporuje účtování interních přesunů reklamovaného zboží, poskytuje základní tisky k reklamacím a je provázán na více úrovních se sledováním pomocí workflow.

## Instalace

**Objekty modulu**

Objekty modulu Reklamace jsou označeny verzí **CM**. Žádný další modul není podmínkou, ale je vhodné využít také modul workflow. Seznam konkrétních objektů modulu je uveden v dokumentaci k aktuálnímu buildu modulů.

## Nastavení

Číslování reklamací se nastaví v Oblasti/proPRODUKTIVITU/Reklamace/Nastavení reklamací. Na záložce číslování se nastaví číselné řady reklamací nákupních, prodejních a interních.

Číselník Důvody reklamace (menu Oblasti/proPRODUKTIVITU/Reklamace/Důvody reklamace) je seznam důvodů reklamace. Pro každý důvod reklamace se nastaví kód, popis, lokace, výchozí stav workflow řádku reklamace, výchozí stav řádku vyřešení reklamace.

Číselník Příčiny reklamace (menu Oblasti/proPRODUKTIVITU/Reklamace/Příčiny reklamace) umožňuje další členění reklamací. Nastaví se kód a popis příčiny. 
Způsoby vyřízení reklamace (menu Oblasti/proPRODUKTIVITU/Reklamace/Způsoby vyřízení reklamace) je číselník obsahující kód, popis, číselnou řadu, název šablony deníku zboží, název listu deníku zboží, šablonu skladového pohybu.
* číselná řada – možnost přednastavit výchozí číslování dokladů jednotlivých vyřízení reklamace. Přednabídne se při funkci Vytovřit doklad (viz dále). 
* název šablony deníku zboží, název listu deníku zboží a šablona skladového pohybu – lze přednastavit v případě řešení reklamace s využitím deníku zboží.

Nastavení workflow – v menu Oblasti/proPRODUKTIVITU/WorkFlow/Nastavení workflow jsou pole pro šablony workflow modulu reklamace. Je možné nastavit workflow pro reklamace, pro řádky reklamace a pro řádky vyřízení reklamace. Bližší popis nastavování workflow je obsažen v popisu modulu workflow.

## Použití

### Formuláře

**Dispečer řádků reklamace**

Pro pohodlnější přístup k evidovaným reklamacím je vytvořen Dispečer řádků reklamace, v jehož hlavičce lze řádky rychle filtrovat a přes tlačítka lze zobrazit příslušný doklad reklamace a měnit stavy workflow řádků reklamací.
 
**Formulář Reklamace**

Hlavička reklamace obsahuje typ reklamace (nákup/prodej/interní), číslo reklamace, identifikační údaje dodavatele či zákazníka, napočítávaná pole navázaných dokladů a stav workflow. 
Řádky obsahují informace o reklamovaném zboží a související informace.
 
Popis některých polí z formuláře reklamace: 
* Typ – nákupní reklamace nebo prodejní nebo interní. 
* Číslo – číslování reklamací. 
* Číslo původu – identifikace zákazníka nebo dodavatele. 
* Ve vyšedlých polích je v průběhu řešení reklamace zobrazen počet navázaných dokladů. Rozkliknutím těchto polí se lze do těchto dokladů dostat.

Z řádků: 
* Číslo původního dokladu – např. číslo účtované příjemky na straně prodeje nebo účtované příjemky vratky na straně nákupu. 
* Reklamované množství, Vyřízené množství, Množství k vyřízení, Množství na řádcích vyřízení – informace o zpracovaném množství.

### Založení reklamace

#### Reklamace typu nákup

Nákupní reklamace se použijí pro evidenci nakoupeného reklamovaného zboží. Vytvářejí z řádku nákupních objednávek pomocí tlačítka Funkce/Vytvořit reklamaci. Tím se řádek přichystá pro vznik reklamace při účtování příjmu.

Uživatel vybere jeden z důvodů reklamace a nastaví reklamované množství. V případě použití šarží zde také vybere šarži.

V řádcích nákupní objednávky lze zobrazit příznak „Vytvořit reklamaci“ a „Kód důvodu reklamace“. Pokud je reklamováno částečné množství z daného řádku, řádek je funkcí rozdělen na dva – reklamované a nereklamnované množství.
V případech, kdy zákazník reklamuje koupené zboží a reklamace tohoto zboží bude postoupena jeho dodavateli, umožňuje modul vytvořit nákupní reklamaci přímo z prodejní reklamace. Na prodejní reklamaci pod tlačítkem Funkce je volba Vytvořit nákupní reklamaci.

#### Reklamace typu prodej

Reklamace typu prodej eviduje situaci, kdy zákazník reklamuje jemu prodané zboží. Zpracování prodejní reklamace začíná na objednávce prodejní vratky – tzn tam, kde zboží vstupuje do skladu. Nejprve se připraví řádek pomocí tlačítka Řádek/Vytvořit reklamaci.

Z takto ošetřeného řádku pak vznikne reklamace při účtování příjmu vratky.

#### Reklamace typu interní

Zakládá se z objednávky transferu opět přes tlačítko Řádek/Vytvořit reklamaci

#### Zpracování reklamace

Pokud je řádek původního dokladu nastaven pro reklamaci (viz předchozí text), při účtování příjmu vznikne reklamace, na které se pokračuje vytvořením řádku vyřízení reklamace, tzn. tlačítko Funkce/Vytvořit řádek vyřízení.
Přitom uživatel zadá množství k vyřízení a kód způsobu vyřízení.

Vytvořený řádek vyřízení se z reklamace otevře přes tlačítko Řádek/Řádky vyřízení reklamace. V okně Řádky vyřízení reklamace lze na záložce Akce změnit stav workflow vyřízení a Vytvořit doklad vyřízení.

Vytvoření dokladu vyřízení obvykle znamená vytvořit např. objednávku nákupní vratky nebo prodejní objednávku nebo řádek deníku zboží.

Řádek reklamace je vyřízen zaúčtováním dokladu, např. zaúčtování objednávky nákupní vratky.

Sledování a řízení postupu reklamace může být podpořeno přepínáním stavů workflow se všemi jeho možnostmi, jako např. informování uživatelů mailem, automatické nastavování polí či řízením přístupu vybraným uživatelům k jednotlivým stavům workflow. (Bližší informace k nastavení a použití workflow je v příslušném popisu modulu workflow.)

### Uzavření reklamace

Po zpracování reklamace se reklamace uzavírá, tj. na formuláři reklamace na záložce Akce funkce Uzavřít reklamaci. Při uzavírání se kontroluje, zda zůstatek k vyřízení v řádcích reklamace je nulový. Uzavřením se na reklamaci nastaví Stav = Uzavřeno a vyplní se pole Uzavřeno dne.
 
### Tisky

V modulu jsou připraveny tisky dvou dokladů, reklamačního protokolu a vyřízení reklamace. Tisky jsou přístupné z formuláře reklamace.

## <a name="see-also"></a>Viz také  
[AC Productivity pack](ac-pp-productivity-pack.md)  