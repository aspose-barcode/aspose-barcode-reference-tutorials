---
category: general
date: 2026-09-29
description: Hoe PDF417-barcodes te decoderen in C# met Aspose.BarCode. Leer een voorbeeld
  van een barcodelezer dat laat zien hoe barcode‑afbeeldingen te lezen en macro‑gegevens
  te extraheren.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- how to read barcode
- barcode reader example
- read pdf417 barcode
- read barcode image c#
language: nl
lastmod: 2026-09-29
og_description: Hoe PDF417‑barcodes te decoderen in C# met Aspose.BarCode. Deze gids
  toont een kant‑en‑klare barcodelezer‑voorbeeld voor het lezen van barcode‑afbeeldingen.
og_image_alt: Screenshot of C# code decoding a PDF417 macro barcode and printing its
  fields
og_title: Hoe PDF417-barcodes te decoderen in C# – compleet barcodelezer‑voorbeeld
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to decode PDF417 barcodes in C# using Aspose.BarCode. Learn a barcode
    reader example that shows how to read barcode images and extract macro data.
  headline: How to decode PDF417 barcodes in C# – step‑by‑step guide
  type: TechArticle
- description: How to decode PDF417 barcodes in C# using Aspose.BarCode. Learn a barcode
    reader example that shows how to read barcode images and extract macro data.
  name: How to decode PDF417 barcodes in C# – step‑by‑step guide
  steps:
  - name: Expected console output
    text: '``` Pdf417MacroFileID: 12345 Pdf417MacroSegmentID: 1 Pdf417MacroFileName:
      Invoice_2026_09_29.pdf ```'
  - name: No barcode detected
    text: '```csharp var results = reader.ReadBarCodes().ToList(); if (!results.Any())
      { Console.WriteLine("No PDF417 barcode found in the image."); return; } ```'
  - name: Unsupported image format
    text: Aspose.BarCode supports PNG, JPEG, BMP, TIFF, and GIF. Attempting to read
      a RAW or WebP file throws `ArgumentException`. Convert the image to a supported
      format before feeding it to the reader.
  - name: Large macro files
    text: Macro‑PDF417 can span many segments. To reconstruct the original file you
      must collect all segments (ordered by `MacroPdf417SegmentID`) and concatenate
      their payloads. The example above only prints individual segment metadata; a
      production implementation would store each segment in a dictionary, the
  - name: Performance tip
    text: If you process thousands of images, reuse a single `BarCodeReader` instance
      with the `SetImage` method instead of creating a new object for each file. This
      reduces memory allocations and speeds up decoding.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- Aspose.BarCode
title: Hoe PDF417-barcodes te decoderen in C# – stapsgewijze handleiding
url: /nl/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417-barcodes te decoderen in C# – stapsgewijze gids

Als je **how to decode PDF417** barcodes in C# nodig hebt, biedt deze tutorial een complete, uitvoerbare oplossing. Je ziet een **barcode reader example** die laat zien **how to read barcode** afbeeldingen, macro‑informatie extraheert en de resultaten naar de console print.

Het decoderen van PDF417 is gebruikelijk bij het verwerken van verzendlabels, tickets of overheids‑ID’s. Aan het einde van deze gids kun je een PDF417‑barcode‑afbeelding lezen, toegang krijgen tot de macro‑velden en typische randgevallen afhandelen. Er is geen externe documentatie nodig – alles wat je nodig hebt is inbegrepen.

## Wat je zult leren

- Installeer de Aspose.BarCode bibliotheek voor .NET  
- Maak een `BarCodeReader` die **read PDF417 barcode** gegevens uit een PNG‑ of JPEG‑bestand leest  
- Itereer over `BarCodeResult`‑objecten en haal macro‑PDF417‑eigenschappen op  
- Los veelvoorkomende problemen op, zoals niet‑ondersteunde afbeeldingsformaten of ontbrekende macro‑data  

## Vereisten

Voordat je begint, zorg ervoor dat je het volgende hebt:

| Requirement | Reason |
|-------------|--------|
| .NET 6.0 SDK or later | Biedt de runtime voor C#‑projecten |
| Visual Studio 2022 (or any IDE that supports .NET) | Maakt eenvoudige projectcreatie en debugging mogelijk |
| NuGet package **Aspose.BarCode** | Levert de `BarCodeReader`‑klasse die in het voorbeeld wordt gebruikt |
| A PDF417 macro image (e.g., `ExtPDF417Meta.png`) | Het bronbestand dat de lezer zal decoderen |

> **Pro tip:** Als je geen PDF417‑afbeelding hebt, kun je er een genereren met de gratis Aspose.BarCode online demo of een echt label scannen.

## Stap 1: Installeer Aspose.BarCode via NuGet

Open een terminal in je solution‑map en voer uit:

```bash
dotnet add package Aspose.BarCode
```

Het commando voegt de nieuwste stabiele versie van Aspose.BarCode toe aan je project en werkt het `.csproj`‑bestand bij. Deze bibliotheek implementeert **read barcode image C#** functionaliteit voor tientallen symbologieën, inclusief PDF417.

## Stap 2: Maak een BarCodeReader om **how to decode PDF417**

De kern van het **how to read barcode** proces is de `BarCodeReader`. Je moet de lezer zowel het bestandspad als de verwachte symbologie (`DecodeType.MacroPdf417`) meegeven. Het opgeven van de juiste `DecodeType` verbetert de detectiesnelheid en nauwkeurigheid.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Adjust the path to point at your PDF417 macro image
string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

// The reader is disposable; wrap it in a using block to release resources automatically.
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Step 3 is inside this block.
}
```

**Waarom dit belangrijk is:**  
- `DecodeType.MacroPdf417` vertelt de engine om te zoeken naar macro‑PDF417‑velden (file ID, segment ID, enz.).  
- Het gebruik van `using` zorgt ervoor dat de onderliggende afbeelding‑stream wordt gesloten, waardoor bestands‑lock‑problemen op Windows worden voorkomen.

## Stap 3: Itereer over gedetecteerde barcodes

Een enkele afbeelding kan meerdere barcodes bevatten. De `ReadBarCodes()`‑methode retourneert een `IEnumerable<BarCodeResult>` die je kunt doorlopen.

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside the loop we will extract macro data.
}
```

Als de afbeelding geen PDF417‑symbolen bevat, wordt de lus‑body nooit uitgevoerd, en kun je dat geval na de lus afhandelen (zie de sectie “Error handling”).

## Stap 4: Toegang tot PDF417 macro‑velden

Elke `BarCodeResult` heeft een `Extended`‑eigenschap met een `Pdf417` sub‑object. De macro‑velden die je meestal nodig hebt zijn:

| Property | Betekenis |
|----------|-----------|
| `MacroPdf417FileID` | Identifier van het volledige macro PDF417‑bestand |
| `MacroPdf417SegmentID` | Volgnummer van het huidige segment |
| `MacroPdf417FileName` | Optionele bestandsnaam opgeslagen in de macro |

Hier is de volledige code die die waarden afdrukt:

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Macro fields are nullable; use the null‑conditional operator to avoid exceptions.
    Console.WriteLine($"Pdf417MacroFileID:   {result.Extended?.Pdf417?.MacroPdf417FileID}");
    Console.WriteLine($"Pdf417MacroSegmentID:{result.Extended?.Pdf417?.MacroPdf417SegmentID}");
    Console.WriteLine($"Pdf417MacroFileName: {result.Extended?.Pdf417?.MacroPdf417FileName}");

    // You can also read other macro properties, such as:
    // result.Extended.Pdf417.MacroPdf417Addressee
    // result.Extended.Pdf417.MacroPdf417Sender
}
```

### Verwachte console‑output

```
Pdf417MacroFileID:    12345
Pdf417MacroSegmentID: 1
Pdf417MacroFileName:  Invoice_2026_09_29.pdf
```

Als de macro‑velden niet aanwezig zijn, zal de output lege regels tonen omdat de eigenschappen `null` zijn. Dat is normaal voor niet‑macro PDF417‑barcodes.

## Stap 5: Omgaan met veelvoorkomende valkuilen (error handling & edge cases)

### Geen barcode gedetecteerd

```csharp
var results = reader.ReadBarCodes().ToList();
if (!results.Any())
{
    Console.WriteLine("No PDF417 barcode found in the image.");
    return;
}
```

### Niet‑ondersteund afbeeldingsformaat

Aspose.BarCode ondersteunt PNG, JPEG, BMP, TIFF en GIF. Het proberen te lezen van een RAW‑ of WebP‑bestand veroorzaakt een `ArgumentException`. Converteer de afbeelding naar een ondersteund formaat voordat je deze aan de lezer geeft.

### Grote macro‑bestanden

Macro‑PDF417 kan over vele segmenten verspreiden. Om het originele bestand te reconstrueren moet je alle segmenten verzamelen (gesorteerd op `MacroPdf417SegmentID`) en hun payloads samenvoegen. Het bovenstaande voorbeeld print alleen de metadata van individuele segmenten; een productie‑implementatie zou elk segment in een dictionary opslaan en ze vervolgens samenvoegen zodra alle segmenten zijn gelezen.

### Prestatie‑tip

Als je duizenden afbeeldingen verwerkt, hergebruik dan een enkele `BarCodeReader`‑instantie met de `SetImage`‑methode in plaats van voor elk bestand een nieuw object te maken. Dit vermindert geheugenallocaties en versnelt het decoderen.

```csharp
using (BarCodeReader reader = new BarCodeReader(null, DecodeType.MacroPdf417))
{
    foreach (string file in Directory.GetFiles(@"YOUR_DIRECTORY", "*.png"))
    {
        reader.SetImage(file);
        // read barcodes as shown earlier
    }
}
```

## Volledig werkend voorbeeld

Kopieer het volgende programma naar een nieuw Console‑App‑project (`dotnet new console`). Het bevat alle stappen, foutafhandeling en commentaren.

```csharp
// Program.cs
using System;
using System.IO;
using System.Linq;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the PDF417 macro image – update to your actual location.
        string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Verify the file exists before attempting to read.
        if (!File.Exists(imagePath))
        {
            Console.WriteLine($"File not found: {imagePath}");
            return;
        }

        // Initialize the reader for Macro PDF417.
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            var results = reader.ReadBarCodes().ToList();

            if (!results.Any())
            {
                Console.WriteLine("No PDF417 barcode detected in the image.");
                return;
            }

            foreach (BarCodeResult result in results)
            {
                // Print macro information safely.
                Console.WriteLine($"Pdf417MacroFileID:   {result.Extended?.Pdf417?.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID:{result.Extended?.Pdf417?.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended?.Pdf417?.MacroPdf417FileName}");
                Console.WriteLine(); // blank line for readability
            }
        }
    }
}
```

**Het programma uitvoeren**

```bash
dotnet run
```

Je zou de macro‑velden in de console moeten zien afgedrukt, overeenkomend met de eerder getoonde verwachte output.

## Conclusie

In deze tutorial heb je geleerd **how to decode PDF417** barcodes in C# met een beknopt **barcode reader example**. Door Aspose.BarCode te installeren, een `BarCodeReader` voor `MacroPdf417` te maken, over de resultaten te itereren en de `Extended.Pdf417` macro‑eigenschappen te benaderen, kun je betrouwbaar **read PDF417 barcode** data uit elke ondersteunde afbeelding lezen.  

Vanaf hier kun je:

- Segment‑aggregatie implementeren om multi‑segment macro‑bestanden opnieuw op te bouwen.  
- Andere symbologieën (QR, Code128) verkennen met hetzelfde `BarCodeReader`‑patroon.  
- De decoder integreren in een web‑API die geüploade afbeeldingen verwerkt (`read barcode image C#` in een service‑context).  

Voel je vrij om te experimenteren met verschillende afbeeldingsbronnen, foutafhandelingsstrategieën en prestatie‑optimalisaties. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PDF417 te lezen in C# – complete barcode reader gids](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/)
- [Hoe PDF417 Barcode te genereren met Aspose – Complete gids](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Hoe PDF417 Barcode te maken met Aspose – Complete stap‑voor‑stap gids](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}