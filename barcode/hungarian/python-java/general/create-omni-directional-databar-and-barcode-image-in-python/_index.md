---
category: general
date: 2026-08-12
description: Hozzon létre omnidirekcionális databar kódot Pythonban, és tanulja meg,
  hogyan készítsen vonalkód képet Pythonban az Aspose.BarCode segítségével. Kövesse
  a lépésről‑lépésre útmutatót a teljes megoldáshoz.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni directional databar
- create barcode image python
language: hu
lastmod: 2026-08-12
og_description: Készíts omnidirekcionális databar kódot Pythonban, és generálj vonalkód
  képet percek alatt. Ez az útmutató egy teljes, futtatható példát mutat be.
og_image_alt: example of create omni directional databar barcode image in Python
og_title: Készíts többirányú adatbárt – teljes Python útmutató
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create omni directional databar with Python and learn how to create
    barcode image python using Aspose.BarCode. Follow the step‑by‑step guide for a
    complete solution.
  headline: Create omni directional databar and barcode image in Python
  type: TechArticle
tags:
- barcode
- Python
- Aspose
- DataBar
title: Omnidirekcionális databar és vonalkód kép létrehozása Pythonban
url: /hu/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Omni‑directional DataBar és vonalkódkép létrehozása Pythonban

Ha **omni directional databar**‑t szeretnél létrehozni egy Python‑projektben, ez az útmutató megmutatja, hogyan teheted meg, valamint hogyan **hozhatsz létre vonalkódképet Pythonban** az Aspose.BarCode könyvtár segítségével. Kész, azonnal futtatható szkriptet kapsz, amely két különböző képarányú PNG‑fájlt hoz létre.

Az Omni‑directional specifikációnak megfelelő DataBar generálása gyakori igény a kiskereskedelmi és logisztikai alkalmazásokban. A tutorial bemutatja a telepítést, az X‑dimenzió beállítását, a képarány módosítását és a végső képek mentését. Külső szolgáltatásra nincs szükség; minden helyben fut.

## Amire szükséged lesz

Mielőtt elkezdenéd, győződj meg róla, hogy:

* Python 3.8 vagy újabb telepítve van a gépeden.
* Hozzáférésed van egy terminálhoz vagy parancssorhoz.
* Írási jogosultságod van egy olyan mappához, ahová a vonalkódképeket menteni szeretnéd.

Az egyetlen harmadik‑fél függőség a **Aspose.BarCode for Python via .NET**, amely alapból támogatja az Omni‑directional DataBar típust.

## 1. lépés: Aspose.BarCode telepítése Pythonhoz

Az Aspose.BarCode biztosítja a példakódban használt `BarcodeGenerator` osztályt. Telepítsd a csomagot a `pip`‑kel:

```bash
pip install aspose-barcode
```

A csomag tartalmazza a szükséges .NET futtatókörnyezet kötéseket, így nem kell külön .NET SDK‑t telepítened.

## 2. lépés: Könyvtár importálása és a generátor létrehozása

A szkript első sorában egy generátort hozunk létre egy stacked Omni‑directional DataBar‑hoz. Mintadatként a GTIN‑14 értéket `(01)12345678901231` használjuk.

```python
# Step 2: Import classes and create the generator
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a stacked Omni‑directional DataBar with the required data
barcode_generator = BarcodeGenerator(
    EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
    "(01)12345678901231"
)
```

*Miért fontos ez a lépés*: Az `EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL` konstans azt mondja a könyvtárnak, hogy a értéket Omni‑directional DataBar‑ként kódolja, ami sok POS‑olvasó számára kötelező formátum.

## 3. lépés: X‑dimenzió (modulszélesség) beállítása

Az X‑dimenzió határozza meg a legkisebb vonalmodul szélességét. A `2` pixel érték tiszta, jól olvasható vonalkódot eredményez túl nagy fájlméret nélkül.

```python
# Step 3: Set the basic X‑dimension (width of the smallest module) in pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 2
```

*Miért fontos ez a lépés*: Az X‑dimenzió finomhangolásával egyensúlyba hozhatod az olvashatóságot és a kép méreteit. Túl kicsi X‑dimenzió rosszul jelenhet meg alacsony felbontású nyomtatókon.

## 4. lépés: Képarány konfigurálása és az első kép mentése

A képarány befolyásolja a DataBar magasságát a szélességhez képest. A `15` képarány kompakt vizuális stílust eredményez.

```python
# Step 4: Configure an aspect ratio of 15 and save the first image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 15
barcode_generator.save("output/StackedAR15.png", BarCodeImageFormat.Png)
```

> **Pro tipp**: Használd a `pathlib.Path`‑t a kimeneti útvonal építéséhez, amely automatikusan létrehozza a hiányzó könyvtárakat.

```python
from pathlib import Path

output_dir = Path("output")
output_dir.mkdir(parents=True, exist_ok=True)
barcode_generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)
```

## 5. lépés: Képarány módosítása a második vizuális stílushoz és egy másik kép mentése

A képarány `30`‑ra állítása magasabb vonalkódot eredményez, ami egyes szkennerhardvereknél kötelező lehet.

```python
# Step 5: Change the aspect ratio to 30 and save the second image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 30
barcode_generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)
```

*Miért fontos ez a lépés*: Különböző kiskereskedők és szkennereszközök eltérő méretkorlátozásokkal rendelkeznek. A két képarány egyetlen szkriptben való biztosítása lehetővé teszi a pontos stílus generálását kódduplicáció nélkül.

## Teljes szkript – omni directional databar és vonalkódkép Pythonban

Az alábbiakban a teljes, futtatható példakód látható, amely tartalmazza az összes korábbi lépést. Mentsd `generate_databar.py` néven, majd futtasd a `python generate_databar.py` paranccsal.

```python
#!/usr/bin/env python3
"""
Complete example that creates an omni directional databar
and demonstrates how to create barcode image python using Aspose.BarCode.
"""

# Import required classes
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from pathlib import Path

def main():
    # Define output directory and ensure it exists
    output_dir = Path("output")
    output_dir.mkdir(parents=True, exist_ok=True)

    # Initialize the generator with Omni‑directional DataBar data
    generator = BarcodeGenerator(
        EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
        "(01)12345678901231"
    )

    # Set X‑dimension to 2 pixels for good readability
    generator.parameters.barcode.x_dimension.pixels = 2

    # First visual style – aspect ratio 15
    generator.parameters.barcode.data_bar.aspect_ratio = 15
    generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)

    # Second visual style – aspect ratio 30
    generator.parameters.barcode.data_bar.aspect_ratio = 30
    generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)

    print(f"Images saved to: {output_dir.resolve()}")

if __name__ == "__main__":
    main()
```

### Várható kimenet

A szkript futtatása a következő fájlokat hozza létre:

```
output/StackedAR15.png   # DataBar with aspect ratio 15
output/StackedAR30.png   # DataBar with aspect ratio 30
```

Mindkét kép egy érvényes Omni‑directional DataBar‑t jelenít meg, amelyet a szabványos kiskereskedelmi berendezések képesek beolvasni.

![példa omni directional databar vonalkódkép Pythonban](example_databar.png "omni directional databar vonalkódkép Python")

*Az előző kép csak egy helyőrző, amely a két mentett PNG‑fájlt szemlélteti.*

## Gyakori problémák kezelése

| Probléma | Ok | Megoldás |
|----------|----|----------|
| `ImportError: No module named aspose` | Az Aspose.BarCode nincs telepítve, vagy másik környezetben van. | Aktiváld a megfelelő virtuális környezetet, és futtasd a `pip install aspose-barcode` parancsot. |
| `PermissionError` mentéskor | A szkriptnek nincs írási joga a célmappához. | Válassz egy saját mappát, vagy futtasd a szkriptet megfelelő jogosultságokkal. |
| A vonalkód nem olvasható | Az X‑dimenzió túl alacsony, vagy a képarány nem kompatibilis a szkennerrel. | Növeld az `x_dimension.pixels` értékét 3‑ra vagy 4‑re, és próbálj ki más `aspect_ratio` értékeket (pl. 20, 25). |
| Hiányzó .NET futtatókörnyezet | Az Aspose.BarCode .NET futtatókörnyezetet igényel Windows‑on/Linux‑on. | Telepítsd a legújabb .NET futtatókörnyezetet a Microsoft oldaláról; a csomag dokumentációja platform‑specifikus útmutatót tartalmaz. |

## A példa bővítése

A szkriptet módosíthatod más DataBar változatok (pl. `DATABAR_STACKED`, `DATABAR_EXPANDED`) generálására. Cseréld ki az `EncodeTypes` konstansot ennek megfelelően:

```python
generator = BarcodeGenerator(EncodeTypes.DATABAR_EXPANDED, "(01)12345678901231")
```

Ha a vonalkódot PDF‑be szeretnéd beágyazni, az Aspose.PDF for Python közvetlenül importálhatja a PNG‑fájlt, vagy használhatod a `save` metódust `BarCodeImageFormat.Pdf` paraméterrel.

## Összegzés

Ez a tutorial bemutatta, hogyan **hozz létre omni directional databar**‑t és hogyan **hozz létre vonalkódképet Pythonban** az Aspose.BarCode segítségével. Most már rendelkezel egy teljes, reprodukálható szkripttel, amely két különböző képarányú PNG‑fájlt generál, kezeli a gyakori buktatókat, és könnyen bővíthető más vonalkódformátumokra.

Ezután fedezd fel a QR‑kódok generálását, a vonalkód PDF‑számlákba való beillesztését, vagy a nagy termékkatalógusok kötegelt feldolgozásának automatizálását. Mindegyik téma az itt bemutatott `BarcodeGenerator` mintára épül. Jó kódolást!


## Mit érdemes legközelebb megtanulni?


Az alábbi tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutató technikáira épülnek. Minden forrás komplett, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy elsajátíthasd az API további funkcióit, és alternatív megvalósítási megközelítéseket alkalmazhass saját projektjeidben.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to create barcode image and render it in Java](/barcode/english/java/barcode-rendering-techniques/rendering-barcode-image-instance/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}