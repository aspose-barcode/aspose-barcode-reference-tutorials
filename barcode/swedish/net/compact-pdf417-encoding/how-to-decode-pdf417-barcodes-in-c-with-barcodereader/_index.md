---
category: general
date: 2026-09-07
description: Lär dig hur du avkodar PDF417‑streckkoder i C# med BarCodeReader. Denna
  steg‑för‑steg‑guide förklarar också hur du läser PDF417‑data effektivt.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- how to read pdf417
- PDF417 barcode decoding C#
- MacroPdf417 extraction C#
- barcode reader BarCodeReader
- GroupDocs.Barcode tutorial
language: sv
lastmod: 2026-09-07
og_description: Hur man avkodar PDF417‑streckkoder i C# med BarCodeReader. Följ den
  här handledningen för att lära dig hur du läser PDF417‑data och extraherar MacroPdf417‑fält.
og_image_alt: Screenshot of C# code reading PDF417 barcode fields in the console
og_title: Hur man avkodar PDF417‑streckkoder i C# – komplett guide
schemas:
- author: GroupDocs
  dateModified: '2026-09-07'
  description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  headline: How to decode PDF417 barcodes in C# with BarCodeReader
  type: TechArticle
- description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  name: How to decode PDF417 barcodes in C# with BarCodeReader
  steps:
  - name: Prepare the project and import namespaces
    text: '```csharp using System; using GroupDocs.Barcode; using GroupDocs.Barcode.Common;
      ```'
  - name: Define the image path
    text: '```csharp // Replace with the absolute or relative path to your barcode
      image string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png"; ```'
  - name: Initialize the barcode reader for MacroPdf417 decoding
    text: '```csharp using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
      { // Step 4 runs inside this block } ```'
  - name: Read every barcode found in the image
    text: '```csharp foreach (BarCodeResult result in reader.ReadBarCodes()) { //
      Step 5 extracts the MacroPdf417 fields } ```'
  - name: Retrieve and display Macro PDF417 specific data
    text: '```csharp Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
      Console.WriteLine'
  - name: Full runnable example
    text: 'Combine the snippets above into a single `Program.cs` file:'
  type: HowTo
tags:
- PDF417
- C#
- barcode decoding
title: Hur man avkodar PDF417‑streckkoder i C# med BarCodeReader
url: /sv/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-with-barcodereader/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man avkodar PDF417‑streckkoder i C# med BarCodeReader

Om du behöver **avkoda PDF417**‑streckkoder i en .NET‑applikation, guidar den här artikeln dig genom hela processen. Du får också reda på **hur du läser PDF417**‑data såsom MacroPdf417‑fil‑ och segmentidentifierare, allt med några få rader C#.

Avkodning av PDF417 är vanligt när du arbetar med transportbiljetter, körkort eller fraktetiketter. I slutet av den här handledningen har du ett körbart konsolprogram som skriver ut varje MacroPdf417‑fält som exponeras av GroupDocs.Barcode‑SDK.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare (koden kompileras med .NET Core och .NET Framework)
* Visual Studio 2022 eller någon IDE som stödjer C#
* **GroupDocs.Barcode**‑NuGet‑paketet (`GroupDocs.Barcode` ≥ 23.3)
* En bildfil som innehåller en Macro PDF417‑streckkod (t.ex. `ExtPDF417Meta.png`)

> **Proffstips:** Installera paketet via CLI:  
> `dotnet add package GroupDocs.Barcode --version 23.3`

## Hur man avkodar PDF417‑streckkoder i C#

Följande avsnitt delar upp lösningen i logiska steg. Varje steg innehåller exakt den kod du behöver samt en kort förklaring till varför den är viktig.

### Steg 1: Förbered projektet och importera namnrymder

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;
```

*Varför?*  
`GroupDocs.Barcode` tillhandahåller klassen `BarCodeReader`, medan `GroupDocs.Barcode.Common` innehåller uppräkningen `DecodeType` som behövs för PDF417‑avkodning.

### Steg 2: Definiera bildens sökväg

```csharp
// Replace with the absolute or relative path to your barcode image
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

*Varför?*  
Läsaren fungerar med alla bildformat som stöds av .NET (`.png`, `.jpg`, `.bmp`). Att ange rätt sökväg säkerställer att SDK:n kan hitta filen.

### Steg 3: Initiera streckkodsläsaren för MacroPdf417‑avkodning

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Step 4 runs inside this block
}
```

*Varför?*  
`DecodeType.MacroPdf417` instruerar SDK:n att leta efter det utökade Macro PDF417‑formatet, som bär med sig extra metadata såsom fil‑ och segment‑ID:n. `using`‑satsen garanterar att ohanterade resurser frigörs omedelbart.

### Steg 4: Läs alla streckkoder som finns i bilden

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Step 5 extracts the MacroPdf417 fields
}
```

*Varför?*  
En bild kan innehålla flera streckkoder. Metoden `ReadBarCodes()` returnerar en samling, så att du kan bearbeta varje kod individuellt.

### Steg 5: Hämta och visa Macro PDF417‑specifik data

```csharp
Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
```

*Varför?*  
Objektet `Extended.Pdf417` exponerar alla Macro PDF417‑fält som definieras i specifikationen. Att skriva ut dem låter dig verifiera att avkodningen lyckades och ger dig den data du behöver för vidare bearbetning.

### Fullt körbart exempel

Kombinera kodsnuttarna ovan till en enda `Program.cs`‑fil:

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // 1️⃣ Path to the image that contains the Macro PDF417 barcode
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 2️⃣ Create a reader configured for MacroPdf417 decoding
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 3️⃣ Iterate over all detected barcodes
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // 4️⃣ Output Macro PDF417 metadata
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
                Console.WriteLine(); // Blank line for readability
            }
        }
    }
}
```

**Förväntad konsolutskrift** (värdena varierar beroende på streckkodens innehåll):

```
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentCount: 3
Pdf417MacroFileName: shipment_data
Pdf417MacroTimestamp: 2024-07-15T10:23:45Z
```

Om bilden inte innehåller en Macro PDF417‑streckkod blir samlingen som returneras av `ReadBarCodes()` tom och inget skrivs ut.

## Vanliga variationer och kantfall

| Situation | Hur du anpassar koden |
|-----------|------------------------|
| **Standard (icke‑macro) PDF417** | Ändra `DecodeType.MacroPdf417` till `DecodeType.Pdf417`. Objektet `Extended.Pdf417` blir `null`, så skydda mot null‑referenser. |
| **Flera bilder** | Lägg in initieringen av läsaren i en `foreach (var path in imagePaths)`‑loop. |
| **Stora bilder** | Sätt `reader.Options.ImageProcessingOptions.MaxImageDimension = 2000;` för att begränsa minnesanvändning. |
| **Prestandakritisk batch** | Återanvänd en enda `BarCodeReader`‑instans med `reader.SetImage(path)` istället för att skapa ett nytt objekt för varje fil. |

## Felsökningschecklista

* **Ingen utskrift:** Verifiera att `imagePath` pekar på en giltig fil och att bilden faktiskt innehåller en PDF417‑streckkod. |
* **Null `Extended.Pdf417`:** Du har troligen använt `DecodeType.Pdf417` istället för `MacroPdf417`. |
* **Undantaget `FileNotFoundException`:** Säkerställ att arbetskatalogen matchar sökvägen eller använd en absolut sökväg. |
* **Lågt förtroendescore:** Förbättra bildkvaliteten eller justera `reader.Options.Quality`‑inställningarna. |

## Slutsats

Du vet nu **hur man avkodar PDF417**‑streckkoder i C# och **hur man läser PDF417**‑metadata såsom Macro‑fil‑ID:n, segment‑ID:n och tidsstämplar. Det kompletta exemplet visar hur du initierar `BarCodeReader`, väljer rätt avkodningstyp, itererar över resultat och extraherar varje tillgängligt MacroPdf417‑fält.

Härifrån kan du:

* Integrera den extraherade datan i ett logistik‑ eller biljettvalideringssystem.
* Utöka konsolappen så att den skriver resultat till en databas eller JSON‑fil.
* Utforska andra streckkodformat som stöds av GroupDocs.Barcode (QR, DataMatrix, Code128, etc.) genom att byta ut `DecodeType`‑uppräkningen.

Lycka till med kodandet, och experimentera gärna med olika bilder och streckkodinställningar för att bemästra PDF417‑avkodning i dina .NET‑projekt!

## Vad bör du lära dig härnäst?

De följande handledningarna täcker närbesläktade ämnen som bygger vidare på teknikerna i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to Read PDF417 in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}