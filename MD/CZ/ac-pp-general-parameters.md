---
Title: "Obecné parametry"
Description: Add-on module general parameters allows you to add to the cards an unlimited number of new parameters.
Author: AUTOCONT
Date: 02/26/2018
Product: dynamics365-business-central
Contentlocale: cs-cz
---

# <a name="ac-pp-general-parameters.md"></a>Obecné parametry

Modul Obecné parametry umožňuje pro kartu zboží, kartu majetku a kartu zaměstnance či obecně pro jakoukoliv jinou kartu definovat další „obecné parametry“. Jsou to parametrizovatelné vlastnosti a jejich hodnoty, které rozšiřují možnosti evidence zboží, dlouhodobého majetku, zaměstnanců příp. jiných entit systému Microsoft Dynamics 365 Business Central.
Parametry lze nastavit uživatelsky, lze jim nastavit předdefinované hodnoty anebo je možné hodnoty parametrů zadávat ručně. Parametry lze seskupovat do šablon.
K dané kartě se přiřazují parametry přes šablony parametrů. Lze tak nadefinovat určitou strukturu (např. šablony „Parametry nemovitosti“, „Parametry automobilů“ apod.). Jedna karta (zboží, majetku apod.) může mít přiřazeno více šablon.
Parametry mohou být povinné a nepovinné a lze jim nastavit prioritu.


## Nastavení

### Parametry

#### Nastavení parametrů

U parametrů lze nastavit tyto vlastnosti:
* Datový typ hodnot parametru (viz. níže).
* Metoda zadávání hodnot.
Obojí se nastavuje na stránce Obecné parametry. Dále se nastavuje:
* Výchozí hodnota parametru.
* Nastavení, zda je parametr povinný.
* Priorita parametru.
Tyto 3 vlastnosti se nastavují na stránce Obecné parametry šablony.

#### Obecné parametry

Pomocí vyhledávací funkce **Řekněte mi, co chcete udělat** (Alt + Q) vyhledejte **Obecné parametry** - v Obecné parametry se definuje seznam parametrů (**Kód, Popis**) a dále **Datový typ hodnot** a **Metoda zadávání** hodnot.

**Datové typy**

Program nabízí více možností, ale pro obecné parametry jsou vhodné následující datové typy:
* Text
* Code
* Integer
* Decimal
* Boolean
* Datetime
* DateFormula
* Date
* Time
* Duration
* RecordID

### Hodnoty parametrů

#### Hodnoty

Na stránce zvolíte v nabídce Navigace/Parametry/**Hodnoty** - Hodnoty obecného parametru (**Kód hodnoty**, **Popis hodnoty** a samotná **Hodnota**).

Nastavení hodnot parametru je nezbytné zejména u parametrů s **Metodou zadávání** – Výběr. Je však možné hodnoty definovat i u parametrů zadávaných Ručním vstupem. Zde je kromě takto zadaných hodnot možné při vložení obecných parametrů zadat i libovolné jiné hodnoty. Hodnoty zadané v nastavení pak slouží pro zjednodušení zadávání.

### Šablony parametrů

Šablony parametrů usnadňují orientaci v parametrech, fungují jako filtry parametrů při zadávání.
Pomocí vyhledávací funkce Řekněte mi, co chcete udělat (Alt + Q) vyhledejte **Šablony obecných parametrů**. Nastavuje se **Název šablony**, její **Popis** a **ID tabulky**, pro kterou se daná šablona bude používat. Standardně lze zvolit tabulky 27 (zboží), 5200 (zaměstnanec) a 5600 (dlouhodobý majetek). 

#### Obecné parametry šablony

Z Šablony obecných parametrů pomocí tlačítka Navigace (případně …)/Šablona/**Parametry** lze otevřít **Obecné parametry šablony** a zde nastavit obecné parametry, které budou figurovat pod danou šablonou. 
Nastavuje se:
* **Výchozí hodnota** parametru,
* **Povinný** – povinnost zadání parametru,
* **Priorita** – určuje posloupnost řazení parametrů podle důležitosti.

## Použití

### Vložení a změna obecných parametrů

#### Vložení a změna obecných parametrů ke kartě

Pro vložení se na všech kartách používá tlačítko **Vložit obecné parametry** na kartě zvolte v nabídce Akce/Funkce. Objeví se průvodce Vložení obecných parametrů, pomocí kterého se ke konkrétní kartě (zboží, majetku aj.) vybere šablona, parametry a nastaví se hodnoty těchto parametrů.
Kroky průvodce vložením parametrů jsou:
* volba šablony v poli **Název šablony**,
* nastavení hodnot povinných parametrů dané šablony,
* nastavení hodnot nepovinných parametrů dané šablony.
Stejný postup se použije při změně parametrů nebo hodnot obecných parametrů dané karty.

### Náhled obecných parametrů karty

#### Prohlížení obecných parametrů karty

Na kartě zboží (resp. dlouhodobého majetku atd.) je tlačítko Navigace/Dlouhodobý majetek/**Obecné parametry**, které zobrazí parametry dané karty pro jednu šablonu parametrů. 
Náhled všech parametrů dané karty lze zobrazit na stránce **Přehled obecných parametrů karty**, na tu se dostanete v nabídce přes Navigace/Obecné parametry. 

### Vyhledávání podle obecných parametrů

Funkcionalitu obecných parametrů lze využít k vyhledání „podobných“ karet. Jinými slovy vyhledání těch karet, které mají například přiřazeny stejné parametry nebo mají stejné hodnoty některých parametrů.
Přehled je na stránce **Přehled DM dle parametrů**.

## <a name="see-also"></a>Viz také  
[AC Productivity pack](ac-pp-productivity-pack.md)  