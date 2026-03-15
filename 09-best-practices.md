---
title: Best Practices
layout: default
nav_order: 9
---

# Best Practices

Néhány hasznos tipp, amivel kihozhatod a maximumot a TextBalance makróból, és gördülékenyebbé teheted az írási folyamatot.

---

## 1. Kezdés: "Vázlat-Először" Megközelítés

**A leggyakoribb hiba**, amit az írók elkövetnek, hogy elkezdenek írni, és csak a végén próbálják betördelni a dokumentumot Címsorokkal.

**A TextBalance módszer:**
1. Mielőtt leírnál egyetlen mondatot is, **gépeld be az összes tervezett fejezet címet**.
2. Formázd meg őket **Heading 1** és **Heading 2** stílusokkal.
3. Nyomj a **Refresh** gombra TextBalance menüszalagon.
4. Oszd szét az `Ideal%` értékeket a létrehozott táblázatban a tervezett arányok szerint.

Ezzel máris kész a "csontváz", amihez menet közben viszonyíthatsz!

---

## 2. Rendszeres, de nem folyamatos Refresh

A TextBalance nem úgy működik, mint egy folyamatos karakter számláló a keret alján. Be kell avatkoznod a folyamatba!

**Mikor nyomd meg a Refresh gombot:**
- Egy bekezdés vagy logikai egység **befejezése után**.
- Amikor elvesztetted a fonalat, vagy nem tudod, túl hosszú lesz-e a jelenlegi fejezet.
- Új címsor hozzáadása esetén.

*Tipp: Használd az **AutoSave Toggle** gombot, amivel eléred, hogy a gomb megnyomása egy automatikus mentést (Ctrl+S) vonjon maga után.*

---

## 3. Ideal% és Limit% Intelligens Használata

### A Limit (Tolerancia) 

Az alapértelmezett Limit 5%. Ez egy disszertációnál remek érték, de egy rövid esszénél túl nagy eltérést engedhet. 

- **Szigorúbb kontroll (pl. cikkeknél):** Állítsd a Limitet `2%`-ra.
- **Lazább írás (pl. könyv első vázlata):** Állítsd a Limitet `10%`-ra.

### Ideal% Dinamikája

Ne ragaszkodj görcsösen az eredetileg beírt `Ideal%` értékekhez. Írás közben előfordul, hogy egy téma több magyarázatot igényel, mint gondoltad.
**Ha a szöveged pirosba csap át**, de úgy érzed, hogy az a tartalom **mindenképpen szükséges**, egyszerűen növeld meg az adott sor `Ideal%` értékét a táblázatban!

---

## 4. Heading 2 (Alcímsorok) Rendszeres Használata

Sokan csak a Heading 1 szinteket használják egy dokumentum során. 

Használd sűrűbben a Headind 2 stílusú Címsorokat! 
Ezek felosztják és arányosítják számodra vizuális Progress Bar-ként, mennyi erőt merítettél a szakasz feloldásakor, így nem fogsz hirtelen kifogyni az anyagból mire az elért hossz végéhez érnél! (Lásd: [Progress Bar a Felület Magyarázatánál]({% link 04-felület-részletes-ismertetése.md %}))

---

## 5. Prezentációk és Szöveg Könyvek (Folyószöveg vs. Beszéd)

Amikor felolvasásra írsz szöveget, szembesülnöd kell a problémával, hogy az írott szó mennyisége másfajta élményként hat az élő beszéd alatt.

**A TextBalance Speech Time funkciójával:**
1. Kapcsold be a **Speech Time** gombot (Toggle ON)
2. Állítsd be a  **Set Tempo** gombbal az egy percre eső olvasási karaktersebességet (Alapértelmezett a 180).
3. Ebből már rögtön és vizuálisan fogod látni, hogy például egy rövid bevezető időszabályba mennyire fog beleférni.

*Tipp: Ne számolj "kerek" percekkel a tervezésnél. Ha 10 perced van, tervezz 8.5 percre az `Ideal%` megadásával, mert élőben az improvizáció, a légzés és a szünetek rengeteg plusz időt emésztenek fel.*

---

## 6. Utolsó simítások (Megosztás előtt)

Amikor a dokumentum elkészült, és ki szeretnéd nyomtatni, vagy el szeretnéd küldeni valakinek, akinek nincsen szüksége a TextBalance jelekre:

1. Ha csak a színezett kiemeléseket és Progress Barokat szeretnéd törölni, használd a **Remove Annotations** gombot. (Az összefoglaló tábla bent marad).
2. Ha teljesen vissza akarod állítani a dokumentum eredeti (makró előtti) állapotát, használd a **Remove Everything** gombot.  

*Ne aggódj: ha véletlenül törlöd őket, egyetlen **Refresh** kattintással a makró bármikor visszagenerálja az adatokat a rejtett szövegekkel.*
