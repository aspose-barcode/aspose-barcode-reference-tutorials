---
category: general
date: 2026-10-28
description: Jak rychle dekódovat PDF417 čárové kódy v C#. Naučte se číst obrázek
  čárového kódu v C# pomocí Aspose.BarCode s kompletním, spustitelným příkladem.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcode image c#
- PDF417 decoding C#
- barcode reader C#
- Aspose.BarCode example
language: cs
lastmod: 2026-10-28
og_description: Jak dekódovat PDF417 čárové kódy v C# pomocí Aspose.BarCode. Tento
  průvodce vám ukáže, jak číst obrázek čárového kódu v C# krok za krokem, včetně kódu.
og_image_alt: Screenshot of C# code that decodes a PDF417 barcode from an image
og_title: Jak dekódovat PDF417 čárové kódy v C# – návod na čtení obrázku čárového
  kódu v C#
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to decode PDF417 barcodes in C# quickly. Learn to read barcode
    image C# using Aspose.BarCode with a complete, runnable example.
  headline: How to decode PDF417 barcodes in C# and read barcode image C#
  type: TechArticle
- description: How to decode PDF417 barcodes in C# quickly. Learn to read barcode
    image C# using Aspose.BarCode with a complete, runnable example.
  name: How to decode PDF417 barcodes in C# and read barcode image C#
  steps:
  - name: What each line does
    text: '| Line | Explanation | |------|-------------| | `result.CodeTypeName` |
      Human‑readable name of the detected barcode type (e.g., “MacroPdf417”). | |
      `result.CodeText` | The raw data encoded in the barcode. | | `result.Extended.Pdf417.MacroPdf417FileID`
      | Identifier that ties all segments of a macro P'
  - name: Handling common edge cases
    text: '| Situation | Recommended handling | |-----------|----------------------|
      | **No barcode found** | Check `reader.ReadBarCodes().Any()` before the loop
      and display a friendly message. | | **Corrupted image** | Wrap the `BarCodeReader`
      creation in a `try/catch` block for `BarCodeException`. | | **Mult'
  - name: Next steps
    text: '* Explore other barcode formats by changing `DecodeType` (e.g., `DecodeType.QR`,
      `DecodeType.Code128`). * Combine multiple decoded segments to reconstruct the
      original document. * Use the `BarCodeGenerator` class to create test PDF417
      barcodes on the fly.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Jak dekódovat PDF417 čárové kódy v C# a načíst obrázek čárového kódu v C#
url: /cs/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-and-read-barcode-image-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dekódovat PDF417 čárové kódy v C# a načíst obrázek čárového kódu C#

Pokud potřebujete **how to decode pdf417** v .NET aplikaci, tento průvodce vám poskytne připravené řešení. Ukážeme vám přesně, jak **read barcode image c#** pomocí knihovny Aspose.BarCode, extrahovat pole macro‑PDF417 a zobrazit je v konzoli.

Dekódování PDF417 čárových kódů se často vyskytuje v logistice, tiketování a systémech ověřování identity. Na konci tohoto tutoriálu budete schopni načíst libovolný obrázek obsahující Macro PDF417 čárový kód, dekódovat jej a získat hodnoty File ID, Segment ID a Segment Count, které jsou nezbytné pro sestavení více‑segmentových dokumentů.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK nebo novější nainstalováno  
* Visual Studio 2022 (nebo jakékoli C# IDE)  
* NuGet balíček Aspose.BarCode pro .NET (`Aspose.BarCode`)  
* Obrázkový soubor, který obsahuje Macro PDF417 čárový kód (příklad používá `ExtPDF417Meta.png`)

You can add the NuGet package with the following command:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Set up the project and import namespaces

Create a new console project and import the required namespaces. The `using` directives give you access to `BarCodeReader`, `DecodeType`, and the result‑extension objects.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

> **Proč je tento krok důležitý** – Import správných jmenných prostorů zabraňuje chybám při kompilaci a zpřístupňuje rozhraní API pro následnou logiku dekódování.

## Step 2: Specify the image path

Define the full or relative path to the barcode image. Keeping the path in a variable makes the code reusable for different images.

```csharp
// Step 2: Specify the path to the image that contains a Macro PDF417 barcode
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

> **Tip:** Použijte `Path.Combine`, pokud sestavujete cestu z více částí; správně ošetřuje oddělovače adresářů napříč operačními systémy.

## Step 3: Create a `BarCodeReader` configured for Macro PDF417 decoding

Instantiate `BarCodeReader` with the image path and the `DecodeType.MacroPdf417` flag. This tells the library to look specifically for Macro PDF417 symbols.

```csharp
// Step 3: Create a BarCodeReader configured for MacroPdf417 decoding
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
```

> **Proč je tento krok důležitý** – Výběrem správného `DecodeType` zvyšujete výkon, protože engine přeskočí nesouvisející formáty čárových kódů.

## Step 4: Read all barcodes and display macro information

Loop through each `BarCodeResult` returned by `reader.ReadBarCodes()`. The result object contains both generic fields (`CodeTypeName`, `CodeText`) and Macro PDF417‑specific extensions (`MacroPdf417FileID`, `MacroPdf417SegmentID`, `MacroPdf417SegmentsCount`).

```csharp
    // Step 4: Read all barcodes in the image and display the most relevant macro information
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Code Type : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // Macro PDF417 specific fields
        Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment ID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Segments  : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
    }
}
```

### What each line does

| Řádek | Vysvětlení |
|------|-------------|
| `result.CodeTypeName` | Lidsky čitelný název detekovaného typu čárového kódu (např. “MacroPdf417”). |
| `result.CodeText` | Surová data zakódovaná v čárovém kódu. |
| `result.Extended.Pdf417.MacroPdf417FileID` | Identifikátor, který spojuje všechny segmenty makro PDF417 dokumentu. |
| `result.Extended.Pdf417.MacroPdf417SegmentID` | Index aktuálního segmentu v rámci celého dokumentu. |
| `result.Extended.Pdf417.MacroPdf417SegmentsCount` | Celkový počet segmentů očekávaných pro dokument. |

> **Pro tip:** Uložte makro pole do databáze, pokud budete později potřebovat znovu sestavit celý dokument. `File ID` vám umožní seskupit segmenty patřící ke stejnému zdroji.

## Step 5: Run the program and verify output

Build and run the console application:

```bash
dotnet run
```

Typical console output looks like this:

```
Code Type : MacroPdf417
Code Text : 0123456789ABCD
File ID   : 101
Segment ID: 1
Segments  : 3
```

If the image contains multiple Macro PDF417 symbols, the loop prints each one sequentially.

### Handling common edge cases

| Situace | Doporučené řešení |
|-----------|----------------------|
| **No barcode found** | Zkontrolujte `reader.ReadBarCodes().Any()` před smyčkou a zobrazte přátelskou zprávu. |
| **Corrupted image** | Zabalte vytvoření `BarCodeReader` do bloku `try/catch` pro `BarCodeException`. |
| **Multiple barcode formats** | Použijte `DecodeType.AllSupported` a filtrujte výsledky podle `result.CodeTypeName == "MacroPdf417"`. |
| **Large images** | Před dekódováním zmenšete velikost obrázku, aby se zlepšil výkon; knihovna přijímá objekt `Bitmap`. |

## Full source code

Below is the complete, self‑contained program. Copy it into `Program.cs` of a new console project and replace `YOUR_DIRECTORY/ExtPDF417Meta.png` with the actual path to your image.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417Decoder
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Specify the path to the image that contains a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Step 3: Create a BarCodeReader configured for MacroPdf417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Step 4: Read all barcodes in the image and display the most relevant macro information
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // Macro PDF417 specific fields
                    Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments  : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                }
            }
        }
    }
}
```

## Conclusion

You now know **how to decode pdf417** čárové kódy v C# a jak **read barcode image c#** pomocí Aspose.BarCode. Tutoriál vás provedl nastavením projektu, načítáním obrázku, konfigurací čtečky, extrakcí výsledků a řešením okrajových případů. S tímto základem můžete integrovat dekódování PDF417 do inventárních systémů, validátorů vstupenek nebo jakéhokoli pracovního postupu, který spoléhá na makro‑kódovaná data.

### Next steps

* Prozkoumejte další formáty čárových kódů změnou `DecodeType` (např. `DecodeType.QR`, `DecodeType.Code128`).  
* Spojte více dekódovaných segmentů pro rekonstrukci původního dokumentu.  
* Použijte třídu `BarCodeGenerator` k vytvoření testovacích PDF417 čárových kódů za běhu.  

Neváhejte experimentovat s různými zdroji obrázků, upravit výstup v konzoli nebo vložit logiku dekódování do webového API pro zpracování v reálném čase. Šťastné programování!

## What Should You Learn Next?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Jak dekódovat PDF417 v C# s příkladem čtečky čárových kódů](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [Jak generovat PDF417 čárové kódy v C# s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [Jak číst čárový kód z obrázku c# pomocí Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}