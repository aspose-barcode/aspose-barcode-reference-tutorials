---
category: general
date: 2026-09-29
description: Hur man avkodar PDF417‑streckkoder i C# med Aspose.BarCode. Lär dig ett
  exempel på streckkodsläsare som visar hur man läser streckkodsbilder och extraherar
  makrodatan.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- how to read barcode
- barcode reader example
- read pdf417 barcode
- read barcode image c#
language: sv
lastmod: 2026-09-29
og_description: Hur man avkodar PDF417‑streckkoder i C# med Aspose.BarCode. Denna
  guide visar ett färdigt exempel på en streckkodsläsare för att läsa streckkodsbilder.
og_image_alt: Screenshot of C# code decoding a PDF417 macro barcode and printing its
  fields
og_title: Hur man avkodar PDF417‑streckkoder i C# – komplett exempel på streckkodsläsare
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
title: Hur man avkodar PDF417‑streckkoder i C# – steg‑för‑steg‑guide
url: /sv/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man avkodar PDF417‑streckkoder i C# – steg‑för‑steg guide

Om du behöver **hur man avkodar PDF417** streckkoder i C#, ger den här handledningen dig en komplett, körbar lösning. Du kommer att se ett **exempel på streckkodsläsare** som demonstrerar **hur man läser streckkod** bilder, extraherar makroinformation och skriver ut resultaten till konsolen.

Att avkoda PDF417 är vanligt när man bearbetar fraktetiketter, biljetter eller statliga ID‑kort. I slutet av den här guiden kommer du att kunna läsa en PDF417‑streckkodbild, komma åt dess makrofält och hantera typiska kantfall. Ingen extern dokumentation krävs – allt du behöver finns med.

## Vad du kommer att lära dig

- Installera Aspose.BarCode‑biblioteket för .NET  
- Skapa en `BarCodeReader` som **läser PDF417‑streckkod**‑data från en PNG‑ eller JPEG‑fil  
- Iterera över `BarCodeResult`‑objekt och hämta macro‑PDF417‑egenskaper  
- Felsöka vanliga problem såsom ej stödda bildformat eller saknad makrodata  

## Förutsättningar

| Krav | Anledning |
|-------------|--------|
| .NET 6.0 SDK eller senare | Tillhandahåller runtime för C#‑projekt |
| Visual Studio 2022 (eller någon IDE som stödjer .NET) | Gör det enkelt att skapa projekt och felsöka |
| NuGet‑paket **Aspose.BarCode** | Tillhandahåller `BarCodeReader`‑klassen som används i exemplet |
| En PDF417‑makrobild (t.ex. `ExtPDF417Meta.png`) | Källfilen som läsaren kommer att avkoda |

> **Pro tip:** Om du inte har en PDF417‑bild kan du generera en med den gratis Aspose.BarCode‑online‑demo eller skanna en riktig etikett.

## Steg 1: Installera Aspose.BarCode via NuGet

Öppna en terminal i din lösningsmapp och kör:

```bash
dotnet add package Aspose.BarCode
```

Kommandot lägger till den senaste stabila versionen av Aspose.BarCode i ditt projekt och uppdaterar `.csproj`‑filen. Detta bibliotek implementerar **läser streckkod bild C#**‑funktionalitet för dussintals symbologier, inklusive PDF417.

## Steg 2: Skapa en BarCodeReader för att **hur man avkodar PDF417**

Kärnan i **hur man läser streckkod**‑processen är `BarCodeReader`. Du måste tala om för läsaren både filsökvägen och den förväntade symbologin (`DecodeType.MacroPdf417`). Att ange rätt `DecodeType` förbättrar detekteringshastigheten och noggrannheten.

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

**Varför detta är viktigt:**  
- `DecodeType.MacroPdf417` talar om för motorn att leta efter macro‑PDF417‑fält (fil‑ID, segment‑ID osv.).  
- Användning av `using` säkerställer att den underliggande bildströmmen stängs, vilket förhindrar fil‑lås‑problem på Windows.

## Steg 3: Iterera över upptäckta streckkoder

En enda bild kan innehålla flera streckkoder. Metoden `ReadBarCodes()` returnerar ett `IEnumerable<BarCodeResult>` som du kan loopa igenom.

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside the loop we will extract macro data.
}
```

Om bilden inte innehåller några PDF417‑symboler körs loopkroppen aldrig, och du kan hantera det fallet efter loopen (se avsnittet “Felhantering”).

## Steg 4: Åtkomst till PDF417‑makrofält

Varje `BarCodeResult` exponerar en `Extended`‑egenskap med ett `Pdf417`‑sub‑objekt. De makrofält du oftast behöver är:

| Egenskap | Betydelse |
|----------|-----------|
| `MacroPdf417FileID` | Identifierare för hela macro‑PDF417‑filen |
| `MacroPdf417SegmentID` | Sekvensnummer för det aktuella segmentet |
| `MacroPdf417FileName` | Valfritt filnamn lagrat i makrot |

Här är den fullständiga koden som skriver ut dessa värden:

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

### Förväntad konsolutskrift

```
Pdf417MacroFileID:    12345
Pdf417MacroSegmentID: 1
Pdf417MacroFileName:  Invoice_2026_09_29.pdf
```

Om makrofälten inte finns kommer utskriften att visa tomma rader eftersom egenskaperna är `null`. Det är normalt för icke‑macro PDF417‑streckkoder.

## Steg 5: Hantera vanliga fallgropar (felhantering & kantfall)

### Ingen streckkod upptäckt

```csharp
var results = reader.ReadBarCodes().ToList();
if (!results.Any())
{
    Console.WriteLine("No PDF417 barcode found in the image.");
    return;
}
```

### Ej stödformat för bild

Aspose.BarCode stödjer PNG, JPEG, BMP, TIFF och GIF. Försök att läsa en RAW‑ eller WebP‑fil kastar `ArgumentException`. Konvertera bilden till ett stödd format innan du matar den till läsaren.

### Stora makro‑filer

Macro‑PDF417 kan sträcka sig över många segment. För att rekonstruera den ursprungliga filen måste du samla alla segment (ordnade efter `MacroPdf417SegmentID`) och konkatenera deras payloads. Exemplet ovan skriver bara ut metadata för varje segment; en produktionsimplementation skulle lagra varje segment i en dictionary och sedan sätta ihop dem när alla segment har lästs.

### Prestandatips

Om du bearbetar tusentals bilder, återanvänd en enda `BarCodeReader`‑instans med `SetImage`‑metoden istället för att skapa ett nytt objekt för varje fil. Detta minskar minnesallokeringar och snabbar upp avkodningen.

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

## Fullständigt fungerande exempel

Kopiera följande program till ett nytt Console App‑projekt (`dotnet new console`). Det inkluderar alla steg, felhantering och kommentarer.

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

**Kör programmet**

```bash
dotnet run
```

Du bör se makrofälten skrivna till konsolen, vilket matchar den förväntade utskriften som visades tidigare.

## Slutsats

I den här handledningen lärde du dig **hur man avkodar PDF417** streckkoder i C# med ett koncist **exempel på streckkodsläsare**. Genom att installera Aspose.BarCode, skapa en `BarCodeReader` för `MacroPdf417`, iterera över resultat och komma åt `Extended.Pdf417`‑makroegenskaperna, kan du på ett pålitligt sätt **läsa PDF417‑streckkod**‑data från vilken stödd bild som helst.  

Härifrån kan du:

- Implementera segmentaggregering för att återuppbygga fler‑segment‑macro‑filer.  
- Utforska andra symbologier (QR, Code128) med samma `BarCodeReader`‑mönster.  
- Integrera avkodaren i ett webb‑API som bearbetar uppladdade bilder (`read barcode image C#` i en tjänstekontext).  

Känn dig fri att experimentera med olika bildkällor, felhanteringsstrategier och prestandaoptimeringar. Lycka till med kodandet!

## Vad bör du lära dig härnäst?

De följande handledningarna täcker nära besläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man läser PDF417 i C# – komplett streckkodsläsarguide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/)
- [Hur man genererar PDF417‑streckkod med Aspose – komplett guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Hur man skapar PDF417‑streckkod med Aspose – komplett steg‑för‑steg guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}