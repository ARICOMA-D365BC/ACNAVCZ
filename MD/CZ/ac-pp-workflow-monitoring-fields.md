---
title: "WorkFlow - Sledování polí "
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

# <a name="ac-pp-workflow-monitoring-fields.md"></a>WorkFlow - Sledování polí

Modul Workflow – sledování polí rozšiřuje funkčnost modulu Workflow – řízení stavů o automatické změny stavů workflow na základě změny hodnoty vybraných polí v tabulce.
V případě změny hodnoty pole systém automaticky vyvolá přednastavenou akci. Množinu sledovaných polí a vyvolávaných akcí je možné nastavit.

## Instalace

**Objekty modulu**

Objekty modulu Workflow – sledování polí jsou označeny verzí WF7.20 resp. pouze WF.
Seznam konkrétních objektů modulu je uveden v dokumentaci k aktuálnímu buildu add-on modulů.

**Další součásti instalace**

Modul Workflow – sledování polí vyžaduje instalovaný modul Workflow – řízení stavů.

## Nastavení

### Obecné

Po importu objektů modulu je třeba provést nastavení workflow.
Nastavení se provede v Oblasti/proPRODUKTIVITU/WorkFlow – Sledovaná pole workflow.

**Nastavení Workflow**

Sledovaná pole se nastavují k jednotlivým šablonám workflow a jejich stavům. Do tabulky se vyplní Kód šablony, Kód stavu, Číslo pole, Typ změny, Kód nového stavu, Nutno potvrdit nový stav, Spustit akce nového stavu, Kontrolovat pole v novém stavu, Nastavit pole v novém stavu a Potlačit protokol.
V poli Kód šablony se vyplní šablona workflow, pro kterou se budou změny testovat.
V poli Kód stavu se vyplní stav, který se bude na změnu testovat.
V poli Číslo pole se vyplní pole, které se bude na změnu testovat.
V poli Kód nového stavu se vyplní stav workflow, který se nastaví, jestliže v záznamu v daném stavu nastala změna v daném poli.
Typ změny určuje, jaká změna bude pro sledování relevantní:
* Libovolná
* Naplnění
* Přepsání
* Vymazání
V poli Nutno potvrdit nový stav se nastaví, zda uživatel musí potvrdit změnu stavu.
V poli Spustit akce nového stavu se určuje, zda se mají provést akce definované na novém stavu (např. zaslání e-mailu).
V poli Kontrolovat pole v novém stavu se stanoví, zda se provedou kontroly na testovaná pole definovaná v novém stavu.
V poli Nastavit pole v novém stavu se zadá, zda se mají provést změny definované v nastavovaných polích nového stavu.
V poli Potlačit protokol se nastaví, zda se má potlačit protokolování změn v protokolu změn workflow.
 
**Definice kontrolovaných polí**

Pro každý monitorovaný stav je možné nadefinovat pole, která se budou kontrolovat při monitorované změně. Kontrolovaná pole se definují na stránce Sledovaná pole workflow pod tlačítkem Auto. kontrolovaná pole. Pro kontrolované pole je nutné nadefinovat pole Číslo, Kontrola hodnoty a Hodnota.
Kontrola hodnoty udává jaký typ kontroly bude prováděn při nastavení daného stavu:
* Kód nutný – v poli musí být vyplněna libovolná hodnota,
* Stejný kód – v poli musí být vyplněna stejná hodnota jako je v poli Hodnota,
* Žádný kód – v poli nesmí být nic vyplněno.

**Definice nastavovaných polí**

Pro každý monitorovaný stav je možné nadefinovat pole, která se budou nastavovat při monitorované změně. Nastavovaná pole se definují na stránce Sledovaná pole workflow pod tlačítkem Auto. nastavovaná pole. Pro nastavované pole je nutné definovat jeho Číslo a Hodnotu.
V poli Hodnota se zadává, na jakou hodnotu se nastaví pole, když nastane daný stav workflow.

**Definice akcí**

V Akcích se definují Codeunity, Reporty a XMLPorty, které je možné spouštět při přechodu do dalšího stavu. V distribuci workflow je obsažena Codeunit 52068185 Workflow Mail pro zasílání mailu při změně stavu workflow. Další obdobné Codeunity pro jiné akce si může partner vytvářet sám dle vlastní potřeby v číslech objektů povolených jeho licencí.

**Definice přiřazení akcí**

Pro každý monitorovaný stav je možné nadefinovat akce, které se budou provádět při monitorované změně. Akce se definují na formuláři Sledovaná pole workflow pod tlačítkem Automatické akce. Pro Akce je nutné nadefinovat Kód akce a volitelně Číslo pole (hodnota) a Hodnotu.
V poli Číslo pole (hodnota) se definuje z jakého pole se vezme obsah a předá se jako parametr akci (např. při změně stavu workflow na kartě zákazníka je možné vyplnit číslo pole 102 a jako parametr se akci předá obsah pole E-Mail).
V poli Hodnota se zadává přímo hodnota, která se předá akci jako parametr (např. konkrétní e-mail).
 
## Použití

Sledování definovaných polí a spouštění nastavených akcí Workflow probíhá automaticky, bez zásahu uživatele.

## <a name="see-also"></a>Viz také  
[AC Productivity pack](ac-pp-productivity-pack.md)  