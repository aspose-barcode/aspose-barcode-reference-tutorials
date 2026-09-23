---
category: general
date: 2026-09-22
description: Tanulja meg, hogyan hozhat létre PDF417 vonalkódot C#-ban, állíthatja
  be a vonalkód méretét, és generálhat vonalkód képfájlokat világos lépésről‑lépésre
  kódpéldákkal.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to create PDF417
- set barcode size
- create barcode image c#
language: hu
lastmod: 2026-09-22
og_description: PDF417 vonalkód gyors létrehozása C#-ban. Ez a bemutató megmutatja,
  hogyan állítható be a vonalkód mérete, engedélyezhető a kompakt mód, és hogyan lehet
  PNG képeket előállítani bármely .NET projekthez.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: PDF417 vonalkód létrehozása C#-ban – lépésről lépésre útmutató
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to create PDF417 barcode in C#, set barcode size, and generate
    barcode image files with clear step‑by‑step code examples.
  headline: How to create PDF417 barcode and set its size in C#
  type: TechArticle
tags:
- PDF417
- C#
- Barcode
- Imaging
title: Hogyan készítsünk PDF417 vonalkódot, és állítsuk be a méretét C#-ban
url: /hu/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozhatunk létre PDF417 vonalkódot és állíthatjuk be a méretét C#-ban

Ha **PDF417 vonalkódot** kell létrehoznod C#-ban, ez az útmutató megmutatja, hogyan generálhatod a vonalkódot, hogyan szabályozhatod a méreteit, és hogyan mentheted el az eredményt képfájlként. Legyen szó jegyrendszerről, logisztikai címkéről vagy biztonságos azonosítóról, a PDF417 formátum elsajátítása lehetővé teszi, hogy nagy mennyiségű adatot kódolj egy kompakt vizuális formában.

Ebben a tutorialban megtanulod:

* **PDF417 vonalkód létrehozását** az Aspose.BarCode (vagy bármely kompatibilis) könyvtárral.  
* **A vonalkód méretének beállítását** az X‑dimenzió és az oszlopszám módosításával.  
* **Vonalkép generálását C#-ban** PNG, JPEG vagy BMP kimenethez.  

A példa a Aspose.BarCode for .NET ingyenes közösségi kiadását használja, de ugyanazok a koncepciók más, hasonló tulajdonságokkal rendelkező könyvtárakra is alkalmazhatók.

## Előkövetelmények

Mielőtt elkezdenéd, győződj meg róla, hogy:

* .NET 6.0 SDK vagy újabb telepítve van.  
* C# IDE (Visual Studio, Visual Studio Code, Rider stb.).  
* Az `Aspose.BarCode` NuGet csomag (`dotnet add package Aspose.BarCode`).  

További konfiguráció nem szükséges; a könyvtár Windows, Linux és macOS rendszereken egyaránt működik.

## 1. lépés: Alap PDF417 vonalkód létrehozása és méretének beállítása

Az első lépés egy `BarcodeGenerator` példányosítása a `EncodeTypes.Pdf417` enummal, valamint a kódolni kívánt szöveg megadása. Ezután állítsd be az **X‑dimenziót** (modul szélesség) és az **oszlopok** számát a teljes méret szabályozásához.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Define the text that the barcode will represent.
string data = "Sample text for PDF417 barcode";

// Create a basic PDF417 barcode generator.
var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Set the module width to 2 pixels (controls bar thickness).
basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Set the column count; 3 columns yields a compact visual but still readable.
basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image.
string basicPath = Path.Combine("YOUR_DIRECTORY", "Pdf417Basic.png");
basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
```

**Miért fontosak ezek a beállítások**

* `XDimension.Pixels` határozza meg a legkeskenyebb vonal szélességét. A kisebb érték szorosabb vonalkódot eredményez, míg a nagyobb érték javítja az olvashatóságot alacsony felbontású szkennereknél.  
* `Pdf417.Columns` befolyásolja a vonalkód arányát. Kevesebb oszlop magasabb, több oszlop laposabb vonalkódot eredményez. Az oszlopok módosítása az **vonalkód méretének beállításának** elsődleges módja anélkül, hogy a kódolt adatot megváltoztatnád.

A kód futtatása után a megadott mappában megtalálod a `Pdf417Basic.png` fájlt. A kép a lenti képernyőképre hasonlít:

<img src="images/pdf417-basic.png" alt="PDF417 vonalkód létrehozásának példája, alapvető vonalkód elrendezés">

## 2. lépés: Kompakt PDF417 vonalkód (truncate mód) ugyanazzal a mérettel

Néha egy rövidebb vonalkódra van szükség a korlátozott hely miatt. A PDF417 *truncate* (kompakt) módot kínál, amely eltávolítja a stop mintát és csökkenti a magasságot. A `Truncate` tulajdonság kapcsolja be ezt a viselkedést.

```csharp
// Reuse the same data string.
var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Keep the same module width and column count for a fair size comparison.
compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Enable compact (truncate) mode – this removes the stop pattern.
compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version.
string compactPath = Path.Combine("YOUR_DIRECTORY", "CompactPdf417.png");
compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
```

**Mi változik a `Truncate = true` esetén?**

* A vonalkód függőlegesen körülbelül 15‑20 %-kal rövidebb lesz, ami kis címkék vagy mobil képernyők esetén hasznos.  
* Az adat teljes mértékben visszanyerhető; a legtöbb modern szkenner automatikusan támogatja a truncate módot.

Az eredményül kapott `CompactPdf417.png` egy vékonyabb változata az alap vonalkódnak.

## 3. lépés: Micro PDF417 vonalkód létrehozása, oszlopok módosítása és mentése

A Micro PDF417 egy újabb, nagy sűrűségű változat, amely nagyon kis helyekre (pl. személyi igazolványok) lett tervezve. Csak 1‑4 oszlopot támogat, és a könyvtár ugyanazt az `XDimension` tulajdonságot biztosítja a méret szabályozásához.

```csharp
// Create a Micro PDF417 generator.
var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);

// Set module width – 2 pixels works well for most printers.
microPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Micro PDF417 allows only 1 to 4 columns; choose 4 for a more square shape.
microPdf417.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode.
string microPath = Path.Combine("YOUR_DIRECTORY", "MicroPdf417.png");
microPdf417.Save(microPath, BarCodeImageFormat.Png);
```

**Fontos tudnivalók a Micro PDF417‑ról**

* Az `EncodeTypes.MicroPdf417` enum automatikusan a mikro változatot választja.  
* Mivel a szimbólum sűrűbb, 300 dpi vagy annál nagyobb nyomtatóra lehet szükség a megfelelő olvashatóság érdekében.  
* Az oszlopszám módosítása az egyetlen méret‑szabályozó lehetőség; a könyvtár továbbra is figyelembe veszi az `XDimension` értéket.

## Hogyan állítsuk be a vonalkód méretét különböző kimeneti formátumokhoz

A fenti példák PNG-t használnak, de ugyanaz a `Save` metódus működik JPEG, BMP vagy TIFF esetén is. Ha konkrét képméretre (pl. 300 × 150 px) van szükséged, kombináld az `XDimension`‑t a `ResolutionX`/`ResolutionY`‑vel:

```csharp
basicPdf417.Parameters.ImageResolution = 300; // DPI
basicPdf417.Parameters.Barcode.XDimension.Pixels = 3; // larger modules for higher DPI
basicPdf417.Save("Pdf417HighRes.jpg", BarCodeImageFormat.Jpeg);
```

Az `ImageResolution` növelése és az `XDimension` skálázása megőrzi a vizuális minőséget a nagy felbontású nyomatokon.

## Gyakori hibák és profi tippek

| Probléma | Miért fordul elő | Megoldás |
|----------|------------------|----------|
| A vonalkód elmosódott a képernyőn | Alacsony DPI és kis `XDimension` | Növeld az `ImageResolution`‑t és/vagy az `XDimension.Pixels`‑t |
| A szkenner nem olvassa a truncate módot | Régi szkenner firmware nem támogatja | Használd a teljes (nem truncate) módot régi hardver esetén |
| Micro PDF417 nem olvasható | Nyomtatás < 300 dpi vagy elégtelen kontraszt | Nyomtasd matt papírra 300 dpi vagy magasabb felbontással, biztosíts sötét előtér |
| Kimeneti fájl sérült | Írási jogosultság hiánya a célmappához | Ellenőrizd, hogy a `YOUR_DIRECTORY` létezik és írható |

**Profi tipp:** Mindig PNG‑ként generáld a vonalkódot, ha veszteségmentes minőségre van szükség a további feldolgozáshoz (pl. PDF‑be ágyazás). A PNG megőrzi a pontos pixelértékeket, míg a JPEG tömörítési artefaktusokat vezet be, amelyek befolyásolhatják a vonalkód olvashatóságát.

## Teljes, futtatható példa

Az alábbiakban egy komplett konzolalkalmazás látható, amely egy futtatás során demonstrálja mindhárom vonalkódtípust. Másold a kódot egy új .NET konzolprojektbe, és futtasd.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // The text to encode – change this to whatever data you need.
        const string data = "Sample text for PDF417 barcode";

        // Directory where images will be saved.
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // ---------- Basic PDF417 ----------
        var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        string basicPath = Path.Combine(outputDir, "Pdf417Basic.png");
        basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Basic PDF417 saved to {basicPath}");

        // ---------- Compact (Truncate) PDF417 ----------
        var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;
        string compactPath = Path.Combine(outputDir, "CompactPdf417.png");
        compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Compact PDF417 saved to {compactPath}");

        // ---------- Micro PDF417 ----------
        var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);
        microPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        microPdf417.Parameters.Barcode.Pdf417.Columns = 4; // 1‑4 allowed
        string microPath = Path.Combine(outputDir, "MicroPdf417.png");
        microPdf417.Save(microPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Micro PDF417 saved to {microPath}");
    }
}
```

**Várható kimenet**

A program három PNG fájlt hoz létre egy `Barcodes` mappán belül:

* `Pdf417Basic.png` – szabványos PDF417 vonalkód három oszloppal.  
* `CompactPdf417.png` – ugyanaz az adat truncate (kompakt) módban, valamivel rövidebb.  
* `MicroPdf417.png` – nagy sűrűségű Micro PDF417 változat négy oszloppal.

Nyiss meg bármelyik képet egy képnéző programmal; a jellegzetes rétegezett megjelenést látnod kell.


## Mit érdemes még megtanulni?

A következő tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás komplett, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API‑funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Create PDF417 Barcode Metadata in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}