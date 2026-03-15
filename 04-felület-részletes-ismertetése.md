---
title: Felület Részletes Ismertetése
layout: default
nav_order: 4
---

# Felület Részletes Ismertetése

Ebben a fejezetben minden gombot, táblázat oszlopot és annotációt részletesen megismerhetsz.

---

## 1. Ribbon Tab – TextBalance Gombok

A TextBalance menüszalag négy csoportra van osztva: **Main**, **Remove**, **Help**, és **Feedback**.

![Ribbon tab teljes](assets/images/ribbon-tab.png)

---

### Main Csoport

#### Refresh Gomb

**Funkció:** A TextBalance elemzés futtatása vagy frissítése.

**Mikor használd:**
- Dokumentum módosítása után (új szöveg, címsorok hozzáadása, törlése)
- Táblázat adatainak módosítása után (Ideal%, Limit%)

**Mit csinál:**
Összegyűjti az összes Heading 1 és Heading 2 címsort, kiszámítja az arányokat, majd frissíti a táblázatot és a címsor annotációkat. Ha be van kapcsolva az AutoSave, a folyamat végén elmenti a dokumentumot.

**Billentyűparancs:** `Alt+,+,` 

#### Speech Time Toggle

**Funkció:** Váltás karakterszám és becsült beszédidő megjelenítés között.

**Karakter nézet (OFF):**
`# Bevezetés ID001 (1247 char, 12.5%)`

**Speech Time nézet (ON):**
`# Bevezetés ID001 (6.9 min)`

**Mikor használd:**
Prezentációk, előadások, prédikációk (vagy más időzített tartalmak) előkészítésénel és megírásánál.

*Megjegyzés: A gomb átváltásakor a Refresh automatikusan lefut.*

![Toggle működés](assets/gifs/speech-time-toggle.gif)

#### Set Tempo Gomb

**Funkció:** Személyes olvasási/beszéd sebesség beállítása a beszélt idő (Speech Time) pontosabb számításához.

Alapértelmezett tempó: 180 karakter/perc.

**Használata:**
A gombra kattintva megadhatod a saját értékedet (50-1000 karakter/perc között). A megadott érték után a Speech Time funkció automatikusan bekapcsol és lefut a Refresh.

#### AutoSave Toggle

**Funkció:** Automatikus dokumentummentés be/kikapcsolása (alapértelmezetten kikapcsolva).

**Mit csinál:**
Ha AutoSave ON: Minden Refresh gomb lenyomás és sikeres elemzés után automatikusan elmenti a dokumentumot (`ActiveDocument.Save`). A gomb lenyomása tehát már önmagában a mentést is jelenti. 
Ha a dokumentumot még nem mentetted el soha (új fájl), az AutoSave nem működik. Kérjük, előbb végezz egy manuális mentést.

---

### Remove Csoport

#### Everything Gomb

**Funkció:** Teljes TextBalance adatkészlet eltávolítása a dokumentumból.

**Mit töröl:**
- Összefoglaló táblázatot
- Összes heading annotációt és progress bar-t
- Dokumentum beállításokat és mentett metaadatokat

**Mit NEM töröl:**
- Magukat a beírt címsorokat és a dokumentumban lévő folyószöveget!

Célja a dokumentum letisztítása megosztás vagy végső beadás előtt. Csak abból a dokumentumból törli az adatokat, amelyik épp nyitva van (a makró továbbra is telepítve marad a számítógépen).
![Remove Everything](assets/images/remove-confirm.png)

#### Annotations Gomb

**Funkció:** Csak az annotációk (hivatkozások, karakteradatok, diagramok) törlése a címsorok mellől.

A táblázat és az ahhoz tartozó beállítások megmaradnak.
*Visszaállítás: Bármely új Refresh kattintás azonnal újragenerálja a törölt annotációkat.*

#### Table Gomb

**Funkció:** Csak az összefoglaló táblázat törlése a dokumentum elejéről. 

Az annotációk a címsorok mellett megmaradnak.
*Visszaállítás: Bármely új Refresh generál egy új táblázatot.*

---

### Help és Feedback Csoport

- **Help Gomb:** Részletes, böngésző alapú súgó (ezt az oldalt) nyitja meg, ahol tanácsokat kaphatsz.
- **Report an Issue:** A GitHub Issues oldalt nyitja meg a böngésződben, ahol jelentheted az esetleges hibákat a TextBalance-al kapcsolatban.
- **Support:** Támogasd a munkánkat, és vedd meg a fejlesztőnek a kedvenc forrócsokoládéját.

---

## 2. Summary Table (Összefoglaló Táblázat)

A táblázat alapértelmezetten a dokumentum elején jelenik meg, és átfogó képet ad a szerkezetről.
![Summary table](assets/images/summary-table.png)

### TotalChar Mező

- A táblázat tetején található **TotalChar** mezőbe beírhatod a dokumentum tervezett, végleges karakterszámát. (Pl. szakdolgozat: 100,000)
- Írd be az új értéket, nyomj Entert, és kattints a Refresh gombra az érvényesítéshez.

### Táblázat Oszlopok

**1. Heading Név (és ID)**  
Nem szerkeszthető oszlop. Ha a címsor szövege megváltozik a dokumentumban, a Refresh itt is frissíti. Az ID (pl. ID001) a belső azonosításhoz szükséges, így kérjük, ne változtasd meg manuálisan.

**2. Actual%**  
Az adott szakasz tényleges hossza a beállított TotalChar-hoz képest. Nem szerkeszthető oszlop, a Refresh során ez dinamikusan frissül. Az érték egy kiszínesített jelző, amely visszajelzést ad a megengedett határokhoz képest:

![Color examples](assets/images/color-examples.png)
- **Zöld:** A szakaszhossz megfelelő. Értéke a Limit-en belül marad az Ideal%-hoz viszonyítva.
- **Narancs:** Túllépés következik. Elérte az Ideal% + Limit határt, de még tűréshatáron belül van.
- **Piros:** Jelentős túllépés történt. Az adott szakaszhossz már nem elfogadott túllépésben van.

**3. Ideal%**  
Ez az a százalékos *célérték*, amekkorára az adott szakaszt tervezed.
- Szabadon átírhatod (belekattintasz a cellába, csak a számot kell megadni)
- Ha egyetlen Ideal% sincs megadva, a makró *automatikusan szétosztja* egyenlő arányban

**4. Limit%**  
A tolerancia határa (alapértelmezetten 5%). Eltérés az Ideal%-tól, ami még "elfogadhatónak" minősül a színjelzéseknél. Ez is egyedileg állítható be, így lazább vagy szigorúbb ellenőrzésre is van mód.

---

## 3. Heading Annotációk

Minden Heading 1 és Heading 2 címsor mellett vizuális visszajelzés segíti a munkádat. 
*A kiegészítések Rejtett Szövegként jelennek meg, ami nem kerül bele a végső PDF exportba vagy nyomtatásba.*

### Level 1 Annotációk (Heading 1)

A főfejezetek mellett látható az aktuális azonosító, karakterszám/beszédidő, és az eddigi teljesítmény vizuális színezése. 

`# Bevezetés ID001 (1247 char, 12.5%)`

### Level 2 Annotációk (Heading 2)

A Heading 2 alcímekhez a TextBalance hozzáad egy vizuális Progress Bar-t, amely megmutatja az alcím karakterszámának *arányát a saját főcíméhez képest*. (Ha a Főcím önmaga `Ideal%=40%`, és a belső H2-es alcím fele akkora terjedelmet ír le, akkor az alcím sávja félig lesz kitöltve).

`## Alcím 1  ████▓▓▓▓░░░░░░░░`
![Progress bar](assets/images/progress-bar.png)

---

## 4. Táblázat Mozgatása

Szabadon áthelyezheted a Summary Table-t bárhova a dokumentumon belül (csak vágd ki a teljes táblázatot és illeszd az új helyre). Ha ezt megteszed és lenyomod a Refresh-t, a makró az új helyen frissíti tovább az értékeit.
*Fontos, hogy sose töröld és ne nevezd át a "TotalChar" sort!*

---

**Kapcsolódó témák:**
- [Munkafolyamatok: Táblázat szerkesztése]({% link 05-munkafolyamatok.md %})
- [Troubleshooting: Színek nem frissülnek]({% link 07-troubleshooting.md %}#4-szinek-nem-frissulnek)
