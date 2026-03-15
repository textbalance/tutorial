# TextBalance Tutorial → GitHub Pages Webhely

## Összefoglaló

Az AI-generált 11 részes tutorial átalakítása GitHub Pages weboldalra (Just-the-Docs témával), tartalmi hibák javításával, emojik eltávolításával, redundáns tartalom rövidítésével.

---

## Javítandó hibák

### Szisztematikus cserék (mind a 11 fájlban)

| Hibás | Helyes |
|---|---|
| `CharCounter` | `TextBalance` |
| `bővítmény` | `makró` |
| emojik (✅❌🟢🟠🔴🎨🔢🎯📘🌐🔗📊💾🗑️📝❓🎤⚙️) | eltávolítás, szöveges megoldás |

### AutoSave leírás javítása

**Hibás (tutorialban):** "Ideal%-okat menti Custom Document Properties-be"  
**Helyes:** Minden Refresh után automatikusan menti a dokumentumot (`ActiveDocument.Save`), így nem kell külön Ctrl+S.

### Telepítés javítása (03-telepites.md)

- ZIP fájl kibontás → **NSI .exe telepítő** (automatikusan kicsomagol és futtatja a HTA-t)
- macOS telepítési leírás → **törlés**

### RGB színek javítása

| Tutorial | Helyes (Constants.bas) |
|---|---|
| Zöld: RGB(146,208,80) | RGB(0,128,0) |
| Narancs: RGB(255,192,0) vagy RGB(255,140,0) | RGB(204,102,0) |
| Piros: RGB(255,0,0) | RGB(204,0,0) |

### Egyéb javítások

- VBA modul struktúra (10. fejezet): valós fájllistára cserélés
- Ribbon csoportok: Feedback csoport hozzáadása
- macOS-re vonatkozó részek törlése (08-gyik, 11-fuggjelek)
- Párbeszédablak szövegek egyeztetése a valós UIHelpers.bas-szal
- Word 2010/2013 támogatás eltávolítása (csak 2016+ marad)
- Redundáns tartalom, túlmagyarázás rövidítése

---

## Just-the-Docs konfiguráció

- [_config.yml.txt](file:///d:/Desktop/TextBalance/installer%20proba/HUN%20-%20tutorial/_config.yml.txt) → `_config.yml` (kiterjesztés javítás)
- Dark/light mode: `color_scheme: nil` + egyéni toggle JS
- Front matter hozzáadása minden [.md](file:///d:/Desktop/TextBalance/installer%20proba/HUN%20-%20tutorial/08-gyik.md) fájlhoz (`title`, `nav_order`, `layout`)
- Link formátum javítás

---

## Szükséges screenshotok és videók

> [!IMPORTANT]
> Az alábbiakat neked kell elkészítened, mert a makró futtatását és a Word felületet nem tudom szimulálni.

### Screenshotok (PNG)

| Fájlnév | Mit mutasson | Melyik fejezethez |
|---|---|---|
| `ribbon-tab.png` | TextBalance tab a ribbonon (Main, Remove, Help, Feedback csoportok) | 03, 04 |
| `welcome-dialog.png` | Első futtatás üdvözlő ablak | 03 |
| `target-length-dialog.png` | Target Document Length input box | 03 |
| `install-success.png` | Telepítés sikeres üzenet | 03 |
| `tutorial-dialog.png` | "Quick tutorial?" kérdés | 03 |
| `summary-table.png` | Összefoglaló táblázat a dokumentum tetején | 04, 05 |
| `heading-annotation.png` | Heading 1 annotáció (ID, char, %) | 04 |
| `progress-bar.png` | Heading 2 progress bar | 04 |
| `color-examples.png` | Zöld/narancs/piros példák egymás alatt | 04 |
| `remove-confirm.png` | Remove Everything megerősítő dialógus | 04 |
| `styles-panel.png` | Word Styles panel Heading 1/2 kiemelve | 02 |
| `navigation-pane.png` | Word Navigation Pane heading-ekkel | 02 |
| `installer-exe.png` | Az exe telepítő ablaka | 03 |

### GIF animációk

| Fájlnév | Mit mutasson | Melyik fejezethez |
|---|---|---|
| `first-run.gif` | Teljes első futtatás (Welcome → Target → Eredmény) | 03 |
| `refresh-cycle.gif` | Szöveg írása → Refresh → Táblázat/annotáció frissülés | 04, 05 |
| `edit-ideal.gif` | Ideal% szerkesztése a táblázatban → Refresh → Szín változás | 05 |
| `speech-time-toggle.gif` | Speech Time be/kikapcsolás | 04 |
| `apply-heading.gif` | Heading 1 stílus alkalmazása szövegre | 02 |

---

## Verification Plan

- Push GitHub-ra → GitHub Pages build ellenőrzés
- Böngészőben: sidebar navigáció, keresés, dark/light toggle, linkek
