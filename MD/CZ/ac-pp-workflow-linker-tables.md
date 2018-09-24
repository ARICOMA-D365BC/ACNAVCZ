---
title: "WorkFlow - Kontrolované tabulky "
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

# <a name="ac-pp-workflow-linker-tables.md"></a>WorkFlow - Kontrolované tabulky

Modul Workflow – kontrolované tabulky rozšiřuje funkčnost modulu Workflow o možnost kontroly záznamů nebo polí v tabulkách svázaných s tabulkou, která je řízena workflow.
Je možné nastavit různé metody kontroly. Stav workflow je povoleno změnit pouze, pokud všechny kontroly v rámci kontrolovaných tabulek proběhnou úspěšně.

## Instalace

**Objekty modulu**

Objekty modulu Workflow – kontrolované tabulky jsou označeny verzí WF7.30.
Seznam konkrétních objektů modulu je uveden v dokumentaci k aktuálnímu buildu add-on modulů.

**Další součásti instalace**

Modul nevyžaduje pro instalaci žádné další součásti.
Modul Workflow – kontrolované tabulky vyžaduje instalovaný modul Workflow – řízení stavů.

## Nastavení

### Obecné

Po importu objektů modulu je třeba provést nastavení workflow.
Nastavení se provede v menu Oblasti/proPRODUKTIVITU/WorkFlow – Šablony workflow.
Pomocí tlačítka Stavy wokflow lze vybrat stav a dále pod tlačítkem Kontrolované tabulky lze nadefinovat konkrétní kontrolovanou tabulku.

**Definice kontrolovaných tabulek**

Pro každý stav workflow je možné nadefinovat kontrolu záznamů nebo polí v tabulkách svázaných s tabulkou, která je řízena WF.

Tabulka Kontrolované tabulky workflow umožňuje:
* Identifikaci tabulky pro kontrolu
* Nastavení pevného filtru pro kontrolovanou tabulku
* Identifikaci pole v tabulce a kontroly pole (Prázdný kód, Kód nutný, Stejny kód)
Nastavení metody kontroly:
* Alespoň jeden existuje – existuje alespoň jeden záznam v tabulce
* Alespoň jeden má pož.hodnotu - existuje alespoň jeden záznam v tabulce, který má ve vybraném poli definovanou hodnotu
* Všechny mají pož.hodnotu - všechny záznamy v tabulce mají ve vybraném poli definovanou hodnotu
* Neexistuje žádný - kontrola je úspěšná pouze pokud neexistuje žádný záznam v kontrolované tabulce (opak "Alespoň jeden existuje")
* Neexistuje žádný s hodnotou - kontrola je úspěšná pouze pokud neexistuje žádný záznam v kontrolované tabulce, který má ve vybraném poli definovanou hodnotu (opak „Alespoň jeden má pož.hodnotu“)
* V rámci změny stavu WF se provede kontrola, zda podřízené tabulky obsahují odpovídající data.
* Filtr na podřízenou tabulku se skládá z definovaných vazeb mezi tabulkami a pevného filtru nastaveného pro kontrolovanou tabulku
* Stav je povoleno změnit pouze pokud všechny kontroly vyhovují

**Podmínky kontroly dle svázaných tabulek**

Umožňuje spouštět kontrolu svázaných tabulek pomocí podmínek.

## Použití

Možnost kontroly záznamů nebo polí v tabulkách svázaných s tabulkou, která je řízena workflow.
* Pokud je workflow na dokladu s hlavičkou a řádky, lze kontrolovat, zda k hlavičce existují nějaké řádky, nebo řádky nějakého typu nebo obsahu. Např. že objednávka obsahuje alespoň jeden řádek se zbožím, nebo že má na všech řádcích vyplněnu cenu nebo lokaci nebo glob. dimenzi, apod.
* Lze kontrolovat, zda zdrojový záznam k nějakému poli v tabulce s použitým workflow obsahuje v dalších polích potřebná data – např. je-li na hlavičce dokladu vyplněno pole Kód prodejce, pak zkontroluje zda-li má tento prodejce vyplněn email.

## <a name="see-also"></a>Viz také  
[AC Productivity pack](ac-pp-productivity-pack.md)  