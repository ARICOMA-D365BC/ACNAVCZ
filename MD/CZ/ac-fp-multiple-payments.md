---
title: "Více úhrad"
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

# <a name="ac-fp-multiple-payments"></a>Více úhrad

Modul Více úhrad rozšiřuje standard prodejních dokladů, kdy namísto jednoho způsobu platby je možné jich definovat více (např. část prodejního dokladu uhradit platební kartou a část hotově).
Na primárních dokladech (faktura, objednávka, dobropis) je v rozpisu platby možné definovat jeden či více typů úhrad (kódů způsobu platby) a tyto následně zaúčtovat (tzn. zaplatit doklad).
Obdobně lze provést zaúčtování rozpisu platby na vytvořeném resp. zaúčtovaném dokladu (faktura, dobropis, záloha).
Modul tvoří základ pro podporu maloobchodního prodeje formou Cash&Carry.

## Instalace

**Objekty modulu**

Objekty modulu Více úhrad jsou označeny verzí **FP**.

**Další součásti instalace**

Modul nevyžaduje pro instalaci žádné další součásti.

## Nastavení

### Nastavení více úhrad

**Nastavení více způsobů platby**

Nastavení je v Oblasti/proFINANCE/Více úhrad – Nastavení více způsobů platby.
V nastavení je možné definovat automaticky generovaný Kód způsoby platby (hotovost).
Dále je možné nastavit, zda má být kontrolováno přiřazení fiskální tiskárny k bankovnímu účtu (má význam při použití modulu Fiskální tiskárny).
Na záložce **Číslování** lze nastavit číselnou řadu pro doklady platby.

## Použití

### Použití více úhrad

**Rozpis platby**

Na nezaúčtovaných dokladech – Prodejní objednávka, Prodejní faktura, Prodejní dobropis je tlačítko Rozpis platby. Také na zaúčtovaných dokladech – Účtované faktury, Účtované dobropisy. Dále na Prodejní zálohové faktuře.
V rozpisu platby lze definovat více kódů způsobu platby a uhradit tak celou částku dokladu.

**Kód fiskální tiskárny** slouží k odfiltrování kódů způsobů platby příslušné fiskální tiskárně.
Do pole **Částka hotovosti (LM)** vloží uživatel částku hotovosti, kterou od zákazníka obdržel.
Pole **Vrátit hotovost (LM)** obsahuje částku, kterou má pokladní vrátit zákazníkovi.
Tlačítko Účtovat umožní zaúčtovat doklad a spárovat platbu s primárním dokladem.


## <a name="see-also"></a>Viz také  
[AC Financial Pack](ac-fp-financial-pack.md) 