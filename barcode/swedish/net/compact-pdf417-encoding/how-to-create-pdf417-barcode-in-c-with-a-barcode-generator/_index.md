---
category: general
date: 2026-11-17
description: Lär dig hur du skapar PDF417‑streckkod i C# – en komplett guide om hur
  du genererar streckkod från en sträng med en C#‑streckkodsgenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode
- c# barcode generator
- generate barcode from string
- create gs1 barcode
language: sv
lastmod: 2026-11-17
og_description: Skapa PDF417‑streckkod i C# snabbt. Den här handledningen visar hur
  du genererar en streckkod från en sträng med en C#‑streckkodsgenerator och inkluderar
  fullständig källkod.
og_image_alt: Screenshot of a generated PDF417 barcode created with a C# barcode generator
og_title: Skapa PDF417‑streckkod i C# – steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  headline: How to create PDF417 barcode in C# with a barcode generator
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  name: How to create PDF417 barcode in C# with a barcode generator
  steps:
  - name: Expected output
    text: '![Generated PDF417 barcode showing the GTIN (01)12345678901234](/images/pdf417-sample.png){:
      .center-image alt="Generated PDF417 barcode created with a C# barcode generator"}'
  - name: Changing the image format
    text: If you prefer JPEG or BMP, just replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`
      or `BarCodeImageFormat.Bmp`. The rest of the code stays identical.
  - name: Adjusting error correction level
    text: PDF417 supports error correction levels 0‑8. Higher levels increase redundancy
      but also enlarge the barcode.
  - name: Generating other GS1 barcodes
    text: 'The same `BarcodeGenerator` can produce **create GS1 barcode** for other
      symbologies, such as `EncodeTypes.Gs1DataMatrix` or `EncodeTypes.Gs1Qr`. Just
      swap the enum value:'
  - name: Handling empty or null data
    text: 'When you **generate barcode from string**, always validate the input:'
  type: HowTo
- questions:
  - answer: Yes. The Aspose.BarCode library targets .NET Standard 2.0, which is compatible
      with .NET Framework 4.6 and later.
    question: Can I use this code on .NET Framework 4.6?
  - answer: 'Set the `Resolution` property before saving: ```csharp generator.Parameters.ImageResolution.DpiX
      = 300; generator.Parameters.ImageResolution.DpiY = 300; ```'
    question: What if I need a higher‑resolution image?
  - answer: 'It will be a standard PDF417 barcode, but it won’t be recognized as a
      GS1‑compliant symbol. Include the `(01)` prefix when you need **create GS1 barcode**
      compliance. ## Conclusion You now know how to **create PDF417 barcode** in C#
      using a robust **c# barcode generator**. The tutorial covered: * In'
    question: Is the barcode still valid without the GS1 Application Identifier?
  type: FAQPage
tags:
- barcode
- C#
- PDF417
- GS1
- code generation
title: Hur man skapar PDF417‑streckkod i C# med en streckkodsgenerator
url: /sv/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar PDF417 barcode i C# med en barcode generator

Om du behöver **create PDF417 barcode** i en .NET-applikation visar den här guiden exakt hur du gör det. Du kommer att lära dig **how to generate barcode** från en vanlig sträng, konfigurera symbolstorleken och spara resultatet som en PNG-fil—allt med en pålitlig C#-barcode generator.

Att generera streckkoder programatiskt tar bort manuella steg och garanterar konsekvent kvalitet. I den här handledningen går vi igenom allt från projektuppsättning till den slutliga bilden, så att du kan integrera streckkodsskapande i vilken C#-lösning som helst idag.

## Förutsättningar

* .NET 6.0 SDK eller senare (koden fungerar med .NET Core och .NET Framework)
* Visual Studio 2022 (eller någon IDE som stödjer C#)
* En licens eller gratis provversion av **Aspose.BarCode for .NET** – biblioteket som används i exemplen
* Grundläggande kunskap om C#-syntax

Inga ytterligare paket krävs; NuGet‑paketet `Aspose.BarCode` innehåller alla klasser du behöver.

## Steg 1 – Ställ in C#-barcode generatorn

Det första du gör när du **create PDF417 barcode** är att instansiera ett `BarcodeGenerator`‑objekt. Detta objekt representerar **c# barcode generator** som kommer att hantera kodning, rendering och sparande.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for PDF417 with the data to encode
        // The data string follows the GS1 Application Identifier (01) for a GTIN
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417, "(01)12345678901234");
```

*Varför detta är viktigt*: `EncodeTypes.Pdf417`‑enumet talar om för biblioteket att använda PDF417‑symbologin, vilket är samma standard som används för ID‑kort och transportetiketter. Strängen `"(01)12345678901234"` är ett **generate barcode from string**‑exempel som också visar hur man **create GS1 barcode**‑data.

## Steg 2 – Konfigurera X‑dimensionen (modulbredd)

X‑dimensionen styr bredden på den minsta stapeln (modulen). Ett vanligt värde för rendering på skärm är 2 pixlar.

```csharp
        // Step 2: Set the X‑dimension (module width) to 2 pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Att explicit sätta X‑dimensionen förhindrar att generatorn använder sitt standardvärde, vilket kan leda till en streckkod som är för liten för vissa skannrar.

## Steg 3 – Definiera antalet kolumner

PDF417 låter dig justera antalet kolumner, vilket påverkar både streckkodens form och datakapacitet. För en kompakt etikett fungerar fyra kolumner bra.

```csharp
        // Step 3: Define the number of columns (e.g., 4) for a compact barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

Om du behöver en högre streckkod, öka kolumnantalet; biblioteket beräknar automatiskt antalet rader som behövs.

## Steg 4 – Spara streckkoden som en bild

Till sist exporterar du streckkoden till en PNG‑fil. PNG bevarar skarpa kanter och stödjer transparens.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("output/Gs1Pdf417.png", BarCodeImageFormat.Png);
    }
}
```

När programmet körs skapas `output/Gs1Pdf417.png`. Öppna filen i någon bildvisare—du kommer att se en ren **PDF417 barcode** som kodar den GS1‑data du angav.

### Förväntat resultat

![Genererad PDF417-streckkod som visar GTIN (01)12345678901234](/images/pdf417-sample.png){: .center-image alt="Genererad PDF417-streckkod skapad med en C#-barcode generator"}

*Bilden ovan visar resultatet av det kompletta kodexemplet. Streckkoden kan skannas av vilken PDF417‑kompatibel läsare som helst.*

## Ytterligare alternativ och vanliga variationer

### Ändra bildformatet

Om du föredrar JPEG eller BMP, byt bara ut `BarCodeImageFormat.Png` mot `BarCodeImageFormat.Jpeg` eller `BarCodeImageFormat.Bmp`. Resten av koden förblir identisk.

### Justera felkorrigeringsnivå

PDF417 stödjer felkorrigeringsnivåer 0‑8. Högre nivåer ökar redundansen men gör också streckkoden större.

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // medium redundancy
```

### Generera andra GS1‑streckkoder

Samma `BarcodeGenerator` kan producera **create GS1 barcode** för andra symbologier, såsom `EncodeTypes.Gs1DataMatrix` eller `EncodeTypes.Gs1Qr`. Byt bara enum‑värdet:

```csharp
BarcodeGenerator gs1Generator = new BarcodeGenerator(
    EncodeTypes.Gs1DataMatrix, "(01)12345678901234");
```

### Hantera tom eller null data

När du **generate barcode from string**, validera alltid indata:

```csharp
string data = GetUserInput();
if (string.IsNullOrWhiteSpace(data))
{
    throw new ArgumentException("Data to encode cannot be null or empty.");
}
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
```

Detta förhindrar körningsfel och säkerställer att streckkoden följer GS1‑formateringsregler.

## Komplett, körbart exempel

Nedan är hela programmet som du kan kopiera‑och‑klistra in i ett nytt konsolprojekt. Det inkluderar alla nödvändiga `using`‑direktiv, mappskapande och felhantering.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Input data – GS1 GTIN with Application Identifier (01)
        const string gs1Data = "(01)12345678901234";

        // Validate input
        if (string.IsNullOrWhiteSpace(gs1Data))
        {
            Console.WriteLine("Error: Barcode data cannot be empty.");
            return;
        }

        // Ensure output directory exists
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);

        // Create the generator for PDF417 (GS1 optional)
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417, gs1Data);

        // Configure appearance
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
        generator.Parameters.Barcode.Pdf417.Columns = 4;    // compact layout
        generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // optional

        // Save as PNG
        string outputPath = Path.Combine(outputDir, "Gs1Pdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

**Kör programmet** (`dotnet run`) och du hittar `Gs1Pdf417.png` i *output*-mappen. Skanna den med någon PDF417‑läsare för att verifiera att GTIN `(01)12345678901234` är korrekt kodad.

## Vanliga frågor

**Q: Kan jag använda den här koden på .NET Framework 4.6?**  
A: Ja. Aspose.BarCode‑biblioteket riktar sig mot .NET Standard 2.0, vilket är kompatibelt med .NET Framework 4.6 och senare.

**Q: Vad händer om jag behöver en bild med högre upplösning?**  
A: Sätt `Resolution`‑egenskapen innan du sparar:

```csharp
generator.Parameters.ImageResolution.DpiX = 300;
generator.Parameters.ImageResolution.DpiY = 300;
```

**Q: Är streckkoden fortfarande giltig utan GS1‑applikationsidentifieraren?**  
A: Den blir en standard PDF417‑streckkod, men den kommer inte att erkännas som en GS1‑kompatibel symbol. Inkludera `(01)`‑prefixet när du behöver **create GS1 barcode**‑efterlevnad.

## Slutsats

Du vet nu hur man **create PDF417 barcode** i C# med en robust **c# barcode generator**. Handledningen täckte:

* Instansiering av `BarcodeGenerator` med GS1‑data  
* Konfigurering av X‑dimension och kolumnantal  
* Sparande av resultatet som en PNG‑bild  
* Utökning av lösningen med felkorrigering, olika format och indata‑validering  

Med detta fundament kan du generera vilken PDF417‑ eller GS1‑streckkod som helst direkt från en sträng, bädda in den i rapporter eller skicka den till skrivare. Utforska Aspose.BarCode‑API:n för att lägga till färger, marginaler eller kombinera flera streckkoder till en enda bild.

**Nästa steg**: prova att generera en **create GS1 barcode** för DataMatrix, experimentera med dynamiska kolumnberäkningar, eller integrera generatorn i en ASP.NET Core‑webbtjänst som returnerar streckkods­bilder på begäran.

Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar PDF417 barcode i C# – komplett guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-guide/)
- [Hur man skapar micro PDF417 barcode och genererar PNG i C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)
- [Hur man skapar macro PDF417 barcode i C# med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}