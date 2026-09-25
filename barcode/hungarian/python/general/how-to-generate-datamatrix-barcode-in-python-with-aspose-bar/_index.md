---
category: general
date: 2026-08-22
description: Tanulja meg, hogyan generáljon DataMatrix vonalkódot Pythonban, és kódolja
  az orosz szöveget az Aspose.BarCode használatával – lépésről lépésre útmutató.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate DataMatrix barcode
- encode Russian text
language: hu
lastmod: 2026-08-22
og_description: Generáljon DataMatrix vonalkódot Pythonban, és kódolja az orosz szöveget
  az Aspose.BarCode segítségével. Kövesse a teljes példát, és futtassa azonnal.
og_image_alt: Python script that generate DataMatrix barcode with encoded Russian
  text
og_title: DataMatrix vonalkód generálása Pythonban – teljes Aspose.BarCode útmutató
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  headline: How to generate DataMatrix barcode in Python with Aspose.BarCode
  type: TechArticle
- description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  name: How to generate DataMatrix barcode in Python with Aspose.BarCode
  steps:
  - name: '**ABC123** – the plain identifier.'
    text: '**ABC123** – the plain identifier.'
  - name: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
    text: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
  - name: Open the PNG file in an image viewer.
    text: Open the PNG file in an image viewer.
  - name: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
    text: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
  - name: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
    text: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
  type: HowTo
tags:
- Aspose.BarCode
- Python
- barcode generation
title: Hogyan generáljunk DataMatrix vonalkódot Pythonban az Aspose.BarCode segítségével
url: /hu/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan generáljunk DataMatrix vonalkódot Pythonban az Aspose.BarCode segítségével

Ha **DataMatrix vonalkódot** szeretnél **generálni Pythonban**, miközben **orosz szöveget** kódolsz, ez az útmutató pontos lépéseket mutat. Megmutatjuk a teljes, futtatható példát, amely egy kiterjesztett kódszöveget épít, beállítja a vonalkódot, és egyetlen szkriptben elmenti a képet.

A nem‑ASCII karaktereket tartalmazó vonalkódok létrehozása gyakran felveti a karakterkészletek és az adatkódolás kérdését. Az Aspose.BarCode `ExtCodetextBuilder`‑jével biztonságosan ágyazhatod be az UTF‑8 szöveget, például cirill betűket, egy DataMatrix szimbólumba. Az eredmény minden, a DataMatrix szabványt támogató szkennerrel működik.

Ebben a tutorialban:

* Telepíted a szükséges Aspose.BarCode csomagot.
* Létrehozod a kiterjesztett kódszöveget, amely keveri az egyszerű adatot és az orosz szöveget.
* **DataMatrix vonalkódot generálsz** a kiterjesztett karakterlánccal.
* Beállítod a vonalkód paramétereit, például a modulméretet.
* Elmented a vonalkódot PNG fájlként.

Nincs szükség külső szolgáltatásokra; minden helyben fut a gépeden.

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy:

* Python 3.8 vagy újabb telepítve van.
* Aktív Aspose.BarCode for Python licenc (egy ingyenes próba is elegendő fejlesztéshez).
* Alapvető ismeretekkel rendelkezel a Python szkriptelésről.

Az Aspose.BarCode könyvtárat a pip segítségével telepítheted:

```bash
pip install aspose-barcode
```

## 1. lépés: Kiterjesztett kódszöveg létrehozása

Az első feladat egyetlen karakterlánc létrehozása, amely tartalmazza a egyszerű termékazonosítót és az orosz kifejezést is. Az `ExtCodetextBuilder` lehetővé teszi, hogy különböző kódszöveg‑részeket összefűzz, miközben megőrzi azok kódolási információját.

```python
# Import required Aspose.BarCode classes
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

# Initialize the extended codetext builder
builder = ExtCodetextBuilder()

# Add a plain ASCII identifier – this could be a SKU, part number, etc.
builder.add_plain_codetext("ABC123")

# Add Russian text using ECI (Extended Channel Interpretation) encoding.
# The eci_encoding value 3 corresponds to UTF‑8.
builder.add_eci_codetext(eci_encoding=3, codetext="Привет")

# Retrieve the combined string that Aspose.BarCode will use.
extended_text = builder.get_extended_codetext()
print("Generated extended codetext:", extended_text)
```

**Miért fontos ez a lépés** – A DataMatrix szimbólumok nyers bájtokat tárolnak. Amikor betűkészleteket keversz, meg kell mondanod a kódolónak, melyik karakterkészlet melyik szegmensre vonatkozik. Az `add_eci_codetext` metódus egy ECI indikátort helyez el az orosz szöveg előtt, biztosítva, hogy a szkennerek a bájtokat UTF‑8‑ként értelmezzék. ECI nélkül a cirill karakterek összezavart adatként jelennek meg.

## 2. lépés: DataMatrix vonalkód generátor létrehozása

Miután a kiterjesztett kódszöveg készen van, példányosíts egy `BarcodeGenerator`‑t, amelynek a típusa `EncodeTypes.DATA_MATRIX`.

```python
# Create a DataMatrix barcode generator using the extended codetext
generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)
```

**Miért DataMatrix?** – A DataMatrix egy kétdimenziós vonalkód, amely akár 2 335 alfanumerikus karaktert vagy 1 556 bájtot is tárolhat. Ideális kis tárgyakhoz, ipari alkatrészekhez, és olyan helyzetekben, ahol többnyelvű szöveget kell beágyazni.

## 3. lépés: (Opcionális) Vonalkód paraméterek konfigurálása

Az Aspose.BarCode számos paramétert kínál. A legtöbb esetben az alapbeállítások olvasható szimbólumot eredményeznek. Azonban előfordulhat, hogy a modul (a mátrix legkisebb négyzete) méretét szeretnéd a nyomtatási követelményekhez igazítani.

```python
# Set the module (pixel) size to 2.5 points – adjust as needed for your printer DPI
generator.parameters.barcode.x_dimension = 2.5
```

Egyéb hasznos paraméterek közé tartozik a hibajavítási szint, a margó és a háttérszín. Ezeket csak akkor módosítsd, ha a célkörnyezeted speciális toleranciákat igényel.

## 4. lépés: A vonalkód kép mentése

Végül írd a vonalkódot egy fájlba. A `save` metódus PNG, JPEG, BMP és több vektoros formátumot is támogat.

```python
# Save the barcode image to the desired folder
output_path = "YOUR_DIRECTORY/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

Amikor megnyitod a `extended_codetext.png` fájlt, egy tiszta DataMatrix szimbólumot látsz. Egy szabványos DataMatrix olvasóval beolvasva a két részt kapod:

1. **ABC123** – az egyszerű azonosító.
2. **Привет** – az orosz üdvözlet, helyesen UTF‑8‑ként dekódolva.

## Teljes, futtatható példa

Az alábbi teljes szkriptet bemásolhatod egy `generate_datamatrix.py` nevű fájlba. Cseréld ki a `YOUR_DIRECTORY`‑t egy létező mappára a rendszereden.

```python
# generate_datamatrix.py
# -------------------------------------------------
# Complete example: generate DataMatrix barcode and encode Russian text
# -------------------------------------------------

import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

def main():
    # Step 1: Build extended codetext
    builder = ExtCodetextBuilder()
    builder.add_plain_codetext("ABC123")
    builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_text = builder.get_extended_codetext()
    print("Generated extended codetext:", extended_text)

    # Step 2: Create DataMatrix generator
    generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)

    # Step 3: Optional parameters (adjust module size if needed)
    generator.parameters.barcode.x_dimension = 2.5

    # Step 4: Save the image
    output_path = "YOUR_DIRECTORY/extended_codetext.png"
    generator.save(output_path)
    print(f"Barcode saved as {output_path}")

if __name__ == "__main__":
    main()
```

Futtasd a szkriptet a parancssorból:

```bash
python generate_datamatrix.py
```

A konzolon a következőhöz hasonló kimenetet kell látnod:

```
Generated extended codetext: (ECI:3)ПриветABC123
Barcode saved as YOUR_DIRECTORY/extended_codetext.png
```

## Az eredmény ellenőrzése

Annak megerősítésére, hogy a vonalkód helyesen kódolja az orosz kifejezést:

1. Nyisd meg a PNG fájlt egy képmegjelenítőben.
2. Használj bármilyen DataMatrix olvasó alkalmazást (számos mobilapp támogatja) vagy egy hardveres szkennert.
3. A dekódolt karakterláncnak `ABC123Привет`‑nek kell megjelenítenie (vagy a két rész külön, a szkenner UI‑jától függően).

Ha az orosz karakterek értelmetlenül jelennek meg, ellenőrizd, hogy a szkenner támogatja‑e az ECI UTF‑8‑at. A legtöbb modern olvasó igen, de a régebbi eszközöknek explicit beállításra lehet szükségük.

## Gyakori hibák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| Görbe cirill kimenet | Hiányzó ECI indikátor | Használd az `add_eci_codetext`‑t `eci_encoding=3`‑val. |
| A vonalkód túl kicsi a nyomtatóhoz | Alapértelmezett modulméret túl finom alacsony DPI‑nél | Növeld a `x_dimension`‑t (pl. `3.0` vagy `4.0`). |
| Fájl nem mentődik | Érvénytelen könyvtárútvonal | Győződj meg róla, hogy a `YOUR_DIRECTORY` létezik és írható. |
| A szkenner nem olvas | Túl nagy adat sűrűség | Csökkentsd a kódolt adat mennyiségét vagy növeld a hibajavítási szintet (`generator.parameters.barcode.error_correction_level`). |

## A példa kiterjesztése

A mintát más nyelvek vagy adat típusok esetén is alkalmazhatod:

* **Japán vagy arab szöveg kódolása** – módosítsd az `eci_encoding`‑t a megfelelő értékre (pl. 5 az ISO‑8859‑5‑höz, 6 az ISO‑8859‑7‑hez).  
* **Több ECI szegmens hozzáadása** – hívd meg az `add_eci_codetext`‑t többször, mindegyikhez saját kódolással.  
* **QR kód létrehozása** – cseréld le a `EncodeTypes.DATA_MATRIX`‑t `EncodeTypes.QR`‑ra.  

Minden egyéb lépés változatlan marad, mivel az `ExtCodetextBuilder` elrejti az alacsony szintű bájtkezelést.

## Összegzés

Most már tudod, hogyan **generálj DataMatrix vonalkódot** Pythonban, és hogyan **kódolj orosz szöveget** az Aspose.BarCode kiterjesztett kódszöveg funkciójával. A teljes szkript kezeletlenül végzi a karakterkészlet‑egyeztetést, a vonalkód létrehozását és a kép kimenetet néhány sor kóddal.

Ezután fedezd fel a többi vonalkód szimbólumot (PDF417, Aztec), vagy integráld a generátort egy webszolgáltatásba, amely igény szerint PNG képeket ad vissza. Ugyanazok a elvek – kiterjesztett kódszöveg építése és a megfelelő `EncodeTypes` kiválasztása – érvényesek az egész Aspose.BarCode csomagra.

Jó kódolást, és élvezd a többnyelvű vonalkód generálás erejét!

## Mit tanulj meg legközelebb?

A következő tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutató technikáira épülnek. Minden forrás teljes, működő kódrészleteket és lépésről‑lépésre magyarázatokat tartalmaz, hogy a további API funkciókat is elsajátíthasd, és alternatív megvalósítási megközelítéseket fedezhess fel saját projektjeidben.

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [Generate a DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET (C#)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}