---
category: general
date: 2026-08-15
description: Olvass be vonalkódot képről C#-ban a BarCodeReader használatával. Tanulja
  meg, hogyan olvasson több vonalkódot C#-ban, hogyan olvasson PDF417 vonalkódot,
  és tekintse meg a teljes C# BarCodeReader példát.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image
- read multiple barcodes c#
- how to read pdf417 barcode
- c# barcodereader example
language: hu
lastmod: 2026-08-15
og_description: Olvassa be a vonalkódot képről C#‑ban egy lépésről‑lépésre útmutatóval.
  Fedezze fel, hogyan olvashat több vonalkódot C#‑ban, dekódolhatja a PDF417 szimbólumokat,
  és futtathat egy teljes C# BarCodeReader példát.
og_image_alt: Screenshot of C# code that reads barcode from image using BarCodeReader
og_title: Vonalkód olvasása képből C#‑ban – BarCodeReader oktató
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Read barcode from image in C# using BarCodeReader. Learn how to read
    multiple barcodes C#, read PDF417 barcode, and see a full C# BarCodeReader example.
  headline: Read barcode from image in C# – BarCodeReader tutorial
  type: TechArticle
tags:
- barcode
- C#
- .NET
- image processing
title: Vonalkód olvasása képből C#-ban – BarCodeReader oktató
url: /hu/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Olvasd be a vonalkódot képről C#‑ban – BarCodeReader bemutató

Ha **vonalkódot szeretnél beolvasni képről** egy .NET alkalmazásban, ez az útmutató pontosan megmutatja, hogyan teheted ezt a `BarCodeReader` osztállyal. Emellett láthatod, hogyan **olvashatsz több vonalkódot C#‑ban**, hogyan dekódolhatsz egy PDF417 szimbólumot, és megkapod a teljes **C# BarCodeReader példát**, amelyet beilleszthetsz a projektedbe.

A bemutató minden lépést lefed – a szükséges NuGet csomag hozzáadásától az kiterjesztett PDF417 mezők kiírásáig – így egy futtatható konzolprogrammal zársz. Külső dokumentációra nincs szükség; minden kód és magyarázat benne van.

## Amire szükséged lesz

* .NET 6.0 SDK vagy újabb (a kód működik .NET Core és .NET Framework alatt is)
* Visual Studio 2022 vagy bármely C#‑kompatibilis szerkesztő
* A `Aspose.BarCode` NuGet csomag (vagy a megfelelő könyvtár, amely biztosítja a `BarCodeReader`‑t)
* Egy képfájl, amely Macro PDF417 vonalkódot tartalmaz (például `ExtPDF417Meta.png`)

Ezeknek a feltételeknek a megléte biztosítja, hogy a példa további konfiguráció nélkül leforduljon.

## Vonalkód beolvasása képről a BarCodeReader-rel

Az első lépés egy `BarCodeReader` példány létrehozása, amely a képfájlra mutat, és megadja a könyvtárnak, hogy melyik vonalkódtípust keresse.

```csharp
using System;
using Aspose.BarCode;               // Namespace for BarCodeReader
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // Path to the image that holds the Macro PDF417 barcode
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417 barcodes only
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Read all barcodes present in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Basic barcode information
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");

                // Extended Macro PDF417 fields (available only for this type)
                Console.WriteLine($"File ID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name        : {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum         : {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Time Stamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee        : {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender           : {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator Flag  : {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Miért működik ez:**  
A `BarCodeReader` megnyitja a képet, a megadott `DecodeType` típusra keres, és egy `BarCodeResult` objektumok gyűjteményét adja vissza. Minden eredmény tartalmazza az általános vonalkód adatokat (`CodeTypeName`, `CodeText`), és a Macro PDF417 esetén egy `Extended.Pdf417` objektumot, amely a szabvány által definiált összes további mezőt mutatja.

## Több vonalkód beolvasása C#‑ban egyetlen képen

Néha egy kép több vonalkódot is tartalmaz (például QR‑kód a PDF417 mellett). Ennek kezeléséhez egyszerűen hagyd ki a kifejezett `DecodeType` megadását, vagy add meg a `DecodeType.AllSupported` értéket, és iterálj a találatokon.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Found {result.CodeTypeName}: {result.CodeText}");
    }
}
```

**Miért van erre szükség:**  
Az `AllSupported` megadása azt mondja a motornak, hogy minden ismert vonalkódformátumot próbáljon ki, ami garantálja, hogy minden szimbólumot felderíts a képen. Ez a javasolt megközelítés, ha előre nem tudod, milyen vonalkódok lesznek jelen.

## PDF417 vonalkód beolvasása C#‑ban

Ha csak a klasszikus PDF417 (nem‑macro) formátum érdekel, állítsd a `DecodeType`‑ot `Pdf417`‑ra. A kód többi része változatlan marad, csak a kiterjesztett mezők nem lesznek elérhetők.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"PDF417 text: {result.CodeText}");
    }
}
```

**Miért fontos ez:**  
A klasszikus PDF417 nem teszi elérhetővé a macro‑specifikus tulajdonságokat, így az `Extended.Pdf417` blokk felesleges. A pontos `DecodeType` használata tovább gyorsítja a beolvasást, mivel a könyvtár kihagyja a nem támogatott algoritmusokat.

## Teljes C# BarCodeReader példa, amelyet másolhatsz

Az alábbiakban a teljes program látható, amely a három szcenáriót egyetlen, könnyen futtatható konzolalkalmazásba egyesíti. Cseréld le a `YOUR_DIRECTORY/ExtPDF417Meta.png` értéket a képed tényleges elérési útjára.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 1️⃣ Read Macro PDF417 and show extended fields
        Console.WriteLine("=== Macro PDF417 ===");
        ReadMacroPdf417(imagePath);

        // 2️⃣ Read any barcode type present (multiple barcodes)
        Console.WriteLine("\n=== All supported barcodes ===");
        ReadAllBarcodes(imagePath);

        // 3️⃣ Read classic PDF417 only
        Console.WriteLine("\n=== Classic PDF417 ===");
        ReadClassicPdf417(imagePath);
    }

    static void ReadMacroPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");
                Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                // ... other extended fields omitted for brevity
                Console.WriteLine(new string('-', 30));
            }
        }
    }

    static void ReadAllBarcodes(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.AllSupported))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"{result.CodeTypeName}: {result.CodeText}");
            }
        }
    }

    static void ReadClassicPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.Pdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"PDF417 text: {result.CodeText}");
            }
        }
    }
}
```

### Várható kimenet

Ha a mintakép Macro PDF417 vonalkódot tartalmaz, a konzol valami hasonlót ír ki:

```
=== Macro PDF417 ===
Code Type : MacroPdf417
Code Text : 1234567890
File ID   : 5
Segment ID       : 2
Segments Count   : 3
File Name        : report.pdf
Checksum         : 0x1A2B
File Size        : 84212
Time Stamp       : 2024-03-15T10:22:31Z
Addressee        : John Doe
Sender           : Acme Corp
Terminator Flag  : True
------------------------------

=== All supported barcodes ===
MacroPdf417: 1234567890
QrCode: https://example.com

=== Classic PDF417 ===
PDF417 text: 0987654321
```

Ha a kép csak egy szabályos PDF417-et tartalmaz, a „Macro PDF417” szakasz üres lesz, és a „Classic PDF417” szakasz megjeleníti a dekódolt szöveget.

## Következtetés

Most már tudod, hogyan **olvass be vonalkódot képről** C#‑ban a `BarCodeReader` segítségével, hogyan **olvass be több vonalkódot C#‑ban** egyetlen fájlban, és a pontos lépéseket a **PDF417 vonalkód beolvasásához** – mind macro, mind klasszikus változatban. A teljes **C# BarCodeReader példa** készen áll, hogy beilleszd bármely .NET projektbe, és kiterjesztheted más formátumok kezelésére vagy egy nagyobb képfeldolgozó csővezetékbe való integrálásra.

**Következő lépések**

* Fedezd fel a hibakezelési mintákat, például a `try / catch`‑et a reader blokk körül.  
* Kísérletezz a `ReaderParameters` objektummal a felismerés sebességének és pontosságának finomhangolásához.  
* Kombináld a vonalkódolvasást képelőfeldolgozó könyvtárakkal (

## Mit érdemes még megtanulnod?

A következő bemutatók szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás tartalmaz teljes, működő kódrészleteket lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [Hogyan olvassunk DataMatrix vonalkódokat az Aspose.BarCode for .NET segítségével](/barcode/english/net/datamatrix-barcode-reading/)
- [DataMatrix vonalkód beolvasása C# – DataMatrix mód generálása (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Vonalkód beolvasása képről – A vonalkód régió kinyerésének elsajátítása Java‑ban az Aspose.BarCode segítségével](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}