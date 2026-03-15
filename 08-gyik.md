---
title: Gyakori Kérdések (GYIK)
layout: default
nav_order: 8
---

# Gyakori Kérdések (GYIK)

Ebben a fejezetben a leggyakrabban felmerülő kérdésekre adunk rövid, lényegretörő válaszokat.

---

## 1. Általános Kérdések

### Mi történik, ha elküldöm a dokumentumot valakinek, akinek nincs meg a TextBalance?
A dokumentum megnyitható marad. A TextBalance elmenti a **Statisztikai Táblázatot** és a **Rejtett Szövegesi Annotációkat** mint Word alapvető elemeket. Az egyetlen dolog, amit a fogadó fél nem tud megtenni, az a **Refresh** – vagyis nem tudja frissíteni a karakterszámokat vagy átrendezni a táblázatot.
Ettől függetlenül, a formázás az olvasó számára is kikapcsolható a `Show/Hide ¶` funkcióval.

### Használhatom más nyelveken lévő szövegekhez is?
Igen! A TextBalance csak a karaktereket számolja, így bármilyen nyelven megírt dokumentummal működik.

### Mennyibe kerül a TextBalance?
A TextBalance egy teljesen ingyenes, nyílt forráskódú projekt (MIT licenc). Támogathatod a fejlesztőt a Ribbon-on található **Support** gomb segítségével.

---

## 2. Telepítés és Kompatibilitás

### Melyik Word verziókkal működik?
A TextBalance a Microsoft Word 2016, 2019, 2021 és Microsoft 365 (Office 365) asztali Windowsos verzióival működik. 
*(A régebbi Word verziókkal kompatibilitási problémák léphetnek fel).*

### Használhatom Word Online-ban vagy mobilon?
Nem. A TextBalance egy VBA (Visual Basic for Applications) makró, amelyet a Word Online (böngészős verzió), az iOS és Android alkalmazások **nem támogatnak**. Csak asztali Windows kliensben működik.

### Hogyan tudom letörölni a gépemről a TextBalance-t?
A TextBalance.exe telepítése az NSI szoftvert használja a regisztrációs adatbázisban történő módosításokhoz. Bármikor leszedheted a szokásos Windows "Programok Hozzáadása és Eltávolítása" ablakból induló törlés folyamat vagy a saját letöltő mappájában lévő `Uninstall.exe` segítségével.

---

## 3. Használat és Funkciók

### Beállíthatok Heading 3 (vagy több) szintet is?
A TextBalance jelenleg csak a **Heading 1** és **Heading 2** szinteket ismeri fel és méri. Ez a döntést a felület egyszerűsége és a táblázat olvashatósága miatt hoztuk meg. A 3-as vagy annál kisebb szintekre ajánljuk az egyszerű (félkövér) alcímek vagy listák használatát, anélkül, hogy bonyolítanád a makró felbontásait.

### Hogyan tüntessem el a zöld/piros betűket nyomtatás előtt?
Ezek az úgynevezett **Rejtett szövegek (Hidden text)**. Alapértelmezetten a Word ezt nem nyomtatja ki, de leellenőrizheted a Print nevű menün keresztül. 
Ha a dokumentumból is el akarod tüntetni megosztás előtt, kattints az **Annotations** (vagy az **Everything**) gombra a *Remove* csoportban a makró Ribbon-ján!

### Mi az a "Limit%" és hogy változtassam?
A Limit% azt jelzi, hogy mennyi százalékos eltérést engedsz meg az Ideal%-hoz képest, mielőtt a szín Narancsra vagy Pirosra váltana. 
A táblázat oszlopában bármelyik cellába kattintva átírhatod (pl. `5.0%` helyett `3.0%`). Változtatás után kattints a Refresh gombra.

---

## 4. Technikai és Biztonsági Kérdések

### Biztonságos a kód futtatása? Küld adatokat valahova?
A TextBalance **100%-ban offline** működik. Semmilyen adatot nem küld sehova, nem csatlakozik az internethez (kivéve a Help és Support menük böngészős gombjait). A dokumentumod tartalma teljes mértékben a saját gépeden marad.

### AutoSave: mit ment pontosan?
Ha bekapcsolod az AutoSave-t (a menüszalagon), a TextBalance minden egyes Refresh parancs futtatása UTÁN automatikusan csinál egy teljes dokumentum mentést (`Ctrl+S`). Tehát nem csak a beállításokat menti el a háttérben, hanem a szöveg módosításait is! 
*(Figyelem: Ha egy teljesen új, "Névtelen1" fájllal dolgozol, az AutoSave addig nem működik, amíg először manuálisan el nem mented a fájlt egy mappába.)*

### Speech Tempo: mi a különbség a karakterek és a beszédidő között?
A Speech Time kalkulátor csupán elosztja a megadott karakterszámot azzal a **tempó értékkel (karakter/perc)**, amit megadtál. Az átlagos beszédtempó 180 karakter/perc, de ez egyénenként változó. 

---

**Nem találod a választ a kérdésedre?**
Nézd meg a [Troubleshooting (Hibaelhárítás)]({% link 07-troubleshooting.md %}) fejezetet, vagy nyiss egy hibajegyet a táblában található [Report an Issue] gomb segítségével!
