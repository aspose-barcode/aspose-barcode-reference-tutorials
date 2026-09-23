---
category: general
date: 2026-09-23
description: c# vonalkód generátor útmutató bemutatja, hogyan lehet egyedi képarányú
  vonalkód képeket generálni az Aspose.BarCode könyvtár segítségével.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- DataBar barcode C#
- barcode aspect ratio
- Aspose.BarCode C#
- barcode image export
language: hu
lastmod: 2026-09-23
og_description: A C# vonalkód-generátor útmutató lépésről lépésre bemutatja, hogyan
  lehet vonalkód képeket generálni, arányokat beállítani, és PNG fájlokat exportálni
  az Aspose.BarCode segítségével.
og_image_alt: Screenshot of a barcode created with a C# barcode generator
og_title: Készítsen magas minőségű vonalkódokat C#-os vonalkódgenerátorral
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  headline: How to use a C# barcode generator for DataBar codes
  type: TechArticle
- description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  name: How to use a C# barcode generator for DataBar codes
  steps:
  - name: Switching to another barcode type
    text: 'If you need a QR code, Code 128, or PDF417, replace the enum value in the
      constructor:'
  - name: Handling unsupported characters
    text: 'The `BarcodeGenerator` validates the input string against the selected
      symbology. Supplying an illegal character throws an `ArgumentException`. Wrap
      the creation in a try‑catch block to provide a friendly error message:'
  - name: Exporting to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the second argument
      of `Save` accordingly:'
  - name: High‑resolution output for printing
    text: 'When printing on high‑DPI printers, increase the X‑dimension and optionally
      set the `Resolution` property:'
  type: HowTo
tags:
- barcode
- c#
- Aspose
title: Hogyan használjunk C# vonalkód-generátort DataBar kódokhoz
url: /hu/python-java/general/how-to-use-a-c-barcode-generator-for-databar-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan használjunk C# vonalkódgenerátort DataBar kódokhoz

Ha **c# barcode generator**‑ra van szüksége, amely DataBar stacked Omni‑Directional szimbólumokat tud előállítani, ez az útmutató egy teljes, azonnal futtatható megoldást nyújt. Megmutatjuk, hogyan generáljon vonalkód‑képeket, hogyan szabályozza az X‑dimenziót, és hogyan változtassa meg a képarányt anélkül, hogy elhagyná az IDE‑t.

A vonalkódok generálása gyakori igény készletkezelő rendszerekben, szállítási címkékben és értékesítési pont alkalmazásokban. A tutorial végére PNG fájlokat hozhat létre tetszőleges képaránnyal, és megérti, hogyan alkalmazhatja a kódot más vonalkódtípusokra is.

## Prerequisites

Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

* .NET 6.0 SDK vagy újabb telepítve  
* Visual Studio 2022 (vagy bármelyik kedvenc C# szerkesztő)  
* NuGet hivatkozás a **Aspose.BarCode**‑ra – a könyvtár, amely a `BarcodeGenerator` osztályt biztosítja  

Külön grafikai könyvtárra nincs szükség; az Aspose.BarCode belsőleg kezeli a kép‑kódolást.

## Step 1: Install the Aspose.BarCode NuGet package

Nyisson egy terminált a projekt mappájában, és futtassa:

```bash
dotnet add package Aspose.BarCode
```

A parancs a könyvtár legújabb stabil verzióját adja hozzá a projektfájlhoz, így a `BarcodeGenerator` osztály használhatóvá válik.

## Step 2: Define the output folder

Válasszon egy mappát, ahová a generált PNG fájlok kerülnek. Az abszolút vagy relatív útvonal egyformán működik, de a relatív útvonal megőrzi a projekt hordozhatóságát.

```csharp
// Define the output folder (relative to the project root)
string outputFolder = "GeneratedBarcodes/";
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
```

A könyvtár programból történő létrehozása megakadályozza a futásidejű hibákat, ha a mappa hiányzik.

## Step 3: Instantiate the C# barcode generator with sample data

A `BarcodeGenerator` konstruktor két argumentumot igényel: a vonalkódtípust és az adat‑stringet. DataBar stacked Omni‑Directional szimbólumhoz a `EncodeTypes.DatabarStackedOmniDirectional` értéket használja.

```csharp
// Create a barcode generator for a DataBar stacked Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

Az adat‑string a GS1 Application Identifier formátumnak megfelelően van felépítve. Az `EncodeTypes` felsorolás több mint 150 vonalkód‑szabványt tartalmaz; más típusra váltáshoz egyszerűen módosítsa az enum értékét.

## Step 4: Set the X‑dimension (pixel size) for the barcode

Az X‑dimenzió szabályozza a legkeskenyebb vonal szélességét. A 2 pixeles érték éles, nagy felbontású képet eredményez, amely a legtöbb képernyőn megfelelő.

```csharp
// Set the X‑dimension to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Az X‑dimenzió módosítása opcionális, de finomhangolt vezérlést biztosít a vonalkód vizuális sűrűsége felett.

## Step 5: Generate a barcode with an aspect ratio of 15 and save it as PNG

Az `AspectRatio` tulajdonság a `DataBar` alobjektumhoz tartozik. Ennek az értéknek a módosítása függőlegesen nyújtja vagy összenyomja a vonalkódot, miközben az adat változatlan marad.

```csharp
// Set aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

A `Save` metódus a vonalkódot a megadott fájlútra írja. A `BarCodeImageFormat.Png` enum veszteségmentes tömörítést biztosít.

![c# barcode generator output example](generated_barcode_example.png)

*Kép: 15‑ös képaránnyal generált vonalkód.*

## Step 6: Change the aspect ratio to 30 and generate a second image

Ugyanazon `BarcodeGenerator` példány újrahasználata elkerüli egy új objektum létrehozását. Egyszerűen frissítse az `AspectRatio` értékét, majd hívja újra a `Save`‑t.

```csharp
// Update aspect ratio to 30 and save a second image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

Most már két PNG fájlja van, amelyek csak a függőleges méretezésben különböznek. Ez a technika hasznos, ha ugyanazt az adatot kell megjeleníteni különböző címkeméretekhez.

## Common variations and edge cases

### Switching to another barcode type

Ha QR kódra, Code 128‑ra vagy PDF417‑re van szüksége, cserélje ki az enum értékét a konstruktorban:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(
    EncodeTypes.QR, "https://example.com");
```

Az összes többi konfigurációs lépés (X‑dimenzió, mentés) változatlan marad.

### Handling unsupported characters

A `BarcodeGenerator` a bemeneti stringet a kiválasztott szimbólumhoz igazítja. Egy illegális karakter `ArgumentException`‑t dob. Tegye a létrehozást try‑catch blokkba, hogy barátságos hibaüzenetet adjon:

```csharp
try
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for the selected barcode type: {ex.Message}");
}
```

### Exporting to other image formats

Az Aspose.BarCode támogatja a BMP, JPEG, TIFF és SVG formátumokat. Ennek megfelelően módosítsa a `Save` második argumentumát:

```csharp
barcodeGenerator.Save($"{outputFolder}Databar.svg", BarCodeImageFormat.Svg);
```

### High‑resolution output for printing

Magas DPI‑ű nyomtatók esetén növelje az X‑dimenziót, és opcionálisan állítsa be a `Resolution` tulajdonságot:

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.ImageResolution.Dpi = 300;
```

Ezek a beállítások nagyobb fájlméretet eredményeznek, de a nyomtatott anyagon is éles éleket biztosítanak.

## Expected output

A teljes program futtatása a következő fájlokat hozza létre a `GeneratedBarcodes/` mappában:

* `DatabarAspectRatio15.png` – standard magasságú DataBar kód  
* `DatabarAspectRatio30.png` – függőlegesen nyújtott változat  

Mindkét kép ugyanazt a GS1 adatot tartalmazza, és bármely vonalkód‑olvasó alkalmazással ellenőrizhető.

## Full source code

Másolja az alábbi kódot egy új konzolos projektbe (`dotnet new console`), és futtassa. A program állapotüzeneteket ír a konzolra, és a PNG fájlokat a lemezre menti.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Define the output folder
        string outputFolder = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputFolder);

        // Step 3: Create a C# barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Step 4: Set common barcode properties (pixel size of X‑dimension)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 5: Generate a barcode with aspect ratio 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputFolder, "DatabarAspectRatio15.png");
        barcodeGenerator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Step 6: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputFolder, "DatabarAspectRatio30.png");
        barcodeGenerator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

A program futtatása a következőhöz hasonló konzolkimenetet eredményez:

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

## Conclusion

Most már rendelkezik egy **c# barcode generator**‑ral, amely képes DataBar stacked Omni‑Directional szimbólumokat létrehozni, az X‑dimenziót szabályozni, és egyedi képarányú PNG fájlokat exportálni. Ugyanez a minta bármely más, az Aspose.BarCode által támogatott vonalkódszimbólumra alkalmazható, így könnyen integrálható készletkezelő, szállítási vagy értékesítési pont megoldásokba.

Ha tovább szeretne elmélyülni, próbálja ki:

* QR kódok vagy PDF417 szimbólumok generálása (`how to generate barcode` mobilalkalmazásokhoz)  
* SVG exportálása skálázható webgrafikához  
* A generált képek közvetlen beágyazása PDF számlákba az Aspose.PDF segítségével  

Kísérletezzen különböző `AspectRatio` értékekkel, X‑dimenzió méretekkel és kimeneti formátumokkal, hogy pontosan a kívánt eredményt érje el.


## What Should You Learn Next?


Az alábbi tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás tartalmaz teljes, működő kódrészleteket lépésről‑lépésre magyarázatokkal, hogy segítsék az API további funkcióinak elsajátítását és alternatív megvalósítási megközelítések felfedezését saját projektjeiben.

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}