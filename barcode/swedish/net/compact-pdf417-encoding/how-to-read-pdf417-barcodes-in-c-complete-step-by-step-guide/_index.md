---
category: general
date: 2026-09-22
description: Lär dig hur du läser PDF417‑streckkoder i C# med ett komplett streckkodsläsarexempel.
  Den här handledningen visar dig hur du snabbt och pålitligt läser streckkodsbilder
  i C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode image c#
- c# barcode reader example
language: sv
lastmod: 2026-09-22
og_description: Hur du läser PDF417‑streckkoder i C# med ett koncist streckkodsläsareexempel.
  Följ guiden för att avkoda Macro PDF417‑bilder och extrahera metadata.
og_image_alt: Screenshot of C# code that reads a PDF417 barcode and prints its metadata
og_title: Hur man läser PDF417‑streckkoder i C# – komplett exempel på streckkodsläsare
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  headline: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  name: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  steps:
  - name: Why each step matters
    text: '1. **Creating the reader with `DecodeType.MacroPdf417`** – Macro PDF417
      is a special variant that can carry file‑level metadata. Specifying the decode
      type ensures the SDK parses those extra fields instead of treating the code
      as a plain PDF417. 2. **Iterating over `ReadBarCodes()`** – An image can '
  - name: Reading a non‑macro PDF417 barcode
    text: If your source images contain regular PDF417 codes (no macro metadata),
      replace `DecodeType.MacroPdf417` with `DecodeType.Pdf417`. The rest of the code
      stays identical, but the `Extended.Pdf417` block will be empty because those
      fields simply don’t exist.
  - name: Handling multi‑segment PDFs
    text: 'Macro PDF417 can split a large document across several barcode segments.
      To reassemble the original file you must:'
  - name: Dealing with corrupted images
    text: '- **Low contrast** – Increase image preprocessing (e.g., histogram equalization)
      before passing it to `BarCodeReader`. - **Rotation** – Use `barcodeReader.SetRotateAngle(90)`
      or enable auto‑rotate if the SDK supports it. - **Partial scans** – Ensure the
      image resolution is at least 300 dpi; otherwis'
  - name: Next steps
    text: '- Explore **read barcode image C#** techniques for other symbologies (QR,
      DataMatrix) using the same `BarCodeReader` API. - Integrate the barcode decoder
      into an ASP.NET Core service to process uploads on the fly. - Experiment with
      image preprocessing libraries (e.g., `OpenCvSharp`) to boost success'
  type: HowTo
tags:
- barcode
- pdf417
- c#
title: Hur man läser PDF417‑streckkoder i C# – komplett steg‑för‑steg‑guide
url: /sv/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man läser PDF417‑streckkoder i C# – komplett steg‑för‑steg‑guide

Om du behöver **how to read pdf417** i en .NET‑applikation visar den här guiden exakt kod och resonemang du behöver. Efter de två första meningarna kommer du att veta hur man läser streckkodsbilder i C# med den populära `BarCodeReader`‑klassen, och du får ett färdigt exempel som extraherar varje del av Macro PDF417‑metadata.

Att läsa PDF417‑streckkoder är ett vanligt krav när man bearbetar fraktetiketter, boardingkort eller säkra dokument. Denna handledning täcker allt från att konfigurera läsaren till att hantera kantfall, så att du kan integrera streckkodsskanning med förtroende.

## Vad du kommer att uppnå

- Dekoda en Macro PDF417‑bildfil.
- Skriv ut grundläggande streckkodsinformation (typ och text).
- Åtkomst till alla utökade Macro PDF417‑fält såsom fil‑ID, segmentantal och tidsstämpel.
- Förstå vanliga fallgropar när du arbetar med multi‑segment PDF417‑koder.

**Förutsättningar**

- .NET 6.0 eller senare (koden fungerar också med .NET Framework 4.7+).
- En referens till barcode‑SDK som tillhandahåller `BarCodeReader`, `DecodeType` och `BarCodeResult` (t.ex. Aspose.BarCode, Dynamsoft eller något bibliotek som exponerar samma API).
- En bildfil (`ExtPDF417Meta.png`) som innehåller en Macro PDF417‑streckkod.

> **Pro tip:** Placera bilden i en mapp relativt till projektroten och sätt dess **Copy to Output Directory**‑egenskap till *Copy if newer* så att sökvägen fungerar under felsökning.

![Hur man läser PDF417‑streckkod med C#](https://example.com/placeholder-image.png)

## Hur man läser PDF417‑streckkod i C# – den kompletta koden

Nedan är ett självständigt program som du kan klistra in i en konsolapplikation. Det skapar en streckkodsläsare, itererar över varje avkodad resultat och skriver ut både standard‑ och utökade Macro PDF417‑fält.

```csharp
using System;
using Aspose.BarCode;          // Replace with the namespace of your barcode SDK
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode reader for a Macro PDF417 image
        // The second argument tells the SDK to look specifically for Macro PDF417 codes.
        using var barcodeReader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417);

        // Step 2: Decode all barcodes present in the image
        foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
        {
            // Step 3: Display the basic barcode information
            Console.WriteLine($"CodeType: {result.CodeTypeName}");
            Console.WriteLine($"CodeText: {result.CodeText}");

            // Step 4: Output Macro PDF417 specific metadata
            // All properties are available through the Extended.Pdf417 object.
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
    }
}
```

### Varför varje steg är viktigt

1. **Creating the reader with `DecodeType.MacroPdf417`** – Macro PDF417 är en speciell variant som kan bära fil‑nivå metadata. Att specificera avkodningstypen säkerställer att SDK:n parsar dessa extra fält istället för att behandla koden som en vanlig PDF417.
2. **Iterating over `ReadBarCodes()`** – En bild kan innehålla mer än en streckkod (t.ex. en QR‑kod bredvid en PDF417). Loopen garanterar att du fångar varje resultat.
3. **Printing `CodeTypeName` and `CodeText`** – Dessa är de mest använda egenskaperna; de ger dig symbologinamnet och den mänskligt läsbara nyttolasten.
4. **Accessing `Extended.Pdf417`** – `Extended`‑objektet visas endast för PDF417‑relaterade avkodningstyper. Varje egenskap mappar direkt till Macro PDF417‑specifikationen, vilket låter dig återskapa den ursprungliga filen eller validera segmentordning.

## Vanliga variationer och kantfall

### Läsa en icke‑macro PDF417‑streckkod

Om dina källbilder innehåller vanliga PDF417‑koder (utan macro‑metadata), ersätt `DecodeType.MacroPdf417` med `DecodeType.Pdf417`. Resten av koden förblir identisk, men `Extended.Pdf417`‑blocket blir tomt eftersom dessa fält helt enkelt inte finns.

### Hantera multi‑segment PDF‑filer

Macro PDF417 kan dela ett stort dokument över flera streckkodsegment. För att återmontera den ursprungliga filen måste du:

1. Samla varje segments `Pdf417MacroSegmentID`.
2. Sortera segmenten efter deras ID.
3. Verifiera att `Pdf417MacroSegmentsCount` matchar antalet mottagna segment.
4. Konkatenera `CodeText` för varje segment i rätt ordning.
5. Valfritt validera `Pdf417MacroChecksum`.

Nedan är ett koncist kodsnutt som demonstrerar återmonteringslogiken:

```csharp
var segments = new SortedDictionary<int, string>();
int expectedCount = 0;

foreach (var result in barcodeReader.ReadBarCodes())
{
    int segId = result.Extended.Pdf417.MacroPdf417SegmentID;
    int segCount = result.Extended.Pdf417.MacroPdf417SegmentsCount;
    expectedCount = segCount;               // will be the same for every segment
    segments[segId] = result.CodeText;       // store payload by segment ID
}

// Verify we have all parts
if (segments.Count == expectedCount)
{
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine("Reassembled payload:");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Missing segments: expected {expectedCount}, received {segments.Count}");
}
```

### Hantera korrupta bilder

- **Low contrast** – Öka bildförbehandling (t.ex. histogramutjämning) innan du skickar den till `BarCodeReader`.
- **Rotation** – Använd `barcodeReader.SetRotateAngle(90)` eller aktivera auto‑rotate om SDK:n stödjer det.
- **Partial scans** – Säkerställ att bildens upplösning är minst 300 dpi; annars kan SDK:n missa små segment.

## c# streckkodsläsare‑exempel – bästa praxis

| Praktik | Anledning |
|----------|-----------|
| **Dispose läsaren med `using`** | Garanti för att inhemska resurser frigörs omedelbart, vilket förhindrar minnesläckor. |
| **Validera att `result.Extended` inte är null** | Vissa SDK:er returnerar `null` för icke‑macro‑koder; kontrollen undviker ett `NullReferenceException`. |
| **Logga `Pdf417MacroFileID`** | Denna identifierare är unik per fil och användbar för revisionsspår. |
| **Omge avkodning med try/catch** | I/O‑fel (saknad fil) eller ej stödda format kastar undantag som bör hanteras på ett smidigt sätt. |

```csharp
try
{
    // decoding logic here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image not found: {ex.FileName}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Förväntad output

Att köra hela programmet mot en korrekt formaterad `ExtPDF417Meta.png` ger en output liknande:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-08-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

Om bilden innehåller flera segment kommer loopen att skriva ut varje segments metadata sekventiellt.

## Slutsats

Du vet nu **how to read pdf417** streckkoder i C# och har ett **c# barcode reader example** som extraherar varje Macro PDF417‑fält. Lösningen täcker grundläggande avkodning, metadata‑extraktion, återmontering av multi‑segment och felhantering, vilket ger dig en produktionsklar grund för alla dokument‑bearbetningsarbetsflöden.

### Nästa steg

- Utforska **read barcode image C#**‑tekniker för andra symbologier (QR, DataMatrix) med samma `BarCodeReader`‑API.
- Integrera streckkodsavkodaren i en ASP.NET Core‑tjänst för att bearbeta uppladdningar i realtid.
- Experimentera med bildförbehandlingsbibliotek (t.ex. `OpenCvSharp`) för att öka framgångsfrekvensen på lågkvalitativa skanningar.

Lycka till med kodningen, och känn dig fri att anpassa exemplet efter ditt specifika användningsområde!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man sparar streckkod i C# – Generera PDF417‑streckkoder](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Hur man läser PDF417 i C# – Komplett steg‑för‑steg‑guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [Hur man ställer in felnivå i PDF417‑streckkod – Komplett guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}