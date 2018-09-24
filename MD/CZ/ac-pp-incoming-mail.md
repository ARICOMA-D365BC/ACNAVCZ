---
title: "Evidence doručené pošty"
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

# <a name="ac-pp-incoming-mail.md"></a>Evidence pošty

Modul Evidence pošty rozšiřuje oblasti Nákupu a prodeje systému Microsoft Dynamics NAV o podporu evidence doručené a odeslané pošty. Evidovanou poštu je možné řízeně zpracovávat pomocí Workflow, provázat s nákupními či prodejními doklady a prostřednictvím modulu Publikování SharePoint připojit ke kartě evidované pošty naskenovaný či elektronicky přijatý dokument.

## Instalace

**Objekty modulu**

Objekty modulu Evidence pošty jsou označeny verzí **DP7.00**.
Seznam konkrétních objektů modulu je uveden v dokumentaci k aktuálnímu buildu add-on modulů.

**Další součásti instalace**

Modul nevyžaduje pro instalaci žádné další součásti.

**Provázanost s dalšími moduly**

Pro řízené zpracování záznamů v modulu Evidence pošty je potřeba využít modul Workflow – řízení stavů. Pro připojení libovolných souborů (scan, e-mail, fax) k evidované poště je třeba využít modul Publikování SharePoint.

## Nastavení

**Obecné nastavení**

Po importu objektů je třeba provést základní konfiguraci modulu Evidence pošty prostřednictvím Šablon evidence pošty v Oblasti/proPRODUKTIVITU/Evidence pošty.
Dále lze v nastavení uživatelů v Oblasti/Správa/Nastavení aplikace/Uživatelé/Nastavení uživatelů přiřadit Číslo zaměstnance pro potřeby modulu evidence pošty.
V Oblasti/Prodej a marketing/Nastavení/Nastavení šablon interakce lze určit šablony interakce pro došlou poštu a pro odeslanou poštu.

**Šablony evidence pošty**

Pro rozdělení pošty dle kategorií je třeba nastavit Šablony evidence pošty v Oblasti/proPRODUKTIVITU/Evidence pošty – Šablony evidence pošty. 

Pro každou šablonu je nutné zvolit Typ pošty (Došlá, Odeslaná), vybrat Číselnou řadu a Kód šablony workflow.
Poznámka: pro evidování změněných stavů workflow na Kartě evidence pošty na záložce Stav, je třeba mít v Šabloně workflow nastavenou Akci Workflow s Typem objektu Codeunit – 52067961 WriteStatusChangeMailRec.

**Nastavení uživatelů**

V nastavení uživatelů v Oblasti/Správa/Nastavení aplikace/Uživatelé/Nastavení uživatelů lze uživateli systému zadat Číslo zaměstnance z tabulky Zaměstnanci.

V případě, že je Číslo zaměstnance zadáno, při výběru ID další zodpovědné osoby na Kartě došlé pošty na záložce Stav se předvyplní Kód další zodpovědné osoby.

**Nastavení šablon interakce**

V Oblasti/Prodej a marketing/Nastavení/Nastavení šablon interakce lze vybrat Šablonu interakce pro Došlou poštu a Odeslanou poštu.

Po spuštění funkce Vytvoř interakci na Kartě evidence pošty vznikne ke Kartě kontaktu odpovídající Položka protokolu interakce.

## Použití

### Karta evidence pošty

**Obecné**

V menu Oblasti/proPRODUKTIVITU/Evidence pošty – Evidence pošty se po výběru šablony evidence pošty zobrazí Přehled evidence pošty. Z Přehledu evidence pošty mohu otevřít existující Kartu evidence pošty nebo založit novou kartu pomocí tlačítka Nový.

**Záložka Obecné**

Po zadání standardních dat v hlavičce dokladu uživatel zadá:
* Částku včetně DPH – pouze evidenční pole, zobrazené v Pultu evidence pošty, viz dále
* Částku bez DPH – pouze evidenční pole
* pole Stav slouží pro použití Workflow, k dispozici volby: Nový, Čeká na schválení, Schváleno, Zamítnuto, Zaúčtováno

**Záložka Související došlý doklad**

Slouží pro evidenci jak nezaúčtovaných tak zaúčtovaných dokladů. Došlý doklad je možno připojit, odpojit nebo vytvořit.

**Vytvořit doklad**

Tato funkce se nachází na záložce Akce pod tlačítkem Vytvořit doklad.

Po úspěšném vytvoření dokladu se uživateli zobrazí hláška s číslem vytvořeného dokladu.
Do hlavičky vytvořeného dokladu se přenesou údaje z hlavičky Karty evidence pošty. Údaje z řádků Karty evidence pošty se nepřenáší.

**Přiložení dokumentů**

Pomocí modulu Publikování SharePoint lze v Kartě evidence pošty Publikovat a Zobrazit dokument. (tlačítko Publikovat a tlačítko Zobrazit na záložce Navigace).

### Pult evidence pošty

**Pult evidence pošty**

V menu Oblasti/proPRODUKTIVITU/Evidence pošty – Pult evidence pošty je možné pracovat s Pultem evidence pošty, tj. řádkové zobrazení Karet evidence pošty.

Standardním způsobem je možné karty evidence pošty filtrovat. Pomocí tlačítek Změna stavu, Navigovat nebo Vytvořit interakci lze pracovat s poštou shodným způsobem jako z Karty evidence pošty. 
Pult evidence pošty zobrazuje pouze neuzavřené Karty evidence pošty.

### Karta uzavřené evidence pošty

**Karta uzavřené evidence pošty**

V Oblasti/proPRODUKTIVITU/Evidence pošty/Uzavřené evidence pošty se nachází historie Karet evidence pošty, které byly uzavřeny pomocí tlačítka Uzavřít evidenci pošty.

## <a name="see-also"></a>Viz také  
[AC Productivity pack](ac-pp-productivity-pack.md)  