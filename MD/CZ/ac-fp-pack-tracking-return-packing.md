---
Title: "Evidence vratných obalů"
Description: 
Author: AUTOCONT
Date: 14/02/2019
Product: dynamics365-business-central
Contentlocale: cs-cz
---

# <a name="fp-pack-tracking-return-packing"></a>Evidence vratných obalů

Add-on modul Evidence vratných obalů je rozšířením modulu Zásoby. Umožňuje sledování oběhu vratných obalů a paletového hospodářství. Lze pomocí něj sledovat obalová salda obchodních partnerů s vazbou na příslušné obchodní transakce (Nákup, Prodej, Příjem, Výdej, Transfer, Spotřeba a Výroba) a dále pak sledovat aktuální cenu obalů.

## Nastavení

### Obecné

Po importu je třeba provést nastavení vratných obalů.
Pro správnou funkci vratných obalů je nutné provést následující nastavení:
* Nastavit výpočtové vzorce a číselné řady
* Založit kategorie vratných obalů
* Založit šablony deníků vrat. obalů

Prvními kroky v nastavení je definice výpočtových vzorců a nastavení čís. řady v Nastavení vratných obalů. Pomocí vyhledávací funkce **Řekněte mi, co chcete udělat (Alt + Q)** vyhledejte **Nastavení vratných obalů**.


* **Vzorec data plat. v prodeji** – vzorec pro výpočet expirace návratu vratného obalu od zákazníka
* **Vzorec data plat. v nákupu** – vzorec pro výpočet expirace návratu vratného obalu dodavateli
* **Bezpečná doba pro vrácení** – maximální možný časový úsek procesu navrácení vratného obalu dodavateli. Datum platnosti musí být menší nebo roven rozdílu max. data platnosti a bezpečné doby pro vrácení.
* **Nevyrovnávat prodej. položky** – volba vypne automatické vyrovnání položky vrat. obalu při dobropsání (prodej)
* **Nevyrovnávat nákup. položky** – volba vypne automatické vyrovnání položky vrat. obalu při dobropsání (nákup)
* **Vyrovnávat dle plátce** – volba nastavuje vyrovnávání položek vrat. obalů dle plátce uvedeného na prodejním dokladu. V případě, že tato volba není zaškrtnuta, provádí se vyrovnání dle zákazníka.
* **Vyrovnávat dle věřitele** – volba nastavuje vyrovnávání položek vrat. obalů dle věřitele uvedeného na nákupním dokladu. V případě, že tato volba není zaškrtnuta, provádí se vyrovnání dle dodavatele.
* **Vyrovnávat dle zboží** – volba nastavuje vyrovnávání položek vrat. obalů dle zboží, které je svázáno s daným vratným obalem. V případě, že tato volba není zaškrtnuta, provádí se vyrovnání dle vratného obalu.

Pro správnou funkci je též nutno nastavit číselnou řadu vratných obalů.
Dalším krokem je nastavení kategorií vratných obalů. Pomocí vyhledávací funkce **Řekněte mi, co chcete udělat (Alt + Q)** vyhledejte **Kategorie vratných obalů**. Kategorie vratných obalů slouží k filtraci v přehledových funkcích a tiskových sestavách.

Šablony deníků slouží k předpřipravení deníků pro účtování o vratných obalech (jedná se o obdobnou funkčnost jako šablony deníků zboží). Pomocí vyhledávací funkce **Řekněte mi, co chcete udělat (Alt + Q)** vyhledejte **Šablony deníku vratných obalů**.

### Nastavení karet vratných obalů

Po výše uvedeném nastavení je nutno zadat karty vratných obalů.

Každá Karta vratného obalu obsahuje tato pole:
* **Číslo** – číslo z číselné řady vratných obalů
* **Popis** – název vratného obalu
* **Kód kategorie vrat. obalu** – identifikace kategorie vratného obalu
* **Vyhledávací popis**
* **Pohyb** – needitovatelné pole z odkazem do tabulky „Položky vratných obalů“. Zde zobrazená hodnota udává stav salda vratných obalů.
* **Vzorec data platnosti v prodeji** – vzorec pro výpočet expirace návratu vratného obalu od zákazníka
* **Vzorec data platnosti v nákupu** – vzorec pro výpočet expirace návratu vratného obalu dodavateli
* **Uzavřeno** – pole pro uzavření (zamezení) dalšího použití dané karty vratného obalu

Nastavené hodnoty mají v případě, že jsou vyplněny, přednost před obecným nastavením.
Z karty je dále možno zobrazit Přehled všech vratných obalů, Položky a každé kartě je možno přiřadit Poznámky.

## Použití

### Vytváření položek vratných obalů

Předpokládané využití Deníků vratných obalů je pro provádění oprav, korekcí a zadání počátečních stavů salda obalů.

Pozor, při použití volby **Oprava** v deníku vratných obalů není při účtování prováděno párování položek dle nastavených kritérií.

Přehled položek vratných obalů je dostupný pomocí vyhledávací funkce **Řekněte mi, co chcete udělat (Alt + Q)**, vyhledejte **Položky vratných obalů**.

Kromě jiných polí je u položek vratných obalů pole **Datum platnosti**, které je využíváno při výpočtech a návrzích vyrovnání vratných obalů. Toto pole je editovatelné. Při změnách však jeho hodnota nesmí přesáhnout datum maximálního možného návratu vratného obalu:
* na řádku nákupu: **Datum platnosti = Max. datum platnosti = Zúčtovací datum + Vzorec data plat. v nákupu**
* na řádku prodeje: **Datum platnosti + Bezpečná doba pro vrácení ≤ Max. datum platnosti (Datum platnosti = Zúčtovací datum + Vzorec data plat. v prodeji)**

Při každém účtování položky vratného obalu je vytvořen záznam v Žurnálu vratného obalu (obdoba Žurnálu zboží).

### Saldo vratných obalů zákazníka

Pro zjištění salda vratných obalů daného zákazníka slouží tisková sestava Saldo vratných obalů zákazníka. Pomocí vyhledávací funkce **Řekněte mi, co chcete udělat (Alt + Q)** vyhledejte **Saldo vratných obalů zákazníka**.
V nabídce **Možnosti** je třeba zvolit, zda se má tisknout saldo obalů dle Zákazníka nebo Plátce.

### Saldo vratných obalů dodavatele

Pro zjištění salda vratných obalů daného dodavatele slouží tisková sestava Saldo vratných obalů dodavatele.
V nabídce **Možnosti** je třeba zvolit, zda se má tisknout saldo obalů dle Dodavatele nebo Plátce.

## <a name="see-also"></a>Viz také  
[AC Financial Pack](ac-fp-financial-pack.md)  