---
Title: "Evidence nářadí a pomůcek"
Description: Add-on module pack production tools allows you to manage tools.
Author: AUTOCONT
Date: 18/02/2019
Product: dynamics365-business-central
Contentlocale: cs-cz
---

# <a name="pp-production-tools.md"></a>Evidence nářadí a pomůcek

Modul Evidence nářadí a pomůcek řeší problematiku evidence nářadí, pomůcek, forem a jiných potřeb obvykle evidovaných pomocí skladové evidence systému. Tento modul je postaven nad základy evidence majetku, s ohledem na sjednocení evidence pro potřeby sledování dlouhodobého majetku a evidence výrobní, tj. půjčování nářadí a pomůcek.

## Nastavení

**Nastavení modulu**

Je nutné nastavit minimálně jednu šablonu deníku evidence nástrojů. Pomocí vyhledávací funkce **Řekněte mi, co chcete udělat (Alt + Q)** vyhledejte **Šablony deníků evidence nástrojů**.  V šabloně je možno volit výchozí **Typ položky**, pokud by byla potřeba definovat deník jen pro jeden pohyb např. **Půjčení**. Dále je potřeba nastavit číselnou řadu dokladů, pomocí kterých se budou pohyby sledovat.
Pro každou šablonu deníku (případně list deníku) je možno definovat kontroly povinných údajů v deníku při účtování pohybu s nářadím v tabulce **Nastavení typů položky evidence nástrojů**. Tam se dostanete zvolením Navigace/Šablona/**Nastavení typu položky**.

**Typy poškození**

Nastavení typů poškození slouží pro rozlišení poškozených evidovaných kusů, ať s ohledem na pozdější statistické vyhodnocování, tak pro případné náhrady ze stran zaměstnanců, kteří poškozené nářadí či pomůcky vrací.
Pro zadání typu poškození jsou k dispozici pole **Kód**, **Popis** a **EAN**, ve kterém je možno definovat čárový kód pro případné využití čteček čárových kódů.

**Karta evidence nástrojů**

Pomocí vyhledávací funkce **Řekněte mi, co chcete udělat (Alt + Q)** vyhledejte **Položky evidence nástrojů**. Vyberte nebo vytvořte novou **Kartu evidence nástrojů**. Evidence nástrojů se používá pro sledování a evidenci všech informací o používaných pomůckách, přípravcích a nářadí.
Na záložce Evidence nástrojů je možno nastavit a sledovat údaje spojené s vlastní evidencí. V poli **EAN** je možno nastavit čárový kód pro umožnění použití čteček čárových kódů. V poli **Číslo police** je možno evidovat přesné místo uložení a dále zde jsou kalkulovaná pole s napočtenými hodnotami celkového množství a množství nářadí volného k zapůjčení.

## Použití

### Evidence nářadí a pomůcek

Pomocí vyhledávací funkce **Řekněte mi, co chcete udělat (Alt + Q)** vyhledejte **Přehled šablon deníku evidence nástrojů**. Zde je možné vybrat z přednastavených deníků evidence.

V deníku je možno volit mezi 4 typy pohybů:
* Příjem – slouží k zařazení evidovaného množství nářadí
* Výdej – slouží k vyřazení nářadí z evidence
* Půjčení
* Vrácení

Při účtování deníků lze evidovat množství, číslo pracovníka, který si nářadí půjčuje či vrací. Dále je obvykle požadováno sledovat kód poškození, kterým lze vyjádřit stav vraceného nářadí a následně je možné řešit nápravu či výměnu nákupem či výrobou nové položky. Pole **Evidenční číslo** slouží ke sledování půjčování kusových položek s unikátním evidenčním číslem pro přesnější rozlišení evidovaných pomůcek. Tato evidence vyžaduje účtovat množství pouze po 1 kusu.

### Údržba

Pomocí vyhledávací funkce **Řekněte mi, co chcete udělat (Alt + Q)** vyhledejte **Položky údržby**. Evidence nad modulem majetek umožňuje při existenci granule *Controlling Fixed Assets* sledovat údržbu evidovaných nářadí a pomůcek pomocí položek údržby. A to údržbu vznikající ze standardních nákupních dokladů, např. nákupní objednávka, nebo položky údržby vznikající interní spotřebou v denících zboží.

### Historie

Při účtování deníku vznikají položky, které je možno zobrazit pomocí vyhledávací funkce **Řekněte mi, co chcete udělat (Alt + Q)** - **Položky evidence nástrojů**.



## <a name="see-also"></a>Viz také  
[AC Productivity pack](ac-pp-productivity-pack.md)  