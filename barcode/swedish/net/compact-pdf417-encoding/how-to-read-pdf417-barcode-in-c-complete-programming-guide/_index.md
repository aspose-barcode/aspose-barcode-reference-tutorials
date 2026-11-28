---
category: general
date: 2026-11-27
description: hur man läser PDF417‑streckkod i C# från en bild med Aspose.BarCode –
  steg‑för‑steg‑guide med komplett kodexempel och felsökningstips.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode from image c#
- C# barcode decoding
- BarCodeReader class
- DecodeType.MacroPdf417
- BarCodeResult properties
language: sv
lastmod: 2026-11-27
og_description: hur man läser pdf417-streckkod i C# snabbt. Lär dig avkoda PDF417-streckkoder
  från bilder med Aspose.BarCode, komplett kod och bästa praxis.
og_image_alt: Console output showing how to read PDF417 barcode in C#
og_title: Hur man läser PDF417-streckkod i C# – steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: how to read pdf417 barcode in C# from an image using Aspose.BarCode
    – step‑by‑step guide with full code example and troubleshooting tips.
  headline: How to read PDF417 barcode in C# – complete programming guide
  type: TechArticle
- description: how to read pdf417 barcode in C# from an image using Aspose.BarCode
    – step‑by‑step guide with full code example and troubleshooting tips.
  name: How to read PDF417 barcode in C# – complete programming guide
  steps:
  - name: Create a new console project
    text: 'Open a terminal (or PowerShell) and run:'
  - name: Install the Aspose.BarCode NuGet package
    text: 'Aspose.BarCode provides the `BarCodeReader` class used in the example.
      Install it with:'
  - name: Add the code shown above
    text: Replace the content of `Program.cs` with the full snippet from the previous
      section. The code demonstrates **C# barcode decoding** and shows how to access
      **BarCodeResult properties** such as `CodeTypeName`, `CodeText`, and the macro‑specific
      `MacroPdf417FileID`.
  - name: Run the application
    text: '```bash dotnet run ```'
  - name: Handle multiple barcodes and error cases
    text: 'Real‑world images may hold more than one barcode or none at all. Wrap the
      reading logic in a `try`/`catch` block to surface parsing errors, and check
      `reader.HasBarcodes` before iterating:'
  - name: Optional – Decode other barcode types from the same image
    text: 'If you later need to **read barcode from image c#** for other symbologies,
      simply change the `DecodeType` argument:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Hur man läser PDF417-streckkod i C# – komplett programmeringsguide
url: /sv/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man läser PDF417‑streckkod i C# – komplett programmeringsguide

Om du behöver **hur man läser pdf417 streckkod** från en bild, visar den här guiden de exakta stegen. Med Aspose.BarCode för .NET kan du avkoda en PDF417‑streckkod i ett enda metodanrop, och guiden går igenom varje nödvändig rad kod.

Att läsa en streckkod från en bild är en vanlig uppgift när du bygger lagerhanteringsskannrar, biljettsvalideringssystem eller dokumentbehandlingspipelines. I den här tutorialen lär du dig hur du sätter upp miljön, installerar det nödvändiga paketet och skriver ett robust C#‑program som läser en PDF417‑streckkod och extraherar dess utökade datafält. Inga externa tjänster krävs; allt körs lokalt.

> **Förutsättningar**  
> • .NET 6.0 SDK eller senare installerad  
> • Grundläggande kunskaper i C# och konsolapplikationer  
> • Tillgång till en bildfil som innehåller en PDF417 (eller Macro PDF417) streckkod  

Vi kommer också att täcka **read barcode from image c#**‑alternativ, förklara de mest användbara egenskaperna i `BarCodeResult`‑objektet och ge dig tips för att hantera flera streckkoder i en enda bild.

---

## Hur man läser PDF417‑streckkod från en bild i C#

Det första stora steget är att skapa en `BarCodeReader` som pekar på bildfilen och talar om för biblioteket vilken streckkodstyp som ska sökas efter. Genom att specificera `DecodeType.MacroPdf417` begränsar du skanningen till PDF417‑varianter, vilket förbättrar hastighet och precision.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image that contains the PDF417 barcode
            string imagePath = @"C:\Barcodes\Pdf417Sample.png";

            // Initialize the reader for Macro PDF417 barcodes
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate through all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // Macro PDF417 specific extended information
                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID : {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    // Show confidence and symbology details
                    Console.WriteLine($"Code Confidence : {result.CodeTextConfidence}");
                    Console.WriteLine($"Is Mirror Image : {result.IsMirrored}");
                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

**Varför detta fungerar** – `BarCodeReader`‑konstruktorn får bildens sökväg och en `DecodeType`. `MacroPdf417` talar om för motorn att leta efter PDF417‑familjen, inklusive makro‑tillägget som bär extra metadata såsom fil‑ID. Metoden `ReadBarCodes()` returnerar en enumerabel av `BarCodeResult`‑objekt, där varje objekt representerar en upptäckt streckkod.

### Steg 1: Skapa ett nytt konsolprojekt

Öppna en terminal (eller PowerShell) och kör:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Att skapa ett fräscht projekt isolerar demon och garanterar att `csproj`‑filen bara innehåller de beroenden du lägger till härnäst.

### Steg 2: Installera Aspose.BarCode NuGet‑paketet

Aspose.BarCode tillhandahåller klassen `BarCodeReader` som används i exemplet. Installera den med:

```bash
dotnet add package Aspose.BarCode --version 23.12
```

Paketet inkluderar stöd för alla 1D‑ och 2D‑symbologier, inklusive PDF417 och dess makro‑variant.

### Steg 3: Lägg till koden som visas ovan

Ersätt innehållet i `Program.cs` med hela kodsnutten från föregående avsnitt. Koden demonstrerar **C# barcode decoding** och visar hur du får åtkomst till **BarCodeResult properties** såsom `CodeTypeName`, `CodeText` och det makro‑specifika `MacroPdf417FileID`.

### Steg 4: Kör applikationen

```bash
dotnet run
```

Om bilden innehåller en läsbar PDF417‑streckkod kommer konsolen att skriva ut något liknande:

```
Code Type : PDF417
Code Text : https://example.com/invoice/12345
Macro PDF417 File ID : 7
Code Confidence : 98.7
Is Mirror Image : False
----------------------------------------
```

Om bilden inte innehåller någon PDF417‑streckkod avslutas loopen helt enkelt utan att skriva ut något.

### Steg 5: Hantera flera streckkoder och felfall

Verkliga bilder kan innehålla mer än en streckkod eller ingen alls. Omge läslogiken med ett `try`/`catch`‑block för att visa parse‑fel, och kontrollera `reader.HasBarcodes` innan du itererar:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    if (!reader.HasBarcodes)
    {
        Console.WriteLine("No PDF417 barcodes detected.");
        return;
    }

    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // existing processing code...
    }
}
```

**Proffstips:** Justera egenskapen `Resolution` på `BarCodeReader` (t.ex. `reader.Resolution = 300;`) när du arbetar med lågupplösta skanningar. Högre upplösning förbättrar detektering men kan öka CPU‑användning.

### Steg 6: Valfritt – avkoda andra streckkodstyper från samma bild

Om du senare behöver **read barcode from image c#** för andra symbologier, ändra helt enkelt argumentet `DecodeType`:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupportedTypes))
{
    // This will detect QR, Code128, DataMatrix, etc.
}
```

Samma `BarCodeResult`‑klass fungerar för alla typer, så du kan återanvända bearbetningsloopen utan förändring.

---

## Förstå de viktigaste klasserna

| Klass | Syfte | Mest användbara medlemmar |
|-------|-------|----------------------------|
| `BarCodeReader` | Öppnar en bild och skannar efter streckkoder | `ReadBarCodes()`, `HasBarcodes`, `Resolution` |
| `BarCodeResult` | Innehåller information om en enskild upptäckt streckkod | `CodeTypeName`, `CodeText`, `CodeTextConfidence`, `Extended` |
| `Extended.Pdf417` | Tillhandahåller makro‑specifik data för PDF417 | `MacroPdf417FileID`, `MacroPdf417SegmentCount`, `MacroPdf417SegmentIndex` |

Att känna till dessa medlemmar låter dig extrahera inte bara den mänskligt läsbara texten utan också den strukturerade metadata som Macro PDF417 bäddar in, vilket ofta krävs för batch‑behandling av flersidiga dokument.

---

## Vanliga fallgropar och hur man undviker dem

* **Fel `DecodeType`** – Att använda `DecodeType.Pdf417` istället för `MacroPdf417` missar makro‑tillägg. Välj exakt den typ som matchar din streckkod.
* **Ej stödformat för bild** – Aspose.BarCode läser PNG, JPEG, BMP, TIFF och GIF. Om du har en RAW‑bild, konvertera den först.
* **Låg bildkontrast** – Förprocessa bilden (öka kontrast eller binarisera) innan du skickar den till `BarCodeReader`. Biblioteket erbjuder också `reader.ImageProcessingOptions`.
* **Stora filer** – För mycket högupplösta skanningar, sätt `reader.MaxBarcodesPerPage` för att begränsa minnesförbrukning.

---

## Slutsats

Du vet nu **hur man läser pdf417 streckkod** i C# med Aspose.BarCode, från projektuppsättning till hantering av makro‑specifika fält. Det kompletta, körbara exemplet demonstrerar **C# barcode decoding**, visar hur du får åtkomst till **BarCodeResult properties**, och ger dig praktiska tips för robust skanning.  

Nästa steg är att utforska relaterade ämnen såsom **read barcode from image c#** för QR‑koder, integrera streckkodsläsning i ASP.NET Core‑API:er, eller experimentera med batch‑behandling av flera bilder. Samma `BarCodeReader`‑klass fungerar över alla stödjade symbologier, så du kan utöka denna lösning till vilken streckkod din applikation än möter.

Lycka till med kodningen, och anpassa gärna exemplet så att det passar ditt eget arbetsflöde!


## Vad bör du lära dig härnäst?


Följande handledningar täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to read macro PDF417 barcode in C# with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-macro-pdf417-barcode-in-c-with-aspose-barcode/)
- [How to read PDF417 barcode in C# – full barcode reader guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-full-barcode-reader-guide/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}