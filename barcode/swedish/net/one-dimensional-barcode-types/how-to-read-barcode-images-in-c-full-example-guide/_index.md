---
category: general
date: 2026-10-15
description: Hur man snabbt läser streckkodsbilder i C# med BarCodeReader. Lär dig
  läsa flera streckkoder och se ett C#-exempel på streckkodsläsare som fungerar med
  Macro‑PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode
- read multiple barcodes
- c# barcode reader example
- Macro‑PDF417 decoding
- barcode metadata extraction
language: sv
lastmod: 2026-10-15
og_description: Hur man läser streckkod i C# med BarCodeReader. Denna handledning
  visar ett komplett C#-streckkodsläsareexempel som hanterar flera streckkoder och
  extraherar Macro‑PDF417‑metadata.
og_image_alt: Screenshot showing how to read barcode with C# BarCodeReader
og_title: Hur man läser streckkod i C# – steg‑för‑steg‑exempel
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  headline: How to read barcode images in C# – full example guide
  type: TechArticle
- description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  name: How to read barcode images in C# – full example guide
  steps:
  - name: Initialise the `BarCodeReader`
    text: '```csharp using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Read all barcodes present in the image
    text: '```csharp // Step 2: Read all barcodes in the image BarCodeResult[] results
      = reader.ReadBarCodes(); ```'
  - name: Display basic barcode details
    text: '```csharp foreach (BarCodeResult result in results) { Console.WriteLine($"CodeType:
      {result.CodeTypeName}"); Console.WriteLine($"CodeText: {result.CodeText}");
      ```'
  - name: Retrieve and show Macro‑PDF417 specific metadata
    text: '```csharp // Macro‑PDF417 extended data Console.WriteLine($"FileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Segment: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Count: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
      Console.WriteLine($"FileName'
  - name: Full runnable program
    text: Below is a self‑contained console application that puts all four steps together.
      Copy the code into a new `.cs` file, adjust the `imagePath`, and run `dotnet
      run`.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Hur man läser streckkodsbilder i C# – fullständig exempelguide
url: /sv/net/one-dimensional-barcode-types/how-to-read-barcode-images-in-c-full-example-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man läser streckkodsbilder i C# – fullständig exempelguide

Om du behöver **how to read barcode** data från en bild i en .NET‑applikation, ger den här guiden dig en färdig‑att‑köra lösning. Du kommer att se ett komplett **c# barcode reader example** som fungerar med Macro‑PDF417‑symboler och kan **read multiple barcodes** från en enda bild.

Att läsa streckkoder är ett vanligt krav för lagersystem, biljettvalidering och dokumentbehandling. I slutet av den här handledningen kommer du att kunna:

* Initiera `BarCodeReader` för vilket som helst stödjt format.  
* Extrahera grundläggande information såsom kodtyp och avkodad text.  
* Hämta Macro‑PDF417‑specifik metadata (fil‑ID, segment, kontrollsumma, …).  
* Hantera bilder som innehåller flera streckkoder utan extra kod.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare installerat.  
* En utvecklingsmiljö (Visual Studio 2022, VS Code eller Rider).  
* **Aspose.BarCode for .NET** NuGet‑paketet (`Aspose.BarCode`) – det tillhandahåller `BarCodeReader`‑klassen som används i exemplet.  
* En bildfil som innehåller en Macro‑PDF417‑streckkod (t.ex. `MacroPdf417.png`).  

Du kan installera NuGet‑paketet med följande kommando:

```bash
dotnet add package Aspose.BarCode
```

## Så läser du streckkod med BarCodeReader i C#

Kärnan i lösningen består av fyra koncisa steg. Varje steg är inneslutet i ett `using`‑block för att garantera att ohanterade resurser frigörs omedelbart.

### Steg 1: Initiera `BarCodeReader`

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Path to the image that contains the Macro‑PDF417 barcode(s)
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for the specific DecodeType
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The remaining steps are inside this block
}
```

**Varför detta är viktigt:**  
`BarCodeReader` accepterar en filsökväg och en `DecodeType`. Att ange `DecodeType.MacroPdf417` talar om för biblioteket att endast leta efter Macro‑PDF417‑symboler, vilket förbättrar detekteringshastigheten och minskar falska positiva.

### Steg 2: Läs alla streckkoder som finns i bilden

```csharp
    // Step 2: Read all barcodes in the image
    BarCodeResult[] results = reader.ReadBarCodes();
```

**Varför detta är viktigt:**  
Metoden `ReadBarCodes()` returnerar en array som kan innehålla en eller flera `BarCodeResult`‑objekt. Detta är punkten där **read multiple barcodes**‑funktionen glänser – du behöver ingen separat loop för varje möjlig streckkod.

### Steg 3: Visa grundläggande streckkoddetaljer

```csharp
    foreach (BarCodeResult result in results)
    {
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

**Varför detta är viktigt:**  
`CodeTypeName` berättar vilken symbologi som upptäcktes (t.ex. “MacroPDF417”), medan `CodeText` innehåller den avkodade nyttolasten. Dessa två fält är de mest frekvent använda i efterföljande logik.

### Steg 4: Hämta och visa Macro‑PDF417‑specifik metadata

```csharp
        // Macro‑PDF417 extended data
        Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
        Console.WriteLine(new string('-', 40));
    }
}
```

**Varför detta är viktigt:**  
Macro‑PDF417 utökar det vanliga PDF417‑formatet med dokument‑nivå metadata. Genom att komma åt egenskapen `Extended.Pdf417` får du allt du behöver för att rekonstruera originalfilen, validera integriteten eller dirigera data till rätt mottagare.

### Fullt körbart program

Nedan finns ett självständigt konsolprogram som samlar alla fyra stegen. Kopiera koden till en ny `.cs`‑fil, justera `imagePath` och kör `dotnet run`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // 1️⃣ Initialise the BarCodeReader for Macro‑PDF417 images
            // ------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ------------------------------------------------------------
                // 2️⃣ Read all barcodes present in the image
                // ------------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes were detected.");
                    return;
                }

                // ------------------------------------------------------------
                // 3️⃣ Iterate over each result – this is where we **read multiple barcodes**
                // ------------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // ------------------------------------------------------------
                    // 4️⃣ Extract Macro‑PDF417 metadata (c# barcode reader example)
                    // ------------------------------------------------------------
                    Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

#### Förväntad konsolutdata

```
CodeType: MacroPDF417
CodeText: https://example.com/document
FileID:    12
Segment:   3
Count:     5
FileName:  report.pdf
Checksum:  0x1A2B3C4D
FileSize:  1048576
Time:      2024-08-15T14:23:00Z
Addressee: John Doe
Sender:    Acme Corp.
Terminator:END
----------------------------------------
```

Om bilden innehåller mer än en Macro‑PDF417‑symbol skriver programmet ut ett separat block för varje streckkod, vilket demonstrerar **read multiple barcodes**‑kapaciteten utan någon extra kod.

## Hantera vanliga edge‑case

| Situation | Vad man ska göra | Orsak |
|-----------|-------------------|-------|
| **File not found** | Omge konstruktionen av `BarCodeReader` med ett `try/catch (FileNotFoundException)`‑block och visa ett vänligt meddelande. | Förhindrar att applikationen kraschar och informerar användaren om den saknade resursen. |
| **No barcode detected** | Kontrollera `results.Length == 0` (som visas i det fullständiga programmet) och hantera det på ett smidigt sätt. | Ger tydlig återkoppling när bilden inte innehåller någon stödjad symbologi. |
| **Different barcode type** | Ändra `DecodeType.MacroPdf417` till `DecodeType.AllSupportedTypes` eller ett annat specifikt enum‑värde. | Gör att samma kodbas kan fungera med QR, Code128, DataMatrix osv., samtidigt som **read multiple barcodes** stöds. |
| **Large images** | Sätt `reader.AutoSize = true` eller skala ner bilden innan den matas in i läsaren. | Förbättrar prestanda och minskar minnesbelastningen på CLR. |
| **Thread‑safe usage** | Skapa en separat `BarCodeReader`‑instans per tråd; klassen är inte trådsäker. | Undviker race‑conditions i flertrådade skannrar eller webbtjänster. |

## Pro‑tips för produktionskod

* **Dispose early:** `using`‑satsen säkerställer att inhemska resurser (t.ex. bildbuffertar) frigörs snabbt. I långlivade tjänster, släpp läsaren så snart du är klar med varje bild.  
* **Batch processing

## Vad bör du lära dig härnäst?

De följande handledningarna täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Läs streckkod från bild C# – komplett guide med Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Hur man skapar macro PDF417 streckkod i C# med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Hur man läser PDF417 i C# – komplett streckkodsläsarexempel](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}