---
title: Word Címsorok Alapjai
layout: default
nav_order: 2
---

# Word Címsorok (Headings) Alapjai

A Microsoft Word címsorai sokkal többek, mint nagyobb, vagy vastagabb betűk. A dokumentum szerkezeti gerincét alkotják. A megfelelő használatuk elengedhetetlen a TextBalance makró helyes működéséhez.

---

## 1. Mi az a Heading a Wordben?

A Microsoft Wordben a címsorok előre definiált stílusok (Heading 1, Heading 2, Heading 3 stb.), amelyek hierarchikusan strukturálják a dokumentumodat.

**Hol találod őket:**
`Home fül → Styles csoport → Heading 1 / Heading 2 / Heading 3`

![Styles panel](assets/images/styles-panel.png)

A címsorok **szemantikusak** – a Word és a TextBalance makró is megérti a szerepüket a dokumentumban. Nem szabad összetéveszteni őket a kézi formázással (pl. Ctrl+B, nagyobb betűméret).

---

## 2. Miért fontosak a címsorok?

Azon túl, hogy a TextBalance erre épül, a címsorok számos előnnyel járnak:

### Automatikus Tartalomjegyzék
`References fül → Table of Contents → Automatic Table`
A Word automatikusan frissíti a tartalomjegyzéket az aktuális oldalszámokkal és címsorokkal.

### Navigációs Panel
`View fül → Navigation Pane checkbox`
![Navigation Pane](assets/images/navigation-pane.png)
Egy pillantással áttekintheted a dokumentum struktúráját, és gyorsan ugorhatsz vagy átrendezhetsz szakaszokat.

### Összecsukható Szakaszok
A hosszú dokumentumokat könnyedén összecsukhatod a címsorok melletti kis nyílra kattintva, így csak a releváns részekre fókuszálhatsz.

### Könnyű Átrendezés (Drag & Drop)
A Navigációs Panelben teljes szakaszokat húzhatsz át máshova a dokumentumban – a tartalmukkal és az alcímsorokkal együtt.

---

## 3. Címsorok Testreszabása

### Kinézet Módosítása

1. Jobb klikk a Heading stíluson (Home → Styles)
2. Válaszd: **"Modify..."**
3. Állítsd be a betűtípust, méretet, színt stb.

Ha módosítasz egy stílust, a dokumentumban lévő összes azonos stílusú címsor azonnal frissül. Ezzel tartható fent a dokumentum egységes arculata.

### Saját Heading Stílusok Létrehozása

Létrehozhatsz új stílusokat, ha egyedi formázásra van szükséged (pl. Függelék, Megjegyzések).

`Home → Styles → Create a Style`

**Fontos beállítás:**
- **Style type:** Paragraph
- **Style based on:** Heading 1 vagy Heading 2  *(Lásd: 4. pont)*

---

## 4. "Based on" Koncepció – KRITIKUS TUDNIVALÓ

Amikor létrehozol egy saját stílust, beállíthatod, hogy milyen másik stílusra épüljön. Ezt a `Modify Style → "Style based on:"` legördülő menüben találod.

A TextBalance makró az **Outline Level**-t figyeli. Az Outline Level csak akkor öröklődik helyesen, ha:
- A stílusod **"Based on: Heading 1"** → Outline Level 1
- A stílusod **"Based on: Heading 2"** → Outline Level 2

Ha a stílusod "Based on: Normal", a TextBalance **nem fogja észlelni** a címsort.

---

## 5. Gyakori Hibák Elkerülése

1. **SOHA ne használj vastag betűt (Bold) heading helyett!** A TextBalance nem látja a kézi formázást.
2. **Ne ugord át a hierarchia szinteket!** Mindig menj sorban: Heading 1 → Heading 2 → Heading 3.
3. **Ne formázd manuálisan a címsorokat!** Használd a Stílus módosítását (Modify Style).
4. **Ne mellőzd a Navigation Pane-t!** A legjobb eszköz a dokumentum áttekintésére.

---

## 6. Összefoglalás

Ha hosszú dokumentumokat írsz heading-ek nélkül, akkor a Word ellen harcolsz. Ha heading-eket használsz helyesen, a Word – és a TextBalance – neked dolgozik.

---

**Kapcsolódó témák:**
- [TextBalance Telepítése]({% link 03-telepites.md %}) – Kezdjük el használni
- [Troubleshooting: Címsorok nem észlelhetők]({% link 07-troubleshooting.md %}#2-címsorok-nem-észlelhetők)
- [Custom Heading Styles használata]({% link 06-halado-funkciok.md %}#4-custom-heading-styles)
