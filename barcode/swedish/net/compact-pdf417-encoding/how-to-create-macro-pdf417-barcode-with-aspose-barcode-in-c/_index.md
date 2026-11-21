---
category: general
date: 2026-11-20
description: Lär dig hur du skapar macro PDF417‑streckkod i C# med Aspose.BarCode.
  Denna guide täcker metadata, parametrar och sparande av bilden.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- macro PDF417 metadata
- Aspose.BarCode C#
- PDF417 macro parameters
- barcode generator example
language: sv
lastmod: 2026-11-20
og_description: Skapa macro-PDF417-streckkod i C# med Aspose.BarCode. Följ den här
  kompletta handledningen för att ange metadata, konfigurera parametrar och exportera
  en PNG.
og_image_alt: Screenshot of a generated macro PDF417 barcode image
og_title: Skapa macro PDF417‑streckkod i C# – steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  headline: How to create macro PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  name: How to create macro PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: Expected output
    text: 'Running the program prints a confirmation line similar to:'
  - name: What if I need more than 20 segments?
    text: The `MacroPdf417SegmentsCount` property can be set up to `255`. Ensure the
      receiving system can handle the larger segment count, and consider splitting
      the data into a manageable number of symbols.
  - name: How does the checksum affect scanning?
    text: The CCITT‑16 checksum (`MacroPdf417Checksum`) provides an additional error‑checking
      layer. If a scanner detects a mismatch, it will reject the barcode. You can
      omit the checksum if your workflow does not require it.
  - name: Can I generate a PDF417 macro barcode without Aspose?
    text: Yes, other libraries (e.g., ZXing.Net, Dynamsoft) support PDF417, but macro‑specific
      fields are often missing. Aspose.BarCode offers the most complete implementation
      for macro metadata.
  - name: What image formats are supported for saving?
    text: The `Save` method accepts any format defined in `BarCodeImageFormat`, such
      as `Png`, `Jpeg`, `Gif`, `Bmp`, and `Tiff`. Choose a format that matches your
      downstream processing pipeline.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Hur man skapar macro PDF417-streckkod med Aspose.BarCode i C#
url: /sv/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så skapar du macro PDF417 streckkod med Aspose.BarCode i C#

Om du behöver **skapa macro PDF417 streckkod** i en .NET-applikation visar den här handledningen de exakta stegen. Du kommer att se hur du konfigurerar macro‑specifik metadata, justerar visuella inställningar och sparar resultatet som en PNG‑fil.

Att generera en macro PDF417 streckkod är användbart när du vill dela upp en stor datamängd över flera symboler samtidigt som du bevarar en filomfattande identifierare. I exemplet nedan använder vi Aspose.BarCode‑biblioteket, som erbjuder ett flytande API för alla PDF417‑funktioner.

I slutet av den här guiden har du ett färdigt konsolprogram som producerar en streckkodsbild som innehåller fullständig macro‑information.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare installerat.
* Visual Studio 2022 (eller någon IDE som stödjer C#).
* **Aspose.BarCode for .NET** NuGet‑paketet (`Aspose.BarCode`).

Du kan lägga till paketet med följande kommando:

```bash
dotnet add package Aspose.BarCode
```

## Steg 1: Initiera streckkodsgeneratorn för macro PDF417

Det första steget är att skapa en instans av `BarcodeGenerator` med enum‑värdet `EncodeTypes.MacroPdf417`. Detta talar om för biblioteket att behandla streckkoden som en macro PDF417‑symbol.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The generator is now ready for further configuration.
```

*Varför detta är viktigt*: Att välja `MacroPdf417` aktiverar alla macro‑relaterade egenskaper på `Pdf417`‑parameterobjektet.

## Steg 2: Ställ in grundläggande visuell utformning

En läsbar streckkod börjar med lämplig modulstorlek och kolumnantal. `XDimension.Pixels`‑egenskapen styr bredden på en enskild modul, medan `Pdf417.Columns` definierar hur många datakolumner varje rad innehåller.

```csharp
    // Set module width to 2 pixels.
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

    // Use 5 columns per row – a compact layout for this example.
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
```

Att justera dessa värden påverkar både skannerns pålitlighet och bildens storlek.

## Steg 3: Definiera macro‑filidentifieringsdetaljer

Macro PDF417 kräver en filidentifierare, en segmentidentifierare och det totala antalet segment. Dessa tre fält gör det möjligt för en skanner att återmontera den ursprungliga datamängden.

```csharp
    // Unique file identifier for the whole macro file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (starting at 0 or 1 based on your protocol).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the complete file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Optional human‑readable file name.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

Dessa **macro PDF417‑parametrar** är kärnan i macro‑funktionaliteten. Utan dem kan en skanner inte länka ihop symbolerna.

## Steg 4: Lägg till valfri macro‑metadata

Utöver de obligatoriska identifierarna stödjer macro‑formatet ytterligare fält såsom kontrollsumma, filstorlek, tidsstämpel, mottagare, avsändare och en terminator‑flagga. Att tillhandahålla dessa data förbättrar felupptäckt och ger kontext för efterföljande system.

```csharp
    // CCITT‑16 checksum example.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate file size in bytes (helps the receiver allocate buffers).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

    // Timestamp of when the macro file was generated.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the final segment.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Proffstips*: Om ditt arbetsflöde inte behöver ett specifikt fält kan du låta det ha sitt standardvärde. Biblioteket kommer att utelämna motsvarande dataelement från streckkoden.

## Steg 5: Spara streckkodsbilden

Efter att ha konfigurerat alla parametrar, anropa `Save` för att exportera streckkoden. Exemplet sparar PNG‑filen i en användarspecificerad katalog.

```csharp
    // Replace with a valid folder on your machine.
    string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

    // Save as PNG – other formats (Jpeg, Gif, etc.) are also supported.
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

När programmet är klart innehåller `ExtPDF417Meta.png` en macro PDF417‑streckkod som kodar texten `"Åspóse.Barcóde©"` tillsammans med all macro‑metadata.

## Fullständig källkod

Nedan är det kompletta, fristående programmet. Kopiera det till ett nytt konsolprojekt och kör det efter att ha installerat Aspose.BarCode‑NuGet‑paketet.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a macro PDF417 barcode generator.
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Visual appearance.
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

                // Step 3: Core macro identifiers.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Step 4: Optional macro metadata.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 5: Export the image.
                string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Macro PDF417 barcode saved to {outputPath}");
            }
        }
    }
}
```

### Förväntat resultat

När programmet körs skrivs en bekräftelsesats ut som liknar:

```
Macro PDF417 barcode saved to YOUR_DIRECTORY/ExtPDF417Meta.png
```

När PNG‑filen öppnas visas en tät, högkontraststreckkod. Skannar du den med en PDF417‑kompatibel skanner returneras den ursprungliga texten plus alla macro‑fält.

## Vanliga frågor och specialfall

### Vad händer om jag behöver mer än 20 segment?

`MacroPdf417SegmentsCount`‑egenskapen kan sättas upp till `255`. Säkerställ att mottagarsystemet kan hantera det större segmentantalet, och överväg att dela upp data i ett hanterbart antal symboler.

### Hur påverkar kontrollsumman skanningen?

CCITT‑16‑kontrollsumman (`MacroPdf417Checksum`) ger ett extra felkontrolllager. Om en skanner upptäcker en avvikelse kommer den att avvisa streckkoden. Du kan utelämna kontrollsumman om ditt arbetsflöde inte kräver den.

### Kan jag generera en PDF417 macro‑streckkod utan Aspose?

Ja, andra bibliotek (t.ex. ZXing.Net, Dynamsoft) stödjer PDF417, men macro‑specifika fält saknas ofta. Aspose.BarCode erbjuder den mest kompletta implementeringen för macro‑metadata.

### Vilka bildformat stöds för sparande?

`Save`‑metoden accepterar alla format som definieras i `BarCodeImageFormat`, såsom `Png`, `Jpeg`, `Gif`, `Bmp` och `Tiff`. Välj ett format som matchar din efterföljande bearbetningspipeline.

## Slutsats

Du vet nu hur du **skapar macro PDF417 streckkod** i C# med Aspose.BarCode. Handledningen täckte generatorinitialisering, visuella inställningar, macro‑filidentifierare, valfri metadata och bildexport. Med denna grund kan du bädda in macro‑PDFs i lagersystem, dokumentspårning eller vilket scenario som helst som kräver segmenterad datatransmission.

Nästa steg inkluderar att experimentera med olika `XDimension`‑värden för högre upplösning, lägga till justeringar av felkorrigeringsnivå, eller integrera streckkoden i ett webb‑API som returnerar PNG‑strömmen direkt. För relaterade ämnen, se handledningarna om **barcode generator example**, **PDF417 macro parameters**, och **macro PDF417 metadata**‑hantering.

Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Hur man skapar PDF417 streckkodsbild i C# med Macro PDF417‑alternativ](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Läs streckkod från bild C# – komplett guide med Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Hur man skapar PDF417 streckkod med Aspose – komplett steg‑för‑steg‑guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}