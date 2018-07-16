---
title: "Doprava základ"
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

# <a name="ac-pp-transport-basic.md"></a>Doprava - základ

Modul Doprava – základ řeší problematiku evidence vozidel, plánování údržby vozidel. Evidence řidičů, evidence knih jízd a evidenci spotřeby pohonných hmot (včetně možnosti importu souborů o nákupech na palivové karty, např. CCS). 
Tento modul je nutnou podmínkou pro používání rozšiřujícího modulu Doprava – plánování.

## Instalace

**Objekty modulu**

Objekty modulu Doprava – základ jsou označeny verzí DO7.10 resp. pouze DO.

**Další součásti instalace**

Modul nevyžaduje pro instalaci žádné další součásti.

## Nastavení

### Nastavení dopravy

**Obecné**

Základní nastavení se provede v Oblasti/proPRODUKTIVITU/Doprava – Nastavení dopravy.
Na záložce **Obecné** zadáte volby:

**Nutné ID původu požadavku** – viz popis modul Doprava – plánování

**Nutné ID PSČ požadavků** – viz popis modul Doprava plánování

Na záložce **Číslování** musíte zadat číselné řady:
**Čísla vozidel** – číselná řada pro karty vozidel,
**Čísla řidičů** – číselná řada pro karty řidičů.

Ostatní pole jsou připravena pro modul Doprava – plánování a není nutné je pro potřeby základního modulu vyplňovat.

**Typ vozidel**

Nastavení typů vozidel slouží k členění automobilového parku dle vašich potřeb a provede se v Oblasti/proPRODUKTIVITU/Doprava – Typy vozidel.
Pro zadání Typu vozidla jsou k dispozici pole Kód a Popis.

**Typy provozu**

Typy provozu je možné použít ke stanovování různých nákladů a normovaných spotřeb u vozidel v závislosti na typu vozidla. Jejich nastavení se provede v Oblasti/proPRODUKTIVITU/Doprava – Typy provozu. 
Typy provozu označují různé druhy pracovního nasazení jaké je dané vozidlo schopné vykonávat, jako např. stojné.
Typy provozu je možné následně v modulu použít ke stanovení různých nákladů a normovaných spotřeb u vozidel v závislosti na typu provozu, který má být vykonáván.
Každý typ provozu má svoji vlastní jednotku množství. Toto umožňuje přiřadit ke každému vozidlu více než jednu jednotku množství.

Pro každý typ provozu lze specifikovat:
* Kód
* Popis
* Kód měrné jednotky – výběrem ze standardního číselníku Měrné jednotky

**Vybavení vozidla**

Vybavení vozidla můžete použít pro specifikaci vybavení vozidel. Nastavení se provede v Oblasti/proPRODUKTIVITU/Doprava – Vybavení. 
Jakmile kód vybavení v číselníku vytvoříte, můžete evidovat množství tohoto vybavení přiděleného k jednotlivým vozidlům.

**Typy údržby**

Typy údržby můžete použít pro členění údržby vozidel dle vašich potřeb. Nastavení se provede v Oblasti/proPRODUKTIVITU/Doprava – Typy údržby.
Jakmile typ údržby vytvoříte, můžete evidovat provedenou či plánovanou údržbu pro jednotlivá vozidla.

**Kódy PHM**

Tabulka Kódy PHM slouží k definování nakupovaných položek, které jsou vám fakturovány jejich dodavateli (např. různé druhy pohonných hmot, poplatky,…). Nastavení Kódů PHM se provede v Oblasti/proPRODUKTIVITU/Doprava – Kódy PHM.
Kódy PHM je nutné zadávat v podobě, v jaké je dodavatel uvádí v elektronickém vyúčtování (má-li být tato funkcionalita používána). 
Pro identifikaci kódu PHM slouží pole Kód a Popis. 
Pro automatické vytváření nákupních faktur je nutné nastavit v poli Typ a Číslo, jakým způsobem má být o daném kódu PHM účtováno:
* Prázdný – výchozí hodnota
* Účet – do řádku nákupní faktury je vložen účet zadaný v poli Číslo
* Zboží – do řádku nákupní faktury je vloženo zboží zadané v poli Číslo
* Údržba DM – do řádku nákupní faktury je vložen dlouhodobý majetek s kódem údržby zadaným v poli Číslo

**Platební karty**

Platební karty použijete k zadání čísel platebních karet, popř. jejich popisu. Nastavení se provede v 
Oblasti/proPRODUKTIVITU/Doprava – Platební karty.

**Odborné způsobilosti**

Odborné způsobilosti můžete použít pro specifikaci znalostí, dovedností evidovaných řidičů. Nastavení číselníku odborných způsobilostí se provede v nabídce Oblasti/proPRODUKTIVITU/Doprava – Odborné způsobilosti. 

**Šablony knihy jízd**

Šablony knihy jízd jsou určeny k vytváření šablon deníků. Nastavení šablon se provede v Oblasti/proPRODUKTIVITU/Doprava – Šablony knihy jízd. 
Šablony umožnují pracovat v okně deníku pro specifický účel, např. dle vozidel.
Šablona knihy jízd obsahuje jeden řádek pro každou šablonu.
Pole **Vynutit návaznost stavu** – řádky musí být zadávány v pořadí, v jaké byly jízdy uskutečněny.
Pole **Čas jízdy nutný** – uživatel musí zadat dobu trvání jízdy.

**Šablony deníku PHM**

Šablony deníku PHM slouží k vytváření a sledování šablon deníků. Nastavení šablon se provede v 
Oblasti/proPRODUKTIVITU/Doprava – Šablony deníku PHM.
Okno Šablony deníku PHM obsahuje jeden řádek pro každou šablonu. Význam jednotlivých polí je obdobný jako u šablon jiných deníků.

**Šablony výpisu čerpání**

Šablony výpisu čerpání slouží k vytváření a sledování jednotlivých šablon výpisů. Nastavení šablon se provede v Oblasti/proPRODUKTIVITU/Doprava/Šablony výpisů čerpání PHM.
V Šabloně výpisu čerpání PHM se definují:
* Název a Popis
* Čísla výpisů – číselná řada pro výpisy čerpání PHM
* Čísla vydaných výpisů – číselná řada pro vydané výpisy čerpání PHM
* Parametry pro elektronické zpracování vyúčtování Cesta pro import, Typ souboru pro import, Typ objektu pro import, ID objektu pro import, Název objektu pro import
* Číslo dodavatele – je nutné vyplnit, budou-li z výpisů generovány nákupní faktury
* Číslo dodavatele PHM – needitovatelné, je zkopírováno ze stejného pole na kartě dodavatele (jedná se o číslo dodavatele PHM, které uvádí v elektronických výpisech, a které je kontrolováno při jejich importu).
* Šablona deníku PHM – je nutné vyplnit, budou-li z výpisů generovány deníky PHM
* List deníku PHM – je nutné vyplnit, budou-li z výpisů generovány deníky PHM

Dále je možné určit Šablonu a List deníku PHM kam budou položky vydaného výpisu exportovány po konečném zaúčtování a Číslo dodavatele pro automatické vytváření nákupních faktur.
Šablony výpisů čerpání PHM lze zobrazit ve dvou rozdílných oknech:
* Přehled šablon výpisů čerpání PHM zobrazuje veškeré šablony, každá na jednom řádku.
* Karta šablony výpisů čerpání PHM má pro každý řádek v přehledu šablon výpisů čerpání PHM k dispozici kartu s podrobnějším zobrazením polí pro zadání.

Obě tato okna zobrazují stejná pole a obě okna také poskytují stejné možnosti pro úpravy obsahů polí.

**Karta vozidla**

Karta vozidla je dostupná v Oblasti/proPRODUKTIVITU/Doprava - Vozidla. Používá se pro evidenci všech informací o používaných dopravních prostředcích. 
Vedení evidence vozidel je důležitou součástí modulu Doprava. Tabulka Vozidlo obsahuje informace využívané celou řadu funkcí tohoto modulu, např. Kniha jízd, Deník PHM atd. Kromě toho je možné napojit vozidlo na funkcionalitu dlouhodobého majetku a zdrojů.
Tabulka Vozidlo obsahuje pro každé vozidlo kartu, na kterou zadáváte základní informace jako je Číslo, Název, Typ, Normovaná spotřeba apod.

**Karta řidiče**

Karta řidiče se používá pro evidenci informací o řidičích. Je dostupná v Oblasti/proPRODUKTIVITU/Doprava – Řidiči.
Kartu řidiče je možné prostřednictvím pole **Číslo zdroje** napojit řidiče na funkcionalitu zdrojů. Pole **Číslo zaměstnance** zatím využito není.
Pomocí tlačítka **Odborná způsobilost** lze zadat či upravit přiřazení odborností k řidičům. Zadáním počátečního, resp. koncového data je možné hlídat vypršení platnosti určité odbornosti.

**Katalog zboží dodavatele**

Katalog zboží dodavatele slouží k napárování kódu zboží dodavatele s interním kódem PHM definujícím zaúčtování (viz výše). 

## Použití

### Použití dopravy

**Evidence údržby vozidla**

Na Kartě vozidla pomocí tlačítka **Evidence údržby** se zobrazí evidence údržby provedené na určitém vozidle.

**Práce s výpisy čerpání PHM**

Přehled výpisů čerpání najdeme v Oblasti/proPRODUKTIVITU/Doprava – Výpisy čerpání PHM. Zvolíme Přehled výpisů čerpání a zvolíme Nový. Po zadání dodavatele je možné importovat soubor od dodavatele pohonných hmot pomocí tlačítka Import výpisu. Následně je nutné doklad Vydat, čímž se doklad přesune do Vydaných výpisů čerpání PHM. (Oblasti/proPRODUKTIVITU/Doprava – Výpisy vydaných čerpání PHM).

Pro vytvoření nákupní faktury spustí uživatel na Vydaném výpisu čerpání PHM funkci **Vytvoření nák. faktury**. Funkce po skončení zobrazí číslo právě vytvořené nákupní faktury.
Pro návrh deníku PHM slouží funkce **Vytvoření deníku PHM**.

**Deník PHM**

Deník PHM slouží k evidenci čerpání pohonných hmot (Oblasti/proPRODUKTIVITU/Doprava – Deník PHM).
Deník PHM je možné vyplňovat ručně nebo jej plnit funkcí z Vydaného výpisu čerpání PHM (viz výše).
Zaúčtováním Deníku PHM se vytvoří Položky PHM, které je možné zobrazit z karty vozidla pomocí tlačítka Položky PHM.

**Kniha jízd**

Kniha jízd (Oblasti/proPRODUKTIVITU/Doprava – Knihy jízd) slouží k evidenci ujetých kilometrů a koncového stavu nádrže pro sledované období.
Zaúčtováním Knihy jízd se vytvoří **Položky knihy jízd**, které je možné zobrazit z karty Vozidla. 

**Sestavy**

Položky PHM a Položky knihy jízd slouží mimo jiné k vyhodnocování provozu vozidla, např. pro zjištění, zda je spotřeba v limitu či nikoli. K tomu slouží sestavy **Provoz vozidla – analýza** a **Provoz vozidla – fin. analýza** dostupné v Oblasti/proPRODUKTIVITU/Doprava.


## <a name="see-also"></a>Viz také  
[AC Productivity pack](ac-pp-productivity-pack.md)  