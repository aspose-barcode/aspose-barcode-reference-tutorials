---
category: general
date: 2026-07-30
description: Hozzon létre Databar Stacked Omnidirectional vonalkódot Pythonban. Kövesse
  ezt a lépésről‑lépésre útmutatót az arány és az XDimension beállításához, valamint
  a PNG exportálásához egy python vonalkód‑generátorral.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked omnidirectional
- python barcode generator
- databar aspect ratio
- xdimension pixel size
- barcodeimageformat png
language: hu
lastmod: 2026-07-30
og_description: Készítsen Databar Stacked Omnidirectional vonalkódot Pythonban. Ez
  az útmutató bemutatja, hogyan állítsa be az XDimension-t, módosítsa a DataBar képarányt,
  és mentse PNG formátumban a BarCodeImageFormat használatával.
og_image_alt: Screenshot of a Databar Stacked Omnidirectional barcode saved as a PNG
  file
og_title: Databar Stacked Omnidirectional vonalkód létrehozása – Python oktató
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Create Databar Stacked Omnidirectional barcode in Python. Follow this
    step‑by‑step guide to configure aspect ratio, XDimension, and export PNG using
    a python barcode generator.
  headline: Create Databar Stacked Omnidirectional Barcode in Python
  type: TechArticle
tags:
- barcode
- python
- databar
title: Databar Stacked Omnidirectional vonalkód létrehozása Pythonban
url: /hu/python-java/general/create-databar-stacked-omnidirectional-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Databar Stacked Omnidirectional vonalkód létrehozása Pythonban

Valaha szükséged volt **databar stacked omnidirectional** vonalkód létrehozására Pythonban, de nem tudtad, hol kezdj? Nem vagy egyedül – sok fejlesztő ugyanebbe a helyzetbe ütközik, amikor először a `BarcodeGenerator` osztállyal dolgozik. A jó hír, hogy a teljes folyamat meglehetősen egyszerű, ha megérted a kulcsfontosságú tulajdonságokat.

Ebben az útmutatóban egy teljes, futtatható példán keresztül vezetünk, amely egy **python barcode generator** segítségével beállítja az XDimension‑t, finomhangolja a DataBar képarányt, és végül két PNG fájlt exportál. A végére szilárd képet kapsz arról, hogyan generálj magas minőségű stacked omnidirectional szimbólumokat bármilyen készlet‑ vagy logisztikai projekthez.

## Mit fogsz megtanulni

- Hogyan hozhatsz létre egy **databar stacked omnidirectional** generátort GTIN‑14 payload‑del.  
- Miért fontos a **XDimension pixel méret** a beolvasás megbízhatósága szempontjából.  
- A **DataBar képarány** hatása a sor szélességére és magasságára.  
- Hogyan mentheted az eredményt **BarCodeImageFormat PNG** fájlként.  
- Tippek arra, hogyan használhatod újra ugyanazt a generátor objektumot több változat előállításához extra memóriaigény nélkül.

### Előfeltételek

- Python 3.8+ (a használt könyvtár tisztán Python, nincs szükség lefordított wheel‑ekre).  
- A `barcode-generator` csomag (telepítés: `pip install barcode-generator`).  
- Egy mappa, amelybe írhatsz – a szkript oda menti a két PNG képet.

Ha magabiztos vagy az alap Python importokkal és az objektum‑orientált kóddal, már készen állsz.

## Databar Stacked Omnidirectional vonalkód létrehozása – Lépés áttekintés

Alább a munkafolyamatot hat kisebb lépésre bontjuk. Minden lépés egy önálló kódrészlet, amelyet egyszerűen másolhatsz‑beilleszthetsz egy REPL‑be vagy szkriptfájlba. Nyugodtan kísérletezz – a képarány vagy az XDimension módosítása azonnal más vizuális stílust eredményez.

---

## 1. lépés: Databar Stacked Omnidirectional generátor létrehozása

Az első dolog, amit teszünk, **databar stacked omnidirectional** generátor példány létrehozása, a megfelelő `EncodeTypes` enum és az adatstring átadása.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1 – initialize the generator with a GTIN‑14 payload
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)
```

> **Why this matters:** A `EncodeTypes.DatabarStackedOmniDirectional` jelző azt mondja a könyvtárnak, hogy stacked omnidirectional szimbólumot állítson elő, ami az egyetlen DataBar változat, amely akár 14 számjegyet is kódolhat, miközben bármely szögből olvasható marad.

---

## XDimension pixel méret beállítása

A **XDimension pixel méret** szabályozza a legkisebb modult (a legvékonyabb fekete sávot). A `2` pixel érték a legtöbb képernyőn megjelenő szituációhoz jól működik.

```python
# Step 2 – set the smallest module to 2 pixels
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2
```

> **Pro tip:** Ha magas DPI‑nél szeretnéd nyomtatni a vonalkódot, emeld ezt az értéket 3‑ra vagy 4‑re, hogy elkerüld a elmosódott éleket.

---

## DataBar képarány módosítása (15)

A **DataBar képarány** meghatározza, mennyire széles egy sor a magasságához képest. A `15` képarány szélesebb sorokat eredményez, amit sok szkenner a gyors mozgású felvételhez előnyben részesít.

```python
# Step 3 – make rows wider (aspect ratio = 15)
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
```

> **Why 15?** A hivatalos GS1 specifikáció 10 és 20 közötti arányt javasol stacked omnidirectional szimbólumokhoz. A `15`‑öt egy kiegyensúlyozott alapértelmezett értékként választottuk.

---

## Vonalkód exportálása PNG-ként a BarCodeImageFormat használatával

Most, hogy a generátor be van állítva, elmentjük a képet. A `BarCodeImageFormat.Png` enum veszteségmentes kimenetet biztosít, ami tökéletes a további feldolgozáshoz.

```python
# Step 4 – save the first PNG with the 15 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR15.png",
    BarCodeImageFormat.Png
)
```

> **What you’ll see:** Nyisd meg a létrehozott PNG‑t; tiszta, nagy kontrasztú vonalkódot kell látnod, viszonylag széles sorokkal.

---

## DataBar képarány módosítása 30-ra

Néha magasabb sorokra van szükség a szélesebb helyett – például egy keskeny címke miatt. A **DataBar képarány** `30`‑ra állítása minden sort magasabbá tesz.

```python
# Step 5 – increase the aspect ratio to make rows taller
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
```

> **Edge case:** Nagyon magas arányok (pl. >40) a vonalkódot a szokásos címkeméreteken túlra nyújthatják, ezért valós nyomtatón teszteld, mielőtt véglegesítenéd.

---

## Vonalkód újra exportálása új képaránnyal

Végül újra felhasználjuk ugyanazt a `barcode_generator` objektumot, hogy egy második PNG‑t írjunk. Nem kell újra létrehozni a generátort – csak módosítsd a tulajdonságot, és hívd meg újra a `Save`‑et.

```python
# Step 6 – save the second PNG with the 30 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR30.png",
    BarCodeImageFormat.Png
)
```

> **Result:** Most már két PNG fájlod van – egy széles sorokkal (`AR15`) és egy magas sorokkal (`AR30`). Hasonlítsd össze őket oldal‑ról‑oldalra, hogy eldöntsd, melyik működik a legjobban a szkenner beállításaidhoz.

---

## Teljes működő példa

Összegezve, itt a teljes szkript, amelyet azonnal futtathatsz. Cseréld le a `YOUR_DIRECTORY`‑t egy abszolút útvonalra a gépeden.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1️⃣ Initialize generator
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)

# 2️⃣ Set smallest module (XDimension)
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2

# 3️⃣ First aspect ratio – wider rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR15.png", BarCodeImageFormat.Png)

# 4️⃣ Second aspect ratio – taller rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR30.png", BarCodeImageFormat.Png)

print("✅ Two PNG files created – AR15 and AR30")
```

**Expected output** (a konzolodban):

```
✅ Two PNG files created – AR15 and AR30
```

És két képfájl jelenik meg a célmappában, készen a beolvasási tesztekre.

---

## Következtetés

Épp most **databar stacked omnidirectional** vonalkódokat hoztunk létre Pythonban, módosítottuk a **XDimension pixel méretet**, két különböző **DataBar képarány** beállítással kísérleteztünk, és a **BarCodeImageFormat PNG** fájlokként exportáltuk az eredményeket. Az egész munkafolyamat néhány sorba sűrítve is teljes kontrollt ad a szkennerek számára legfontosabb vizuális jellemzők felett.

Mi a következő? Próbáld meg a payload‑ot egy másik GTIN‑re cserélni, játsz a színekkel a PNG palettás képpé alakításával, vagy generálj egy PDF‑jelentést, amely mindkét PNG‑t egymás mellett ágyazza be. A `BarcodeGenerator` osztály elég rugalmas ahhoz, hogy ezeket a forgatókönyveket is kezelje, szóval bátran kísérletezz.

Van kérdésed egy adott felhasználási esettel kapcsolatban, vagy hibába ütköztél? Írj egy megjegyzést alább, és szívesen segítek. Boldog kódolást!

## Mit érdemes még megtanulni?

Az alábbi oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódpéldákat tartalmaz lépésről‑lépésre magyarázatokkal, hogy megismerd a további API funkciókat és alternatív megvalósítási megközelítéseket saját projektjeidben.

- [Vonalkód kép generálása – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}