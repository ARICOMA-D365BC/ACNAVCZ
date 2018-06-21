---
title: "Fiscal Printers - VAROS"
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

# <a name="ac-fp-fiscal-printers"></a>Fiskální tiskárny
Add-on modul Fiskální tiskárny – VAROS slouží k vytvoření a tisku pokladního dokladu na fiskální tiskárně FT4000 firmy VAROS.
Při účtování primárních dokladů (faktura, objednávka, dobropis) s rozpisem platby (jedním či více typy úhrad) jsou automaticky vytvářeny fiskální položky a tyto jsou pak odeslány k tisku na fiskální tiskárnu. Předávané soubory jsou uloženy do složky na disku, odkud si je SW k tiskárně VAROS převezme a zpět vrátí soubor s potvrzením. 
K tisku na fiskální tiskárně dochází také při zaúčtování rozpisu platby na vytvořeném resp. zaúčtovaném dokladu (faktura, dobropis, záloha).
Rovněž všechny vklady a výběry hotovosti do registrační pokladny jsou evidovány a vytištěny na fiskální tiskárně.

## Instalace
**Objekty modulu**
Objekty modulu Více úhrad jsou označeny verzí 
**FP7.20 resp. pouze FP**. 
**Další součásti instalace**
Podmínkou provozování je minimálně edice Starte Pack a **modul 4050120 (Více úhrad)**.

## Nastavení
### Nastavení více úhrad
**Seznam platebních míst**
Nastavení je v Oblasti/proFINANCE/Fiskální tiskárny – Platební místa.
Zde je možné definovat seznam používaných platebních míst, přičemž jedno platební místo může zahrnovat více fiskálních tiskáren: 
**Seznam fiskálních tiskáren**
Nastavení je v Oblasti/proFINANCE/Fiskální tiskárny – Fiskální tiskárny
Zde je možné definovat používané fiskální tiskárny včetně jejich parametrů: 
Většina uvedených parametrů musí být shodně nastavena také v konfiguraci fiskální tiskárny. Jedná se o:
* Nastavení % DPH
* Text měny
* Umístění předávaných souborů pro registrační dávku, potvrzení a bloček.
* Prodlevu registrace
* Kód platebního místa
* Kód způsobu platby (hotovost) – tento kód je použit pro zadanou částku hotovosti v lokální měně na formuláři Rozpis platby.
* Čísla dokladů platby – není-li zadáno, použije se číselná řada z Nastavení více způsobů platby.
**Protiúčet pro vyrovnání**
Pro evidenci veškerých fiskalizovaných transakcí slouží Položky bankovních účtů. Nastavením takového účtu pro každou fiskální tiskárnu a typ platidla je pak možné provádět vzájemné odsouhlasení evidence z NAV a přímo z fiskálního modulu.
Nastavení je v Oblasti/Správa financí/Bankovní správa – Bankovní účty.
Zde je třeba vytvořit karty „bankovních účtů“ přináležející k fiskální tiskárně:
Vyplněním kódu fiskální tiskárny uživatel provede propojení, díky kterému částky.
Definice hodnot Typů platidel pro fiskální tisk:
1.	Hotovost
2.	Platební karta
3.	Stravenky
4.	Šeky
5.	Slovenská koruna
**Nastavení více způsobů platby**
Nastavení je v Oblasti/proFINANCE/Více úhrad – Nastavení více způsobů platby.

## Použití
### Operace podláhající fiskalizaci
Prodej
Při prodeji z prodejní faktury 
Prodej
Vklad/Výběr
### Tisk
**Daňový doklad**
Bloček vytištění fiskální tiskárnou je sám o sobě daňovým dokladem, popř. dokladem o úhradě faktury.
Modul neřeší případné úpravy standardních tiskových výstupů daňových dokladů (např. účtovaná prodejní faktura).
**Registrace platby**
Při účtování dokladu s rozpisem plateb , nebo při zaúčtování rozpisu platby na vytvořeném resp. zaúčtovaném dokladu, případně při účtování vkladu nebo výběru hotovosti do registrační pokladny je vytvořen soubor s registrační dávkou a uložen do definovaného adresáře.
Po zpracování souboru fiskální tiskárnou FT4000 je zpět vrácen soubor s potvrzením (bloček). 
Během zpracování jsou k fiskální položce doplněny tyto atributy:
* Datum a čas registrace	
* Registrační dávka
* Číslo bločku	
* Bloček


## <a name="see-also"></a>Viz také  
[AC Financial Pack](ac-fp-financial-pack.md)  