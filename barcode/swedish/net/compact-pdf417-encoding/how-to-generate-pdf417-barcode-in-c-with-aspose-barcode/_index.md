---
category: general
date: 2026-11-27
description: Lär dig hur du genererar PDF417‑streckkod i C# med Aspose.BarCode. Justera
  dimensioner, ange kolumnantal och spara som PNG på några rader kod.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode C#
- PDF417 barcode dimensions
- barcode image PNG
- BarcodeGenerator usage
language: sv
lastmod: 2026-11-27
og_description: Generera PDF417-streckkod i C# omedelbart. Denna handledning visar
  hur du konfigurerar dimensioner, kolumnantal och sparar resultatet som en PNG-bild.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: Generera PDF417‑streckkod i C# – snabb guide med Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  headline: How to generate PDF417 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  name: How to generate PDF417 barcode in C# with Aspose.BarCode
  steps:
  - name: Why each line matters
    text: '* **BarcodeGenerator** – the core class that creates a barcode image. Passing
      `EncodeTypes.Pdf417` selects the PDF417 symbology. * **XDimension.Pixels** –
      determines the smallest bar width. Smaller values shrink the image; larger values
      improve readability on low‑resolution scanners. * **Pdf417.Colu'
  - name: Changing the encoded data
    text: 'Replace the second argument of `BarcodeGenerator` with any UTF‑8 string,
      e.g.:'
  - name: Adjusting image size without losing quality
    text: 'If you need a larger image for printing, increase `XDimension.Pixels`:'
  - name: Handling very long inputs
    text: 'PDF417 can encode up to 1 850 characters. For extremely long strings, you
      may want to increase the column count:'
  - name: Saving in other formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the format like
      this:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Hur man genererar PDF417‑streckkod i C# med Aspose.BarCode
url: /sv/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så genererar du PDF417-streckkod i C# med Aspose.BarCode

Om du behöver **generera PDF417-streckkod** i en .NET-applikation visar den här guiden en kortfattad, end‑to‑end‑lösning. Du kommer att se hur du skapar streckkoden, finjusterar dess storlek och skriver resultatet till en PNG‑fil — allt med Aspose.BarCode‑biblioteket.

Att generera en PDF417-streckkod är vanligt när du måste koda stora mängder data för skanning på mobila enheter, boardingkort eller lageretiketter. I slutet av den här handledningen har du ett färdigt konsolprogram som producerar en högkvalitativ PNG‑bild.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare installerat  
* En aktuell version av **Aspose.BarCode for .NET** (NuGet‑paketet `Aspose.BarCode`)  
* En IDE eller editor (Visual Studio, VS Code, Rider, etc.)  

Koden fungerar på Windows, Linux och macOS eftersom Aspose.BarCode är plattformsoberoende.

## Steg 1: Skapa ett nytt konsolprojekt

Öppna en terminal och kör:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Detta skapar ett minimalt C#‑projekt med namnet **Pdf417Demo** och lägger till beroendet `Aspose.BarCode`.

## Steg 2: Skriv koden för streckkodsgenerering

Öppna **Program.cs** och ersätt dess innehåll med följande:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Create a PDF417 barcode generator with the desired text
            // EncodeTypes.Pdf417 tells Aspose.BarCode which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417, "Sample text for PDF417 barcode");

            // 2️⃣ Adjust barcode dimensions and column count
            // XDimension controls the width of a single module (pixel size).
            // Setting it to 2 pixels yields a compact yet readable barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Columns define how many data columns the barcode will have.
            // A value of 3 works well for short strings; increase for longer data.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Optional: increase error correction level for more robust scanning.
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 2;

            // 3️⃣ Save the generated barcode as a PNG file
            // The output path can be absolute or relative to the project folder.
            string outputPath = "Pdf417Basic.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to '{outputPath}'.");
        }
    }
}
```

### Varför varje rad är viktig

* **BarcodeGenerator** – kärnklassen som skapar en streckkodsbild. Att skicka `EncodeTypes.Pdf417` väljer PDF417‑symbologin.  
* **XDimension.Pixels** – bestämmer den minsta stapelbredden. Mindre värden minskar bilden; större värden förbättrar läsbarheten på lågupplösta skannrar.  
* **Pdf417.Columns** – styr antalet datakolumner. Fler kolumner ger en kortare men högre streckkod; färre kolumner gör den bredare.  
* **ErrorCorrectionLevel** – högre nivåer lägger till redundanta data, vilket gör streckkoden tolerant mot skador på bekostnad av storlek.  
* **Save(..., BarCodeImageFormat.Png)** – skriver bilden till disk i PNG‑format, ett förlustfritt format som är idealiskt för vidare bearbetning eller inbäddning i dokument.

## Steg 3: Bygg och kör programmet

Från terminalen, kör:

```bash
dotnet run
```

Du bör se:

```
PDF417 barcode saved to 'Pdf417Basic.png'.
```

En fil med namnet **Pdf417Basic.png** visas i projektmappen. När du öppnar den visas en tydlig PDF417‑streckkod som kodar texten *“Sample text for PDF417 barcode”*.

![Genererad PDF417-streckkod sparad som en PNG‑fil](pdf417-barcode-example.png "Genererad PDF417-streckkod i PNG-format")

*Bildtext: skärmdump av en genererad PDF417‑streckkod sparad som en PNG‑fil, som demonstrerar resultatet av handledningen för att generera PDF417‑streckkod.*

## Steg 4: Vanliga variationer och kantfall

### Ändra den kodade datan

Ersätt det andra argumentet till `BarcodeGenerator` med någon UTF‑8‑sträng, t.ex.:

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "https://example.com/checkout?order=12345")
```

Generatorn delar automatiskt upp datan över rader och kolumner.

### Justera bildstorlek utan att förlora kvalitet

Om du behöver en större bild för utskrift, öka `XDimension.Pixels`:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // double the module width
```

### Hantera mycket långa indata

PDF417 kan koda upp till 1 850 tecken. För extremt långa strängar kan du vilja öka kolumnantalet:

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 5; // more columns, less height
```

Om innehållet överskrider den maximala kapaciteten kastar Aspose.BarCode ett `ArgumentException`. Omslut genereringskoden i ett try‑catch‑block för att visa ett vänligt felmeddelande.

### Spara i andra format

Aspose.BarCode stödjer BMP, JPEG, TIFF och SVG. Ändra formatet så här:

```csharp
generator.Save("Pdf417Vector.svg", BarCodeImageFormat.Svg);
```

## Steg 5: Verifiera streckkoden

Du kan bekräfta att streckkoden är giltig genom att skanna den med någon PDF417‑läsarapp (t.ex. smartphone‑kamerappar som stödjer streckkodsskanning). Den avkodade texten bör matcha strängen du skickade till generatorn.

Om skanningen misslyckas:

* Se till att bilden inte är komprimerad (använd PNG eller förlustfri SVG).  
* Verifiera att `ErrorCorrectionLevel` är tillräckligt hög för den avsedda miljön.  
* Kontrollera att streckkodens dimensioner är lämpliga för skannarens upplösning.

## Slutsats

Du vet nu hur du **genererar PDF417-streckkod** i C# med Aspose.BarCode, anpassar dess dimensioner, sätter kolumnantalet och exporterar resultatet som en PNG‑bild. Detta tillvägagångssätt fungerar för ett brett spektrum av scenarier, från mobila biljetter till lagerhantering.

Nästa steg kan du utforska:

* **Läsa** en PDF417‑streckkod med `BarCodeReader`.  
* Generera andra symbologier såsom QR‑kod eller DataMatrix.  
* Bädda in PNG‑filen i PDF‑filer, rapporter eller webbsidor.  

Känn dig fri att experimentera med olika felkorrigeringsnivåer, bildformat och datapayloads för att passa ditt projekts behov. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar PDF417-streckkod i C# med Aspose.BarCode BarcodeGenerator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/)
- [Hur man genererar PDF417-streckkod och renderar den som PNG](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/)
- [Hur man genererar PDF417-streckkod i C# och ställer in streckkodens storlek](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}