---
title: Telepítés és Első Lépések
layout: default
nav_order: 3
---

# Telepítés és Első Lépések

Ebben a fejezetben megtanulhatod, hogyan telepítsd és használd először a TextBalance makrót.

---

## 1. Rendszerkövetelmények

### Operációs Rendszer
- Windows 7 Service Pack 1 vagy újabb (Windows 10/11 ajánlott)

### Microsoft Word Verzió
- Word 2016, 2019, 2021
- Microsoft 365 (Office 365) asztali alkalmazás

*Megjegyzés: A Word Online (böngészős verzió) nem támogatott, mivel nem képes makrókat futtatni.*

## 2. Telepítés Lépésről Lépésre

A TextBalance telepítése gyors és automatizált. 

1. Töltsd le a legújabb **TextBalance Setup** telepítőfájlt (`.exe`)
2. **Futtasd** a letöltött telepítőfájlt
3. Kövesd a telepítő varázsló utasításait (a telepítő felesleges felhasználói beavatkozás nélkül kibontja és bemásolja a fájlokat, majd regisztrálja a szükséges Windows és Word konfigurációkat)
4. A telepítés sikerességét a képernyőn megjelenő **Installation complete!** ablak jelzi
![installer-exe.png](assets/images/installer-exe.png)

### Word Újraindítása

Fontos: A Wordöt a **telepítés után újra kell indítani**, hogy a TextBalance megjelenjen a menüszalagon.
Ellenőrizd a ribbon-ot: új **TextBalance** fület kell látnod.
![Ribbon tab](assets/images/ribbon-tab.png)

---

## 3. Első Indítás

### Dokumentum Előkészítése

Mielőtt használnád a TextBalance-t, alakítsd ki a dokumentumod struktúráját megfelelő Word Címsorokkal (`Heading 1`, `Heading 2`).
![Heading alkalmazása](assets/gifs/apply-heading.gif)

### TextBalance Indítása

1. Kattints a **TextBalance** fülre
2. Kattints a **Refresh** gombra

### Welcome Dialog

Első használatkor egy üdvözlő ablak jelenik meg, amely rákérdez, hogy hozzá szeretnéd-e adni a makrót a dokumentumhoz. Kattints a **Yes** gombra.
![Welcome dialog](assets/images/welcome-dialog.png)

### Target Document Length Beállítása

A következő lépésben a céldokumentum hossza állítható be karakterben. 
![Target length input](assets/images/target-length-dialog.png)

- **Ha most kezded írni:** Add meg a becsült végleges karaktermennyiséget.
- **Ha már megírtad:** Hagyd az aktuális értéket.

*Tipp: Ezt később bármikor módosíthatod az elkészült táblázatban.*

### Táblázat és Annotációk Megjelenése

A TextBalance elemzi a dokumentumot, létrehozza a statisztikai táblázatot és a címsor annotációkat.
Amikor elkészült, egy jóváhagyó üzenetet látsz, valamint lehetőséget arra, hogy egy gyors bemutatót kérj (amely megnyitja ezt a weblapot).
![Installation complete](assets/images/install-success.png)
![Tutorial dialog](assets/images/tutorial-dialog.png)

---

## 4. Mit Látsz Most?

### Összefoglaló Táblázat

A dokumentum elején megjelenik a Summary Table:
![Summary table](assets/images/summary-table.png)

Oszlopok:
- **Actual%** – A szakasz tényleges hossza a cél dokumentumhoz képest
- **Ideal%** – A kívánt hossz (ezt folyamatosan szerkesztheted írás közben)
- **Limit%** – Tolerancia (alapértelmezett 5%)

### Heading Annotációk

A Heading 1 címsorok mellé kerülnek az azonosítók, karakterszámok és százalékok:
`# Bevezetés ID001 (1247 char, 35.2%)`
![Heading annotation](assets/images/heading-annotation.png)

A Heading 2 címsorok mellé egy vizuális Progress Bar kerül, amely az alcím arányát mutatja a szülő Heading 1 elemen belül.
![Progress bar](assets/images/progress-bar.png)

### Rejtett Szöveg (Hidden Text)

Az annotációk **rejtett szövegként** (Hidden text) kerülnek beillesztésre. Nem nyomtatódnak ki és nem számítanak bele a szószámba sem. A `Show/Hide ¶` funkcióval be- vagy kikapcsolhatod a láthatóságukat.

---

## 5. Eltávolítás (Uninstall)

A TextBalance számítógépről történő végleges letörlése a Windows szokásos programeltávolítóján keresztül zajlik ("Add or Remove Programs" vagy `Uninstall.exe` a telepítési mappában).

A kód és adatok **csak az aktuális dokumentumból** történő eltávolításához (amikor a program még telepítve marad) lásd: [Felület Részletes Ismertetése - Everything gomb]({% link 04-felület-részletes-ismertetése.md %}#remove-csoport).

---

**Kapcsolódó témák:**
- [Word Címsorok Alapjai]({% link 02-word-headings-alapjai.md %}) 
- [Felület Részletes Ismertetése]({% link 04-felület-részletes-ismertetése.md %}) 
- [Troubleshooting: "No headings found"]({% link 07-troubleshooting.md %}#1-no-headings-found-hibaüzenet) 
