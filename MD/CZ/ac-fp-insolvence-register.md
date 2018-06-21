--- 
title: "Insolvenční rejstřík"
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

# <a name="ac-fp-insolvenční-rejstřík"></a>Insolvenční rejstřík

Add-on Insolvenční rejstřík slouží k evidenci záznamů z  https://isir.justice.cz o insolvenčním řízení společností. Je nástrojem pro další akce s kontakty společnosti, které jsou v insolvenčním řízení, např. při zadávání prodejních dokladů, jejich účtování (dodání, fakturace). Poskytuje vybraným osobám společnosti aktuální informace o nových záznamech v insolvenčním rejstříku.

## Instalace

**Objekty modulu**

Objekty add-on modulu Insolvenční rejstřík jsou označeny verzí IR4.10 resp. pouze IR. Seznam konkrétních objektů modulu je uveden v dokumentaci k aktuálnímu buildu add-on modulů.

**Další součásti instalace**

Add-on modul vyžaduje pro instalaci tyto další add-on moduly: 
* AC4005390	Spooler – komunikace s veřejnou databází IR
* Komunikace s veřejnou databází IR probíhá prostřednictvím veřejné webové služby na adrese: https://isir.justice.cz:8443/isir_ws/services/IsirPub001
* V rámci infrastruktury musí být proto povolena komunikace na portu 8443. 
* Pro automatizované zpracování je potřebná instalace aplikačního serveru Microsoft Dynamics NAV.

**Provázanost s dalšími moduly**

Pro automatické upozorňování formou reportů zasílaných emailem je potřeba aplikační server a add-on modul:
* AC4003720	Plánovač SharePoint

## Nastavení

### Nastavení Spooleru

 Pro import záznamů z webového portálu Insolvenčního rejstříku je potřeba nastavit:
* Agenta - agent pro příjem záznamů z IR do databáze NAV
* Úlohu spooleru
Nastavení se provede v menu Správa > Nastavení aplikace > Spooler > Agenti.
Komunikace s veřejnou databází IR probíhá prostřednictvím veřejné webové služby na adrese:
https://isir.justice.cz:8443/isir_ws/services/IsirPub001
Tato adresa je zadána jako parametr komunikace agenta pro příjem záznamu IR.
Správa >  Nastavení aplikace > Spooler > Úlohy spooleru

### Nastavení insolvenčního rejstříku

V Nastavení insolvenčního rejstříku jsou k dispozici tyto položky:
**Číslo poslední akce** – poslední použité ID z tabulky Akce insolvenčního rejstříku.
**Aktualizovat Stav řízení ins.rejstříku** – definuje, zda workagent bude automaticky doplňovat tabulku (číselník) „Stav řízení insolvenčního rejstříku“ při příjmu akcí IR.
**Aktualizovat Typ události insolventního rejstříku** - definuje, zda workagent bude automaticky doplňovat tabulku (číselník) „Typ události insolvenčního rejstříku“ při příjmu akcí IR.

## Práce s Insolvenčním rejstříkem

### Obecné

Funkcionalita Insolvenčního rejstříku je k dispozici v hlavní nabídce modulu Prodej a marketing.
Evidence o probíhajících IR je v systému k dispozici na:
* Kartě věci insolvenčního rejstříku
* Kartě kontaktu
* Kartě dodavatele
* Kartě zákazníka
* Kartě nastavení společnosti

### Karta věci insolvenčního rejstříku

Karta věci insolvenčního rejstříku poskytuje uživateli přehled o všech probíhajících událostech jednoho insolvenčního řízení. Součástí údajů jsou také informace o jménech dlužníků, správců, stavu řízení, datumech a časech zveřejnění, apod. 
Záložka **Obecné** obsahuje ručně editovatelnou položku **„Stav věci“** [option = Otevřeno, Uzavřeno]. Odpovědná osoba ve společnosti tedy bude moci po vlastním uvážení rozhodnout, zda některá insolvenční řízení uzavře prostřednictvím nastavení pole Stav Věci = Uzavřeno.
Kromě toho karta obsahuje pole **Zkontrolováno**, kde uživatel ručně zaškrtne, že provedl kontrolu. 
Záložka **Správce** obsahuje informace o správci IR (jako jméno, adresu, IČO, DIČ, rodné číslo).
Řádky Karty věci insolvenčního rejstříku zobrazují data z tabulky 4003802 Událost insolvenčního rejstříku. Hodnoty v řádcích jsou seskupeny do záložek dle hodnoty oddílu (A,B,C,D,P) v tabulce Událost insolvenčního rejstříku. Číselné pořadí řádku znamená pořadí v konkrétní záložce.
Na kartě věci IR lze z **tlačítka Věc** zobrazit následující údaje:
* Přehled F5 
* **Osoby** – obsahuje informace o osobách zainteresovaných v řízení konkrétní věci insolvenčního řízení. Pro osoby je možné zobrazit jejich adresy. 
Rozeznáváme 2 druhy role v řízení: 
* Správce
* Dlužník
**Tlačítko Řádek** obsahuje možnost **„Zobrazit dokument“** připojený ke konkrétnímu řádku. Jeho umístnění je definováno ve sloupci ID dokumentu. Dokumenty nejsou uloženy v systému. V řádcích je pouze odkaz na soubor ve veřejné databázi IR. 

### Evidence insolventního řízení u kontaktu

Karta kontaktu je na tlačítku Kontakt > Insolvenční rejstřík doplněna o možnost zobrazit evidenci insolvenčních řízení týkající se dané firmy nebo osoby. Identifikace probíhá na základě údaje IČO nebo rodného čísla. 
Karta kontaktu dále obsahuje indikátor počtu záznamů v tabulce Věc IR. Indikátor je umístěn vedle ikony poznámek (tužka) a umožňuje zobrazení evidence IR daného kontaktu. 
Indikátor zobrazuje 3 možné stavy:
* Bez záznamu (nezobrazuje se nic)
* Existují uzavřené záznamy v IR (zobrazuje se „(0)“)
* Existují aktivní (neuzavřené) záznamy v IR (zobrazí se např. „(2)“ – číslo představuje počet otevřených záznamů IR)

### Evidence insolvenčních řízení u karty zákazníka

Karta zákazníka je na tlačítku Zákazník > Insolvenční rejstřík doplněna o možnost zobrazit evidenci insolvenčních řízení. Identifikace probíhá na základě údaje IČO nebo rodného čísla. 
Karta dále obsahuje stejný indikátor počtu záznamů v tabulce Věc IR jako je na kartě kontaktu.

### Evidence insolvenčních řízení u karty dodavatele

Karta dodavatele je na tlačítku Zákazník > Insolvenční rejstřík doplněna o možnost zobrazit evidenci insolvenčních řízení. Identifikace probíhá na základě údaje IČO nebo rodného čísla. 
Karta dále obsahuje stejný indikátor počtu záznamů v tabulce Věc IR jako je na kartě kontaktu.

### Evidence insolvenčních řízení u informací o společnosti

Karta informace o společnosti je na tlačítku Společnost > Insolvenční rejstřík doplněna o možnost zobrazit evidenci insolvenčních řízení týkající se vlastní společnosti. Identifikace probíhá na základě údaje IČO.
Karta dále obsahuje stejný indikátor počtu záznamů v tabulce Věc IR jako je na kartě kontaktu.

### Možnost vypnout test na insolvenci 

Z výkonnostních důvodů je možno kontrolu insolvenčního rejstříku u vybraných kontaktů (např. zahraničních) vypnout. Pro tyto účely slouží boolean „Vypnout test na insolvenci“.
Boolean je umístněn na záložce Zahraniční obchod na Kartě kontaktu, Kartě zákazníka a Kartě dodavatele.
Hodnota booleanu se validuje z Karty kontaktu na Kartu zákazníka a/nebo na Kartu dodavatele a naopak. 
V procesu kontroly insolvenčního rejstříku u Karet kontaktů nebude NAV procházet ty karty, které mají boolean „Vypnout test na insolvenci“ – ANO. V tom případě dochází k ignoraci karty věci insolvenčního řízení, nezobrazí se indikátor počtu insolvenčních řízení, účtování probíhá běžně. 

## Práce s IR v prodejních dokladech

### Nastavení Prodeje a pohledávek

V Nastavení prodeje a pohledávek je možné definovat chování systému s ohledem na záznamy v insolvenčním rejstříku.
Pole **„Kontrola při insolvenci“** [option = „prázdný“, Upozornění, Blokace] spolu s polem „Blokování účtování při insolvenci“ určuje chování systému takto:
**„prázdný“** – kontrola je vypnuta 
**Upozornění** – při účtování je zobrazen formulář s upozorněním, že „Zákazník má záznam v IR, s dotazem zda chce uživatel pokračovat ANO/NE“. Formulář zobrazuje počet otevřených/uzavřených záznamů IR.
**Blokace** – není možné zaúčtovat dodání, fakturu, nebo oboje dle nastavení pole **„Blokovat účtování při insolvenci**. 
Pole **„Blokovat účtování při insolvenci“** [option = „prázdný“, Dodat, Fakturovat, Vše] – spojené s vybraným option v poli „Kontrola při insolvenci“
**„prázdný“** – blokace je vypnuta 
**Dodat** – na prodejním dokladu není možné zaúčtovat dodání pokud má zákazník otevřený záznam v IR. 
**Fakturovat** – na prodejním dokladu není možné zaúčtovat fakturu pokud má zákazník otevřený záznam v IR. 
**Vše** – na prodejním dokladu není možné zaúčtovat dodání ni fakturu pokud má zákazník otevřený záznam v IR. 

### Upozornění na prodejních dokladech

Při vložení zákazníka na prodejní doklad (objednávka, faktura, nabídka) bude v případě, že má Zákazník záznam v insolvenčním rejstříku zobrazen formulář s informacemi o počtu otevřených a uzavřených záznamů v IR. 
Upozornění je zobrazeno pro zákazníky se stavem IR Otevřeno i Uzavřeno. 

### Účtování prodejních dokladů

Dle Nastavení prodeje a pohledávek bude systém v případě existence otevřených záznamů daného zákazníka v insolvenčním rejstříku upozorňovat nebo zcela blokovat účtování dodání a fakturace.
Blokaci je možné na prodejním dokladu uvolnit prostřednictvím pole  „Povolit účtování při insolvenci“. Pole se nachází ve formuláři Prodejní objednávka na záložce Dodávky a ve formuláři Prodejní faktura na záložce Obecné.
Pole „Povolit účtování při insolvenci“ může zaškrtnout pouze uživatel, který má v uživatelských kontrolách nastaveno pole **„Povolit uvolnění blokace při insolvenci“**. 

## Reporty pro upozornění na Insolvenční řízení

### Obecné

V souvislosti s IR jsou k dispozici 2 základní reporty pro upozornění uživatelů na existenci IR u partnerů v databázi NAV a současně také pro případ podání IR na vlastní společnost.
* Kontrola insolvenčního rejstříku 
* Přehled prodejních dokladů v insolvenci

### Nastavení SharePlanu

Oba reporty je možné spouštět prostřednictvím Plánovače úloh na aplikačním serveru a automaticky je zasílat odpovědným osobám emailem. K tomu je potřebné vytvořit Kartu úlohy SharePlanu, intervaly v záložce Plánování a nastavit Parametry reportu. 
Na tlačítku **Úloha > Akce** lze definovat údaje pro zasílání reportu emailem. 

### Report Kontrola insolvenčního rejstříku

Report automaticky upozorňuje na vstup obchodního partnera (kontaktu/zákazníka/dodavatele) do insolvenčního řízení nebo na podání návrhu na insolvenční řízení vůči vlastní společnosti
Zdrojem dat je tabulka Věc insolvenčního rejstříku. V reportu je možné nastavit tyto parametry:
* Zpětně o – pole slouží pro zadání časového/datového intervalu, od kdy zpětně uživatel požaduje report zpustit. (je možné zadat datum, nebo hodnotu v podobě příznaku, např. 3D 5H = 3 dny 5 hodiny. Pro potřeby detailnějšího sledování insolvenčních řízení taky M=minuta, S=sekunda)
* Netisknout vlastní společnost – report nebude obsahovat záznam z IR, které bylo započato na vlastní společnost.
* Netisknout kontakt – report nebude obsahovat řádky kontaktu
* Netisknout zákazníka – report nebude obsahovat řádky zákazníka.
* Netisknout dodavatele - report nebude obsahovat řádky dodavatele.

### Report Přehled prodejních dokladů v insolvenci

Report automaticky upozorňuje na existenci prodejních dokladů v systému, u kterých má zákazník záznam v insolvenčním rejstříku a to:
* Nezaúčtovaných objednávek
* Otevřených položek zákazníka všech typů (faktura, platba, dobropis, upomínka, penále)
* Upomínek
* Penále
Zdrojem dat je tabulka Prodejní hlavička a Položka zákazníka. V reportu je možné nastavit tyto parametry:
* filtr dle údajů z karty zákazníka
* filtr dle údajů z hlavičky prodejních dokladů
* filtr dle údajů z položek zákazníka 
* Včetně uzavřených řízení – pokud je zaškrtnuto, zobrazí se i doklady pro zákazníky, kteří mají uzavřené záznamy v IR.

## <a name="see-also"></a>Viz také   
[AC Financial Pack](ac-fp-financial-pack.md)
