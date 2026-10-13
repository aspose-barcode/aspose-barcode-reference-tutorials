---
category: general
date: 2026-09-29
description: Tanulja meg, hogyan hozhat létre mindenirányú Databar vonalkódot C#-ban
  az Aspose.BarCode segítségével. Állítsa be az X-dimenziót, határozza meg a képarányt,
  és mentse PNG képekként.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional databar barcode
- DataBar stacked omnidirectional barcode
- set barcode aspect ratio
- Aspose.BarCode C#
- generate barcode image
language: hu
lastmod: 2026-09-29
og_description: Készítsen minden irányban olvasható Databar vonalkódot C#-ban az Aspose.BarCode
  használatával. Tanulja meg beállítani az X-dimenziót, módosítani a képarányt, és
  PNG fájlok exportálását.
og_image_alt: Screenshot showing two PNG files of an omnidirectional Databar barcode
  with different aspect ratios
og_title: Omnidirekcionális Databar vonalkód létrehozása C#-ban – lépésről lépésre
  útmutató
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  headline: How to create omnidirectional Databar barcode in C#
  type: TechArticle
- description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  name: How to create omnidirectional Databar barcode in C#
  steps:
  - name: What if I need a different X‑dimension?
    text: You can assign any integer value to `XDimension.Pixels`. Values below `1`
      are ignored, and values above `10` may produce oversized modules that exceed
      printer margins. Test the visual output after each change.
  - name: How do I encode other AI‑generated data (e.g., UPC, EAN)?
    text: Replace the data string in the `BarcodeGenerator` constructor with the appropriate
      Application Identifier (AI). For a UPC‑A code, use `"012345678905"` without
      an AI prefix.
  - name: Can I export to formats other than PNG?
    text: Yes. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`,
      `BarCodeImageFormat.Tiff`, and `BarCodeImageFormat.Bmp`. Choose the format that
      matches your downstream workflow.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Hogyan hozzunk létre omnidirekcionális Databar vonalkódot C#‑ban
url: /hu/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozzunk létre omnidirekcionális Databar vonalkódot C#-ban

Ha **omnidirekcionális Databar vonalkódot** kell létrehoznod egy .NET alkalmazásban, ez az útmutató megmutatja a pontos lépéseket. Meg fogod látni, hogyan inicializálj egy DataBar stacked omnidirectional vonalkódot, állítsd be az X‑dimenziót, módosítsd a képarányt, és generálj PNG képeket az Aspose.BarCode segítségével.

A **DataBar stacked omnidirectional vonalkód** generálása gyakori, amikor termékazonosítókat kell kódolni a kiskereskedelmi szkennerek számára. Ebben az oktatóanyagban megtanulod, hogyan **állítsd be a vonalkód képarányát**, szabályozd a modul méretét, és exportáld az eredményt anélkül, hogy elhagynád az IDE-t.

## Előfeltételek

- .NET 6.0 vagy újabb telepítve
- Visual Studio 2022 (vagy bármely C#‑kompatibilis IDE)
- A **Aspose.BarCode for .NET** NuGet csomag (23.12-es vagy újabb verzió)

A csomagot a NuGet Package Manager segítségével adhatod hozzá:

```bash
dotnet add package Aspose.BarCode
```

## 1. lépés: Az omnidirekcionális Databar vonalkód inicializálása

Az első lépés egy `BarcodeGenerator` példány létrehozása, amely a **DataBar stacked omnidirectional** szimbólumot célozza. A konstruktor megkapja a kódolás típusát és az adatkarakterláncot.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialise a DataBar stacked omnidirectional barcode with GTIN data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Miért fontos:** A `EncodeTypes.DatabarStackedOmniDirectional` érték azt mondja az Aspose.BarCode-nak, hogy a konkrét omnidirekcionális Databar formátumot jelenítse meg, amely mindkét irányban történő szkenneléshez szükséges.

## 2. lépés: Az X‑dimenzió (modulméret) meghatározása

Az X‑dimenzió szabályozza egyetlen vonalkódmodul szélességét pixelben. A `2` pixel érték jól működik a képernyőn történő megjelenítéshez és a legtöbb nyomtatóhoz.

```csharp
        // Set the basic size of the barcode modules (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Miért fontos:** A konzisztens X‑dimenzió biztosítja, hogy a vonalkód megfeleljen a kiskereskedelmi szkennerek minimális méretkövetelményeinek, miközben a képfájl mérete kezelhető marad.

## 3. lépés: Az első képarány beállítása és a kép mentése

A **képarány** meghatározza a DataBar magasság‑szélesség arányát. A `15` képarány kompakt, magas vonalkódot eredményez, amely ideális szűk címkehelyekhez.

```csharp
        // Apply aspect ratio 15 and save the first PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Miért fontos:** A képarány módosítása lehetővé teszi, hogy a vonalkódot különböző címkelayoutokba illeszd anélkül, hogy a olvashatóságot csökkentenéd. A mentett PNG bármely képnézőben megtekinthető.

## 4. lépés: A képarány módosítása és egy második kép generálása

Néha szélesebb vonalkódra van szükség – például, ha a címke több vízszintes helyet biztosít. A képarány `30`‑ra változtatása laposabb megjelenést eredményez.

```csharp
        // Change aspect ratio to 30 and save a second PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Miért fontos:** A **set barcode aspect ratio** tulajdonság kiaknázásával egyetlen kódbázisból több vonalkódvariációt is előállíthatsz, ezáltal egyszerűsítve az automatizált címkekészítési folyamatokat.

## Várt kimenet

A program futtatása két PNG fájlt hoz létre az alkalmazás kimeneti mappájában:

| Fájlnév                     | Képarány | Vizuális leírás |
|----------------------------|----------|-----------------|
| `DatabarAspectRatio15.png` | 15       | Magas, keskeny vonalkód, amely szűk címkékhez alkalmas |
| `DatabarAspectRatio30.png` | 30       | Szélesebb vonalkód, amely több vízszintes helyet tölt ki |

![Omnidirekcionális Databar vonalkód létrehozásának példája](databar-example.png "Omnidirekcionális Databar vonalkód létrehozásának példája")

*A képernyőkép a két generált PNG fájlt mutatja egymás mellett.*

## Gyakori kérdések és szélhelyzetek

### Mi van, ha más X‑dimenzióra van szükségem?

Bármilyen egész számot hozzárendelhetsz a `XDimension.Pixels`‑hez. Az `1` alatti értékek figyelmen kívül maradnak, a `10` feletti értékek túl nagy modulokat eredményezhetnek, amelyek meghaladják a nyomtató margóit. Minden módosítás után teszteld a vizuális kimenetet.

### Hogyan kódoljak más AI‑generált adatot (pl. UPC, EAN)?

Cseréld le a `BarcodeGenerator` konstruktorában lévő adatkarakterláncot a megfelelő Alkalmazási Azonosítóra (AI). UPC‑A kód esetén használd a `"012345678905"`‑t AI előtag nélkül.

### Exportálhatok más formátumokba, mint a PNG?

Igen. A `Save` metódus elfogadja a `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`, `BarCodeImageFormat.Tiff` és `BarCodeImageFormat.Bmp` formátumokat. Válaszd ki azt a formátumot, amely megfelel a további munkafolyamatodnak.

## Pro tipp: a generátor újrahasználata kötegelt feldolgozáshoz

Ha tucatnyi vonalkódot kell generálni változó képarányokkal, tartsd életben a `BarcodeGenerator` példányt, és csak a `DataBar.AspectRatio` értékét módosítsd minden `Save` előtt. Ez elkerüli a generátor minden egyes képhez való újra‑példányosításának terheit.

```csharp
var ratios = new[] { 10, 15, 20, 30 };
foreach (var ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    generator.Save($"DatabarAspectRatio{ratio}.png", BarCodeImageFormat.Png);
}
```

## Következtetés

Most már tudod, hogyan **hozz létre omnidirekcionális Databar vonalkódot** C#-ban az Aspose.BarCode használatával. A `BarcodeGenerator` inicializálásával, az X‑dimenzió beállításával, a **set barcode aspect ratio** módosításával és a PNG fájlok mentésével olyan vonalkódképeket állíthatsz elő, amelyek megfelelnek a különféle címkekövetelményeknek.  

Ezután fedezd fel a kapcsolódó témákat, mint a **generate barcode image** QR kódokhoz, a **DataBar stacked omnidirectional barcode** validálása, vagy a generált PNG-k PDF számlákba való integrálása az Aspose.PDF segítségével. Kísérletezz különböző képarányokkal és modulméretekkel, hogy megtaláld a legoptimálisabb beállítást a saját nyomtatóhardveredhez.

---

## Mit érdemes legközelebb megtanulni?

A következő oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás tartalmaz teljes, működő kódrészleteket lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [Hogyan használjunk vonalkód-generátort C#-ban DataBar omnidirekcionális vonalkódok létrehozásához](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [DataBar stacked omnidirekcionális vonalkód C#‑ban – Teljes útmutató](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [Hogyan generáljunk vonalkódot C#‑ban – vonalkód kép létrehozása C#‑ban DataBar Expanded használatával](/barcode/english/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}