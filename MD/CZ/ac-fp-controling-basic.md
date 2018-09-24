---
title: "SADA ROZŠÍŘENÍ PRO FINANCE"
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

# <a name="ac-fp-controling-basic"></a>Sada rozšíření pro finance 

AddOn modul Controlling Basic – Sada Rozšíření aplikace obsahuje tyto funkcionality:
* Kontrola CreditCheck
* Úpravy v archivaci nákupních a prodejních dokladů - poslední archivovaný dokument
* Hierarchický návrh cen
* Splátkové kalendáře
* Spotřební daň
* Viditelný poplatek
* Vytváření webových zdrojů kontaktu
* Drobné úpravy běžně používaných reportů (finanční, účetní, bankovní, pokladní, majetek, nákupní, prodejní, skladové apod.)
* Úpravy pro nastavení parametrů plánovače úloh
* A řada dalších menších úprav, vylepšení a rozšíření

## Instalace

**Objekty modulu**

Objekty add-on modulu jsou označeny verzí CO.

## Funkcionality modulu

### Splátkové kalendáře

Funkcionalita Splátkových kalendářů je k dispozici v prodeji i v nákupu a její fungování je v obou oblastech obdobné. 
Ve splátkovém kalendáři můžeme použít funkci Navrhnout splátkový kalendář. 
Vyplníme pole:
* Počet splátek,
* Datum splatnosti první splátky,
* Periodu splátek.

Ve splátkovém kalendáři se automaticky vytvoří řádky.
Zaúčtovaná prodejní faktura:

* Na zaúčtované prodejní faktuře lze také použít funkci Splátkového kalendáře

### Creditcheck

Funkcionalita umožňuje získat důležité informace o partnerech. Informace jsou importovány přes webovou službu Creditcheck ERP. V databázi Creditcheck lze tedy prověřovat partnera bez přihlášení.
V Nastavení elektronické komunikace na záložce Kontrola CreditCheck je třeba vyplnit následující pole:
HTTP služby CreditCheck – webová adresa služby CrediCheck pro stažení dat:
http://creditwebservices.creditcheck.cz/CreditCheckAktualizace.asmx?op=GetCreditChecks

Nepoužívat kontakty pro CreditCheck - pokud firma nepoužívá kontakty je třeba zaškrtnout tento boolean. Pak se při stažení dat z CrediChecku budou plnit přímo pole Stav CreditCheck na kartě zákazníka, dodavatele.
Datum aktualizace Credit Check – poslední datum, kdy byla provedena aktualizace stavu CreditCheck.

V Nastavení uživatelů na záložce Obecné je nový boolean Povolit změnu stavu CreditCheck, který pokud jej má uživatel zaškrtnut, pak mu umožní zrušit naimportovaný stav.

### Kontroly směnných kurzů

Pro eliminaci rizika nesprávného zadání směnného kurzu a tudíž zaúčtování dokladu s nesprávným kurzem, byly do systému doplněny 2 nové kontroly.
Kontrola správnosti směnného kurzu.

Na kartě Měna lze definovat 2 nová pole 
* Dolní limit částky vzt. sm.kurzu
* Horní limit částky vzt. sm.kurzu

Je-li některé z nich vyplněno, pak systém provádí kontrolu:
* při vkládání hodnoty do Směnných kurzů, 
* při vkládání kurzu na nákupních, prodejních nebo servisních dokladech

## <a name="see-also"></a>Viz také  
[AC Financial Pack](ac-fp-financial-pack.md)