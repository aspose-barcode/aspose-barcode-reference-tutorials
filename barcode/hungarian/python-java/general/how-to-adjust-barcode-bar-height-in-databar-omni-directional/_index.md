---
category: general
date: 2026-11-27
description: Tanulja meg, hogyan állíthatja be a vonalkód sávmagasságát egy DataBar
  Omni‑Directional vonalkódgenerátorban. A lépésről‑lépésre bemutatott kód megmutatja,
  hogyan állítható a magasság 30 px és 60 px értékre.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- adjust barcode bar height
- DataBar Omni‑Directional barcode
- set XDimension
- barcode image format
- BarCodeImageFormat
- barcode generator python
language: hu
lastmod: 2026-11-27
og_description: Állítsa be a vonalkód sávmagasságát a DataBar Omni‑Directional vonalkódgenerátorban
  Python segítségével. Kövesse a teljes útmutatót a magasságok, az X‑dimenzió beállításához,
  és a PNG képek mentéséhez.
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode with adjusted bar height
og_title: A DataBar Omni‑Directional generátorban a vonalkód sávmagasságának beállítása
schemas:
- author: GroupDocs
  dateModified: '2026-11-27'
  description: Learn how to adjust barcode bar height in a DataBar Omni‑Directional
    barcode generator. Step‑by‑step code shows setting heights to 30 px and 60 px.
  headline: How to adjust barcode bar height in DataBar Omni‑Directional generator
  type: TechArticle
tags:
- barcode
- python
- DataBar
- imaging
title: Hogyan állítsuk be a vonalkód sávmagasságát a DataBar Omni‑Directional generátorban
url: /hu/python-java/general/how-to-adjust-barcode-bar-height-in-databar-omni-directional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan állítsuk be a vonalkód sávmagasságát a DataBar Omni‑Directional generátorban

Ha **a vonalkód sávmagasságát** szeretné módosítani egy DataBar Omni‑Directional vonalkódban, ez az útmutató pontosan megmutatja, hogyan teheti meg. Egy teljes, futtatható Python példát láthat, amely a sávmagasságot 30 px‑ről 60 px‑re változtatja, miközben az X‑dimenziót és a képformátumot változatlanul hagyja.

A vonalkód vizuális méreteinek módosítása gyakori igény, ha a vonalkódnak egy adott címkemérethez vagy tervezési irányelvhez kell illeszkednie. A sávmagasság mellett a **X‑dimenziót** (modulméret) vagy egy másik **vonalkód képformátumot**, például PNG‑t vagy JPEG‑t is módosíthat.

Ebben a tutorialban Ön:

* Telepíti a szükséges könyvtárat (GroupDocs.Barcode for Python)
* Létrehozza a DataBar Omni‑Directional vonalkód generátort
* Beállítja a modulméretet az `XDimension` segítségével
* Kétszer módosítja a sávmagasság tulajdonságát
* Elmenti a kapott képeket a kívánt **BarCodeImageFormat**‑ban

Előzetes tapasztalat a GroupDocs API‑val nem szükséges – csak alapvető Python ismeretekre van szükség.

## Előfeltételek

Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

* Python 3.8 vagy újabb verzióval
* `groupdocs.barcode` csomaggal (`pip install groupdocs-barcode`)  
* Írási jogosultsággal egy olyan mappára, ahová a PNG fájlok mentésre kerülnek

Ha nem ismeri a **DataBar Omni‑Directional vonalkódot**, tudja, hogy ez egy 14‑jegyű GTIN‑t kódol, és széles körben használják a kiskereskedelemben, hogy bármilyen tájolásból beolvasható legyen.

## 1. lépés: A DataBar Omni‑Directional vonalkód generátor beállítása

Először importálja a szükséges osztályokat, és hozza létre a generátort a kódolni kívánt GTIN adatokkal.

```python
from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a DataBar Omni‑Directional barcode
# The string "(01)12345678901231" follows the GS1 Application Identifier syntax
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")
```

*Miért fontos:* Az `EncodeTypes.DatabarOmniDirectional` állandó azt mondja a könyvtárnak, hogy az Omni‑Directional szimbólumot állítsa elő. Az adatkarakterlánc tartalmazza az `(01)` AI‑t, amely egy GTIN‑14 értéket jelöl.

## 2. lépés: Az X‑dimenzió (modulméret) meghatározása

Az X‑dimenzió szabályozza a legkeskenyebb sáv szélességét. Képernyőn történő megjelenítéshez gyakori érték a **2 px modulonként**.

```python
# Set the module (X‑dimension) size – 2 px per module
gen.parameters.barcode.x_dimension.pixels = 2
```

A konzisztens **set XDimension** biztosítja, hogy a vonalkód megfelelően méreteződjön különböző nyomtatók és szkennerek esetén.

## 3. lépés: A sávmagasság beállítása 30 px‑re és a kép mentése

Most módosítjuk a sávmagasság tulajdonságát. Az első magasság **30 px**, amely kis címkékhez megfelelő.

```python
# Define the first bar height (30 px)
gen.parameters.barcode.bar_height.pixels = 30

# Save the barcode as a PNG image
gen.save("output/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png)
```

A `BarCodeImageFormat.Png` állandó a **vonalkód képformátum** PNG‑t választja, amely veszteségmentes minőséget biztosít.

### Várható eredmény

A `DatabarBarHeight30Pixels.png` fájl egy DataBar Omni‑Directional vonalkódot tartalmaz, amelynek sávjai 30 px magasak. Alább egy helyőrző előnézet:

![30 px sávmagasságú DataBar vonalkód](images/databar_30px.png "30 px sávmagasságú DataBar vonalkód")

> **Tipp:** Ha PNG‑t egy képszerkesztőben nyitja meg, láthatja a pontos sávmagasságot. A keskeny sávok 2 px szélesek, ahogy korábban definiáltuk.

## 4. lépés: A sávmagasság módosítása 60 px‑re a magasabb vonalkódhoz

Olyan alkalmazásokhoz, amelyek nagyobb vizuális lábnyomot igényelnek – például fuvarcímkék – a sávmagasságot **60 px**‑re növelheti.

```python
# Change the bar height to 60 px for a taller barcode
gen.parameters.barcode.bar_height.pixels = 60
```

Csak a `BarHeight` tulajdonság változik; az X‑dimenzió és a kódolás változatlan marad, így a vonalkód továbbra is olvasható.

## 5. lépés: A frissített vonalkód kép mentése

Végül írja ki a magasabb vonalkódot egy második PNG fájlba.

```python
# Save the updated barcode image
gen.save("output/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png)
```

### Várható eredmény

A `DatabarBarHeight60Pixels.png` ugyanazt az adatot kódolja, de minden sáv most 60 px magas. A vizuális különbség alább látható:

![60 px sávmagasságú DataBar vonalkód](images/databar_60px.png "60 px sávmagasságú DataBar vonalkód")

## Teljes, futtatható példa

Mindent egy helyen, itt a teljes szkript, amelyet bemásolhat egy `adjust_barcode_height.py` nevű fájlba, és közvetlenül futtathat.

```python
# adjust_barcode_height.py
# Demonstrates how to adjust barcode bar height for a DataBar Omni‑Directional barcode

from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create the generator with GTIN data
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")

# 2️⃣ Set module size (X‑dimension) to 2 px
gen.parameters.barcode.x_dimension.pixels = 2

# 3️⃣ First bar height: 30 px
gen.parameters.barcode.bar_height.pixels = 30
gen.save(os.path.join(output_dir, "DatabarBarHeight30Pixels.png"), BarCodeImageFormat.Png)

# 4️⃣ Second bar height: 60 px
gen.parameters.barcode.bar_height.pixels = 60
gen.save(os.path.join(output_dir, "DatabarBarHeight60Pixels.png"), BarCodeImageFormat.Png)

print(f"Barcodes saved to '{output_dir}'")
```

A szkript futtatása:

```bash
python adjust_barcode_height.py
```

Két PNG fájlt kell látnia az `output` mappában, mindkettő a beállított sávmagasságot tükrözi.

## Gyakori kérdések és széljegyek

| Kérdés | Válasz |
|----------|--------|
| **Használhatok JPEG‑et PNG helyett?** | Igen. Cserélje le a `BarCodeImageFormat.Png`‑t `BarCodeImageFormat.Jpeg`‑re. A JPEG veszteséges, ezért a pontos olvasáshoz a PNG‑t részesítse előnyben. |
| **Mi van, ha a sávmagasság nem 10‑es többszöröse?** | A `BarHeight.Pixels` tulajdonság bármely egész értéket elfogad. Csak rendelje hozzá a kívánt pixel számot (pl. `45`). |
| **A sávmagasság módosítása befolyásolja a kódolt adatot?** | Nem. Csak a vizuális megjelenés változik; az adatkarakterlánc változatlan marad. |
| **Hogyan változtathatom meg az X‑dimenziót az első kép mentése után?** | A `gen.parameters.barcode.x_dimension.pixels` értékét bármikor módosíthatja a `save()` hívása előtt. A változás a későbbi képekre vonatkozik. |
| **A generátor szálbiztos?** | A `BarcodeGenerator` példány nem garantáltan szálbiztos. Ha párhuzamosan generál vonalkódokat, hozzon létre külön példányt szálanként. |

## Következtetés

Most már tudja, hogyan **állítsa be a vonalkód sávmagasságát** egy DataBar Omni‑Directional generátorban Python‑ban. A tutorial bemutatta a generátor létrehozását, az **X‑dimenzió** beállítását, a **vonalkód sávmagasság** módosítását, valamint a képek mentését a kívánt **vonalkód képformátumban**.

Innen tovább kísérletezhet más magasságokkal, különböző modulméretekkel, vagy áttérhet alternatív képformátumokra, például JPEG‑re vagy BMP‑re. Felfedezheti a további **barcode generator python** funkciókat is, mint például a humán‑olvasható szöveg hozzáadása vagy a színsémák módosítása.

Boldog kódolást, és tartsa a vonalkódjait élesen és tökéletesen méretezve!


## Mit tanuljon meg legközelebb?


Az alábbi tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsen elsajátítani további API‑funkciókat és alternatív megvalósítási megközelítéseket saját projektjeiben.

- [How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Create omni directional databar and barcode image in Python](/barcode/english/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/)
- [.net barcode generator – change barcode height](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}