---
category: general
date: 2026-07-27
description: Hogyan olvassuk be a PDF417 vonalkódot C#-ban gyorsan. Tanulja meg, hogyan
  olvasson több vonalkódot, dekódoljon képeket, és szerezze meg a Macro PDF417 metaadatokat
  egy teljes C# vonalkód példában.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- c# barcode example
- read barcode image c#
language: hu
lastmod: 2026-07-27
og_description: Hogyan olvassuk be a PDF417 vonalkódot C#‑ban ezzel a lépésről‑lépésre
  útmutatóval. Dekódold a képeket, kezeld a több vonalkódot, és nyerd ki a Macro PDF417
  metaadatokat egy azonnal futtatható példában.
og_image_alt: Screenshot showing how to read PDF417 barcode using C# code
og_title: PDF417 olvasása C#-ban – Teljes vonalkód példa
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  headline: How to Read PDF417 in C# – Complete Barcode Example
  type: TechArticle
- description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  name: How to Read PDF417 in C# – Complete Barcode Example
  steps:
  - name: Loads a barcode image from disk.
    text: Loads a barcode image from disk.
  - name: Decodes **PDF417** (including Macro PDF417) barcodes.
    text: Decodes **PDF417** (including Macro PDF417) barcodes.
  - name: Prints basic information such as code type and text.
    text: Prints basic information such as code type and text.
  - name: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
    text: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image-processing
- Aspose
title: Hogyan olvassuk a PDF417-et C#-ban – Teljes vonalkód példa
url: /hu/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan olvassuk a PDF417-et C#-ban – Teljes vonalkód példa

Gondoltad már valaha, **hogyan olvassunk PDF417** vonalkódot egy C# alkalmazásban anélkül, hogy a haját húznád? Nem vagy egyedül. Akár logisztikai szkenner, jegyellenőrző vagy csak egy PDF417‑kódolt azonosítóból szeretnél adatot kinyerni, a folyamat eleinte kissé titokzatosnak tűnhet.  

Ebben az útmutatóban végigvezetünk egy **c# barcode example** példán, amely beolvassa a PDF417 képet, kezeli a **read multiple barcodes** esetét, ha több van jelen, és kinyeri az összes hasznos Macro PDF417 metaadatot, amire szükséged lehet.

## Mit fogsz építeni

A útmutató végére egy kis konzolprogramod lesz, amely:

1. Betölti a vonalkód képet a lemezről.  
2. Dekódolja a **PDF417** (beleértve a Macro PDF417) vonalkódokat.  
3. Kiírja az alapinformációkat, mint a kód típusa és a szöveg.  
4. Kiadja a teljes Macro PDF417 mezők halmazát (file ID, segment ID, checksum, stb.).  

Nincs külső szolgáltatás, csak egyetlen NuGet csomag és néhány C# sor.

## Előkövetelmények – Amire szükséged van a kezdéshez

- **.NET 6.0** vagy későbbi (a kód .NET Framework 4.6+ alatt is működik).  
- A **Aspose.BarCode for .NET** könyvtár legújabb verziója – telepítsd NuGet-en keresztül (`Install-Package Aspose.BarCode`).  
- Egy képfájl, amely PDF417 vonalkódot tartalmaz (a demó a `ExtPDF417Meta.png`-t használja).  
- Alapvető C# konzolalkalmazás ismeretek (ha már írtál “Hello World” programot, rendben vagy).

> **Pro tip:** Ha nincs kéznél PDF417 mintád, generálj egyet az Aspose demo oldalon, vagy használj egy okostelefon-alkalmazást, amely PDF417 címkéket tud létrehozni.

## 1. lépés: A projekt beállítása és a könyvtár telepítése

Először hozz létre egy új konzolprojektet:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
dotnet add package Aspose.BarCode
```

Ez letölti a szükséges **c# barcode example** függőségeket. Nyisd meg a `Program.cs`-t, és cseréld le az alapértelmezett kódot az alábbi vázra:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

## 2. lépés: A Barcode Reader inicializálása PDF417-hez

A megoldás szíve a `BarCodeReader` osztály. Megadjuk neki, melyik fájlt szkenneli és melyik vonalkódtípust érdekel – ebben az esetben `DecodeType.Pdf417` vagy a makró változat `DecodeType.MacroPdf417`. A makró típus használata biztosítja, hogy az kiterjesztett mezőket is elkapjuk.

```csharp
// Step 2: Create the reader, targeting Macro PDF417 barcodes
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(
           imagePath, DecodeType.MacroPdf417))
{
    // The rest of the logic lives inside this block.
}
```

Miért használjuk a `MacroPdf417`-t a sima `Pdf417` helyett? A Macro PDF417 extra metaadatokat tartalmaz (file ID, segment count, timestamps, stb.), amelyekre számos valós alkalmazás támaszkodik – gondolj a több oldalra szétosztott szállítmánylistákra.

## 3. lépés: Az összes a képen található vonalkód beolvasása

Egyetlen kép tartalmazhat **read multiple barcodes** – például egy QR kódot a PDF417 mellett. A `ReadBarCodes()` metódus egy `IEnumerable<BarCodeResult>`-et ad vissza, amelyet bejárhatunk.

```csharp
// Step 3: Iterate through every barcode detected
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside we’ll output both generic and macro‑specific data.
}
```

Ha a kép csak egy PDF417-et tartalmaz, a ciklus még mindig egyszer lefut, így a kód rugalmas marad a jövőbeni esetekhez, amikor **read multiple barcodes**-t kell beolvasni ugyanarról a szkennerről.

## 4. lépés: Alapvető vonalkód információk megjelenítése

Mielőtt a makró mezőkbe merülnénk, hasznos megjeleníteni a vonalkód típusát és a dekódolt szöveget. Ez segít ellenőrizni, hogy az olvasó valóban PDF417-et, és nem más szimbólumot érzékelt.

```csharp
Console.WriteLine($"CodeType : {result.CodeTypeName}");
Console.WriteLine($"CodeText : {result.CodeText}");
```

A `CodeTypeName` *MacroPdf417*-t (vagy *Pdf417*-t, ha a makró jelző nincs beállítva) fog visszaadni, míg a `CodeText` a vonalkódban kódolt nyers adatot tartalmazza.

## 5. lépés: Macro PDF417 metaadatok kinyerése

Az `Extended` tulajdonság mély betekintést nyújt a PDF417-specifikus struktúrába. Az alább kiírt minden mező közvetlenül a PDF417 makró specifikációra hivatkozik.

```csharp
// Step 5: Macro PDF417 metadata – all optional, but very handy
Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Minden sor a makró payload egy másik részét húzza ki:

- **FileID** – a teljes dokumentumkészlet egyedi azonosítója.  
- **SegmentID** – a több szegmensből álló fájl melyik részét nézed.  
- **SegmentsCount** – a várt szegmensek teljes száma.  
- **FileName, Checksum, FileSize** – hasznos a továbbított fájl integritásának ellenőrzéséhez.  
- **TimeStamp, Addressee, Sender** – opcionális mezők, amelyeket sok logisztikai rendszer beágyaz.

Ha ezek közül bármelyik mező hiányzik a forrás vonalkódból, a könyvtár `null` vagy `0` értéket ad vissza, amit szükség szerint kezelhetsz.

## 6. lépés: A teljes példa futtatása

Összegezve, itt van a teljes, azonnal futtatható program:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the reader for Macro PDF417 (covers both standard and macro)
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Loop through every barcode detected – handles read multiple barcodes gracefully
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic info
                    Console.WriteLine($"CodeType : {result.CodeTypeName}");
                    Console.WriteLine($"CodeText : {result.CodeText}");

                    // Macro PDF417 specific metadata
                    Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Várható kimenet

Ha a programot egy érvényes `ExtPDF417Meta.png`-en futtatod, valami hasonlót kell látnod:

```
CodeType : MacroPdf417
CodeText : https://example.com/track?order=12345
Pdf417MacroFileID          : 101
Pdf417MacroSegmentID       : 1
Pdf417MacroSegmentsCount   : 3
Pdf417MacroFileName        : order_manifest.pdf
Pdf417MacroChecksum        : 0x1A2B3C4D
Pdf417MacroFileSize        : 45296
Pdf417MacroTimeStamp       : 2024-03-15T10:27:00Z
Pdf417MacroAddressee       : LogisticsDept
Pdf417MacroSender          : WarehouseA
MacroPdf417Terminator      : true
----------------------------------------
Decoding complete. Press any key to exit.
```

Ha a kép több mint egy vonalkódot tartalmaz,

## Mit érdemes következőként megtanulni?

A következő útmutatók szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódpéldákat tartalmaz lépésről‑lépésre magyarázatokkal, hogy elsajátíthasd a további API funkciókat, és alternatív megvalósítási megközelítéseket fedezhess fel saját projektjeidben.

- [Hogyan generáljunk PDF417 vonalkódokat – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [Hogyan hozzunk létre vonalkódot – Compact PDF417 az Aspose.BarCode segítségével](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hogyan olvassunk DataMatrix vonalkódokat az Aspose.BarCode for .NET segítségével](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}