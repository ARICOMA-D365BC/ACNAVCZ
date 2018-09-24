---
title: "WorkFlow - řízení stavů"
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

# <a name="ac-pp-workflow-status-management.md"></a>WorkFlow - Řízení stavů

Modul Workflow – řízení stavů přidává do systému Microsoft Dynamics NAV nástroje pro řízení stavů při postupném zpracování úloh jedním či více uživateli. Umožňuje konfigurovat stavy zpracování, ve kterých se může úloha (doklad, záznam) nacházet. Sledovat aktuální stav a průběh zpracování a následně automatizovaně vyplňovat formuláře a záznamy definovanými hodnotami či spouštět libovolné programové akce při změně stavu úlohy. Uplatňuje se zejména pro řízené schvalování a oběh dokladů. Jedná se o obecný nástroj použitelný na libovolném místě (kartách resp. tabulkách) systému.

## Instalace

**Objekty modulu**

Objekty modulu WorkFlow – řízení stavů jsou označeny verzí WF7.10.
Seznam konkrétních objektů modulů je uveden v dokumentaci k aktuálnímu buildu add-on modulů.

**Další součásti instalace**

Modul nevyžaduje pro instalaci žádné další součásti.

### Napojení do aplikace

**Úpravy tabulek**

Do tabulky, do které se doplňuje workflow, je třeba založit 2 nová pole Pole musí mít čísla 61400 a 61401. Dále je do tabulky nutné přenést funkce. V tabulce 52068180 Workflow Setup je nutné pro každé použití workflow vytvořit pole, v němž se bude parametrizovat šablona workflow pro každé konkrétní použití workflow. Ve funkci SetDefaultStatus je třeba změnit následující řádky na konkrétní pole z tabulky 52068180:
* lreSetup.TESTFIELD("Workflow Template");
* "Workflow Template Code" := lreSetup."Workflow Template";
Do triggeru OnInsert je třeba přenést kód, který zajišťuje nastavování výchozího stavu.

**Úpravy formulářů**

Na formuláři musí být zobrazeno pole Workflow Status Code, které je v tabulce již vytvořeno. V triggeru OnAssistEdit je kód, který zobrazuje historii změn pole. Na formuláři je dále tlačítko Funkce, na němž je volba změna stavu. Toto tlačítko je možné zkopírovat do formuláře, na kterém je implementováno workflow – využívá funkcí, které jsou v tabulce již připraveny.

## Nastavení

### Obecné

Po importu objektů je třeba provést nastavení workflow.

**Nastavení workflow**

Nastavení se provede v Oblasti/proPRODUKTIVITU/WorkFlow - Nastavení Workflow.

**Založení šablony Workflow**

Pro správnou funkcionalitu je třeba vytvořit šablony workflow a přiřadit je jednotlivým implementacím workflow v systému.
Nastavení šablon workflow pro jednotlivé implementace workflow v aplikaci se provede v menu Oblasti/proPRODUKTIVITU/WorkFlow – Šablony workflow.

V šabloně se zadá Kód, Popis a Číslo tabulky, pro kterou je tato šablona určena. Volitelně lze také zapnout logování změn pro dané workflow a používání poznámek workflow.
Pod tlačítkem Stavy workflow se definují jednotlivé stavy workflow.
Pro stav workflow je třeba nadefinovat Kód, Popis a Filtr dalšího stavu, který určuje, do jakých dalších stavů je možné z daného stavu přejít. Jeden ze stavů v každé šabloně musí být označen jako Výchozí stav – ten se vyplní při založení řádku v tabulce, ve které je implementováno workflow. Některé stavy mohou být označeny jako Konečný stav, z něhož se už nepokračuje do dalšího stavu.

**Definice kontrolovaných polí**

Pro každý stav je možné nadefinovat pole, která se budou kontrolovat při přechodu do daného stavu. Kontrolovaná pole pro aktivní řádek se definují pod tlačítkem Kontrolovaná pole. 
Pro kontrolované pole je nutné vyplnit Číslo pole, Kontrolu hodnoty a příp. Hodnotu. Kontrola hodnoty udává, jaký typ kontroly bude prováděn při nastavení daného stavu:
* Kód nutný – v poli musí být vyplněna libovolná hodnota;
* Stejný kód – v poli musí být vyplněna stejná hodnota jako v poli Hodnota;
* Žádný kód – v poli nesmí být nic vyplněno.
 
**Definice nastavovaných polí**

Pro každý stav je možné nadefinovat pole, která se budou nastavovat při přechodu do tohoto stavu. Nastavovaná pole pro aktivní řádek se definují pod tlačítkem Nastavovaná pole. Pro nastavované pole je nutné vyplnit jeho Číslo a Hodnotu. V poli Hodnota se zadává na jakou hodnotu se nastaví pole při přechodu na daný stav workflow.

**Definice akcí**

V Akcích se definují Codeunity, Reporty a XMLPorty, které je možné spouštět při přechodu do dalšího stavu. V distribuci workflow je obsažena Codeunit 52068189 Workflow Mail with Confirm pro zasílání mailu při změně stavu workflow. Další obdobné Codeunity pro jiné akce si může partner vytvářet sám dle vlastní potřeby v číslech objektů povolených jeho licencí.

**Definice přiřazení akcí**

Pro každý stav je možné nadefinovat akce, které se budou provádět při přechodu do daného stavu. Pro Akci je nutné nadefinovat Kód akce a je možné nadefinovat Číslo pole (hodnota) a Hodnota. V poli Číslo pole (hodnota) se definuje z jakého pole se vezme obsah a předá se jako parametr akci (např. při změně stavu workflow na kartě zákazníka je možné vyplnit číslo pole 102 a jako parametr se akci předá obsah pole E-mail). V poli Hodnota se zadává přímo hodnota, která se předá akci jako parametr (např. konkrétní e-mail).

Pod tlačítkem Texty mailu je možné definovat obsah mailu (předmět a vlastní text). Do textu je možné vkládat kódy, které se při odeslání mailu nahradí obsahem polí. Kódy se definují pod tlačítkem Pole mailu.

**Podmíněné workflow**

V systému lze definovat podmínky, za kterých se provede:
* Akce workflow
* Nastavovaná pole
* Kontrolovaná pole
 
Význam jednotlivých hodnot pole Kontrola hodnoty:
* <prázdný> - řádek podmínky není uplatňován
* Kód nutný – pro splnění podmínky je vyžadována neprázdná hodnota v definovaném poli
* Stejný kód – pro splnění podmínky je vyžadována stejná hodnota jako v poli Hodnota
* Žádný kód – pro splnění podmínky je vyžadována prázdná hodnota v definovaném poli
* Filtr – pro splnění podmínky je vyžadováno, aby hodnota v definovaném poli spadala do filtru v poli Hodnota
* Vzorec data (prac.datum) – pro splnění podmínky je vyžadováno, aby datum v definovaném poli odpovídal datu vypočtenému z pracovního data a datového vzorce v poli Hodnota
* Vzorec data (sys. datum) – pro splnění podmínky je vyžadováno, aby datum v definovaném poli odpovídal datu vypočtenému ze systémového data a datového vzorce v poli Hodnota

## Použití

### Použití workflow

Na stránce, pro kterou je implementováno workflow, je k dispozici funkce Změna stavu, jejímž prostřednictvím uživatel volí další stav workflow. Po spuštění této funkce se zobrazí okno s nabídkou stavů, do kterých je možné přejít z aktuálního stavu.

**Protokol změn workflow**

Pokud byla při definici šablony workflow nastavena volba Logovat změny, jednotlivé změny stavu jsou zaznamenány v Protokolu změn workflow. Protokol změn workflow zachycuje kdy, kým a jaká změna stavu workflow byla provedena.

## <a name="see-also"></a>Viz také  
[AC Productivity pack](ac-pp-productivity-pack.md)  