---
title: Technikai Információk
layout: default
nav_order: 10
---

# Technikai Információk

Ez a fejezet a TextBalance belső működését mutatja be technikai részletességgel. Ha szeretnéd megérteni, hogyan működik a makró "motorháztető alatt", itt megtalálod a válaszokat.

---

## 1. Adattárolás

### Custom Document Properties

A TextBalance a **Custom Document Properties** (Egyéni Dokumentum Tulajdonságok) rendszerét használja az adatok tárolására.

**Mit tárol:**
A `ConfigManager.bas` modul a következő Document Properties-eket kezeli:
- `TextBalanceFirstRun` (Boolean)
- `TextBalanceUserTotal` (TotalChar)
- `AutoSave` (Boolean string)
- `DisplaySpeechTime` (Boolean string)
- `SpeechTempo` (Integer string)

Ezek a dokumentumban tárolt metaadatok, és a szöveg kimentése, illetve megosztása után is megőrződnek. Belső memóriában őrzött értékek.  
*(Az Ideal%-ok csak magában az Összefoglaló Táblázatban - a felhasználó elől nem rejtetten -  kerülnek rögzítésre).*

### Mikor Mentődnek az Adatok?

**AutoSave ON esetén:**
Minden **Refresh után** a TextBalance automatikusan elmenti a **teljes dokumentumot** (az `ActiveDocument.Save` VBA parancs meghívásával). 

**AutoSave OFF esetén:**
Nem történik automatikus mentés. A Document Properties is csak akkor íródik be véglegesen a fájlba, amikor te rányomsz a mentésre (Ctrl+S).

---

## 2. Színkód Logika

### RGB Színkódok

A TextBalance `Constants.bas` modulja standard RGB értékeket használ a rejtett szöveg színezéséhez:

**Zöld (Megfelelő):**
`RGB(0, 128, 0)`

**Narancs (Közel a határhoz):**
`RGB(204, 102, 0)`

**Piros (Túllépés):**
`RGB(204, 0, 0)`

---

## 3. Bar Karakterek (Progress Bar)

### Unicode Karakterek

A Heading 2 melletti vizuális Progress Bar fix hosszúságú (alapértelmezetten 40 karakterből áll) és standard Unicodes szimbólumokból generálódik:

**Használt karakterek (`Constants.bas`):**
- Tele blokk (Aktuális alcím szakasz): `█` = U+2588 (FULL BLOCK)
- Fél blokk (Többi alcím): `▓` = U+2593 (DARK SHADE)
- Üres blokk (Hátralévő rész a Főcímsor alapján): `░` = U+2591 (LIGHT SHADE)

---

## 4. VBA Modulok Szerkezete

A TextBalance VBA kódja specifikus modulokba van szervezve egy hatékony feldolgozási logika láncolatában.

### Modul Lista

**Fájlnév: TextBalance.dotm**
(STARTUP mappában vagy a globális makrók között helyezkedik el)

- `Main.bas`: A Ribbon gombokhoz kapcsolódó fő belépési pontok. (Refresh, Toggle funkciók)
- `TableManager.bas`: A Summary Table megtalálása, létrehozása, írása.
- `AnnotationManager.bas`: Rejtett szöveg és progress bar hozzáadása, színezése és törlése.
- `HeadingProcessor.bas`: Elemzi a dokumentum Heading 1 és 2 címeit, gyűjti azok méretét és a teszi a matematikai arányló számítást.
- `ConfigManager.bas`: Betölti és menti a Custom Document Properties adatokat.
- `Constants.bas`: Állandók tárolása (színkódok, Progress Bar unicode karakterek, betöltési szintek)
- `ErrorManager.bas`: Hibák elkapása (try-catch), és figyelmeztető ablakok megjelenítése a felhasználónak.
- `UIHelpers.bas`: Welcome dialog, Target length input, Tutorial és egyéb felhasználói dialógusok megjelenítése.
- `clsHeadingInfo.cls` és `clsSiblingInfo.cls`: Osztályok a heading adatstruktúra tárolásához.

---

## 5. Teljesítmény és Használati Korlátok

A Microsoft Word natív módszerével a TextBalance `Range` objektumokkal hajtja végre a műveleteket. Minden frissítéskor (Refresh) végigmegy a Range iterációin. 

### Teljesítmény (Várható értékek):

Kisebb dokumentumokban ez mindössze töredék másodperceket vesz igénybe.
Nagyobb, 100-200 oldalas dokumentumokban, ahol sűrű Címsorokat (100+) használsz, egy-egy `Refresh` frissítés 2-5 másodpercbe is telhet, sőt, bekapcsolt `AutoSave` ON állapotában a Windows a dokumentum merevlemezre írása miatt ezt tovább növeli.

**Lassúság fő okozója (Track Changes)**: A TextBalance működéséhez a bekapcsolt Word "Track Changes" (Korrektúra) mód egy iszonyatos teher. Minden újratesztelésnél és átírásnál a Word nyomon szeretné a törölt és újonnan újraírt statisztikákat fogni, amely lefagyasztja a programot. Emiatt a TextBalance `Refresh` folyamata azonnal letiltja ezt és üzenettel figyelmeztet. 
Kérjük, kapcsold ki a Word korrektúra módját a frissítések idejéig!
