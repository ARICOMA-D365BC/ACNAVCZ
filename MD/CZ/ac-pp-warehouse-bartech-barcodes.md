---
title: "Řízení čárových kódů"
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

# <a name="ac-pp-warehouse-bartech-barcodes.md"></a>Řízení čárových kódů
Add-on v Microsoft Dynamics NAV byl zpracován pro zvýšení produktivity práce skladníka, který provádí skladové operace ať už na základě existují-cích objednávek, nebo vytváří jednoduché doklady dle aktuální potřeby. 
Předpokladem použití funkčnosti je definice čísel čárových kódů v křížo-vých odkazech pro karty zboží.
Add-on podporuje sledování zboží dle sériových čísel nebo sledování čísel šarží.
Celé řešení se skládá z:
* Add-on Warehouse Bartech Barcodes, který zajišťuje funkčnost zpracování dokladů a operací v Microsoft Dynamics NAV.
* Aplikace Mobilní skladník UNI, která je instalována 
a)	 na PC a zajišťuje přenos dat mezi terminálem a uložištěm dat odkud si následně přebírá Microsoft Dynamics NAV
b) do terminálu čtečky, kde umožňuje zpracován jednotlivých skladových operací
* Terminál – fyzické zařízení k vlastnímu provádění skladové čin-nosti pracovníkem ve skladech.
Add-on umožňuje provádění vybraných skladových operací: 
* Jednoduché doklady pro příjem, výdej, převod mezi sklady a in-venturu (deníky zboží)
* Příjem a výdej vytvářený dle objednávky (prodejní a nákupní ob-jednávka, prodejní a nákupní objednávka vratky, objednávka spo-třeba a objednávka transferu)
K přenosu dat mezi dtb Microsoft Dynamics NAV a aplikací zpracovávající data z terminálů slouží samostatná dtb SQL.

## Instalace
**Objekty modulu**
Objekty add-on modulu Warehouse Bartech Barcodes jsou označeny verzí MSU.
**Další součásti instalace**
Add-on modul vyžaduje pro instalaci aplikace Mobilní skladník UNI. V rámci dokumentace této aplikace je popsána také instalace SQL dtb a nástroje pro synchronizaci dat mezi terminálem čtečky a samotnou dtb.
K funkčnosti je nutná granule 4120 Item Cross References.

## Nastavení
Informační systém poskytuje číselníky skladů (včetně přihrádek pokud jsou použity), karet zboží, čárových kódů ve vazbě na MJ a definici použitelných řad dokladů pro zpracování v terminálu. V případě, že v terminálu probíhá zpracování na základě objednávek, jsou také z informačního sys-tém exportovány řádky příslušných dokladů. 
Data poskytnuta informačním systémem jsou zapsána do odpovídajících tabulek samostatné SQL dtb určené pro Mobilního skladníka UNI.
Data po zpracování v terminálu jsou zpětně zapisována do SQL dtb odkud jsou přebírána do MBS NAV a zpracována na základě definice příslušné skladové operace (řady). 
Proces zpracování jednotlivých skladových operací je identifikován pomocí „řad“. Každá řada má v Microsoft Dynamics NAV vlastní nastavení, které specifikuje, jak provedená akce v terminálu, bude zaznamenána v informačním systému.
### Nastavení a číselníky
**Nastavení MSU**
Oblasti – proPRODUKTIVITU – Řízení čárových kódů – Nastavení – Nastavení MSU
**Aktivace MSU**
Volba, která aktivuje celý modul pro zpracování skladových operací pomocí ter-minálů čteček čárových kódů.
**Logovat zpracování spooleru**
Toto nastavení aktivuje zápis do logu událostí systému windows (pro aplikace) v případě, že se provádí synchronizace MSU přes Navision Spooler.
* **Verze SQL serveru** – zadejte verze SQL serveru, na kterém je umístěná dtb pro MSU. Addon komunikuje s SQL serverem verze 2000, 2005 nebo 2008.
* **SQL server** – zadejte odkaz na SQL server
* **SQL databáze** – zadejte jméno dtb pro zápis skladových operací provedených terminálem čtečky
* **Windows přihlášení** – zadejte, pokud ověření přihlášení do dtb je provedeno řadičem domény systému Windows
* **SQL název uživatele** – zadejte ID uživatele v případě, že není použito Windows přihlášení
* **SQL heslo** – zadejte heslo v případě, že není použito Windows přihlášení
* **Způsob připojení** - toto nastavení ovlivňuje, zda komunikace s SQL serverem probíhá přímo, nebo přes rozhraní ODBC. Výchozí nastavení je „SQL Native Client“. V případě nefunkčnosti nativního připojení je třeba změnit na „SQL Ole DB“
**Lokace**
V rámci nastavení lze vybrat lokace, které budou použité při zpracování operací pomocí terminály. Výběr lokace pro takové použití je prováděn zaškrtnutím pole MSU Export. 
Pro jednotlivé lokace lze definovat, zda export karet zboží bude obsahovat ak-tuální stav zásob (i ve vazbě na přihrádky, pokud jsou pro danou lokaci použity) či nikoliv. Pokud informace aktuálního stavu zásob nebude v terminálu využívá-na, doporučuje se vzhledem k časové náročnosti výpočtu parametr MSU počítat množství nepoužít.
**Čárové kódy**
Z Microsoft Dynamics NAV jsou exportovány pouze karty zboží s naplněným čáro-vých kódem v tabulce Křížový odkaz zboží. Zboží bez definovaného čárového kó-du nelze v terminálu zpracovat.
**Karta řady**
Jedná se o číselník definující způsob, jakým bude operace při importu do Micro-soft Dynamics NAV zpracována. Při evidenci každé operace v terminálu čtečky dochází k přiřazení konkrétní řady (buď pracovníkem skladu pokud se jedná o jednoduchý doklad nebo automaticky pokud se jedná o operaci na základě ob-jednávky).
* **Kód** – identifikace řady 
* **Typ** – typ operace. V souladu se členěním aplikace Mobilní skladník jsou možné hodnoty: „Vstupní“, „Výstupní“, „Přeřazení“ a „Inventura“. 
Typ Přeřazení je specifickým typem zpracování jednokrokového přesunu zboží mezi sklady, které Microsoft Dynamics NAV zpracuje pomocí deníku přeřazení. 
Typ inventura je určen pouze pro zaznamenání fyzické inventury, která je v Microsoft Dynamics NAV zpracovaná zápisem množství fyzické inventu-ry do předchystaného deníku fyzické inventury. 
Ostatní operace se dělí na vstupní a výstupní na základě toho, zda se jed-ná o úbytek zboží ze skladu nebo přírůstek.
Všechny typy operací pracují s přihrádkami. 
* **Popis** – popis operace 
* **Viditelný kód** – slouží pro definici kódu, který se zobrazuje uživateli při výběru řady v terminálu
* **Oprava** – definuje způsob vložení množství při importu do NAV (je-li hod-nota Ano, vkládá se množství s opačným znaménkem) a skladový záznam bude označen příznakem Oprava  
* **Účtovat** – parametr, který určuje, zda skladové operace mají být účtovány současně s importem do systému, nebo zda jsou pouze zaznamenány in-formace o zpracovaném množství a zaúčtování skladového pohybu již zů-stává na ručním zpracování uživatelem. 
* **Doklad tvořit** – rozlišuje, zdali je řada definována pro volné použití (uživa-tel prostřednictvím terminálu naplní deník zboží) nebo zda jsou doklady v terminálu tvořeny na základě objednávek z NAV (v tom případě se impor-tem aktualizují data na příslušných dokladech). Pro Typ "Přeřazení" a "In-ventura" je možná hodnota tohoto pole pouze "Volně"
* **Způsob zpracování množství** – parametr má význam pouze ve vazbě na typ dokladu vytvářený dle objednávky a určuje, zda zpracované množství na řádku dokladu bude přepisováno vždy s nově zpracovaným skladovým pohybem z terminálu, nebo zda bude množství připočítáváno k již zada-nému množství v polích K příjmu (nákupní objednávka, příjemka transfe-ru), K dodání (prodejní objednávka, dodávka transferu), Množ. vratky dodání (objednávka nákupní vratky), Množ. vratky příjmu (objednávka prodejní vratky) nebo K zaúčtování (objednávka spotřeby)
* **Šablona deníku zboží**, **List deníku zboží** – lze definovat šablonu a list dení-ku zboží pro doklady vytvářené volně 
* **Šablona skladového pohybu** – pro vybranou šablonu a list deníku zboží lze předdefinovat použití šablony skladového pohybu s předdefinovaným ty-pem a OOUSZ
* **Obecná obch. účtoskupina** – parametr je možné využít v případě, že OOUSZ není definována v rámci použité šablony skladového pohybu.
* **Kód údržby** – parametr je použit ve vazbě na skladové operace spojené s majetkem
* **Importovat číslo DM** – parametr je použit ve vazbě na skladové operace spojené s majetkem. Číslo DM je přenášeno z terminálu pomocí volitelné položky
Každá řada s použitým parametrem tvorby dokladu dle objednávky musí mít defi-nován typ dokladu dané operace. 
V levé části karty řady jsou volby pro typy dokladů implicitně zpracovávající úbytky ze skladu a v pravé části jsou typu dokladů pro přírůstky na sklad.
Filtry na záložce Obecné lze využít pro řady s typem dokladu dle objednávky, kdy řádky dokladů jsou exportovány z Microsoft Dynamics NAV jako podklad pro zpracování terminálem. Specifické filtry pro jednotlivé typy dokladů jsou uvedené na samostatných záložkách.
**Skladníci**
Přístup do terminálu čtečky a zpracování skladových operací lze svázat s informací o uživateli, který operace v terminálu provádí. Číselník skladníků lze zadat v Microsoft Dynamics NAV a exportovat do terminálu společně s ostatními číselní-ky. Číselník není povinný, záleží na nastavení aplikace Mobilního skladníka UNI.
### Synchronizace dat
Komunikace Microsoft Dynamics NAV s SQL serverem je řešena přes rozhraní ADO, které je součástí Microsoft Data Access Components (MDAC)
**Exporty**
Z Microsoft Dynamics NAV lze předávat do terminálu tři skupiny dat
* čárové kódy karet zboží společně se stavem skladu ve vazbě na MJ a event. přihrádku
* řádky objednávek, které slouží jako podklad pro zpracování. Může se jednat o řádky prodejních objednávek a objednávek vratek, řádky nákupních objednávek a objednávek vratek, řádky objednávek spotřeby a řádky objednávek dodávek a příjemek transferu.
* samostatné číselníky (skladníci, řady pohybů, lokace + přihrádky)
Export dat lze spustit ručně dle potřeby, nebo automatizovaně pomocí Shareplanu. Pro každou skupinu dat lze nastavit samostatnou úlohu sha-replanu a přiřadit periodu spouštění (např. číselníky je možné synchroni-zovat 1x denně a export objednávek každých 15 minut…)
**Importy**
Do Microsoft Dynamics NAV lze importovat pouze provedené skladové pohyby. Všechny importované skladové pohyby jsou zaevidované v tabulce Položky MSU.
Importy dat lze také spustit ručně dle potřeby, nebo automatizovaně pomocí Shareplanu. Úloze lze přiřadit periodu spouštění dle potřeby.
* **Kód řady** – identifikace řady, ve které byl doklad zaevidován. Dle nastavení řady v Microsoft Dynamics NAV bude příslušná operace zpracována
* **Číslo zboží** – číslo zpracovaného zboží pomocí terminálu čtečky
* **Množství** – zpracované množství pomocí terminálu čtečky
* **Kód měrné jednotky** – měrná jednotka skladové operace zboží
* **Kód lokace** – sklad, na kterém byla operace provedena
* **Kód přihrádky** – identifikace přihrádky v rámci skladového pohybu 
* **Typ dokladu** – informace o jaký typ zpracovávaného dokladu se jedná, pokud je doklad tvořen dle objednávky
* **Číslo dokladu a číslo řádku dokladu** – identifikace dokladu v případě, že skladový doklad byl zpracován na základě podkladu z NAV 
* **Stav zpracování** – Nový (), Zpracováno (skladový pohyb, kterého import proběhl bez chyb), Chyba (při zpracování došlo k chybě), Expirováno (skladový doklad ne-zpracován v IS a trvale vyřazen ze zpracování)
* **Datum zpracování** – evidence provedení importu skladového pohybu
* **Stav účtování** – evidence stav účtování skladového pohybu 
* **Kód pracovníka** – identifikace skladníka, který skladový pohyb v terminálu zazna-menal

## Použití
### Evidence importovaných skladových operací
Všechny skladové pohyby zaevidované a ukončené v terminálu jsou při importu do Microsoft Dynamics NAV ukládány do tabulky Položky MSU.
Formulář položek MSU nabízí možnost přímého zobrazení dokladu objednávky pomocí tl. Položka a volby Zobrazit doklad.
Zpracování jednotlivých skladových pohybů by mělo být průběžně kontrolováno, z důvodu možných chyb vzniklých při importu. V případě chybového stavu zpracování lze pomocí funkce Zpracovat položky zobrazit chybu, která způsobila, že položka nebyla zpracována. Po opravě příčin chybového stavu se lze pokusit položku touto funkcí opětovně zpracovat. 
Formulář umožňuje hromadné zpracování chybových položek pomocí „vymodření“ příslušných záznamů a spuštění funkce Zpracovat doklad.
### Operace pro navýšení množství na skladě
Navýšením množství na skladě (příjem) se v kontextu systému Microsoft Dynamics NAV může jed-nat o příjem, storno výdeje, nákupní příjemku, prodejní příjemku vratky, příjem transferu, výstup výroby, storno spotřeby výroby, výstup montážního dokladu, storno spotřeby montážního dokladu a storno spotřeby projektu.
Pomocí terminálů čteček čárových kódů lze zpracovat uvedené doklady vyjma dokladů týkající se výroby a montážního dokladu.
#### Jednoduchý doklad bez objednávky
Tvorba dokladů v terminálu je popsána v dokumentaci k aplikaci MSU
Jednoduchý doklad bez objednávky je v „řadách“ definován jako doklad zpracovaný v Microsoft Dynamics NAV pomocí deníku zboží. Na kartě příslušné řady je definice použití šablony a listu dení-ku zboží, nastavení šablony skladového pohybu…).
Je-li na příslušné řadě pro terminál nastaven parametr Účtovat, bude operace účtována současně s importem. Systém tak zaúčtuje skladový pohyb s ID uživatelem, s jehož přístupovými právy je spuštěn Aplikační server. Informaci o uživateli skladu, který skladovou operaci provedl lze nalézt v položkách MSU. 
Do řádku deníku je rovněž přebírána Obecná obchodní účto skupina, popř. Šablona skladového pohybu definovaná pro příslušnou řadu.
Tímto způsobem mohou být zpracovány doklady typu příjem nebo storno výdeje. 
Příklad definice řady pro skladové doklady typu příjem bez objednávky.
#### Operace pro snížení množství na skladě
Snížením množství na skladě (výdej) se v kontextu systému Microsoft Dynamics NAV může jednat o výdej, storno příjmu, prodejní dodávku, dodávku, nákupní dodávku vratky, dodávku transferu, spo-třebu, storno výroby, spotřebu montážního dokladu, storno výstupu montážního dokladu a spotře-bu projektu.
Pomocí terminálů čteček čárových kódů lze zpracovat uvedené doklady vyjma dokladů týkající se výroby a montážního dokladu. 
Proces zpracování je shodný s navýšením množství na skladě (viz předchozí kapitola).
Příklad definice řady pro skladové doklady typu výdej bez objednávky
Příklad definice řady pro skladové doklady typu výdej na základě objednávky
#### Skladové přesuny
Přesunem se v kontextu systému Microsoft Dynamics NAV jedná o přeřazení. To slouží jak k převodu mezi lokacemi, tak i z přihrádky na přihrádku v rámci téže lokace.
Doklad je vytvářen prostřednictvím terminálu dle aktuálních potřeb uživatele.
Zadané pohyby jsou importovány do NAV do deníku přeřazení s typem položky Transfer.
Příklad definice řady pro skladové doklady typu přeřazení
#### Inventury skladu
Standardní proces inventury se skládá z následujících kroků:
1.	Výpočet množství na skladě v Deníku fyzické inventury
2.	Tisk Seznamu fyzické inventury
3.	Provedení fyzické inventury ve skladu
4.	Zadání dat ze skladů do Deníku fyzické inventury
5.	Zaúčtování Deníku fyzické inventury
Mezi body 1 až 3 nesmí dojít k účtování přírůstků ani úbytků na inventarizované sklady.
Při použití terminálu je proces zpracování v Microsoft Dynamics NAV obdobný, pouze odpadá bod 2 a bod 4 není prováděn manuálně, nýbrž importem z terminálu.
Ve funkci Vypočítat množství zásob je na záložce Možnosti doplněn parametr pro vynulování pole množství fyzické inventury, který je potřeba zvolit při zpracování inventury pomocí terminálů. 
Příklad definice řady pro skladové doklady typu inventura:
Import skladových operací provedených terminálem čtečky provede zápis pole množství fyzické in-ventury v příslušném deníku dle definice řady.
#### Operace velkého skladu
Ve velkém skladu je příjem i výdej zboží dvoufázový. To znamená, že zboží se do skladu nejprve přijímá a následně až zaskladňuje. Obdobně se zboží ze skladu nejprve vyskladňuje a až následně se ze skladu dodává. Nyní je možné s aplikací Mobilní skladník postihnout i tyto procesy. Byla proto nově vytvořena synchronizace dvou dokladů a to vyskladnění a zaskladnění.
Po importu skladových pohybů systém doplňuje množství ke zpracování a kódy příslušných přihrádek do dokladů Zaskladnění a Vyskladnění. V případě vyskladnění jde o řádky typu Vzít, v případě zaskladnění jde o řádky typu Vložit.
#### Omezení funkcionality
Některé funkcionality či vlastnosti NAV nelze v souvislosti s integrací s aplikací Mobilní skladník využí-vat a naopak:
* MSU nepodporuje sledování sériových čísel zároveň se sledováním čísel šarží; pokud bude takto nastaveno v NAV, bude se v MSU jevit jako se sledováním SČ (v NAV musí uživatel při příjmu doplnit šarži ručně)
* NAV umožňuje definovat přihrádky jen pro některé operace. Integrace s MSU podporuje přihrádky pouze u lokací s povinným použitím přihrádek u všech operací (příznak Přihrádka nutná).
* MSU nepodporuje práci s variantami dle funkcionality NAV.
* Funkce pro zadávání data výroby při příjmu zboží se SČ či šarží není v NAV podporována (v NAV se sleduje Datum záruky, popř. Datum expirace).
* Možnost MSU vytvářet nákupní či prodejní operace (tedy se zadáním dodavatele či zákazní-ka) bez objednávky není v NAV podporována. Vždy budou vytvořeny položky zboží s typem Příjem nebo Výdej.
* Informace o čísle balíku ani o váze balíku z MSU nebude v NAV zaznamenána. Pouze pole EAN kód balíku se přenáší do pole Sledovací číslo zásilky v prodejní objednávce.
* V NAV není podporována funkcionalita MSU umožňující definovat různé přístupy pro různé skladníky, tzn. všechna data budou exportována tak, že k nim budou mít stejný přístup všichni uživatelé terminálů.
* V NAV není podporována funkcionalita MSU umožňující definovat libovolné volitelné para-metry. Vzhledem ke specifickému použití u každého zákazníka může být realizováno jako zá-kaznické řešení.
* Skladové doklady NAV jako Skladový přesun, Výstup výroby, Spotřeba do výroby, Výstup a storno montáže, Spotřeba a storno spotřeby montáže nejsou podporovány.


## <a name="see-also"></a>Viz také  
[AC Productivity pack](ac-pp-productivity-pack.md)  