---
category: general
date: 2026-08-22
description: A C#-os vonalkódgenerátor oktatóanyag bemutatja, hogyan lehet vonalkód
  PNG fájlokat generálni, DataBar vonalkódokat létrehozni, és a vonalkód magasságát
  néhány lépésben beállítani.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- generate barcode PNG
- create DataBar barcode
- adjust barcode height
language: hu
lastmod: 2026-08-22
og_description: A C# vonalkód-generátor útmutató lépésről lépésre bemutatja, hogyan
  generáljunk PNG vonalkódot, hozzunk létre DataBar vonalkódokat, és állítsuk be hatékonyan
  a vonalkód magasságát.
og_image_alt: Screenshot of two DataBar Omni‑directional barcodes with different heights
  saved as PNG files
og_title: vonalkód generátor C# – DataBar vonalkódok létrehozása és magasságuk beállítása
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to generate barcode PNG files,
    create DataBar barcodes, and adjust barcode height in just a few steps.
  headline: How to use a barcode generator C# to create DataBar Omni‑directional barcodes
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Hogyan használjunk C#-os vonalkódgenerátort DataBar Omni‑directional vonalkódok
  létrehozásához
url: /hu/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan használjunk C# barcode generator-t a DataBar Omni‑directional vonalkódok létrehozásához

Ha szükséged van egy **barcode generator C#**-ra, amely magas‑minőségű PNG képeket tud előállítani, ez az útmutató mindent lefed. Megtanulod, hogyan generálj barcode PNG fájlokat, hozd létre a DataBar Omni‑directional vonalkódot, és állítsd be a vonalkód magasságát anélkül, hogy elhagynád az IDE‑t.

A vonalkódok programozott generálása megszünteti a grafikus szerkesztő használatával járó manuális lépést. A tutorial végére két PNG fájlod lesz – egy 30‑pixel magasságú és egy 60‑pixel magasságú – készen állva számlákba, címkékbe vagy készletkezelő rendszerekbe való beillesztésre.

**Prerequisites**

- .NET 6.0 vagy újabb (a kód .NET Framework 4.7+‑vel is működik)
- Hivatkozás a `Aspose.BarCode` NuGet csomagra (vagy bármely hasonló API‑t kínáló könyvtárra)
- Alapvető ismeretek C#‑ról és a Visual Studio‑ról vagy a kedvenc IDE‑dról

---

## 1. lépés: A barcode generator C# projekt beállítása

A **barcode generator C#** példány létrehozása az első dolog, amit megteszel. A konstruktor két argumentumot vár: a vonalkód típusát (`EncodeTypes.DatabarOmniDirectional`) és az adatpayloadot. Ebben a példában a payload a GS1 Application Identifier formátumnak megfelelő 14‑jegyű GTIN.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the barcode generator for a DataBar Omni‑directional code
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

**Miért fontos:** A `EncodeTypes.DatabarOmniDirectional` enum azt mondja a könyvtárnak, hogy egy olyan DataBar‑t jelenítsen meg, amely bármely irányból olvasható, ami ideális a kis kiskereskedelmi címkékhez.

---

## 2. lépés: A modul dimenzió (X‑dimension) meghatározása

Az X‑dimension szabályozza egyetlen vonalkód modul szélességét. 2 pixelre állítva tiszta, jól olvasható képet kapunk, miközben a fájlméret alacsony marad.

```csharp
        // Set the module (X) dimension to 2 pixels per module
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Tipp:** Ha korlátozott hely miatt szűkebb vonalkódra van szükséged, csökkentsd az értéket 1 pixelre, de teszteld a olvashatóságot egy szkennerekkel.

---

## 3. lépés: Az első PNG generálása 30‑pixel magasságú vonalakkal

A vonalmagasság határozza meg, milyen magasak a vonalak. A 30‑pixel magasság gyakori alapértelmezett a szabványos címkéknél.

```csharp
        // Set bar height to 30 pixels
        generator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image as PNG
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png",
                       BarCodeImageFormat.Png);
```

A `DatabarBarHeight30Pixels.png` fájl most egy **generate barcode PNG**‑t tartalmaz, amely közvetlenül használható weboldalakon vagy igény szerint nyomtatható.

---

## 4. lépés: A vonalkód magasságának 60 pixelre állítása és a második PNG mentése

A vonalmagasság módosítása olyan egyszerű, mint egy új érték hozzárendelése ugyanahhoz a tulajdonsághoz. Ez bemutatja a generátor **adjust barcode height** képességét.

```csharp
        // Change bar height to 60 pixels for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png",
                       BarCodeImageFormat.Png);
    }
}
```

Most már rendelkezel a `DatabarBarHeight60Pixels.png` fájllal, amely ideális nagyobb csomagoláshoz, ahol a vonalkódot távolabbról kell beolvasni.

**Várt kimenet**

- `DatabarBarHeight30Pixels.png` – egy kompakt DataBar Omni‑directional vonalkód, 30 px magas.
- `DatabarBarHeight60Pixels.png` – ugyanaz a vonalkód, kétszeres magasságú a jobb láthatóság érdekében.

Mindkét kép PNG fájl, megőrizve a veszteségmentes minőséget, és szükség esetén támogatja az átlátszóságot.

---

## Hogyan generáljunk barcode PNG fájlokat különböző formátumokban

Bár ez az útmutató a PNG‑re fókuszál, a `Save` metódus más formátumokat is elfogad, például `Jpeg`, `Bmp`, és `Svg`. Ahhoz, hogy **how to generate barcode** fájlokat más formátumban készíts, egyszerűen cseréld le a `BarCodeImageFormat.Png`‑t a kívánt enum értékre:

```csharp
generator.Save(@"path\barcode.svg", BarCodeImageFormat.Svg);
```

Az SVG választása praktikus, ha vektoros képre van szükséged, amely pixelálás nélkül skálázható.

---

## Gyakori buktatók, amikor **create DataBar barcode** képeket készítesz

| Probléma | Ok | Megoldás |
|----------|----|----------|
| Barcode appears blurry | X‑dimension too low for the target resolution | Increase `XDimension.Pixels` to 3 or 4 |
| Scanner cannot read the code | Bar height too short for the scanner’s optics | Use a minimum of 30 pixels or follow the scanner’s specifications |
| Data string is rejected | Incorrect GS1 formatting | Ensure the string starts with the proper Application Identifier, e.g., `(01)` for GTIN‑14 |

Ezeknek a pontoknak a korai kezelése időt takarít meg a vonalkódok termelési folyamatba való integrálásakor.

---

## Haladó tipp: Ugyanannak a generátornak az újrahasználata több vonalkódhoz

Ha **generate barcode PNG** fájlokra van szükséged egy termékcsoporthoz, használd újra ugyanazt a `BarcodeGenerator` példányt, és csak a `CodeText` tulajdonságot frissítsd:

```csharp
string[] gtins = { "(01)12345678901231", "(01)98765432109876" };
int[] heights = { 30, 60 };

foreach (var gtin in gtins)
{
    generator.CodeText = gtin;          // Change data payload
    foreach (var h in heights)
    {
        generator.Parameters.Barcode.BarHeight.Pixels = h;
        string fileName = $"Databar_{gtin.Substring(4)}_{h}Px.png";
        generator.Save($@"YOUR_DIRECTORY\{fileName}", BarCodeImageFormat.Png);
    }
}
```

Ez a minta minimalizálja az objektumok létrehozásának terhelését, és tömör kódot eredményez.

---

## Összegzés

Most már rendelkezel egy teljes **barcode generator C#** munkafolyammal, amely **creates DataBar barcodes**, **generates barcode PNG** fájlokat, és lehetővé teszi a **adjust barcode height** egyetlen tulajdonság módosításával. A példa mindent lefed a projekt beállításától a szélsőséges esetek kezeléséig, így magabiztosan integrálhatod a vonalkód létrehozását bármely .NET alkalmazásba.

**Következő lépések**

- Fedezz fel más vonalkód szimbólumokat (`EncodeTypes.QR`, `EncodeTypes.Code128`), hogy bővítsd a megoldásodat.
- Kombináld a generátort az ASP.NET Core‑val, hogy a vonalkódokat valós időben szolgáld ki egy API végponton keresztül.
- Kísérletezz színbeállításokkal (`generator.Parameters.Barcode.ForeColor`) a márkaépítés érdekében.

Boldog kódolást, és legyenek a beolvasásaid mindig gyorsak!

## Mit érdemes még megtanulni?

A következő útmutatók szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy elsajátíthasd a további API funkciókat, és alternatív megvalósítási megközelítéseket fedezhess fel saját projektjeidben.

- [Hogyan generáljunk és állítsunk be vonalkód magasságot egy dimenziós Databar esetén az Aspose.BarCode for .NET használatával](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Egy dimenziós Databar 2D vonalkódok generálása az Aspose.BarCode .NET API-val](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [Hogyan generáljunk DataMatrix vonalkódokat az Aspose.BarCode for .NET használatával – Lépésről‑lépésre útmutató](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}