---
title: Munkafolyamatok (Workflows)
layout: default
nav_order: 5
---

# Munkafolyamatok (Workflows)

Ebben a fejezetben különböző használati eseteket nézhetsz meg részletesen, hogy lásd, hogyan illeszkedik a TextBalance a mindennapi munkádba.

---

## 1. Dokumentum Tervezés (Planning Mode)

**Használati eset:** Új dokumentumot kezdesz, és előre szeretnéd megtervezni a szerkezetet.

### Előkészítés
A folyószöveg megírása előtt hozd létre a teljes Heading struktúrát, majd állítsd be a **Target Document Length** értékét (a **Refresh** lenyomása után). *Például: szakdolgozatnál 40-50 olal -> 100,000 karakter.*

### Ideal Percentages Tervezése
A táblázat létrejöttével megtervezheted, hogy egy adott szakasz mekkorának kell, hogy legyen a teljes cél hosszúsághoz viszonyítva. Állítsd be az `Ideal%` mezőbe például az **Irodalmi Áttekintés** sorához a szükséges %-os értéket.

![Ideal planning](assets/gifs/edit-ideal.gif)

### Írás Közben Követés
Gépelés és folyószövegírás közben (kb minden 15 perc vagy egy szakasz befejezése után) nyomd meg a **Refresh** gombot. 
Ahogy írsz, az `Actual%` értékek változnak és jelezni fogják a Zöld/Narancs/Piros kódolással, hogy hol állsz az előre beállított arányokhoz képest.
Például: *Módszertan szakasz Actual: 32.5% / Ideal: 20% -> Piros kijelzés, ami azt jelzi: a szakaszt le kell rövidíteni.*

![Refresh cycle](assets/gifs/refresh-cycle.gif)

---

## 2. Meglévő Dokumentum Elemzése (Analysis Mode)

**Használati eset:** Már megírtad a dokumentumot, és szeretnéd elemezni a szerkezetet.

1. Indítsd el a TextBalance-t az elkészült dokumentumban, és hagyd a céldokumentum hosszt az alapértelmezett (jelenlegi teljes) karaktermennyiségén.
2. A futtatás azonnal szétosztja minden Heading 1 számára egyenletesen az `Ideal%`-ot, majd ezen felül a megfelelő Zöld/Narancs/Piros kódolással jeleníti meg a meglévő folyószöveg helyzetét. Lásd, melyik szakaszba került több információ a megengedettnél.
3. Két dolgot tehetsz: Átírod az `Ideal%`-ot abban az esetben ha a te szubjektív meglátásod indokolttá teszi az adott szakasz hosszát, vagy átstrukturálod/lerövidíted az írott szöveget a határértékeken belülire.

---

## 3. Prezentáció Időzítése (Speech Time Mode)

**Használati eset:** Előadást, prédikációt, beszédet írsz, és azt egy adott időkeretbe kell beszorítanod.

1. Kapcsold be a **Speech Time** módot (a táblázatban és a címsorokban megjelennek is percek a karakterek helyett/mögött).
2. Opcionális lépésként állítsd be a saját olvasási/beszédtempódat (a **Set Tempo** mezőben az egy percre eső felolvasható karakterszámmal).
3. Ebből már rögtön és vizuálisan fogod látni, hogy például egy rövid bevezető felolvasása a papírról 1 percet, míg a történet kifejtése pontosan 4.5 percet is igénybe fog venni. Próbáld ki otthon hangosan felolvasni és igazíts a tempón szükség esetén.

---

## 4. Hosszú Dokumentumok (100+ oldal)

Hónapokig tartó tervezés, disszertációk vagy könyvek esetében a **Refresh** gyakoriság és mentés éles elválasztása hasznosabb:
- Kapcsold be az **AutoSave Toggle** funkciót. Az adatok minden egyes **Refresh** után egy kattintással el fognak mentődni a dokumentუმmal (így megkíméled magad a Ctl+S folyamatos manuális használatától).  
- Csak a szakaszok legvégén értékelj.
- Nagyon figyelj rá: Használd a Word alcímsorokat (Heading 2), mivel könyveknél és nagyobb leírásoknál a Level 2 `Progress Bar` grafikai előrejelzés könnyebbé teszi a szakasz belső arányának feltérképezését.

---

## Tanácsok a sikeres használathoz

- **Piros szín esetén ne stresszelj!** A piros csak vizuális jelzése a tervezettet meghaladó túllépésre. Ha szakmailag egy bekezdés okkal tartalmaz rengeteg releváns leírást, elég csak az `Ideal%` megnövelése az eredmény normalizálásához.
- **Refresh Időzítése:** Ne használjuk szavanként a frissítést. Szakaszt zársz le, újabb paragrafusokat viszel a gépre, ekkor ellenőrizd az egyensúlyt!

---

**Kapcsolódó témák:**
- [Táblázat Szerkesztése]({% link 04-felület-részletes-ismertetése.md %})
- [Best Practices]({% link 09-best-practices.md %})
