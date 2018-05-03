---
title: "HelpDesk"
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

# <a name="ac-pp-helpdesk.md"></a>HelpDesk

Modul  Helpdesk slouží k centralizovanému zadávání, evidenci, zpracování a vyhodnocování různých požadavků uživatelů v systému Microsoft Dynamics NAV. Uživatelé zde mohou zadávat požadavky na servisní úkony, na poskytnutí podpory, úpravu nebo doplnění funkcionality, evidovat reklamace a podobně. Umožňuje také kategorizaci požadavků, nastavení priorit a řízené zpracování přiřazenými řešiteli. K dispozici je i historie uzavřených požadavků HelpDesku.

## Instalace
**Objekty modulu**
Objekty modulu HelpDesk jsou označeny verzí HK.
**Workflow helpdesk požadavků**
V případě požadavku na řízení procesu zpracování HelpDesk požadavků prostřednictvím modulu Workflow je potřeba mít zakoupený a nakonfigurovaný modul Workflow – řízení stavů.
**Publikování dokumentů SharePoint k helpdesk požadavkům**
Pokud je požadováno publikování elektronických dokumentů k Helpdesk požadavkům, je nutné mít zakoupen a anastaven modul Publikování SharePoint.

## Nastavení

#### Obecné
Po importu objektů je třeba provést nastavení HelpDesku.
Nastavení se provede v Oblasti/proPRODUKTIVITU/HelpDesk – Nastavení helpdesku.
#### Nastavení Helpdesku
Aby bylo možné zadávat požadavky do HelpDesku, je nutné předem provést některá nastavení:
* Nastavit HelpDesk.
* Založit číselnou řadu pro požadavky HelpDesku.
* Založit kategorie uživatelů.
* Zadat oprávněné osoby a přiřadit je do kategorií.
* Naplnit tabulku priorit požadavků.
* Vytvořit kategorie požadavků (volitelně, pokud se sledují).
* Naplnit tabulku způsobů řešení.
* Vytvořit šablonu workflow pro Helpdesk.
* Nastavit workflow pro HelpDesk.
V nastavení helpdesku lze na záložce Obecné zvolit, zda bude při zadání požadavků povinné vyplňovat kategorii požadavků 1-3, výchozí prioritu a zda je nutné nové požadavky zadávat pomocí průvodce.
Na záložce Číslování se přiřadí číselná řada vytvářeným požadavkům Helpdesku. Definice číselné řady se tvoří stejným způsobem jako pro jiné agendy (v Oblasti/Správa/Nastavení aplikace/Obecné/Číselná řada).
#### Kategorie uživatelů
Kategorie uživatele obsahuje pole Kód, Popis a Váha. Kategorie uživatelů představují skupiny uživatelů. Skupinám uživatelů se přiřadí určitá váha (stupeň důležitosti), která je jedním z faktorů při automatickém výpočtu priority požadavku.
#### Oprávněné osoby
V dalším kroku se nastaví seznam oprávněných osob, které budou s HelpDeskem pracovat. Pro každou oprávněnou osobu se zvolí příslušná Kategorie uživatele, podle které program automaticky předvyplní Váhu požadavku pro danou osobu. Předvyplněnou hodnotu pole Váha lze pro každou osobu individuálně upravit. Pro výpočet celkové priority požadavku, pak program použije tuto hodnotu. 
Údaje k oprávněným osobám se zadávají přímo do karty. Na záložce Spojení lze doplnit podrobnější kontaktní údaje k dané osobě (Adresa, Telefon, Fax, Mobil, E-mail).
Když se do pole ID Uživatele vyplní odpovídající přihlašovací jméno dané oprávněné osoby, bude se při pořizování požadavku do HelpDesku automaticky nabízet kód oprávněné osoby, která požadavek zadává. Povolena změna uživatele opravňuje  ke změně Oprávněné osoby (poIe Identifikace helpdesk) při zadávání nového požadavku do HelpDesku. Zvolená Výchozí priorita se bude automaticky nabízet v nově pořizovaném požadavku.
#### Priority požadavků
Aby bylo možné vyhodnocovat požadavky podle jejich naléhavosti, je nutné vyplnit Priority požadavků v Oblasti/proPRODUKTIVITU/HelpDesk – priority požadavků. Kromě polí **Kód** a **Popis** priority je důležité zadat pole:
* **Váha** – pro výpočet výsledné priority požadavku. Váhy lze stanovit libovolně, záleží na místních podmínkách a zvyklostech (zpravidla čím závažnější je požadavek, tím vyšší váha)
**Výpočet data odezvy, Výpočet data řešení** – vzorce pro výpočet. Do polí lze zadat celá čísla se zkratkou jednotky času (např. D = den, M = měsíc, K = kvartál, R = rok). Výsledné datum se vypočte z data, kdy byl požadavek zadán (datum lze následně upravit).
#### Kategorie požadavků
Pro sledování požadavků z jiných hledisek než podle závažnosti je možné nadefinovat kategorie požadavků, a to až ve 3 úrovních, pro které platí stromový rozpad (tzn. jsou ve vztahu hierarchické podřízenosti, tj. volba Kategorie 1 určí, jaké se budou nabízet Kategorie 2, a ty zase ovlivní nabídku Kategorií 3).
U kategorií se vždy zadává **Kód** (max. 10 znaků) a **Popis** (max. 50 znaků). Na další (podřízenou) úroveň kategorií se přejde stiskem tlačítka **Kategorie požadavku**.
#### Řešení
V této tabulce je možné nadefinovat **Kód** (max. 10 znaků) a **Popis** (max. 30 znaků) jednotlivých způsobů řešení požadavků.
#### Založení šablony workflow
V Oblasti/proPRODUKTIVITU/WorkFlow – Šablony workflow je nutné založit šablonu workflow pro Helpdesk, ve které se zadá číslo tabulky 52068298 – HelpDesk požadavek. Pod tlačítkem **Stavy workflow** se definují jednotlivé stavy.
Pro stav workflow je třeba nadefinovat **Kód, Popis** a **Filtr dalšího stavu**, který určuje, do jakých dalších stavů je možné z daného stavu přejít. Jeden ze stavů musí být označen jako **Výchozí stav** – ten se vyplní při založení nového helpdesk požadavku. Některé stavy mohou být označeny jako **Konečný stav**, z něhož se už nepokračuje do dalšího stavu.
Pro aktivní řádek lze specifikovat **Akce workflow, Kontrolovaná pole** a **Nastavovaná pole**. V Akcích se definují Codeunity, Reporty či XMLporty, které se automaticky spustí při přechodu do daného stavu (např. odeslání e-mailové zprávy). U kontrolovaných resp. nastavovaných polí se určí, co a kde se má kontrolovat nebo nastavit při přechodu do daného stavu.
Detailní popis nastavování workflow je předmětem samostatného manuálu.
#### Nastavení workflow pro HelpDesk
Kód šablony pro HelpDesk se vyplní na záložce **Obecné** v **Nastavení workflow** v poli **Šablona worflow helpdesku** (v Oblasti/proPRODUKTIVITU/WorkFlow – Nastavení workflow).

## Použití

### Vytvoření požadavku
#### Obecné
Po provedení potřebných nastavení lze zadávat požadavky HelpDesku. Požadavky lze zadávat ručně nebo prostřednictvím Průvodce vytvořením požadavku. V Oblasti/proPRODUKTIVITU/HelpDesk – Pult dispečera helpdesku na záložce Navigace zvolte tlačítko **Průvodce**. Povinnost použití průvodce lze definovat v Nastavení helpdesku.
#### Průvodce vytvořením požadavku
Na první straně Průvodce vytvořením požadavku se určí osoba zadavatele a priorita požadavku. 
Pole **Kód zadavatele** se automaticky předvyplní podle toho, kdo je přihlášen k aplikaci (pokud jeho ID Uživatele je vyplněno u příslušné oprávněné osoby). Pokud má uživatel povolenou změnu uživatele na Kartě oprávněné osoby, může hodnotu ručně změnit výběrem z tabulky oprávněných osob. 
**Priorita požadavku** se automaticky přednastaví z Karty oprávněné osoby. Zadavatel ji výběrem z tabulky priorit požadavku může změnit.
Obě pole jsou povinná, nelze pokračovat bez vyplnění obou hodnot.
Na druhé straně průvodce je pole **Stručný popis požadavku** pro krátký výstižný popis požadavku. Pro detailnější popis požadavku slouží pole **Popis požadavku**.
Na další straně průvodce je možné zařadit požadavek do různých předefinovaných kategorií (pole **Kategorie 1-3**). Vyplnění polí je povinné jen v případě, že bylo v nastavení HelpDesku zatrženo některé z polí Vynutit kategorii 1-3. 
Na poslední straně průvodce se stiskem tlačítka Dokončit vytvoří nový požadavek helpdesku. 
Pokud byla zatržena volba **Publikovat dokumenty**, je zároveň spuštěn **Průvodce publikováním**.
Publikování dokumentů vyžaduje modul Publikování SharePoint a je podrobněji popsáno v samostatném manuálu k tomuto modulu.

### Požadavky
#### Obecné
Karta helpdesk požadavku zobrazuje relevantní informace vztahující se ke zvolenému požadavku. Údaje v bílých polích lze editovat (např. je možné doplnit prioritu dispečera, upravit data odezvy či řešení, event. změnit zařazení do kategorií na záložce Kategorie). 
Požadavek lze také přidělit k určitému projektu. Pokud příslušný projekt ještě neexistuje je možné jej vytvořit přímo z karty požadavku na záložce Akce pomocí tlačítka **Vytvoř projekt**. Touto operací je založen nový projekt se stejným kódem jako je číslo požadavku (i se stejným popisem) a tento kód se automaticky doplní do pole **Číslo projektu**. Kartu přiřazeného projektu a jeho položky lze pak zobrazit pomocí tlačítka **Karta projektu**.
Na záložce **Řádky** se po založení objeví nový záznam s výchozím stavem podle definice v šabloně workflow pro helpdesk. Při každé další změně stavu workflow požadavku se, v případě že máte pro tento stav nastavenu Akci Workflow logování (52068291 WriteStatusChangeHlpDesk), vygeneruje další řádek s odpovídajícími hodnotami (viz podrobnější popis níže u zpracování požadavku).
**Přehled helpdesk požadavků**
Přehled helpdesk požadavků lze zobrazit v Oblasti/proPRODUKTIVITU/HelpDesk/Helpdesk požadavky.
**Poznámky k požadavku**
Ke každému vytvořenému požadavku je možné doplnit poznámky. První vstup do poznámek je možný už při vytváření požadavku v Průvodci, jak bylo popsáno výše.
Uživatelé mohou využívat 2 formy poznámek: 
* řádkové poznámky dostupné na záložce **Řádky poznámek** – tyto strukturované poznámky obsahují pole Datum, Poznámka (100 znaků) a Kód. 
* volné poznámky dostupné na záložce **Detailní údaje** – tyto poznámky umožňují zadávat libovolný text, který může být navíc zobrazen v informačním okně **Náhled obsahu**.
Je na rozhodnutí správce, která forma poznámek bude v rámci celé firmy využívána. 
#### Dokumenty
Pokud je instalován modul Publikování SharePoint, pak je možné u každého požadavku v Přehledu helpdesk požadavků na záložce Akce pomocí tlačítka Publikovat publikovat dokument a pomocí tlačítka Zobrazit zobrazit publikovaný dokument. Podrobnější popis postupu nastavení a práce při publikování a zobrazování dokumentů je v manuálu k modulu Publikování SharePoint.
#### Tisk
Pomocí tlačítka **Tisk** v Přehledu helpdesk požadavků se spustí sestava **Helpdesk požadavky** (do vstupního filtru se nabídne číslo aktuálně zobrazeného požadavku, rozsah tisku lze pak blíže specifikovat prostřednictvím filtrů a parametrů.

### Zpracování požadavku
#### Obecné
Po vytvoření požadavku je možné jej dále zpracovávat. K tomu se na Kartě helpdesk požadavku využívá především záložka **Řešení**.
#### Řešení
Při zpracování HelpDesk požadavku se na kartě požadavku na záložce **Řešení** vyplní příslušné údaje, především **Kód řešení, Trvání, Popis řešení** (max. 250 znaků) a **Kód dalšího řešitele**. Kód řešení se vybírá z předdefinované tabulky možných způsobů řešení.
Délka **Trvání** se zadává ve dnech, hodinách, minutách, sekundách, příp. milisekundách, a to buď přímo vypsáním čísla a jednotky (lze použít zkratku počátku slova – např. d=den, m=minuta, mil=milisekunda apod.) nebo zadáním pouze čísla, které je interpretováno jako údaj v hodinách. Např. údaj 28,35 je převeden na 1 den 4 hodiny 21 minuty.
#### Změna stavu
Pro přechod do další fáze řešení požadavku je třeba stisknout tlačítko **Změna stavu** (nebo použít kombinaci kláves Ctrl + F11). Nabídnou se další stavy workflow, které podle definice filtru dalšího stavu workflow připadají v úvahu (podrobněji popsáno u zadávání stavů workflow).
Po dokončení operace je aktualizován **Kód stavu workflow** na záložce Obecné. Pokud je ve zvoleném stavu workflow nastavena akce workflow s přiřazenou codeunitou 52068291 – WriteStatusChangeHlpDesk, přičte se hodnota trvání do celkové doby trvání na záložce Obecné a vygeneruje se další řádek do položek helpdesk požadavku dokumentující historii průběhu řešení - datum, řešitel, kód řešení, popis, trvání.
#### Export do PDF a mail
Na **Kartě helpdesk požadavku** na záložce **Akce** je k dispozici tlačítko **Export do PDF a mail**, které pro aktuální požadavek vygeneruje sestavu Helpdesk požadavky do souboru PDF a vloží tento soubor jako přílohu emailu. Uživatel následně provede vlastní odeslání emailu.

### Pult dispečera
#### Obecné
Pult dispečera je dotupný v Oblasti/proPRODUKTIVITU/HelpDesk – Pult dispečera helpdesku. Umožňuje souhrnný pohled na zadané požadavky.
#### Pult dispečera helpdesku
Tato volba HelpDesku nabízí přehledové zobrazení požadavků s přednastavenými volitelnými filtry v záhlaví pro snadnější vyhledávání a orientaci. Požadavky lze filtrovat např. podle stavu, podle uživatele, zadavatele, řešitele či podle kategorií. Zobrazený přehled požadavků je možno navíc seřadit podle různých klíčů, zvl. podle čísla, priority, stavu workflow nebo kategorií.
Vybraný požadavek lze pak zobrazit volbou **Karta** (nebo Shift + F7).
#### Priorita požadavku
Jedním z nejdůležitějších kritérií pro rozhodování o plánování a  koordinaci kapacit na řešení požadavků je stupeň naléhavosti, s jakou je nutno se tím kterým požadavkem zabývat. Významnou pomůckou dispečera v tomto procesu může být ukazatel celkové priority požadavku, jak byl vypočítán programem na základě vstupních parametrů:
* **Váha** oprávněné osoby, tj. zadavatele požadavku
* **Priorita požadavku** stanovená zadavatelem při vytváření
* **Priorita požadavku** stanovená dispečerem helpdesku při event. následném přehodnocení důležitosti požadavku.
Celková priorita je vypočtena jako:
* součin hodnot **Váha** zadavatele (hodnota na kartě příslušné oprávněné osoby) a **Priorita požadavku** stanovené zadavatelem pokud dispečer nestanoví jinou prioritu (tj. priorita dispečera je nevyplněna)
* součin hodnot **Váha** zadavatele a **Priorita požadavku** stanovené dispečerem (tj. priorita dispečera je vyplněna)

### Sestavy
#### Obecné
Nabídka tiskových sestav přiřazených modulu HelpDesk se nachází v Oblasti/proPRODUKTIVITU/HelpDesk – Sestavy a Analýzy. Podle zadaných filtrů lze tisknout jednotlivé Karty helpdesk požadavků, zpožděné požadavky a seznam helpdesk požadavků.

### Uzavřené požadavky
#### Obecné
Výběrem položky v Oblasti/proPRODUKTIVITU/HelpDesk – Přehled uzavřených helpdesk požadavků se zobrazí uzavřené požadavky, tj. požadavky, které už byly vyřízeny. Požadavky jsou uzavírány automaticky prostřednictvím nadefinování nastavovaných polí po přechodu do konečného stavu (podrobněji viz manuál k workflow).

### Export helpdesk požadavků
#### Export do Excelu
Volba v Oblasti/proPRODUKTIVITU/HelpDesk – Export helpdesk požadavků – umožní exportovat vybrané požadavky do Excelu v předdefinované podobě.

## <a name="see-also"></a>Viz také  
[AC Productivity pack](ac-pp-productivity-pack.md)  