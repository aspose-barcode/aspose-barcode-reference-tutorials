---
category: general
date: 2026-10-28
description: Hur man genererar en streckkod med anpassad text med Aspose.BarCode –
  steg‑för‑steg‑guide för .NET‑utvecklare för att skapa streckkodsbilder med Aspose.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- generate barcode custom text
- create barcode aspose
language: sv
lastmod: 2026-10-28
og_description: Hur man genererar streckkod med anpassad text i .NET med Aspose.BarCode.
  Följ den här kompletta guiden för att skapa och spara en Macro PDF417‑streckkod.
og_image_alt: how to generate barcode example PNG image showing a Macro PDF417 barcode
og_title: Hur man genererar streckkod med anpassad text – Aspose.BarCode-handledning
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  headline: How to generate barcode with custom text using Aspose.BarCode for .NET
  type: TechArticle
- description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  name: How to generate barcode with custom text using Aspose.BarCode for .NET
  steps:
  - name: Why each line matters
    text: '* **EncodeTypes.MacroPdf417** – selects the Macro PDF417 symbology, which
      supports segmented data and metadata. * **XDimension.Pixels** – controls the
      size of each module; a value of 2 pixels yields a clear, scannable image. *
      **Pdf417.Columns** – reduces the overall width, making the barcode more c'
  - name: Using a different barcode type
    text: If you need to **generate barcode custom text** for a QR code instead of
      Macro PDF417, replace `EncodeTypes.MacroPdf417` with `EncodeTypes.QR`. The rest
      of the parameter structure stays the same, but QR codes do not support Macro
      metadata fields.
  - name: Handling Unicode characters
    text: The example already includes Unicode characters (`Å`, `ó`, `©`). Aspose.BarCode
      handles UTF‑8 input out of the box, but you should ensure the source file is
      saved with UTF‑8 encoding to avoid compile‑time warnings.
  - name: Saving to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG in addition to PNG. Change
      the `BarCodeImageFormat` enum value accordingly:'
  - name: Large data sets
    text: Macro PDF417 can split data across multiple segments. When the text exceeds
      the capacity of a single segment, increment `MacroPdf417SegmentID` and keep
      `MacroPdf417SegmentsCount` consistent across all generated parts. This approach
      is essential for **create barcode aspose** scenarios where the paylo
  - name: Error handling
    text: 'Wrap the generation logic in a try‑catch block to surface runtime issues
      such as invalid file paths or unsupported characters:'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- .NET
title: Hur man genererar streckkod med anpassad text med Aspose.BarCode för .NET
url: /sv/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så här genererar du en streckkod med anpassad text med Aspose.BarCode för .NET

Att generera en streckkod med anpassad text är ett vanligt krav när du behöver bädda in identifierare, tidsstämplar eller annan metadata direkt i en visuell kod. Denna handledning visar hur du genererar en Macro PDF417‑streckkod som innehåller anpassad text och en komplett uppsättning metadata, med hjälp av **Aspose.BarCode**‑biblioteket för .NET.

Du kommer att lära dig hur du konfigurerar generatorn, applicerar anpassad text, ställer in Macro PDF417‑specifika fält och sparar resultatet som en PNG‑bild. Inga externa verktyg krävs – bara Aspose.BarCode‑NuGet‑paketet och en .NET‑utvecklingsmiljö.

## Förutsättningar

* .NET 6.0 SDK eller senare installerat  
* Visual Studio 2022 (eller någon IDE som stödjer .NET)  
* **Aspose.BarCode för .NET** NuGet‑paket (`Install-Package Aspose.BarCode`)  

Dessa förutsättningar säkerställer att koden kompileras och körs utan ytterligare konfiguration.

## Steg 1: Installera Aspose.BarCode‑paketet

Öppna en terminal i din projektmapp och kör:

```bash
dotnet add package Aspose.BarCode
```

Kommandot lägger till den senaste stabila versionen av Aspose.BarCode i ditt projekt, vilket ger dig åtkomst till klassen `BarcodeGenerator` och alla relaterade parametrar.

## Steg 2: Skapa en ny konsolapplikation

Skapa en minimal konsolapp som kommer att innehålla logiken för streckkodsgenerering:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The full barcode generation flow is encapsulated in a separate method
            GenerateMacroPdf417Barcode();
        }

        /// <summary>
        /// Generates a Macro PDF417 barcode with custom text and metadata, then saves it as PNG.
        /// </summary>
        private static void GenerateMacroPdf417Barcode()
        {
            // Step 1: Instantiate the generator with the desired encode type and data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the visual appearance of the barcode
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // Size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;            // Number of columns in the symbol

                // Step 3: Populate Macro PDF417 specific metadata fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example value
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the barcode image to disk
                string outputPath = @"ExtPDF417Meta.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

### Varför varje rad är viktig

* **EncodeTypes.MacroPdf417** – väljer Macro PDF417‑symbologi, som stödjer segmenterad data och metadata.  
* **XDimension.Pixels** – styr storleken på varje modul; ett värde på 2 pixlar ger en klar, skannbar bild.  
* **Pdf417.Columns** – minskar den totala bredden, vilket gör streckkoden mer kompakt för utskrivna etiketter.  
* **MacroPdf417* properties** – bäddar in filnivåinformation (ID, segmentantal, tidsstämplar osv.) direkt i streckkoden. Denna funktion är unik för Macro PDF417 och används ofta i logistik‑ eller dokumenthanteringssystem.  
* **Save(..., BarCodeImageFormat.Png)** – skriver en förlustfri PNG‑fil och bevarar streckkodens skarpa kanter för pålitlig skanning.

## Steg 3: Kör programmet och verifiera resultatet

Bygg och kör konsolappen:

```bash
dotnet run
```

Programmet skapar `ExtPDF417Meta.png` i projektets arbetskatalog. När du öppnar filen visas en Macro PDF417‑streckkod som kodar texten **“Åspóse.Barcóde©”** tillsammans med den metadata du angav.

**Förväntat resultat** – en PNG‑bild liknande den som visas nedan:

![exempel på utdata för hur man genererar streckkod PNG‑bild som visar en Macro PDF417‑streckkod](ExtPDF417Meta.png)

*Bildens alt‑text (“exempel på utdata för hur man genererar streckkod PNG‑bild”) förstärker huvudnyckelordet för tillgänglighet och SEO.*

## Vanliga variationer och kantfall

### Använda en annan streckkodstyp

Om du behöver **generera streckkod med anpassad text** för en QR‑kod istället för Macro PDF417, ersätt `EncodeTypes.MacroPdf417` med `EncodeTypes.QR`. Resten av parameterstrukturen förblir densamma, men QR‑koder stödjer inte Macro‑metadatafält.

### Hantera Unicode‑tecken

Exemplet innehåller redan Unicode‑tecken (`Å`, `ó`, `©`). Aspose.BarCode hanterar UTF‑8‑inmatning direkt, men du bör säkerställa att källfilen sparas med UTF‑8‑kodning för att undvika kompileringstidvarningar.

### Spara till andra bildformat

Aspose.BarCode stödjer BMP, JPEG, TIFF och SVG utöver PNG. Ändra `BarCodeImageFormat`‑enum‑värdet därefter:

```csharp
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

### Stora datamängder

Macro PDF417 kan dela upp data över flera segment. När texten överskrider kapaciteten för ett enda segment, öka `MacroPdf417SegmentID` och håll `MacroPdf417SegmentsCount` konsekvent över alla genererade delar. Detta tillvägagångssätt är avgörande för **create barcode aspose**‑scenarier där nyttolasten är större än vad en enskild streckkod kan rymma.

### Felhantering

Omge genereringslogiken med ett try‑catch‑block för att visa körningsfel såsom ogiltiga filsökvägar eller tecken som inte stöds:

```csharp
try
{
    GenerateMacroPdf417Barcode();
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Barcode generation failed: {ex.Message}");
}
```

## Pro‑tips för pålitlig streckkodsgenerering

* **Validera streckkoden** efter skapandet med `BarCodeReader`. Detta extra steg bekräftar att den kodade datan matchar dina förväntningar.

  ```csharp
  using (BarCodeReader reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
  {
      if (reader.Read())
          Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
  }
  ```

* **Håll X‑dimensionen mellan 2 – 4 pixlar** för de flesta skannrar. Mindre värden kan ge oläsliga bilder på lågupplösta enheter.

* **Undvik mycket långa filnamn** i `MacroPdf417FileName`. Specifikationen begränsar fältet till 32 tecken.

* **Använd konsekventa tidsstämplar** (UTC) när du genererar flera segment för att förenkla efterföljande bearbetning.

## Slutsats

Du vet nu **hur du genererar streckkod** med anpassad text med Aspose.BarCode för .NET, hur du konfigurerar Macro PDF417‑metadata och hur du sparar resultatet som en PNG‑bild. Det kompletta, körbara exemplet demonstrerar varje nödvändigt steg – från installation av NuGet‑paketet till hantering av Unicode‑tecken och sparande av utdata.

Från detta kan du:

* **Generera streckkod med anpassad text** för andra symbologier (QR, DataMatrix, etc.)  
* **Skapa barcode Aspose**‑arbetsflöden som batch‑processar tusentals bilder  
* Integrera streckkodsgenereringskoden i ASP.NET Core‑tjänster, Windows‑tjänster eller Azure Functions  

Experimentera med olika parametrar, utforska ytterligare metadatafält och integrera streckkoden i dina dokument‑automatiseringspipelines. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur du skapar PDF417‑streckkod med Aspose – Komplett steg‑för‑steg‑guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Generera streckkod från text med Aspose.BarCode – C#‑guide](/barcode/english/net/one-dimensional-barcode-types/generate-barcode-from-text-using-aspose-barcode-c-guide/)
- [Hur du använder Aspose.BarCode för att skapa DataMatrix‑kodtext i .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}