---
title: "Správa upozornění"
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

# <a name="ac-pp-notifications.md"></a>Správa upozornění

Modul Správa upozornění umožňuje systémové upozorňování na stavy dat a procesů evidovaných v systému Microsoft Dynamics NAV. Upozorňování pracuje jak interně v prostředí systému, tak i externě formou e-mailu.
Z hlediska informačního systému Microsoft Dynamics NAV je tento modul vhodným doplněním modulů 
WorkFlow – řízení stavů, WorkFlow – sledování polí či Evidence doručené pošty. Dohromady tvoří tyto moduly sadu pro řízení a kontrolu procesů a událostí v organizaci.
Základem použití modulu je definování sledovaných stavů a událostí v systému, na které je třeba upozornit uživatele nebo na ně určitým způsobem reagovat. Kromě sledování aktuální události lze sledovat i vývoj události v čase. 
Modul je vyvinut jako off-line pracující nástroj, který nereaguje na okamžitou změnu v datech, ale poskytuje a zasílá informace o stavu dat v naplánovaných intervalech.
Modul Správa upozornění slouží např. k hlídání termínů na dokladech (datum dodání, splatnosti). Je možno informovat mailem zaměstnance o aktuálnosti termínu (kontroly, plnění, splnění, …). Tento modul je postaven samostatně a nezasahuje do ostatních modulů.
**Princip funkce modulu**
Modul Správa upozornění vytváří, aktualizuje a uchovává k záznamům v určených tabulkách systému Microsoft Dynamics NAV další doprovodné informace o jejich vzniku či stavu zpracování, tzv. Položky událostí. Další využití těchto položek pak závisí na konkrétním řešení, ve které má být Správa upozornění použita, v modulu samotném není nijak řešeno.
Pro každou tabulku v systému, která má být sledována funkcionalitou Správa upozornění, je nastavena tzv. Karta šablony události. Na této kartě jsou specifikovány další omezující podmínky, tzn. Modul Správa upozornění nemusí pracovat se všemi záznamy z dané tabulky, ale pouze s vybranou podmnožinou.
Ke každé šabloně jsou dále definovány Fáze událostí, tj. stavy, ve kterých se může konkrétní Položka události nacházet. U fází jsou uvedena i pravidla jejich použití odkazující se např. na vznik záznamu nebo určité datumové pole.
Vlastní hromadné vytvoření a aktualizace Položek upozornění je řešeno spuštěním reportu (ručně či plánovačem). Je možná i ruční změna přímo v Položkách událostí.

## Instalace
**Objekty modulu**
Objekty modulu Správa upozornění jsou označeny verzí
 **EN7.00, EN7.20**
Seznam konkrétních objektů modulu je uveden v dokumentaci k aktuálnímu buildu add-on modulů.
**Další součásti instalace**
Pro automatické upozorňování formou zaslaných e-mailů je potřeba aplikační server a modul Rozšíření plánovače úloh (Job Queue).

## Nastavení
#### Karta šablony události
V Oblasti/proPRODUKTIVITU/Správa upozornění zvolte Šablony událostí a tlačítko **Nový**. Otevře se **Karta šablony událostí**.  Karta šablony události se používá pro zadání sledované události. 
Pole **Kód** slouží k rozlišení jednotlivých sledovaných událostí a pole **Název** k pojmenování sledované události. V poli **Číslo tabulky** vybereme tabulku, nad kterou chceme provádět sledování a dále zvolíme **Číslo pole** z dané tabulky – dle tohoto pole se vyhodnocuje daná fáze. Funkcionalita pracuje i s kalkulovanými poli. Jedná se o nepovinné pole.
**Číslo pomocného pole** se zobrazuje v položkách upozornění a slouží pouze pro bližší rozlišení události.
**Číslo formuláře** – zadává se stránka, která se má otevřít pro zobrazení události v Položkách upozornění.
**Filtr tabulky** – zadáním tohoto filtru nad tabulkou uvedenou v poli **Číslo tabulky** lze omezit záznamy, které bude systém kontrolovat.
Dalším filtrem jsou Datumové filtry, které najdeme pod tlačítkem **Filtry data**.
V polích **Začátek fáze** a **Konec fáze** se zadává vzorec data vztažený k systémovému datu (TODAY).
Pole **Výstupní kontrola** je nepovinné. Pokud je zadáno a podmínka výstupní kontroly je splněna, tak se neupozorňuje a položka upozornění se uzavře a přesune do položek uzavřených událostí.
Pokud pole **Aut.uzavřít položky mimo filtr** není zaškrtnuto, tak se položky upozornění dají uzavírat pouze ručně. 
Pole **Filtr ID uživatele** – hodnota tohoto pole se propisuje do položek upozornění a slouží k filtrování dle ID uživatele. 
Pole **Vypnuto** určuje stav sledované události – zda se sleduje či nikoliv.
#### Fáze události
Pro každou Kartu šablony události se nastavují fáze, do kterých se daná událost může dostat při splnění podmínek. Do nastavení fází pole se dostaneme z Karty šablony události pomocí tlačítka **Fáze**.
Pole **Kód** slouží k rozlišení jednotlivých fází sledování.
Pole **Typ kontroly** nabývá hodnot Položka, Datový interval nebo Číselný interval. Při výběru fází má nejvyšší prioritu výběru Položka, pak Datový interval a nakonec Číselný interval. Toto pole se vztahuje k poli **Číslo pole** z Karty šablony události.
Při výběru typu kontroly Položka se bere do úvahy pole **Trvání**. Určuje, jak dlouho bude fáze trvat od doby vzniku položky upozornění.
Při výběru Datový interval se pracuje s poli **Začátek fáze** a **Konec fáze**. Zadává se vzorec data vztažený k systémovému datu (TODAY).
Hodnota Číselný interval pracuje s poli **Počáteční číslo** a **Koncové číslo**.
Pole **Barva** slouží k barevnému označení řádku v položkách upozornění.
Pole **Priorita** je pouze evidenční a propisuje do položek upozornění.
Pole **Filtr ID uživatele** – hodnota tohoto pole se doplňuje do položek upozornění a slouží k filtrování položek dle ID uživatele.
Každé fázi lze přiřadit e-mailovou adresu určující komu danou událost odeslat, koho upozornit. 
#### E-maily – zadání adresáta
E-maily se nastavují na stránce Fáze polí přes tlačítko **E-maily**. Jsou 3 způsoby, jak zadat adresáta e-mailu. (Tyto způsoby se dají kombinovat, tj. e-mail může odejít na všechny 3 definice pro jednu položku.)
1.	Ručně definovaný e-mail
Vyplním pole **e-mail**. Použiji, pokud chci poslat upozornění vždy na tento e-mail.
2.	Dynamický e-mail z pole v záznamu, který je zdrojem upozornění
Vyplním pole **Číslo pole e-mailu**. Jde o textové pole z tabulky definované šablonou události. Použiji, pokud chci poslat upozornění na e-mail, který je přímo uložen v záznamu ve zdrojové tabulce šablony upozornění, který je zdrojem upozornění. (např. upozornění nad kartou zaměstnance, která obsahuje i jeho e-mail)
3.	Dynamický e-mail z pole relační tabulky, která má vazbu s tabulkou šablony upozornění přes jedno pole dle záznamu, který je zdrojem upozornění. 
Vyplním pole **Číslo relační tabulky** – tabulka, kde bude pole pro e-mail, pole **Číslo relačního pole e-mailu** – pole s e-mailem v relační tabulce, pole **Číslo pole relace z** – pole z tabulky šablony události, které definuje vazbu do relační tabulky, pole **Číslo pole relace do** – pole z relační tabulky, na které je definována vazba. Použiji, pokud chci poslat upozornění na e-mail, který je uložen v relační tabulce ke zdrojové tabulce šablony upozornění s vazbou přes jedno pole (např. upozornění nad prodejním dokladem, kdy chci e-mail poslat na prodejce dokladu – e-mail je uložen v poli E-mail v tabulce Prodejce/nákupčí, která má z prodejní hlavičky vazbu přes jedno pole Kód prodejce – Kód. 
#### E-maily – obsah
Jsou 2 způsoby, jak definovat obsah e-mailu (předmět a tělo).
1.	S pevně definovanou naprogramovanou strukturou 
V tomto případě **Typ e-mailu** je **Standard**.  
**Předmět:** kód šablony události + popis fáze
**Tělo:** pole primární klíč z položky události
2.	S dynamickým obsahem 
V tomto případě je obsah definovaný pomocí polí a textů e-mailu. **Typ e-mailu** je **Strukturovaný**. Předmět i tělo se definuje v textech mailu s využitím polí e-mailu. Pole je možné definovat z tabulek – zdrojová tabulka šablony upozornění, 52068220 – Šablona události, 52068221 Fáze pole, 52068224 Položka události.

## Použití
#### Vytvoření a aktualizace položek událostí
Vytvoření a aktualizace položek upozornění se provádí reportem 52068221 Vytvoření a aktualizace položek událostí. 
Tento report je možné spouštět ručně, ale je upraven pro automatické spouštění pomocí modulu Rozšíření plánovače úloh (Job Queue).
Najdete jej v Oblasti/proPRODUKTIVITU/Správa upozornění – Vytvoření a aktualizace položek událostí.
Po spuštění reportu systém dle zadaného kódu šablony události projde sledovaná pole a dle zadaných kritérií (v textu výše) naplní tabulku Položky událostí.
V případě, že k fázím byla zadána e-mailová adresa, systém automaticky odešle e-mail s řádky upozornění na zadané e-mailové adresy (odesílání reportů je řízené reportem 52068222 Odesílání mailů z položek událostí a parametrizací plánovače úloh).
#### Zobrazení položek událostí
Položky událostí (upozornění) lze zobrazit buď přímo z Karty šablony události přes volbu CTRL +F7 **Položky** nebo v Oblasti/proPRODUKTIVITU/Správa upozornění – Položky událostí.
Položky událostí lze filtrovat dle polí v hlavičce. Zobrazují stav v jakém se sledovaná událost nachází. Pole **Stav** je pouze evidenční a má tyto hodnoty: Otevřeno a Řešeno. Nově vytvořené řádky jsou ve stavu Otevřeno. Do stavu Řešeno se dostanou v případě, že uživatel událost v řádku vyřešil, tzn. otevře odpovídající záznam specifikovaný na Kartě šablony události funkcí na tlačítku **Otevřít formulář**.
K vytvořeným řádkům upozornění je možno zadat poznámku přes funkci na tlačítku **Poznámky**.
#### Ruční změna a aktualizace fází události
V Položkách událostí je možné ručně měnit fázi události. To se provádí pomocí tlačítka **Ruční nastavení fáze**.
Pole **Ručně změněno** v položkách události zobrazuje, zda byla fáze změněna ručně.
Pomocí funkce **Zrušení ručního nastavení** se fáze opět nastaví na svůj původní stav.
Pomocí funkce **Aktualizovat vybrané položky** lze ručně provádět aktualizaci jednotlivých fází události.
#### Uzavírání položek událostí
Na stránce Položky událostí lze ručně provádět uzavírání položek a jejich přesun do uzavřených položek událostí pomocí tlačítka **Uzavřít vybrané položky**.
#### Historie – uzavřené položky událostí
Uzavřené položky událostí lze nalézt v Oblasti/proPRODUKTIVITU/Správa upozornění/Uzavřené položky událostí.
Do tohoto přehledu se dostanou položky událostí, které jsou buď uzavřeny ručně nebo pomocí aktualizace položek událostí (automaticky).
Na stránce Uzavřené položky událostí se lze pomocí tlačítka **Otevřít formulář** dostat do dokladu přes číslo formuláře zadané v Kartě šablony události.
Pomocí tlačítka Poznámky lze zobrazit zadanou poznámku k příslušnému řádku upozornění.

## <a name="see-also"></a>Viz také  
[AC Productivity pack](ac-pp-productivity-pack.md)  