---
title: "Faktoring"
author: Autocont
ms.custom: na
ms.date: 04/13/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: dynamics-nav-2018
ms.translationtype: Human Translation
ms.sourcegitcommit:
ms.openlocfilehash:
ms.contentlocale: cs-cz
ms.lasthandoff: 03/27/2018

---

# <a name="ac-fp-faktoring"></a>Faktoring

Modul Faktoring rozšiřuje oblast Správy financí systému Microsoft Dynamics NAV o možnost evidence a účtování postoupení pohledávek a vytváření faktoringových smluv.

## Instalace

**Objekty modulu**

Objekty modulu faktoring jsou označeny verzí **FC7.10** resp. pouze **FC**.

**Další součásti instalace**

Modul Faktoring nevyžaduje další součásti instalace.

## Nastavení

### Obecné

Po importu objektů je třeba provést nastavení modulu faktoring. Základní nastavení se provede v Oblasti/proFINACE/Faktoring.
Pro správnou funkci modulu Faktoring je nutné provést následující kroky:
* V účtové osnově založit finanční účty pro sledování postoupených pohledávek a nákladové a výnosové účty pro přeúčtování faktoringu (volitelně)
* Založit účto skupiny pro faktoring
* Přiřadit účto skupiny pro faktoring
* Nastavit účtování faktoringu
* Vytvořit šablonu pro faktoringové smlouvy

### Založení účtů v účtové osnově

Aktualizace účtové osnovy se provádí v Oblasti/Správa financí/Finance/Účetní osnova. Ve formuláři Účetní osnova lze zadat finanční účty potřebné pro účtování faktoringu.

### Založení účto skupiny pro faktoring

Účto skupiny se nastavují v Oblasti/Správa/Nastavení aplikace/Správa financí/Účto skupiny – Účto skupiny zákazníků. 
Ve formuláři Účto skupiny zákazníků lze zadat účto skupiny, které se použijí pro zaúčtování faktoringu.

### Nastavení náhradních účto skupin zákazníka

Formulář Náhrady účto skupin zákazníka se nachází na formuláři Účto skupiny zákazníka na záložce Navigace, volba Náhrady.
Nastavením kombinace hodnot polí Náhradní účto skupina zákazníka a Účto skupiny zákazníka definujeme Číslo účtu, na které se bude účtovat v souvislosti s faktoringem.

### Nastavení faktoringu

Formulář Nastavení faktoringu je v Oblasti/proFINANCE/Faktoring – Nastavení faktoringu.
Na formuláři Nastavení faktoringu je potřeba provést následující nastavení:
* Účto skupina faktoringů: účto skupina, která je použita při účtování faktoringové pohledávky
* Protiúčet nákladů: účet, na který se zaúčtuje pohledávka za zákazníkem
* Protiúčet výnosů: účet na který se zaúčtuje výnos z faktoringu
* DPH účto skupina zboží: zde je třeba nastavit DPH účto skupinu zboží, která v kombinaci s DPH obchodní účto skupinou ze zákazníka-faktora reprezentuje účtování bez DPH
* Přeúčtovat původní položku: volba ANO umožňuje dále sledovat pohledávku za původním zákazníkem na podrozvahových účtech
* Účto skupina přeúčtování a Protiúčet přeúčtování:  podrozvahové účty, na kterých se bude dále sledovat pohledávka k původnímu zákazníkovi
* Čísla faktoringů: číselná řada, kterou budou faktoringy číslovány

### Tvorba dokumentu faktoringu

Je možné definovat šablony pro převod faktoringových smluv do dokumentů Microsoft Word.
Dokument vytvoříme na kartě faktoringu pomocí funkce **Vytvořit dokument faktoringu** na kartě **Navigace**.
Na záložce **Možnosti** vybereme potom v poli **Šablona Word** příslušnou šablonu, podle které chceme dokument vygenerovat.

## Použití

### Pořízení dokladu faktoringu

Formulář dokladu faktoringu je umístěn v Oblasti/proFINANCE/Faktoring/Přehled faktoringů. Do hlavičky dokladu je nutné vyplnit pole **Zákazník-číslo** (Číslo faktora) a **Zúčtovací datum**.
Konkrétní pohledávky / závazky, které mají být postoupeny, lze vybrat pomocí polí **Typ položky** a **Číslo položky**. Pokud se jedná o regresní faktoring, faktor může pohledávku/závazek vrátit, musí být zaškrtnuto pole **Regresní faktoring** na řádku dokladu.

### Zaúčtování faktoringu

Před zaúčtováním dokladu faktoringu je třeba doklad vydat – tlačítko **Vydat** na záložce Akce. (Ctrl + F9). Účtování dokladu se prování přes tlačítko **Účto** (F9). Po zaúčtování vznikne doklad **Zaúčtovaný faktoring**, ten lze najít v Oblasti/proFINANCE/Faktoring/Přehled zaúčtovaných faktoringů.
Řádky dokladu Zaúčtovaný faktoring jsou rozděleny do třech záložek:
* Pohledávky – postoupené položky
* Faktoring pohledávky – nově vzniklé položky zákazníka k faktorovi
* Platby – položky typu platba, které vyrovnávají faktoringové pohledávky
Účtováním faktoringu jsou uzavřeny původní položky zákazníka / dodavatele a k faktorovi jsou zaúčtovány nové pohledávky. Finanční účtování je určeno **Účto skupinou Faktoringu** z Nastavení faktoringu (v tomto případě – FAKTORING). 
Pokud je v Nastavení faktoringu zapnuté **Přeúčtovat původní položku**, vznikne u původního zákazníka / dodavatele nová zákaznická / dodavatelská položka. Ta umožňuje sledovat saldo původních zákazníků / dodavatelů včetně postoupených dokladů. Finanční účtování je určeno **Účto skupinou přeúčtování** z Nastavení faktoringu (v tomto případě – PŘEÚČTO.F.). V Nastavení Náhrad účto skupin zákazníka by pro tuto účto skupinu měl být nastaven podrozvahový účet. Podrozvahová položka je uzavřena v okamžiku uzavření faktoringové pohledávky.
Finanční účtování v závislosti na nastavení systému může mít následující dopad do účetní osnovy (příklad postoupení jedné položky s přeúčtováním na podrozvahový účet).

### Vrácení faktoringové pohledávky

Pokud se jedná o regresní faktoring, faktor může pohledávku vrátit, musí být doklad zaúčtován se zaškrtnutým pole **Regresní faktoring** na řádku dokladu.
Pro vrácení pohledávky je nutné v Zaúčtovaném faktoringu zvolit akci **Vrátit pohledávku faktoringu**.
Po tomto příkazu systém odúčtuje nově vzniklou faktoringovou položku a naúčtuje ji zpět k zákazníkovi / dodavateli.

## <a name="see-also"></a>Viz také   
[AC Financial Pack](ac-fp-financial-pack.md)















