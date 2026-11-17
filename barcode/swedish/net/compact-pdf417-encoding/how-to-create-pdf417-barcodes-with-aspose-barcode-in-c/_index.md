---
category: general
date: 2026-11-17
description: Hur man skapar PDF417‑streckkoder med Aspose.BarCode – steg‑för‑steg‑guide
  som också visar hur man skapar streckkod med Aspose i C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create pdf417
- create barcode aspose
language: sv
lastmod: 2026-11-17
og_description: Hur man skapar PDF417-streckkoder med Aspose.BarCode. Denna handledning
  guidar dig genom de exakta stegen för att skapa en Aspose-streckkod, konfigurera
  Macro PDF417-metadata och spara bilden.
og_image_alt: Screenshot of a PDF417 barcode generated with Aspose.BarCode in C#
og_title: Hur man skapar PDF417‑streckkoder med Aspose.BarCode – komplett C#‑guide
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: How to create PDF417 barcodes using Aspose.BarCode – step‑by‑step guide
    that also shows how to create barcode aspose in C#.
  headline: How to create PDF417 barcodes with Aspose.BarCode in C#
  type: TechArticle
- description: How to create PDF417 barcodes using Aspose.BarCode – step‑by‑step guide
    that also shows how to create barcode aspose in C#.
  name: How to create PDF417 barcodes with Aspose.BarCode in C#
  steps:
  - name: Set up the project and import Aspose.BarCode
    text: 'Create a new console project and add the Aspose.BarCode NuGet package:'
  - name: Initialise the `BarcodeGenerator` for Macro PDF417
    text: The `BarcodeGenerator` constructor takes the barcode type and the text you
      want to encode. For Macro PDF417 you use `EncodeTypes.MacroPdf417`.
  - name: Configure appearance and Macro PDF417 metadata
    text: Configure appearance and Macro PDF417 metadata
  - name: Save the barcode image
    text: '```csharp // Choose the output folder (ensure it exists) and save as PNG.
      string outputPath = "MacroPdf417.png"; generator.Save(outputPath, BarCodeImageFormat.Png);
      Console.WriteLine($"PDF417 barcode saved to {outputPath}"); } ```'
  - name: Full, runnable example
    text: 'Putting everything together, here’s the complete program you can compile
      and run immediately:'
  type: HowTo
tags:
- barcode
- pdf417
- aspose
- csharp
title: Hur man skapar PDF417‑streckkoder med Aspose.BarCode i C#
url: /sv/net/compact-pdf417-encoding/how-to-create-pdf417-barcodes-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar PDF417‑streckkoder med Aspose.BarCode i C#

Om du behöver **skapa PDF417**‑streckkoder för lager, frakt eller dokumentspårning, visar den här guiden de exakta stegen med Aspose.BarCode. Du får se hur du skapar en streckkod, konfigurerar Macro PDF417‑fält och exporterar resultatet som en PNG‑bild – allt i ett enda körbart C#‑program.

Att skapa en PDF417‑streckkod är vanligt när du måste koda stora mängder data i ett kompakt, maskinläsbart format. Aspose.BarCode gör processen enkel och låter dig finjustera dimensioner, kolumner och hela Macro PDF417‑metadatauppsättningen. I slutet av den här handledningen har du ett komplett, fristående exempel som du kan lägga in i vilket .NET‑projekt som helst.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare (koden fungerar också med .NET Framework 4.7+).
* En giltig Aspose.BarCode‑licens för .NET (den fria utvärderingen fungerar för testning).
* Visual Studio 2022, VS Code eller någon annan C#‑kompatibel IDE.
* Grundläggande kunskap om C#‑syntax och `using`‑satsen.

> **Proffstips:** Om du kör exemplet utan licens kommer Aspose att lägga till ett litet vattenmärke på den genererade bilden.

## Hur man skapar PDF417‑streckkod med Aspose.BarCode

Följande avsnitt delar upp implementeringen i fyra tydliga steg. Varje steg innehåller ett kodexempel, en förklaring till **varför** koden behövs, samt praktiska tips du kan använda i dina egna projekt.

### Steg 1: Ställ in projektet och importera Aspose.BarCode

Skapa ett nytt konsolprojekt och lägg till Aspose.BarCode NuGet‑paketet:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Öppna sedan `Program.cs` och lägg till de nödvändiga namnutrymmena:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

*Varför detta är viktigt:* Att importera `Aspose.BarCode.Generation` ger dig tillgång till `BarcodeGenerator` och `EncodeTypes`‑enumerationen, som är kärnklasserna för streckkodsgenerering.

### Steg 2: Initiera `BarcodeGenerator` för Macro PDF417

Konstruktorn för `BarcodeGenerator` tar streckkodstypen och den text du vill koda. För Macro PDF417 använder du `EncodeTypes.MacroPdf417`.

```csharp
// Initialise a Macro PDF417 generator with the data you want to encode.
using (BarcodeGenerator generator = 
       new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text for PDF417"))
{
    // The generator instance will be disposed automatically at the end of the block.
```

*Varför detta är viktigt:* `using`‑satsen säkerställer att ohanterade resurser (som GDI+‑handtag) frigörs omedelbart, vilket förhindrar minnesläckor i långvariga tjänster.

### Steg 3: Konfigurera utseende och Macro PDF417‑metadata

#### 3.1 Justera visuella parametrar

```csharp
    // Set the module (X) dimension – 2 pixels gives a reasonably dense barcode.
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Define the number of columns; fewer columns make the barcode taller.
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

#### 3.2 Fyll i Macro PDF417‑fält

Macro PDF417 låter dig dela upp ett stort dokument i flera streckkodsegment. Fälten nedan är valfria men ofta nödvändiga för logistik- eller dokumenthanteringssystem.

```csharp
    // Unique identifier for the whole file (must be the same across all segments).
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Segment index (starting at 1). Here we generate the 12th segment.
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that will be produced.
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Human‑readable file name, useful for audits.
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // CCITT‑16 checksum – helps receivers verify data integrity.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate file size in bytes; some scanners use this for validation.
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

    // Timestamp of the original file creation.
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2024, 5, 1);

    // Optional address fields that can be read by advanced scanners.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator tells the scanner that this is the last segment.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;
```

*Varför dessa fält är användbara:*  
* **FileID** binder alla segment tillsammans och möjliggör återuppbyggnad.  
* **SegmentID** och **SegmentsCount** låter läsaren veta i vilken ordning segmenten ska läsas och när serien är komplett.  
* **Checksum** och **FileSize** ger snabba integritetskontroller utan att behöva avkoda hela nyttolasten.

> **Observera:** `MacroPdf417FileID` måste vara unik per logiskt dokument. Att återanvända samma ID för orelaterade filer kan orsaka fel vid återuppbyggnad.

### Steg 4: Spara streckkodsbilden

```csharp
    // Choose the output folder (ensure it exists) and save as PNG.
    string outputPath = "MacroPdf417.png";
    generator.Save(outputPath, BarCodeImageFormat.Png);
    Console.WriteLine($"PDF417 barcode saved to {outputPath}");
}
```

*Varför PNG?* PNG bevarar exakt pixeldata utan komprimeringsartefakter, vilket är idealiskt för streckkodsläsare som förlitar sig på skarpa kanter.

### Fullständigt, körbart exempel

När allt har satts ihop, här är det kompletta programmet som du kan kompilera och köra omedelbart:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1‑4: generate a Macro PDF417 barcode and save it as PNG
            using (BarcodeGenerator generator = 
                   new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text for PDF417"))
            {
                // Appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // Macro PDF417 metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
                    new DateTime(2024, 5, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
                    Pdf417MacroTerminator.Set;

                // Save
                string outputPath = "MacroPdf417.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"PDF417 barcode saved to {outputPath}");
            }
        }
    }
}
```

**Förväntad output:** Efter att ha kört programmet hittar du `MacroPdf417.png` i projektmappen. När du öppnar bilden visas en tät, högkontrast PDF417‑streckkod som kodar “Sample text for PDF417” tillsammans med den macro‑metadata du angav.

## Vanliga frågor och hantering av kantfall

| Fråga | Svar |
|-------|------|
| *Kan jag generera flera segment i en loop?* | Ja. Öka `MacroPdf417SegmentID` för varje iteration, håll `MacroPdf417FileID` konstant och uppdatera `MacroPdf417SegmentsCount` först när du känner till det totala antalet segment. |
| *Vad händer om data överskrider en enda PDF417‑symbol?* | Macro |

## Vad bör du lära dig härnäst?

De följande handledningarna täcker närliggande ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar macro PDF417‑streckkod i C# med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Hur man skapar en micro PDF417‑streckkod i C# med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/)
- [Hur man skapar streckkod – Compact PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}