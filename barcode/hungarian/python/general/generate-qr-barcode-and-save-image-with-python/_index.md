---
category: general
date: 2026-11-27
description: Generáljon QR vonalkódot Pythonban az Aspose.Barcode használatával, és
  tanulja meg, hogyan mentse el gyorsan a vonalkód képet a lemezre.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate QR barcode
- save barcode image
- Aspose.Barcode Python
- extended codetext QR
- barcode version information
language: hu
lastmod: 2026-11-27
og_description: Generáljon QR vonalkódot Pythonban az Aspose.Barcode segítségével,
  és azonnal mentse el a vonalkód képét. Kövesse a teljes példát a QR kódok létrehozásához,
  testreszabásához és tárolásához.
og_image_alt: Screenshot of a generated QR barcode created with Python
og_title: QR-kód generálása és kép mentése Python‑nal – lépésről lépésre útmutató
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate QR barcode in Python using Aspose.Barcode and learn how to
    save barcode image to disk quickly.
  headline: Generate QR barcode and save image with Python
  type: TechArticle
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: QR kód generálása és kép mentése Pythonnal
url: /hu/python/general/generate-qr-barcode-and-save-image-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# QR barcode generálása és kép mentése Pythonban

Ha Python alkalmazásban **QR barcode**-t kell generálnod, ez az útmutató megmutatja, hogyan teheted ezt az Aspose.Barcode könyvtár segítségével. Megtanulod a **barcode kép mentése** helyes módját egy helyi mappába, a könyvtár verzióinformációinak lekérdezését, valamint a kiterjesztett kódszöveg szegmensek kezelését.

QR kódok létrehozása gyakori követelmény jegyrendszerek, mobil fizetések és termékkövetés esetén. A tutorial végére egy azonnal futtatható szkriptet kapsz, amely QR barcode képfájlt állít elő, és kiírja a verzióinformációkat hibakeresés vagy megfelelőség céljából.

## Előkövetelmények

* Python 3.8 vagy újabb telepítve.  
* Az `aspose-barcode` csomag. Telepítsd a `pip install aspose-barcode` paranccsal.  
* Írási jogosultság a könyvtárban, ahová a barcode kép kerül mentésre.

Nem szükséges további külső szolgáltatás; a teljes folyamat helyben fut.

## 1. lépés: Kiterjesztett kódszöveg építése `ExtCodetextBuilder`-rel

A kiterjesztett kódszöveg lehetővé teszi, hogy egyszerű szöveget és ECI (Extended Channel Interpretation) szegmenseket keverj egyetlen QR kódban. Ez akkor hasznos, ha különböző karakterkészletekből származó karaktereket kell beágyazni, például az euró jelet.

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# Create the builder instance
ext_builder = ExtCodetextBuilder()

# Add a plain text segment
ext_builder.add_plain_codetext("ABC123")

# Add an ECI segment that uses ISO‑IEC 8859‑1 (code page 3)
ext_builder.add_eci_codetext(3, "€123")
```

**Miért fontos ez a lépés:**  
`ExtCodetextBuilder` összeállítja a végső karakterláncot, amelyet a QR kódoló feldolgoz. A kiterjesztett kódszöveg építése nélkül a barcode csak egyszerű ASCII karaktereket tartalmazna, és nem tudná ábrázolni a helyspecifikus szimbólumokat.

## 2. lépés: A kombinált kiterjesztett kódszöveg lekérése

```python
# Get the final extended codetext that will be encoded
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

A kimenet a következőképpen néz ki:

```
Extended codetext: ABC123[ECI3]€123
```

A szögletes zárójelbe tett `[ECI3]` jelző azt mondja a QR kódolónak, hogy a következő karakterekhez a megadott karakterkészletet használja.

## 3. lépés: QR barcode generálása a kiterjesztett kódszöveg használatával

```python
# Create a QR barcode generator with the extended codetext
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)
```

**Magyarázat:**  
`BarcodeGenerator` két argumentumot kap: a barcode típusát (`QR`) és a kódolandó adatot (`extended_codetext`). A generátor előkészíti a megjelenítéshez szükséges belső struktúrákat.

## 4. lépés: A generált barcode kép mentése

```python
# Define the output path – adjust the folder as needed
output_path = "output/qr_extended.png"

# Save the image in PNG format
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")
```

**Miért érdemes ezt a megközelítést használni:**  
A `save` hívása közvetlenül a lemezre írja a képet a fájlkiterjesztésből kikövetkeztetett formátummal. A metódus támogatja a PNG, JPEG, BMP és TIFF formátumokat, így rugalmasan alkalmazható különböző downstream fogyasztók számára.

### A mentett kép ellenőrzése

Nyisd meg a `output/qr_extended.png` fájlt bármely képnézővel. Egy QR kódot kell látnod, amely beolvasáskor visszaadja a `ABC123€123` karakterláncot. A legtöbb modern mobil QR olvasó automatikusan kezeli az ECI szegmenst.

## 5. lépés: Aspose.BarCode verzióinformáció lekérdezése (opcionális, de hasznos)

Az Aspose.BarCode könyvtár pontos verziójának ismerete akkor segít, ha hibákat kell jelenteni vagy kompatibilitást kell ellenőrizni.

```python
# Retrieve version details
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Tipikus kimenet:

```
Aspose.BarCode version:
  Assembly version : 23.9.0.0
  File version     : 23.9.0
  Product          : Aspose.BarCode for Python via .NET
  Release date     : 2023-09-15
```

## Teljes szkript – másold, illeszd be és futtasd

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# 1️⃣ Build extended codetext
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC123")
ext_builder.add_eci_codetext(3, "€123")
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 2️⃣ Generate QR barcode
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)

# 3️⃣ Save barcode image
output_path = "output/qr_extended.png"
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")

# 4️⃣ Display version information
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

A szkript futtatása előállítja a QR kód képet, és kiírja a kiterjesztett kódszöveget és a verzióadatokat a konzolra.

## Gyakori variációk és szélsőséges esetek

| Helyzet | Javasolt módosítás |
|-----------|------------------------|
| **Más karakterkészlet** | Módosítsd az `add_eci_codetext`-nek átadott ECI azonosítót. UTF‑8 esetén használd a `5`-öt. |
| **Magasabb hibajavítás** | Állítsd be a `barcode.parameters.barcode.qr_error_level = bc.QRErrorLevel.H` értéket a `save` hívása előtt. |
| **Egyéni képméret** | Használd a `barcode.parameters.image_width` és `barcode.parameters.image_height` értékeket a pixelméretek szabályozásához. |
| **Nem PNG kimenet** | Módosítsd a `output_path` fájlkiterjesztését `.jpg` vagy `.bmp`-re. A könyvtár automatikusan kiválasztja a megfelelő enkódert. |

## Profi tippek

* **Hozd létre a kimeneti mappát** programozottan, ha esetleg nem létezik:

  ```python
  import os
  os.makedirs(os.path.dirname(output_path), exist_ok=True)
  ```

* **Ellenőrizd a QR kódot** a generálás után, úgy, hogy visszaolvasod az `aspose.barcode.BarcodeReader` segítségével. Ez biztosítja, hogy a kódolt adat megfelel a várakozásoknak, különösen ECI szegmensek használata esetén.

  ```python
  reader = bc.BarcodeReader(output_path, bc.DecodeType.QR)
  for result in reader.read():
      print("Decoded text:", result.code_text)
  ```

* **Teljesítmény tipp** – használd újra ugyanazt a `BarcodeGenerator` példányt, ha egy ciklusban sok QR kódot kell generálni. Állítsd vissza a `code_text` tulajdonságot új objektum létrehozása helyett minden iterációban.

## Következtetés

Most már tudod, hogyan **generálj QR barcode**-t Pythonban az Aspose.Barcode segítségével, hogyan építs kiterjesztett kódszöveget, amely egyszerű és ECI szegmenseket kever, és hogyan **mentsd el a barcode képet** helyesen a lemezre. A szkript azt is bemutatja, hogyan kérdezd le a könyvtár verzióinformációit a hibakereséshez.

A következő lépések, amelyeket érdemes felfedezni:

* Logó átfedés vagy egyedi színek hozzáadása a QR kódhoz.  
* A QR barcode közvetlen beágyazása PDF-ekbe az Aspose.PDF használatával.  
* Tömeges generálás automatizálása nagy adathalmazokhoz.

Nyugodtan kísérletezz különböző adatpayloadokkal, hibajavítási szintekkel és képformátumokkal. Boldog kódolást!

## Mit érdemes legközelebb megtanulni?

A következő tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy elsajátíthasd a további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [How to generate Code 128 barcode and save barcode image with Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [How to generate DataMatrix barcode in Python with Aspose.BarCode](/barcode/english/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}