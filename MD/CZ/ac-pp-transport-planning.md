---
title: "Doprava - Plánování"
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

# <a name="ac-pp-transport-planning.md"></a>Doprava - Plánování

Modul Doprava plánování rozšiřuje základní modul dopravy zejména o řízení a plánování jízd pomocí příkazů k jízdě a pomocí pultu dispečera dopravy.

**Klíčové výhody**

* Správa dopravy je integrovaná v informačním systému Microsoft Dynamics NAV a tedy není nutno pořizovat speciální software.
* Pro řízení dopravy je k dispozici centrální místo – pult dispečera dopravy.
* Možnost hromadného naplnění knihy jízd z vydaných příkazů k jízdě.

## Instalace

**Objekty modulu**

Objekty modulu Doprava – plánování jsou označeny verzí DO7.20.

**Další součásti instalace**

Podmínkou použití modulu je modul Doprava – základ.

## Nastavení

**Obecné**

Základní nastavení se provede v Oblasti/proPRODUKTIVITU/Doprava – Nastavení dopravy.
Na záložce **Obecné** zadáte volby:
* **Nutné ID původu požadavku** – vynutí zadání ID původu požadavku na dopravu při zakládání nového požadavku v průvodci, tedy zadání nákupní či prodejní objednávky, ke které se požadavek na dopravu vztahuje.
* **Nutné PSČ požadavků** – vynutí zadání PSČ míst „odkud – kam“ při zakládání nového požadavku na dopravu.
Na záložce **Číslování** se zadávají číselné řady:
* **Čísla vozidel** – číselná řada pro karty vozidel,
* **Čísla řidičů** – číselná řada pro karty řidičů,
* **Čísla příkazů k jízdě** – číselná řada pro nevydané příkazy k jízdě,
* **Čísla vydaných příkazů k jízdě** – číselná řada pro vydané příkazy k jízdě.

**Další nastavení**

Další nastavení a číselníky jsou součástí modulu Doprava – základ, jsou tedy popsány v jeho manuálu.

## Použití

### Pult dispečera dopravy

**Pult dispečera dopravy**

Centrem plánování dopravy je Pult dispečera dopravy, který zobrazuje požadavky na dopravu nové, zaplánované i uzavřené. Pult dispečera dopravy je v Oblasti/proPRODUKTIVITU/Doprava.
V řádcích jsou jednotlivé požadavky, v hlavičce pak filtry na filtrování řádků přes vozidlo, typ vozidla, stav požadavku, datum požadavku a přes globální dimenze. Dispečer dopravy tím získá rychlý přehled o požadavcích na dopravu „kdo, kdy, čím, kam“ má jet.

**Založení nového požadavku na dopravu**

Pro založení nového požadavku na dopravu je připraven průvodce.
Jsou dvě cesty odkud založit nový požadavek na dopravu:
* Z pultu dispečera dopravy pomocí tlačítka **Nový požadavek**.
* Z prodejní či nákupní objednávky pomocí tlačítka **Vytvořit požadavek dopravy**.

Tyto dva způsoby se liší tím, že při vytváření objednávek je automaticky nastavena vazba k danému dokladu, a proto je tento krok přeskočen.
V prvním kroku založení nového požadavku se zadá vazba na prodejní či nákupní objednávku (ne/vyplnění závisí na Nastavení dopravy, viz výše). Tento krok je přeskočen, pokud je požadavek zakládán přímo z dokladu.
Ve druhém kroku se zadává datum, čas, vozidlo a popis:
Třetí krok – zadání místa „odkud“. Pokud existuje vazba na objednávku, údaje se předvyplní z objednávky, v případě prodeje z adresy použité lokace, v případě nákupu z kódu adresy objednávky.
Čtvrtý krok – zadání cílového místa. Pokud existuje vazba na objednávku, údaje se předvyplní z objednávky, a to z adresy příjemce u prodeje nebo z adresy použité lokace u nákupu.
Pátý krok – zadání předpokládaného počtu kilometrů a hmotnosti:
Založený požadavek se objeví v pultu dispečera dopravy ve stavu Nový.

### Příkazy k jízdě

**Vytvoření příkazu k jízdě**

Dispečer vyhodnocuje požadavky na dopravu nashromážděné v pultu dispečera dopravy a z těchto požadavků vytváří příkazy k jízdě. K tomu je určena funkce v pultu dispečera dopravy – tlačítko **Vytvoř příkaz k jízdě**. Příkaz k jízdě je touto funkcí založen a řádek požadavku v pultu dispečera je automaticky nastaven do stavu **Zaplánováno**.
Při tomto vytváření příkazů k jízdě se kontroluje, že řádek požadavku na dopravu je ve stavu **Nový**.
Stav jednotlivých požadavků je možné měnit i pomocí funkce **Změna stavu**.
(Příkazy k jízdě lze zakládat i z karty příkazu – pomocí CTRL + N nebo tlačítka Nový).
Příkazy k jízdě lze z pultu vytvářet také hromadně. Funkce Vytvoř příkaz k jízdě zpracuje všechny označené (vymodřené) řádky pultu s tím, že požadavky se stejným řidičem a vozidlem seskupí do jednoho příkazu (řidič a vozidlo je v hlavičce příkazu k jízdě).
Vytvořený příkaz k jízdě se vytiskne a přepne do stavu **Vydáno** pomocí tlačítka **Vydání**. Přitom se automaticky nastaví v pultu dispečera dopravy příslušný řádek do stavu **Uzavřeno**. Vydané příkazy k jízdě jsou dostupné v Oblasti/proPRODUKTIVITU/Doprava – Přehled vydaných příkazů k jízdě. 

### Přenos vydaných příkazů do knihy jízd

Modul nabízí užitečnou možnost hromadného naplnění knihy jízd z vydaných příkazů k jízdě. K tomu je určena v knize jízd funkce Navrhni příkazy. Uživatel zafiltruje požadované příkazy, typicky vyfiltruje vozidlo a datum.
Funkce naplní řádky knihy jízd a ty jsou připraveny k dalšímu zpracování a účtování.


## <a name="see-also"></a>Viz také  
[AC Productivity pack](ac-pp-productivity-pack.md)  