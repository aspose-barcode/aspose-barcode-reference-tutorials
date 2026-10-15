---
category: general
date: 2026-10-14
description: Készítsen egy console barcode scanner‑t C#‑ban, amely PDF417 barcode‑kat
  olvas, kezeli a macro PDF417‑t, és decode több barcode‑t egyetlen image‑ről.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create console barcode scanner
- read barcodes from picture
- c# barcode reader example
lastmod: 2026-10-14
og_description: Készítsen egy console barcode scanner‑t C#‑ban, hogy gyorsan PDF417
  és macro PDF417 barcode‑kat olvasson image‑kről. Ez a step‑by‑step útmutató bemutatja,
  hogyan decode több barcode‑t egy picture‑ban.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Console barcode scanner létrehozása C#‑ban – teljes útmutató
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  headline: Create console barcode scanner in C# – barcode reader example
  type: TechArticle
- description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  name: Create console barcode scanner in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
- console application
title: Console barcode scanner létrehozása C#‑ban – PDF417 barcode olvasási példa
url: /hu/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konzolos vonalkódolvasó létrehozása C#‑ban – PDF417 vonalkód olvasási példa

`BarCodeReader` is Aspose.BarCode's core class that decodes barcodes from images and returns detailed metadata. If you need to read PDF417 barcode data from an image, this guide shows you how to do it with the **BarCodeReader** class in C#. You’ll learn a **konzolos vonalkódolvasó létrehozása** example that also handles macro PDF417 and can read multiple barcodes in a single image.

Working with barcodes often means dealing with different image sources, varying lighting conditions, and sometimes composite data such as macro PDF417 segments. This tutorial covers everything you need to decode a PDF417 barcode, extract its extended fields, and process several barcodes from the same picture. By the end you will have a runnable console program that reads barcodes from an image file and prints detailed information to the console.

## Gyors válaszok
- **Mi a példa feladata?** Létrehoz egy konzolos vonalkódolvasót, amely PDF417 és macro PDF417 vonalkódokat olvas be egy képből, és kiírja az összes dekódolt mezőt.  
- **Melyik könyvtár szükséges?** Aspose.BarCode for .NET (NuGet).  
- **Képes egyszerre több vonalkódot olvasni?** Igen – az olvasó végigiterál a képen található összes vonalkódon.  
- **Szükség van internetkapcsolatra?** Nem, a könyvtár teljesen offline működik.  
- **Melyik .NET verzió támogatott?** .NET 6.0 vagy újabb.

## Amire szükséged lesz

* .NET 6.0 SDK vagy újabb telepítve  
* A **Aspose.BarCode for .NET** NuGet csomag legújabb verziója (vagy bármely kompatibilis könyvtár, amely biztosítja a `BarCodeReader` és a `DecodeType.MacroPdf417` elemeket)  
* Egy képfájl, amely PDF417 vagy macro PDF417 vonalkódot tartalmaz (a mintában a `ExtPDF417Meta.png` van használva)  
* Kódszerkesztő vagy IDE, például Visual Studio 2022  

No additional services or external APIs are required.

## A projekt beállítása a vonalkódolvasáshoz

1. **Új konzolos projekt létrehozása**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **A vonalkód könyvtár hozzáadása**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **A vonalkód kép másolása**  

   Place `ExtPDF417Meta.png` (or any image that contains a PDF417 barcode) into the project folder.  
   For this tutorial we assume the file resides at `YOUR_DIRECTORY/ExtPDF417Meta.png`.

The project is now ready to compile and run the barcode reader example.

## Hogyan hozhatok létre konzolos vonalkódolvasót C#‑ban?

`BarCodeReader` is a class provided by Aspose.BarCode that reads barcodes from images and returns their decoded data.  
Load the image with `BarCodeReader`, set the decode type to `MacroPdf417`, and iterate over the results – that’s all you need to create a console barcode scanner. The reader automatically releases native resources thanks to the `using` statement, so you don’t have to manage memory manually. This approach works for any image format supported by .NET, such as PNG, JPEG, or BMP.

### Lépésről‑lépésre útmutató

The core of the solution is a `using` block that creates a `BarCodeReader` instance, specifies `DecodeType.MacroPdf417`, and iterates over every detected barcode. The following code is a complete, self‑contained program that you can paste into `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Miért működik ez**:  

* `DecodeType.MacroPdf417` tells the reader to look for the macro extension of PDF417, which carries additional metadata such as file ID, segment count, and timestamps.  
* The `using` statement guarantees that unmanaged resources (file handles, native decoding buffers) are released promptly.  
* The `foreach` loop automatically processes **all** barcodes that the image contains, satisfying the *read multiple barcodes* requirement.  

When you run the program (`dotnet run`), you should see output similar to the following:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

If the image contains more than one PDF417 barcode, the loop prints a separate block for each barcode, thereby demonstrating how to **read multiple barcodes** from a single picture.

## Hogyan olvashatok be több vonalkódot egy képből?

Use a single `BarCodeReader` instance and set the `DecodeType` flag to include all formats you want to detect. By combining flags with the bitwise OR operator, you can tell the library to look for PDF417, QR, Code‑128, and many other symbologies in one pass. This eliminates the need for separate readers and reduces processing time.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* is a bitmask, so you can combine any number of supported formats. Aspose.BarCode supports **30+ barcode symbologies**, including QR, DataMatrix, Code‑128, and UPC‑A, allowing a single scanner to handle diverse use cases such as product labeling, ticket validation, and identity verification.

## Mi az a macro PDF417, és hogyan érhetem el biztonságosan a mezőit?

Macro PDF417 is an extension of the PDF417 symbology that allows a large data set to be split across multiple barcode symbols.  
Macro PDF417 adds a rich set of extended properties. However, not every barcode includes every field. Accessing a missing property can throw a `NullReferenceException`. The safest approach is to verify each property before printing, ensuring your application remains stable even when macro data is absent.

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Miért fontos*: In real‑world deployments you may receive plain PDF417 barcodes that lack macro data. The defensive check ensures your application continues to run without crashing.

## Gyakori hibák és legjobb gyakorlatok

| Probléma | Miért fordul elő | Javasolt megoldás |
|----------|------------------|-------------------|
| A képfájl útvonala helytelen | `BarCodeReader` fájl‑nem‑található kivételt dob a dekódolás előtt | Használd a `Path.Combine`‑t, és ellenőrizd a fájl létezését a `File.Exists`‑szel |
| Alacsony felbontású kép | A dekóder nem találja a vonalkód széleit, ezért nulla találatot ad | Biztosíts legalább 300 dpi felbontást a megbízható eredményekhez |
| A vonalkód > 45°-ra elfordítva | Sok könyvtár feltételezi, hogy a vonalkód függőlegesen áll | Állítsd `reader.RecognitionOptions.RotateImage = true`‑ra, ha a kép elfordulhat |
| Hiányzó macro mezők | Null értékű tulajdonság olvasására tett kísérlet összeomláshoz vezet | Mindig ellenőrizd a `null` értéket a macro tulajdonságok elérése előtt |
| Nagy kötegű feldolgozás | Az olvasó minden fájlhoz való újra‑létrehozása többletterhet okoz | Használd újra ugyanazt a `BarCodeReader` példányt különböző streamekkel sok kép feldolgozásakor |

## Miért használjuk az Aspose.BarCode‑ot egy konzolos vonalkódolvasóhoz?

Aspose.BarCode can decode **30+ barcode types** and processes images up to **200 MP** without loading the entire file into memory, achieving throughput of **150 frames per second** on a typical 3.2 GHz CPU. These quantified capabilities make it a reliable choice for high‑volume, on‑premises scanning solutions where latency and accuracy are critical.

## Mit érdemes legközelebb megtanulni?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step‑by‑step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Hogyan olvassuk be a DataMatrix vonalkódokat az Aspose.BarCode for .NET használatával](/barcode/english/net/datamatrix-barcode-reading/)
- [DataMatrix vonalkód olvasása C# – DataMatrix mód generálása (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Vonalkód olvasása képből – A vonalkód régió kinyerésének elsajátítása Java‑ban az Aspose.BarCode segítségével](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

## Gyakran ismételt kérdések

**Q: Használhatom ezt a szkennert éles környezetben?**  
A: Igen. Vásárolj kereskedelmi Aspose.BarCode licencet a kiértékelési vízjel eltávolításához és a teljes támogatás eléréséhez.

**Q: A könyvtár működik Linuxon és macOS‑on?**  
A: Teljesen. Az Aspose.BarCode for .NET platformfüggetlen, és fut .NET 6+ környezetben Windows, Linux és macOS rendszereken.

**Q: Hogyan kezeljem a nagyon nagy képeket anélkül, hogy a memória kimerülne?**  
A: Használd a `LoadOptions` konstruktorát a streaming mód engedélyezéséhez, amely a képet darabokban dolgozza fel ahelyett, hogy teljes egészében RAM‑ba töltené.

**Q: Lehet-e titkosított vagy jelszóval védett képeket dekódolni?**  
A: Az olvasó képes kezelni a szabványos PNG/JPEG jelszóval védett képeket; egyszerűen add meg a jelszót a `reader.ImagePassword`‑on keresztül.

**Q: Mi van, ha a vonalkódom részben sérült?**  
A: Engedélyezd a hibajavítási opciókat, például `reader.RecognitionOptions.CorrectErrors = true`, hogy növeld a rezilienciát a sérülés vagy zaj ellen.

---

**Utolsó frissítés:** 2026-10-14  
**Tesztelve:** Aspose.BarCode 24.11 for .NET  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Hogyan olvassuk be a Pdf417-et C‑ben – Teljes vonalkódolvasó példa](/barcode/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Több vonalkód olvasása C – Teljes útmutató Pdf417‑tel](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)
- [Vonalkód dekódolása képből C‑os vonalkódolvasó példával](/barcode/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}