---
category: general
date: 2026-08-09
description: QR vonalkód létrehozása Pythonban az Aspose.BarCode segítségével. Tanulja
  meg, hogyan építsen kiterjesztett kódszöveget, állítsa be a megjelenést, és mentse
  el a képet – mindezt egyetlen útmutatóban.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create QR barcode
- Aspose.BarCode Python
- extended codetext QR
- QR code generation Python
- barcode visual customization
language: hu
lastmod: 2026-08-09
og_description: QR vonalkód létrehozása Pythonban az Aspose.BarCode segítségével.
  Ez az útmutató bemutatja, hogyan építsünk kiterjesztett kódszöveget, állítsuk be
  a vizuális paramétereket, és exportáljuk a képet.
og_image_alt: Screenshot of a generated QR barcode created with Aspose.BarCode in
  Python
og_title: QR vonalkód létrehozása az Aspose.BarCode segítségével Pythonban – teljes
  kódpélda
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  headline: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  type: TechArticle
- description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  name: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  steps:
  - name: Common variations
    text: '- **Multiple ECI segments:** Call `add_eci_codetext` multiple times to
      mix several languages. - **Different ECI identifiers:** Use `27` for ISO‑8859‑1,
      `28` for ISO‑8859‑2, etc., depending on your target encoding.'
  - name: Edge case handling
    text: '- **High‑density data:** If the encoded data is large, you may need to
      increase `x_dimension` or choose a higher error‑correction level (via `qr_generator.parameters.qr.error_correction_level`).
      - **Transparent background:** Set `qr_generator.parameters.barcode.bg_color
      = Color.Transparent` for PNGs'
  - name: Verifying the result
    text: 'Open the saved file in any image viewer. You should see a QR code that,
      when scanned, returns the combined string:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: QR vonalkód létrehozása az Aspose.BarCode segítségével Pythonban – lépésről‑lépésre
  útmutató
url: /hu/python/general/create-qr-barcode-with-aspose-barcode-in-python-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# QR vonalkód létrehozása az Aspose.BarCode segítségével Pythonban – lépésről‑lépésre útmutató

Ha **QR vonalkódot** kell létrehoznod Pythonban, ez a tutorial végigvezeti a teljes folyamaton az Aspose.BarCode könyvtár használatával. Akár termékazonosítókat, többnyelvű szöveget vagy egyedi adatot kódolsz, megmutatjuk, hogyan építs fel egy kiterjesztett kódszöveget, állítsd be a vizuális paramétereket, és mentsd el a végleges képet egyetlen, futtatható szkriptben.

A példa bemutatja, hogyan jelenítheted meg a könyvtár verzióját, ami segít ellenőrizni, hogy kompatibilis kiadást használsz. A útmutató végére egy használatra kész QR vonalkód képet és a konfigurációs lehetőségek világos megértését kapod.

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy a következők rendelkezésre állnak:

- Python 3.8+ telepítve.
- Az `aspose-barcode` csomag (telepítés: `pip install aspose-barcode`).
- Alapvető ismeretek a Python szintaxisáról.
- Írási jogosultság a kimeneti könyvtárban, ahová a PNG fájl mentésre kerül.

> **Pro tipp:** Használj virtuális környezetet a verzióütközések elkerülése érdekében más projektekben.

## 1. lépés: Az Aspose.BarCode könyvtár verziójának ellenőrzése

A könyvtár verziójának megjelenítése biztosítja, hogy olyan kiadást használsz, amely támogatja a kiterjesztett kódszöveget és a QR kódolást.

```python
from asposebarcode import BuildVersionInfo

# Show the current Aspose.BarCode version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)
```

**Miért fontos:**  
A régebbi kiadások esetleg nem tartalmazzák az `ExtCodetextBuilder` osztályt, amely a vegyes egyszerű és ECI szegmensekhez szükséges. A verzió ellenőrzése megakadályozza a későbbi futásidejű hibákat.

## 2. lépés: Kiterjesztett kódszöveg (extended codetext) felépítése

A kiterjesztett kódszöveg lehetővé teszi egyszerű ASCII adatok és Unicode (ECI) szegmensek kombinálását, ami elengedhetetlen a többnyelvű QR kódokhoz.

```python
from asposebarcode import ExtCodetextBuilder

# Initialize the builder
ext_builder = ExtCodetextBuilder()

# Add a plain segment – typically a product ID or numeric code
ext_builder.add_plain_codetext("ABC12345")

# Add an ECI segment – here we embed Japanese greeting "こんにちは"
# 26 is the ECI identifier for UTF‑8 encoding
ext_builder.add_eci_codetext(26, "こんにちは")

# Retrieve the full extended codetext that the QR generator will use
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")
```

**Miért fontos:**  
Az `add_plain_codetext` metódus az adatot szabványos ASCII‑ként tárolja, míg az `add_eci_codetext` egy Unicode blokkot előtagként az adott ECI jelölővel lát el. Ez a megközelítés biztosítja, hogy a QR‑olvasók helyesen értelmezzék a japán szöveget, elkerülve a torz karaktereket.

### Gyakori variációk

- **Több ECI szegmens:** Hívd meg az `add_eci_codetext` metódust többször a különböző nyelvek keveréséhez.
- **Eltérő ECI azonosítók:** Használd a `27`‑et az ISO‑8859‑1‑hez, a `28`‑at az ISO‑8859‑2‑höz stb., a célkódolástól függően.

## 3. lépés: QR vonalkód generálása a kiterjesztett kódszöveggel

Miután megvan a megfelelően formázott karakterlánc, létrehozhatjuk a QR kódot.

```python
from asposebarcode import BarCodeGenerator, EncodeTypes, BarCodeImageFormat

# Create the QR generator with the extended codetext
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)
```

**Miért fontos:**  
Az `EncodeTypes.QR` azt mondja az Aspose.BarCode‑nak, hogy a QR szimbólumot használja. Az `extended_codetext` közvetlen átadása összekapcsolja a vegyes adatot a QR mátrixszal, megőrizve mind az egyszerű, mind a Unicode részeket.

## 4. lépés: Vizuális megjelenés finomhangolása (opcionális, de ajánlott)

A vonalkód vizuális paramétereinek finomhangolása javítja a beolvasási megbízhatóságot és megfelel a márka irányelveinek.

```python
# Set module (pixel) size – larger values increase overall image size
qr_generator.parameters.barcode.x_dimension = 4      # each module = 4 pixels

# Set border thickness – a thin white border helps scanners isolate the QR code
qr_generator.parameters.barcode.border_width = 2    # 2-pixel border
```

**Miért fontos:**  
- **`x_dimension`** szabályozza egy QR modul méretét; túl kicsi esetén olvasási hibák léphetnek fel alacsony felbontású eszközökön.  
- **`border_width`** egy csendes zónát (quiet zone) ad hozzá. Egyes olvasók legalább 4 modul széles csendes zónát igényelnek; a könyvtár ezt automatikusan hozzáadja, de növelheted a biztonság kedvéért.

### Szélsőséges esetek kezelése

- **Nagy sűrűségű adat:** Ha a kódolt adat nagy, növelned kell az `x_dimension` értékét vagy magasabb hibajavító szintet kell választanod (a `qr_generator.parameters.qr.error_correction_level` segítségével).  
- **Átlátszó háttér:** Állítsd be a `qr_generator.parameters.barcode.bg_color = Color.Transparent` értéket PNG‑k esetén, ahol alfa csatorna szükséges.

## 5. lépés: QR vonalkód kép mentése

Végül írd a képet a lemezre a kívánt formátumban.

```python
# Define output path – replace YOUR_DIRECTORY with an actual folder
output_file = "YOUR_DIRECTORY/extended_qr.png"

# Save as PNG; other formats include JPEG, BMP, GIF, TIFF
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

**Miért fontos:**  
A PNG formátum veszteségmentes minőséget biztosít, ami ideális a tiszta élekre szoruló QR kódokhoz. Ha webalkalmazáshoz más formátumra van szükséged, egyszerűen módosítsd a `BarCodeImageFormat` enumerációt.

### Az eredmény ellenőrzése

Nyisd meg a mentett fájlt bármely képnézegetőben. Egy QR kódot kell látnod, amely beolvasáskor visszaadja a kombinált karakterláncot:

```
ABC12345
こんにちは
```

A legtöbb modern QR‑olvasó alkalmazás először a egyszerű szegmenst jeleníti meg, majd helyesen rendereli a japán üdvözletet.

---

## Teljesen futtatható szkript

Másold az alábbi blokkot egy `create_qr_barcode.py` nevű fájlba, majd futtasd a `python create_qr_barcode.py` paranccsal. Állítsd be a `YOUR_DIRECTORY`‑t egy írható mappára a gépeden.

```python
# create_qr_barcode.py
from asposebarcode import (
    BuildVersionInfo,
    ExtCodetextBuilder,
    BarCodeGenerator,
    EncodeTypes,
    BarCodeImageFormat,
)

# 1️⃣ Display library version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)

# 2️⃣ Build extended codetext (plain + Japanese Unicode)
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC12345")
ext_builder.add_eci_codetext(26, "こんにちは")
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")

# 3️⃣ Create QR generator
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)

# 4️⃣ Optional visual tweaks
qr_generator.parameters.barcode.x_dimension = 4
qr_generator.parameters.barcode.border_width = 2

# 5️⃣ Save image
output_file = "YOUR_DIRECTORY/extended_qr.png"
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

A szkript futtatása kiírja a verziót, a kiterjesztett kódszöveget, és megerősíti, hogy a PNG fájl létrejött.

---

## Összegzés

Most már tudod, hogyan **hozz létre QR vonalkód képeket** Pythonban az Aspose.BarCode segítségével. A tutorial lefedte:

1. A könyvtár verziójának ellenőrzését.  
2. Kiterjesztett kódszöveg építését egyszerű és ECI (Unicode) szegmensekkel.  
3. A QR kód generálását.  
4. A vizuális paraméterek testreszabását, például modulméretet és border_width‑et.  
5. A végleges kép PNG formátumban történő mentését.

Innen tovább felfedezheted:

- Hibajavító szintek módosítása (`qr_generator.parameters.qr.error_correction_level`).  
- Logó vagy háttérkép hozzáadása (`qr_generator.parameters.qr.logo`).  
- Exportálás más formátumokba, például SVG‑be a skálázható webgrafikához.  
- A generátor integrálása Flask vagy Django végpontra a valós‑időben történő QR generáláshoz.

Kísérletezz különböző adatpayloadokkal és vizuális beállításokkal, hogy megfeleljenek alkalmazásod márkájának és beolvasási követelményeinek. Boldog kódolást!

## Mi legyen a következő tanulnivalód?

Az alábbi tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás komplett, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy elsajátíthasd az API további funkcióit és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Create barcode aspose .net - Configuring DataMatrix Code Text](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}