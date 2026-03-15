---
title: Függelék
layout: default
nav_order: 11
---

# Függelék

Ez a fejezet összegyűjti a TextBalance használatához szükséges kiegészítő információkat: rendszerkövetelményeket, támogatott Word verziókat, hibajelentési módot és licenc információkat.

---

## 1. Támogatott Platformok és Verziók

### Támogatott Windows Verziók

- Windows 7 Service Pack 1 vagy újabb
- Windows 10
- Windows 11

### Támogatott Microsoft Word Verziók

- Microsoft Word 2016
- Microsoft Word 2019
- Microsoft Word 2021
- Microsoft 365 (Office 365) Asztali kliens

**NEM támogatott:**
- Microsoft Word 2013 vagy korábbi. (VBA kompatibilitási problémák)
- Word Online (Böngészős verzió, VBA hiányában)
- Word Mobile (iOS / Android)
- macOS asztali kliensek (Az .exe fájl alapú telepítő miatt, bár maga a TextBalance VBA kód és .dotm fájl potenciálisan kompatibilis lehet, de hivatalosan nem támogatott).

---

## 2. Telepítési Részletek

### Telepítő Program
A TextBalance egy telepítőt biztosít (**TextBalance Setup.exe** néven). 
A telepítő egy NSI (Nullsoft Scriptable Install System) környezetből készült szkript, amely a következőket végzi:

1. Kikeresi a felhasználó meglévő Microsoft Word globális sablon (STARTUP) könyvtárát. (`%APPDATA%\Microsoft\Word\STARTUP`)
2. Kimásolja oda a legális `TextBalance.dotm` fájlt.
3. Beállít bizonyos regisztrációs kulcsokat annak érdekében, hogy a Word automatikusan engedélyezze a VBA futtatását erre a modulra.

Ezen automatizált rendszer következtében neked nincs is dolgod elhelyezni manuálisan a fájlokat, mint a korábbi "Bővítmények" esetében.

### Eltávolítás
Minden esetben asztali szoftverhez méltóan a Vezérlőpult - Programok Eltávolítása (*Add or Remove Programs*) listájából ki is jelölheted a szoftvert végleges, Word programot is feloldó törléseként.

---

## 3. Hibajelentés (Report an Issue)

Ha valamilyen rendellenességgel (Bug)  tallálkozol, nyugodtan jelentsd a nyílt forráskódú GitHub fejlesztő felületen as "Issues" szekcióként, amit a Ribbonon vagy az alábbi linkan is megtehetsz:

[https://github.com/textbalance/x/issues](https://github.com/textbalance/x/issues)

**Mit írj bele? Csatolj bizonyítékokat:**
1. Röviden mondd el, melyik környezetet használod (Pl. "Microsoft Word 2021, Win 11).
2. Tegyél ki egy képernyőfotót (Screenshot-ot) arrol az ablak hibaüzenetről, amit a *TextBalance Error* jelöl kék fejlécben.
3. Ird le, pontosan milyen szöveget vagy Word Formázást nyomtál elöbb a gombra nyomás pillanatában,  ugyanis 99%-ban a specifikusan a dokumentumodban létrejött egyedi eseményeket (pl. belehelyezett belső táblázat Címsor megjelölése) olvassa félre a TextBalance.

---

## 4. Licenc Információk

A TextBalance sablon és VBA forráskód a megengedő **MIT Licenc** alatt áll:

```
MIT License

Copyright (c) 2026

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

**Egy szóval:** 
Kereskedelmi célokra, szaktananyagokra, sőt a forráskódban lévő módosításokra is teljesen szabadon, de teher és következmények figyelembe vállalása nélkül használható a szoftver. Ahogyan is az írja, a projektet "AS IS" (ahogy van) alapon juttatják el számodra, garanciák nélkül. Mindig készíts biztonsági mentést.

---

## 5. Changelog / Változtatások

**v1.0 (Béta)** - Elsődleges kiadás

Véglegesített TextBalance funkciók:
- Dinamikus Ideal% betöltés a felhasználó szűnőjéből AutoSave rendszerrel.
- Automatikus Rejtett Szöveg használása Annotációhoz a láthatatlan jelenlétért felesleges tárolások helyett .
- AutoSave Toggle és Speech Time kapcsoló a dokumentum hosszosztásainak testreszabásáért.
- Ribbon (menüszalag) beágyazása a Wordbe, automatikus exés háttértelepítéssel.

---

## Visszatekintő: Gyors Linkek

Ezzel a dokumentáció fejezeteinek végére értél. Bízunk benne, hogy a TextBalance elősegíti a rendezettebb és átláthatóbb írói folyamataidat.
Ide kattintva bármikor visszaugorhatsz és felidézheted az alábbi lépéseket:

- → [Bevezetés és Példák]({% link index.md %})
- → [Sikeres Telepítés]({% link 03-telepites.md %})
- → [Melyik gomb mit tud]({% link 04-felület-részletes-ismertetése.md %})
- → [Nem működik? Keresd a megoldást]({% link 07-troubleshooting.md %})
