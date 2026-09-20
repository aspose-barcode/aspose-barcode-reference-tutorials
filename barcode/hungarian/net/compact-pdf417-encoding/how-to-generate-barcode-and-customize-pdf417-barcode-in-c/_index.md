---
category: general
date: 2026-09-19
description: Hogyan generáljunk vonalkódot C#-ban lépésről‑lépésre útmutatóval. Tanulja
  meg testreszabni a PDF417 vonalkód beállításait, és hozzon létre egy vonalkód képet,
  amelyet a C# fejlesztők azonnal használhatnak.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- customize pdf417 barcode
- create barcode image c#
language: hu
lastmod: 2026-09-19
og_description: Hogyan generáljunk vonalkódot C#-ban részletes útmutatóval. Testreszabhatja
  a PDF417 vonalkód paramétereit, és létrehozhat egy vonalkód képet, amelyet a C#
  projektek ma már használhatnak.
og_image_alt: Screenshot of a generated MicroPDF417 barcode image created with C#
  code
og_title: Hogyan generáljunk vonalkódot és testre szabjuk a PDF417 vonalkódot C#‑ban
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  headline: How to generate barcode and customize PDF417 barcode in C#
  type: TechArticle
- description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  name: How to generate barcode and customize PDF417 barcode in C#
  steps:
  - name: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
    text: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
  - name: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
    text: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
  - name: Increase `ErrorLevel` to improve tolerance.
    text: Increase `ErrorLevel` to improve tolerance.
  type: HowTo
tags:
- barcode
- C#
- pdf417
title: Hogyan generáljunk vonalkódot és testre szabjuk a PDF417 vonalkódot C#‑ban
url: /hu/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan generáljunk vonalkódot és testre szabjuk a PDF417 vonalkódot C#-ban

Ha **hogyan generáljunk vonalkódot** kell egy .NET alkalmazásban, ez a tutorial egy teljes, azonnal futtatható megoldást mutat be. Megtanulja, hogyan testre szabja a PDF417 vonalkód méreteit, válassza ki az oszlopok számát, és végül **vonalkód kép létrehozása C#**-ban, amelyet a projektek közvetlenül beágyazhatnak.

Vonalkód generálásához nem szükséges összetett build pipeline. A útmutató végére egy PNG fájlt fog kapni, amely egy MicroPDF417 vonalkódot tartalmaz, és pontosan megfelel a kívánt méretnek és felbontásnak.

## Előfeltételek

* .NET 6.0 SDK vagy újabb (a kód .NET Framework 4.6+‑al is működik)
* Visual Studio 2022 (vagy bármelyik kedvenc C# szerkesztő)
* Aspose.BarCode for .NET NuGet csomag – telepítés:  
  `dotnet add package Aspose.BarCode`

Nem szükséges további külső eszköz.

## 1. lépés: A projekt beállítása és a névterek importálása

Hozzon létre egy új konzolos projektet, és adja hozzá az Aspose.BarCode hivatkozást.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Nyissa meg a `Program.cs`-t, és adja hozzá a szükséges `using` direktívákat:

```csharp
using System;
using Aspose.BarCode.Generation;   // Provides BarcodeGenerator and EncodeTypes
using Aspose.BarCode;               // Contains BarCodeImageFormat enum
```

Ezek a névterek teszik elérhetővé az osztályokat, amelyek segítségével **hogyan generáljunk vonalkódot** és vezérelhetők a PDF417‑specifikus beállítások.

## 2. lépés: A MicroPDF417 generátor inicializálása a kívánt szöveggel

Az első sor létrehoz egy `BarcodeGenerator` példányt, amely a MicroPDF417 szimbólumra van beállítva. A konstruktor a kódolás típusát és a kódolni kívánt adatkarakterláncot veszi át.

```csharp
// Step 2: Create a MicroPDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");
```

**Miért fontos:** A MicroPDF417 a teljes PDF417 szabvány kompakt változata, amely ideális kis címkékhez vagy mobil képernyőkhöz. A generátor helyes `EncodeTypes`-al való inicializálása biztosítja, hogy a könyvtár a megfelelő kódolási algoritmust használja.

## 3. lépés: Az X‑dimenzió (modul szélesség) testreszabása a finomabb felbontás érdekében

Az X‑dimenzió szabályozza egyetlen vonalkód modul (a legkisebb fekete vagy fehér sáv) szélességét. Alacsony pixelérték beállítása magasabb felbontású képet eredményez.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Miért fontos:** A nagyobb X‑dimenzió könnyebbé teszi a vonalkód olvasását alacsony felbontású szkennerek számára, míg a kisebb érték több adatot tömörít egy korlátozott térbe. Állítsa be ezt az értéket a szkennelési környezetnek megfelelően.

## 4. lépés: Az oszlopok számának meghatározása a vonalkód méretének szabályozásához

A MicroPDF417 1‑4 oszlopot engedélyez. Több oszlop rövidebb, szélesebb vonalkódot eredményez; kevesebb oszlop magasabb, keskenyebb vonalkódot hoz létre.

```csharp
// Step 4: Define the number of columns (1‑4 are allowed) to control barcode size
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Miért fontos:** A megfelelő oszlopszám kiválasztása lehetővé teszi, hogy a vonalkódot egy adott UI elembe vagy nyomtatott címkére illessze anélkül, hogy kézzel kellene méretezni.

## 5. lépés: A vonalkód mentése PNG képként

Végül írja a generált vonalkódot a lemezre. A PNG veszteségmentes minőséget őriz, ami fontos a tiszta olvasáshoz.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\MicroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Ha a célkönyvtár nem létezik, a `Save` metódus `ArgumentException`-t dob. Egyszerű ellenőrzéssel megakadályozható ez:

```csharp
if (!System.IO.Directory.Exists(@"C:\Barcodes"))
{
    System.IO.Directory.CreateDirectory(@"C:\Barcodes");
}
```

### Teljes forráskód

Az összetevők összeállításával itt a teljes, futtatható program:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");

            // 2️⃣ Set the X‑dimension (module width) in pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Define the number of columns (1‑4 are allowed) to control barcode size
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Ensure the output folder exists
            string folder = @"C:\Barcodes";
            if (!System.IO.Directory.Exists(folder))
                System.IO.Directory.CreateDirectory(folder);

            // 4️⃣ Save the generated barcode as a PNG image
            string outputPath = System.IO.Path.Combine(folder, "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

A program futtatása egy **MicroPdf417.png** nevű fájlt hoz létre, amely a lenti képernyőképre hasonlít (a kép elhagyva a rövidség kedvéért). A vonalkód a *Sample* szöveget kódolja, és tiszteletben tartja a megadott X‑dimenziót és oszlopszám beállításokat.

## PDF417 egyéb beállításainak testreszabása

Miközben ez az útmutató a **pdf417 vonalkód testreszabása** méretet befolyásoló paraméterekre összpontosít, az Aspose.BarCode számos további beállítást kínál, amelyekre szüksége lehet:

| Tulajdonság | Cél | Tipikus értékek |
|----------|---------|----------------|
| `generator.Parameters.Barcode.Pdf417.Rows` | A sorok számát (magasság) szabályozza | 3‑30 |
| `generator.Parameters.Barcode.Pdf417.ErrorLevel` | Beállítja a hibajavítási szintet (magasabb = toleránsabb) | 0‑8 |
| `generator.Parameters.Barcode.Pdf417.Truncated` | Truncált vonalkódot generál (nincs stop minta) | `true`/`false` |
| `generator.Parameters.Barcode.Pdf417.CompactionMode` | Numerikus, szöveges vagy bájt kompresszió választása | `CompactionModes.Numeric`, stb. |

**Pro tipp:** Ha egy fix szélességű vonalkódra van szükség, kezdje a `Columns` növelésével és az `XDimension` csökkentésével. Ha a szkenner hiányzó szimbólumokat jelez, növelje a `ErrorLevel`-t a redundancia javítása érdekében.

## Szélsőséges esetek kezelése

* **A szöveg túl hosszú a MicroPDF417-hez:** A Micro változat legfeljebb 1 KB adatot támogat. Ha a karakterlánc meghaladja ezt a határt, válts a teljes `Pdf417` szimbólumra az `EncodeTypes.MicroPdf417` helyett `EncodeTypes.Pdf417`-re módosítva.
* **Nem támogatott képképformátum:** A `BarCodeImageFormat` támogatja a `Jpeg`, `Bmp` és `Gif` formátumokat is. Válasszon egy olyan formátumot, amely illeszkedik a további feldolgozási csővezetékhez.
* **Keresztplatformos útvonalak:** Használja a `Path.Combine`-t a keményen kódolt backslash-ek helyett, ha Linuxra vagy macOS-re céloz.

## A vonalkód ellenőrzése

Az előállított képet bármely szabványos vonalkódolvasó alkalmazással (mobil vagy asztali) ellenőrizheti. A szkennernek vissza kell adnia az eredeti **Sample** szöveget. Ha nem sikerül:

1. Ellenőrizze, hogy az X‑dimenzió nincs 1 pixel alá állítva (néhány szkenner nem képes al‑pixel modulok feloldására).
2. Győződjön meg arról, hogy a kimeneti fájl nem sérült – futtassa újra a programot, és hasonlítsa össze a fájlméreteket.
3. Növelje a `ErrorLevel`-t a tolerancia javítása érdekében.

## Következtetés

Most már tudja, **hogyan generáljunk vonalkódot** C#-ban az Aspose.BarCode használatával, hogyan **testre szabjuk a pdf417 vonalkód** méreteit és oszlopszámát, valamint hogyan **vonalkód képet hozzunk létre C#-ban**, amelyet a projektek közvetlenül beágyazhatnak. A teljes példa egy gyakorlati munkafolyamatot mutat be a projekt beállításától a végső PNG kimenetig.

Ezután fedezze fel a többi szimbólumot, például a QR, Code128 vagy DataMatrix kódolásokat az `EncodeTypes` enum értékének cseréjével. További paraméterek, mint a `Resolution` vagy a `Margin` beállítása lehetővé teszi, hogy minden vonalkódot pontosan az Ön alkalmazásához igazítson.

Boldog kódolást, és engedje, hogy a vonalkódok felhatalmazzák a következő automatizálási projektjét!

## Mit érdemes következőként megtanulni?

Az alábbi tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás tartalmaz teljes, működő kódrészleteket lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket saját projektjeiben.

- [Hogyan generáljunk PDF417 vonalkód képet C#-ban az Aspose segítségével](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Hogyan hozzunk létre PDF417 vonalkódot az Aspose‑szal – Teljes lépésről‑lépésre útmutató](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Hogyan mentsünk vonalkódot C#‑ban – PDF417 vonalkódok generálása](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}