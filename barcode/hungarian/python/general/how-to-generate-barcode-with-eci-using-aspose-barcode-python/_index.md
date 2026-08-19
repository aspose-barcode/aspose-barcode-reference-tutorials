---
category: general
date: 2026-08-19
description: Hogyan generáljunk vonalkódot ECI-vel az Aspose.Barcode for Python használatával.
  Tanulja meg, hogyan adjon hozzá ECI adatot, keverje a sima szöveget, és mentse el
  a képet egy átfogó útmutatóban.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to add eci
- Aspose.Barcode Python
- extended codetext barcode
- ECI encoding Python
language: hu
lastmod: 2026-08-19
og_description: Hogyan generáljunk vonalkódot ECI-vel az Aspose.Barcode for Python
  segítségével. Kövesse ezt az útmutatót, hogy megtudja, hogyan adjon hozzá ECI adatot,
  testreszabja a megjelenést, és mentse az eredményt.
og_image_alt: Screenshot showing a barcode generated with how to generate barcode
  example
og_title: Hogyan generáljunk vonalkódot ECI-vel az Aspose.Barcode Python használatával
  – lépésről lépésre
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  headline: How to generate barcode with ECI using Aspose.Barcode Python
  type: TechArticle
- description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  name: How to generate barcode with ECI using Aspose.Barcode Python
  steps:
  - name: Expected result
    text: When you open `extended_codetext.png`, you should see a Code 128 barcode
      that encodes the numeric string `1234567890` followed by the Chinese characters
      “特殊字符”. Scanning the barcode with a modern scanner that respects ECI will return
      the original mixed string.
  - name: What if I need a different character set?
    text: Choose the appropriate ECI value from the ISO/IEC 18004 table. For example,
      ECI 27 represents ISO‑8859‑1 (Latin‑1). Replace the numeric identifier in `add_eci_codetext`
      accordingly.
  - name: Can I embed more than one ECI block?
    text: Yes. Call `add_eci_codetext` multiple times. The builder inserts the necessary
      ECI switch codes between blocks, preserving the order you add them.
  - name: Does the generator support QR codes with ECI?
    text: Absolutely. Replace `barcode.Symbology.CODE_128` with `barcode.Symbology.QR`
      and adjust any QR‑specific parameters (e.g., error correction level) via `generator.parameters.qr`.
  - name: How to handle very long data strings?
    text: For linear barcodes like Code 128, the maximum length is about 80 characters
      when using extended codetext. If you exceed that, consider switching to a two‑dimensional
      symbology such as QR or Data Matrix, which can store thousands of characters.
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: Hogyan generáljunk vonalkódot ECI-vel az Aspose.Barcode Python használatával
url: /hu/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan generáljunk vonalkódot ECI-vel az Aspose.Barcode Python használatával

Ha szeretnéd megtudni, **hogyan generálj vonalkódot**, amely egyszerű karaktereket és ECI‑kódolt adatokat egyaránt tartalmaz, ez az útmutató bemutatja a teljes folyamatot. Pontosan látni fogod, **hogyan adjunk hozzá eci** szekciókat, állítsuk be a méretet, és írjuk a képet lemezre egyetlen, futtatható szkripttel.

Az útmutató a következőket tárgyalja:

* Az Aspose.Barcode könyvtár verziójának lekérdezése (opcionális, de hibakereséshez hasznos).  
* Kiterjesztett kódszöveg (codetext) string felépítése, amely egyszerű és ECI‑kódolt karaktereket kever.  
* Vonalkód generátor létrehozása olyan szimbólumhoz, amely támogatja a kiterjesztett kódszöveget.  
* A vonalkód méreteinek testreszabása és a végleges PNG fájl mentése.

Külső dokumentáció nem szükséges; másold a kódot, futtasd, és kapsz egy vonalkód képet, amely kínai karaktereket tartalmaz ECI 26 (UTF‑8) kódolással.

## Előkövetelmények

Mielőtt elkezdenéd, győződj meg róla, hogy rendelkezel:

* Python 3.8 vagy újabb telepítve.  
* `aspose-barcode` csomag telepítve (`pip install aspose-barcode`).  
* Írási jogosultsággal a mappához, ahová a PNG fájlt menteni szeretnéd.

Ha virtuális környezetet használsz, először aktiváld, hogy a függőségek izoláltak maradjanak.

## 1. lépés: Az Aspose.Barcode verzió ellenőrzése (opcionális)

A pontos könyvtárverzió ismerete segít, ha hibákat kell jelenteni vagy funkciókat kell összehasonlítani a kiadások között.

```python
import aspose.barcode as barcode
from aspose.barcode.generation import BuildVersionInfo

ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)
```

*Miért fontos*: A verziókimenet megerősíti, hogy a futtatókörnyezet megegyezik a követett dokumentációval. Különböző verziók eltérő ECI értékeket támogatnak, így ez egy gyors ellenőrzés.

## 2. lépés: Kiterjesztett kódszöveg építése egyszerű és ECI‑kódolt részekkel

Az Aspose.Barcode biztosítja a `ExtCodetextBuilder` osztályt az egyszerű adatok és az ECI‑kódolt szegmensek összefűzéséhez. Ebben a példában egy numerikus stringet keverünk kínai karakterekkel.

```python
from aspose.barcode.generation import ExtCodetextBuilder

builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using ECI 26 (UTF‑8)
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)
```

*Magyarázat*:
* `add_plain_codetext` olyan adatot szúr be, amelyet a vonalkód szimbóluma egyszerű karakterként kezel.  
* `add_eci_codetext` azt mondja a generátornak, hogy az adott szöveg előtt helyezzen el egy ECI indikátort (itt **26**, ami az UTF‑8-hoz tartozik). Ez pontosan **hogyan adjunk hozzá eci** adatot egy vonalkódhoz.

Többször is meghívhatod a `add_eci_codetext`-et, hogy több különböző nyelvi blokkot ágyazz be. A builder automatikusan kezeli a szükséges escape szekvenciákat.

## 3. lépés: Válassz szimbólumot, amely támogatja a kiterjesztett kódszöveget

Nem minden vonalkódtípus képes ECI szegmenseket tárolni. A Code 128, QR és Data Matrix gyakori választások. A példa a Code 128-at használja, mivel széles körben támogatott és jól működik vegyes alfanumerikus adatok esetén.

```python
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,   # Code128 supports extended codetext
    extended_codetext
)
```

*Miért a Code 128?*: Elfogadja a teljes ASCII tartományt és a builder által előállított ECI escape szekvenciákat, így ideális a „hogyan generáljunk vonalkódot” szituációra, amely egyszerű és kódolt szöveget kever.

## 4. lépés: A vonalkód megjelenésének beállítása

A `parameters` objektum segítségével szabályozhatod a méretet, magasságot, margókat és számos egyéb vizuális jellemzőt.

```python
# Width of a single module (the smallest bar)
generator.parameters.barcode.x_dimension = 2   # 2 pixels per module

# Height of the bars (for linear barcodes)
generator.parameters.barcode.bar_height = 50  # 50 pixels tall

# Optional: add quiet zone (margin) if required by a scanner
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10   # 10 pixels margin on each side
```

*Tipp*: Ha a vonalkódot nyomtatni szeretnéd, növeld arányosan az `x_dimension` és `bar_height` értékeket, hogy a cél DPI-nél is olvasható maradjon.

## 5. lépés: A vonalkód kép mentése

Végül írd a generált képet egy fájlba. Az Aspose.Barcode támogatja a PNG, JPEG, BMP és számos egyéb formátumot.

```python
output_path = "output/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

Győződj meg róla, hogy az `output` mappa létezik, vagy hozd létre az `os.makedirs("output", exist_ok=True)` paranccsal a `save` hívása előtt.

### Várható eredmény

Amikor megnyitod a `extended_codetext.png` fájlt, egy Code 128 vonalkódot kell látnod, amely kódolja a `1234567890` numerikus stringet, majd a “特殊字符” kínai karaktereket. A vonalkód modern, ECI‑t támogató szkennerrel történő leolvasása visszaadja az eredeti kevert stringet.

![Vonalkód generálva a hogyan generáljunk vonalkód példával](https://example.com/images/barcode-sample.png){: .align-center alt="Vonalkód generálva a hogyan generáljunk vonalkód példával"}

## Gyakori kérdések és szélhelyzetek

### Mi van, ha más karakterkészletre van szükségem?

Válaszd ki a megfelelő ECI értéket az ISO/IEC 18004 táblázatból. Például az ECI 27 az ISO‑8859‑1 (Latin‑1) karakterkészletet jelenti. Ennek megfelelően cseréld ki a numerikus azonosítót a `add_eci_codetext`-ben.

### Beágyazhatok több mint egy ECI blokkot?

Igen. Hívjad többször a `add_eci_codetext`-et. A builder a szükséges ECI váltó kódokat helyezi el a blokkok között, megőrizve a hozzáadás sorrendjét.

### Támogatja a generátor a QR kódokat ECI-vel?

Teljesen. Cseréld le a `barcode.Symbology.CODE_128`-t `barcode.Symbology.QR`-ra, és állítsd be a QR‑specifikus paramétereket (pl. hibajavítási szint) a `generator.parameters.qr` segítségével.

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorLevel.H
```

### Hogyan kezeljünk nagyon hosszú adatstringeket?

Lineáris vonalkódok, mint a Code 128 esetén, a kiterjesztett kódszöveg használatakor a maximális hossz körülbelül 80 karakter. Ha ezt meghaladod, fontold meg egy kétdimenziós szimbólumra, például QR vagy Data Matrix váltást, amelyek több ezer karaktert is tárolhatnak.

## Teljes, futtatható szkript

Az alábbiakban a teljes program található, amelyet átmásolhatsz egy `generate_extended_barcode.py` nevű fájlba, és közvetlenül futtathatsz.

```python
import os
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# ------------------------------------------------------------------
# Optional: print library version – useful for troubleshooting
# ------------------------------------------------------------------
ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)

# ------------------------------------------------------------------
# Build extended codetext: plain numbers + Chinese characters (ECI 26)
# ------------------------------------------------------------------
builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using UTF‑8
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)

# ------------------------------------------------------------------
# Create a Code128 generator – supports the extended codetext format
# ------------------------------------------------------------------
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,
    extended_codetext
)

# ------------------------------------------------------------------
# Customize appearance (size, quiet zone, etc.)
# ------------------------------------------------------------------
generator.parameters.barcode.x_dimension = 2
generator.parameters.barcode.bar_height = 50
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10

# ------------------------------------------------------------------
# Ensure output directory exists and save the image
# ------------------------------------------------------------------
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)
output_path = os.path.join(output_dir, "extended


## Mit érdemes legközelebb megtanulni?

A következő oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás tartalmaz teljes, működő kódrészleteket lépésről‑lépésre magyarázatokkal, hogy elsajátíthasd a további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [Hogyan generáljunk vonalkód képet kiegészítő tér testreszabásával az Aspose.BarCode használatával](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Hogyan generáljunk vonalkód képet Java-ban az Aspose.BarCode használatával](/barcode/english/java/barcode-rendering-techniques/)
- [Hogyan generáljunk DataMatrix vonalkódot az Aspose.BarCode .NET számára](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}