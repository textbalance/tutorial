---
title: Troubleshooting (Hibaelhárítás)
layout: default
nav_order: 7
---

# Troubleshooting (Hibaelhárítás)

Ez a fejezet a leggyakoribb problémákat és megoldásaikat tartalmazza. Ha valami nem működik, valószínűleg itt találsz választ.

---

## 1. "No headings found" Hibaüzenet

**Probléma:**
```
No headings found in document.
Please add Heading 1 or Heading 2 styles to your document.
```
A TextBalance nem talált egyetlen Heading 1 vagy Heading 2 stílust sem a dokumentumban.

**Lehetséges Okok és Megoldások:**
- **Nincsenek heading-ek a dokumentumban:** Ellenőrizzük a Word *Navigation Pane* ablakát (`View → Navigation Pane`). Ha üres, használd a Címsoroknál a `Home → Styles → Heading 1/2` menüsort!
- **Kézi formázás heading helyett:** Ctrl+B (vastagítás) bekezdés NEM Címsor stílus! Formázd át azokat Microsoft Word Headingre!
- **Custom Style:** Ha a dokumentum egyedi címsort használ (pl. "Függelék Fejezet" style típus), annak a formázása **"Based on: Normal"**. Módosítsd `Heading 1`-re a megfelelő stílus paraméterét! Bővebben a [Címsorok haladó beállításaiban]({% link 02-word-headings-alapjai.md %})

---

## 2. Címsorok Nem Észlelhetők

Előfordulhat, hogy látod azokat a Navigációs ablakban de a Makró nem dolgozik ezekkel.

- **Outline Level Hiba:** A `Jobbklikk → Paragraph → Outline level` nincsen a pontos Head szintekre beállítva. 
- **Hidden Text Bejövő:** Formázása be van kapcsolva a stílusnál. Látni fogod, ha pontozott a betű alatt. (Kattints: `Jobbklikk → Font → Hide` opció kikapcsolva)
- **Nested Table:** Egy Word-ös belső táblázatban hoztad létre a Fejezetneveket. Tedd sima lapfő részre! A makró kiküszöböli a belső oldalak táblázatokból álló betöltését. 

---

## 3. Táblázat Rossz Helyen vagy Duplikálódott

**Probléma:** Két összefoglaló táblázat jelenik meg a frissítés után.

**Ok:** Módosítottad vagy törölted a kezdeti táblázatot és makró nem ismeri föl hol kell azt újragenerálnia, úgyhogy inkább egy újat szült az elején. A probléma leginkább a "**TotalChar**" sor átírása miatt lép életbe, mert onnan indítja el az egész folyamatot!
**Megoldás:** Töröld mind a két Táblázatot, majd fuss egy `Refresh` parancsra és készíts egy letisztult 1 darabból álló eredetit. AutoSave használata esetén az Ideal értékek emlékezetbe vannak már írva!

---

## 4. Színek Nem Frissülnek

**Probléma:** Kibővítetted egy szakaszt 5 oldallal és az Zöld maradt.

**Lehetséges Ok és Megoldás:** A Makró régebbi rejtett szövegen lévő gyorsítótárában akadhatott egy kis hiba, amibe egy ráfedett új érték bújt oda.
`Megoldás: TextBalance Tab -> Remove gomb (Annotations), Várj picit, majd nyomj rá: Refresh!`
*Tipp: Ellenőrizzük, hogy a Limit értéke nem lett e hibásan elírva magában a táblázatban (pl %50).*

---

## 5. AutoSave Nem Működik

A Címsori táblázat `Limit` és `Total` értékeit a dokumentum memóriába (Custom Document Properties) menti, emellett a teljes fájlon meghív egy lementést (vagyis az együttes funkciók **CTRL+S** kiváltója lesz), ezért, ne zárd be csak úgy minden módosítás közbeni feszültségben a Windows-t, ha ez a Tab funkció nincs is aktiválva (AutoSave ON)!

**Kritikus:** Amennyiben egy új (pl. `Document1` hívottzáson lévő, mappában soha le nem helyezett fájllal kezded), a TextBalance "Save" lépéseit nem tudja elvégezni, mert előbb be kell azt manuálisan egy megnevezéssel töltened! Mentsd el az üres fájlt majd kezdd a funkció működtetését!

---

## 6. Progress Bar Nem Pontos (Orphan Text)

A Heading 2 értékszint megborulhat az első Főcím kiömlő szövegétől (ami előtt még nincs belső Alcím). A `Módszertan` alatt lévő "Árva Bekezdés" karakterszáma kivált az alcímek ideális értékrendjéből! Készíts annak a megjelölésére egy sima belső alcímet (Legkisebb "Bevezetőnek" is elegendő). (Erről bővebben: [Haladó Funkciók]({% link 06-halado-funkciok.md %}))

---

## 7. Word Összeomlás (Crash) / Lassúság

Ha frissíted, és hosszan akad a TextBalance, arra három probléma enged következtetni: 

- Nagyon hosszú, 100+ oldalas a fájl. Oszd 2 részre az ellenőrzést, vagy csak a végleges fejezeti csukópontokon tölts.
- Többször próbálkozol Refresht indítani 1 másodperc alatt. LASSÍTS! Ez nem egy Online Browser. Várj pár másodpercet és csak utána kattints.
