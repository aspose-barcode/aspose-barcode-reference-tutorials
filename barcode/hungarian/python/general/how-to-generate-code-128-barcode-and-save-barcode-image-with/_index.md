---
category: general
date: 2026-09-23
description: Tanulja meg, hogyan generáljon Code 128 vonalkódot, és mentse el a vonalkód
  képét az Aspose.BarCode segítségével Pythonban – lépésről‑lépésre útmutató.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate code 128 barcode
- save barcode image
- Aspose.BarCode Python
- extended codetext builder
- barcode PNG export
language: hu
lastmod: 2026-09-23
og_description: Készítsen Code 128 vonalkódot, és mentse el a vonalkód képét az Aspose.BarCode
  segítségével Pythonban. Kövesse ezt a teljes példát a vonalkód létrehozásához, testreszabásához
  és PNG fájlként történő exportálásához.
og_image_alt: Python-generated Code 128 barcode saved as PNG image
og_title: Code 128 vonalkód generálása és vonalkód kép mentése – Python útmutató
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to generate Code 128 barcode and save barcode image using
    Aspose.BarCode in Python – step‑by‑step guide.
  headline: How to generate Code 128 barcode and save barcode image with Aspose.BarCode
  type: TechArticle
tags:
- barcode
- Code 128
- Python
- Aspose
title: Hogyan generáljunk Code 128 vonalkódot, és mentsük el a vonalkód képet az Aspose.BarCode
  segítségével
url: /hu/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan generáljunk Code 128 vonalkódot és mentsük el a vonalkód képet az Aspose.BarCode segítségével

Ha **Code 128 vonalkódot** kell **generálnod** és **el kell mentened a vonalkód képét** egy Python projektben, ez a bemutató pontos lépéseket mutat. Az Aspose.BarCode `ExtCodetextBuilder`‑jével egyszerre ágyazhatsz be egyszerű szöveget és Unicode szegmenseket egyetlen payload‑ba, majd a végeredményt PNG fájlként renderelheted.

Megkapod a teljes, futtatható szkriptet, minden sor magyarázatát, valamint tippeket a gyakori buktatókhoz, például az ECI kódolás kezeléséhez vagy a megfelelő kimeneti mappa kiválasztásához. Nincs szükség külső dokumentációra – csak másold, illeszd be és futtasd.

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy:

* Python 3.8+ telepítve van.
* Az `aspose.barcode` csomag (telepítés: `pip install aspose-barcode`).
* Írási jogosultságod van abba a könyvtárba, ahová a PNG-t menteni szeretnéd.

A kód bármely, az Aspose.BarCode által támogatott szimbólumrendszerrel működik, de a példa a **Code 128**-ra fókuszál, mivel hatékonyan kódol alfanumerikus adatokat és támogatja a kiterjesztett karakterkészleteket.

## 1. lépés: A szükséges osztályok importálása

```python
import barcode                     # Core Aspose.BarCode namespace
from barcode import BarCodeWriter, BarCodeEncodeMode, BarCodeImageFormat
from barcode import ExtCodetextBuilder, BuildVersionInfo
```

*Miért ez a lépés?* Az osztályok importálása hozzáférést biztosít a kiterjesztett codetext építőhöz, a képet létrehozó íróhoz és a verziósegítőhöz, amely a könyvtár frissítéseinek hibakeresésében hasznos lehet.

## 2. lépés: A kiterjesztett codetext felépítése

```python
# Create a builder for extended codetext
builder = ExtCodetextBuilder()

# Add plain text (no ECI) – this part is simple ASCII
builder.add_plain_codetext("ABC123")

# Add a Unicode segment with ECI 0x03 (UTF‑8). The word “Пример” means “Example” in Russian.
builder.add_eci_codetext(0x03, "Пример")

# Retrieve the full extended codetext string
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

Az `ExtCodetextBuilder` lehetővé teszi egyszerű ASCII és Unicode adatok keverését egyetlen vonalkód payload‑ban. Az ECI (Extended Channel Interpretation) `0x03` bájt azt jelzi a szkennernek, hogy a következő bájtok UTF‑8 kódolásúak, ami elengedhetetlen olyan nyelvekhez, mint az orosz, kínai vagy arab.

## 3. lépés: A vonalkód író konfigurálása Code 128-hoz

```python
writer = BarCodeWriter()
writer.encode_type = BarCodeEncodeMode.CODE_128   # Choose Code 128 symbology
writer.code_text = extended_codetext
```

Az `encode_type` értékének `CODE_128`‑ra állítása azt utasítja az írót, hogy **Code 128 vonalkódot** rendereljen. A `code_text` tulajdonság a korábban épített kiterjesztett sztringet kapja.

## 4. lépés: A vonalkód kép mentése PNG formátumban

```python
output_path = "YOUR_DIRECTORY/extended_codetext.png"
writer.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode image saved to {output_path}")
```

A `save` metódus a vonalkódot egy fájlba írja. A `BarCodeImageFormat.PNG` használata biztosítja a veszteségmentes tömörítést és a széles körű kompatibilitást web‑ és mobilalkalmazásokkal.

## 5. lépés (opcionális): Az Aspose.BarCode könyvtár verziójának ellenőrzése

```python
version_info = BuildVersionInfo()
print("Assembly version :", version_info.ASSEMBLY_VERSION)
print("Product version   :", f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR}")
print("Release date      :", version_info.RELEASE_DATE)
```

A pontos könyvtárverzió ismerete akkor hasznos, ha hibákat kell jelenteni vagy a viselkedést különböző kiadások között kell összehasonlítani.

## Várt kimenet

A szkript futtatása a következőhöz hasonló konzolkimenetet eredményez:

```
Extended codetext: ABC123[ECI=03]Пример
Assembly version : 23.12.0.0
Product version   : 23.12
Release date      : 2023-12-01
Barcode image saved to YOUR_DIRECTORY/extended_codetext.png
```

A generált PNG (`extended_codetext.png`) így néz ki:

![Python-generated Code 128 barcode saved as PNG image](images/code128_extended.png)

*A kép egy Code 128 vonalkódot mutat, amely egyszerre kódolja az ASCII `ABC123` sztringet és a orosz „Пример” szót.*

## Gyakori kérdések és speciális esetek kezelése

| Kérdés | Válasz |
|----------|--------|
| **Használhatok másik szimbólumrendszert?** | Igen. Cseréld le a `BarCodeEncodeMode.CODE_128`‑t bármely más támogatott módra, például `QR`, `EAN_13` vagy `PDF_417`. |
| **Mi van, ha az Unicode szövegem emojikat tartalmaz?** | Az emojik is UTF‑8 karakterek, így ugyanaz a `add_eci_codetext` hívás működik. Győződj meg róla, hogy a cél szkenner támogatja a használt ECI‑t. |
| **Hogyan változtathatom meg a kép méretét?** | Állítsd be a `writer.x_dimension` és `writer.bar_height` értékeket a `save` hívás előtt. |
| **Milyen mappát használjak az `output_path`‑hez?** | Bármelyik mappát, amelybe a Python folyamat írást tud végezni. Használd az `os.makedirs`‑t `exist_ok=True` paraméterrel a mappa automatikus létrehozásához. |

## Profi tippek

* **Kerüld a keménykódolt útvonalakat.** Használd az `os.path.join`‑t és a `Path`‑t a `pathlib` modulból a platformfüggetlen kompatibilitásért.
* **Érvényesítsd a vonalkódot.** Mentés után olvasd vissza a képet a `barcode.BarCodeReader`‑rel, hogy megerősítsd, a kódolt szöveg megegyezik az `extended_codetext`‑tel.
* **Teljesítmény tippek.** Ha sok vonalkódot generálsz egy ciklusban, újrahasználd egyetlen `BarCodeWriter` példányt, és csak a `code_text`‑et frissítsd minden iterációban.

## Összegzés

Most már tudod, hogyan **generálj Code 128 vonalkódot** vegyes ASCII és Unicode adatokkal, és hogyan **mentsd el a vonalkód képet** PNG‑ként az Aspose.BarCode Python SDK‑val. A teljes szkript lefedi a kiterjesztett codetext építését, az író konfigurálását, a kép exportálását és a könyvtárverzió ellenőrzését.

Innen tovább felfedezheted:

* Előtér‑/háttérszínek hozzáadása (`writer.back_color`, `writer.fore_color`).
* A vonalkód beágyazása PDF‑ekbe az `Aspose.PDF`‑vel.
* A `BarCodeReader` osztály használata a mentett kép dekódolásához és a tartalom automatikus ellenőrzéséhez.

Jó kódolást, és bátran kísérletezz más szimbólumrendszerekkel és képformátumokkal!

## Mit tanulj meg legközelebb?

A következő oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás komplett, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy könnyedén elsajátíthasd az API további funkcióit és alternatív megvalósítási módokat a saját projektjeidben.

- [Generate Code128 Barcode with Aspose.Barcode Python – Full Guide](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}