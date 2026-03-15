---
title: Haladó Funkciók
layout: default
nav_order: 6
---

# Haladó Funkciók

Ez a fejezet a TextBalance makró mélyebb működését és haladó használati módjait mutatja be.

---

## 1. Ideal Percentage Logika

### Automatikus Elosztás

Amikor még nincs beállított érték az `Ideal%` oszlopban a Summary Table-ben, a makró a TotalChar hosszt **automatikusan és egyenlően felosztja** annyi felé, ahány darab `Heading 1` stílus található a szövegben. 

### Scaling >100% Együttes Esetén

Ha módosítod a cellákat, és az összes `Ideal%` összege véletlen több lesz 100%-nál, a TextBalance arányosan leskálázza (Scaling) a beadott mutatóidat, hogy az mindig a TotalChar értékét (a 100%-ot) ossza vissza. Erre azért van szükség, hogy a TextBalance pontosan kalkulálhassa a tényleges túlfutásokat (a színek a táblázat háttérben kiszámolt és fixált valós 100%-ához mérten fognak kijelzésre kerülni a dokumentumon és Progress Barokon keresztül).

![Scaling example](assets/images/color-examples.png) 

### Részletes Színkód Logika és Limit Érték

A `Limit%` az eltérés toleranciaszintjét jelenti, amelyet te mondhatsz meg.

**Logikai számítások:**
- **Zöld (RGB 0, 128, 0):** `Actual% <= Ideal% + Limit%`
- **Narancs (RGB 204, 102, 0):** `Ideal% + Limit% < Actual% <= Ideal% + (2 * Limit%)`
- **Piros (RGB 204, 0, 0):** `Actual% > Ideal% + (2 * Limit%)`

Ha a Te elvárásod jóval szigorúbb, egyenként vagy megváltoztatva az egész táblázat Tolerancia határt (Limit cellába átírással) kisebb, például `3%` százalékos engedményeket tudsz beállítani.

---

## 2. Táblázat Mozgatása

A TextBalance Summary Table szabadon mozgatható a Word dokumentumon belül. 
Ha a Refresh gombot lenyomod a makró visszakeresi a "TotalChar" vagy "Total Char" elsősori nevet. 
- A táblázat a vágólappal új helyre került? Semmi gond! Ezen az új helyen fog módosulni a továbbiakban.
- Véletlenül ki is lett vágva / törölve teljes egészében? Egy kattintás a Refresh-re, a számítási mód újragenerálódik! *(De ügyelj rá: az előzőekben általad fixált manuális AutoSave nélküli egyedi szűrések a törlés után visszaállnak a nullára.)*

**Szigorú szabály:** Soha ne módosítsd vagy formázd át a táblázat első sorában található `"TotalChar"` betűkaraktertípust vagy a belső értékek táblázatát! Ezzel automatikusan "kikapcsol" a frissítés és újat hoz létre a meglévő mellé.

---

## 3. Orphan Text (Árva szöveg) problémája

Árva szöveg (Orphan Text) olyan szövegtartalom a munkában, amelyet **közvetlenül egy Heading 1 után kezdtél írni**, de amely után **nem kezdődött alcím (Heading 2)**. 
A TextBalance a Progress Baron ezt úgy mutatja majd be, mint az összes többi létező felbontás nélküli szöveget – ami azt sugallhatja hogy pontatlan a felosztás és értelmetlen szakaszba csöppent az olvasó. Javasoljuk tehát az első Heading 1 utána egyből egyértelmű Alcímmel jelezni magát a szakasz bekezdését (Például: "Bevezető"). 

---

## 4. Custom Heading Styles (Egyedi Stílus) használata

Ha nem szeretnéd az "alapértelmezett Word gyári kék" Headings kinézetet meghagyni, módosítsd bátran a `Styles` bekezdésekkel. De figyelj a legfontosabb "Rule of Thumbs"-ra. Egyedi stílus készítésekor: a Stílusnak feltétlen **"Style Based on: Heading 1"** vagy **"Heading 2"** osztályzónak kell érvényesülnie a paraméterek során. 
Ha beállítod, hogy "Based on: Normal/Normál Folyószöveg" – makró nem fog tudni mihez viszonyítani! Címsorokat ezután nem regisztrál magába, a táblázat összeomlik!

---

## 5. Progress Bar Vizuális működése (Heading 2)

A `Level 2` felett kialakuló sáv egy 40 karakterből álló felülnézet, ami a Főcím aránylagos belső testvérértékét szimbolizálja és 3 szimbólum elemből töltheti ki a felületeket.
* [Tele Blokk]: A Jelenlegi alcím szakasza.
* [Közepes Árnyékolás]: A többi fejezeti alcím szakasza / Árva szöveg.
* [Üres Blokk]: Felesleges még be nem írt szakasz. 

Amikor a teljes arányszám be lett érve és kész a szerkezet, ezek az értékek fognak fixálódni!

---

## 6. H3 és További Címsorok (Hiánya)

A TextBalance fejlesztése során az egyszerűség döntötte el az irányvonalak fókuszát. A makró **szándékosan hagyja figyelmen kívül a H3+** (Level 3, stb.) Címsorokat. Ezeknek a hierarchikus felöleléseknek megvan az a terhük, hogy aprólékos "túlteljesedést" végezzen az olvasó és zavaros lesz tőlük a Táblázaton lévő kód is. Használd a Level 2-eket (és a "Normál vastag betű" opciókat az apró albekezdésekre) a munka fókuszálásához!

---

**Kapcsolódó témák:**
- [Word Címsorok Alapjai – "Based on" Koncepció]({% link 02-word-headings-alapjai.md %}#4-based-on-koncepció--kritikus-tudnivaló)
- [Troubleshooting – Címsorok nem észlelhetők]({% link 07-troubleshooting.md %}#2-címsorok-nem-észlelhetők)
