---
category: general
date: 2026-08-09
description: Skapa streckkodsbilder med en C#‑streckkodsgenerator och lär dig att
  generera flera streckkoder med anpassade bildförhållanden på några minuter.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- c# barcode generator
- generate multiple barcodes
- barcode aspect ratio
- barcode image format
language: sv
lastmod: 2026-08-09
og_description: Skapa streckkodbild med en C#‑streckkodsgenerator. Denna handledning
  visar hur du genererar flera streckkoder, justerar bildförhållanden och sparar PNG‑filer
  effektivt.
og_image_alt: Example of create barcode image output with aspect ratios 15 and 30
  using C# barcode generator
og_title: Skapa streckkodbild med C#-streckkodsgenerator – snabbguide
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create barcode image with a C# barcode generator and learn to generate
    multiple barcodes with custom aspect ratios in minutes.
  headline: Create barcode image with C# barcode generator – guide
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: Skapa streckkodbild med C#-streckkodsgenerator – guide
url: /sv/python-java/general/create-barcode-image-with-c-barcode-generator-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa streckkodbild med C# streckkodsgenerator – guide

Om du snabbt behöver **skapa streckkodbild**, visar den här guiden hur du gör det med en C# streckkodsgenerator. Du kommer att lära dig att generera flera streckkoder, ändra bildförhållandet och spara varje bild som en PNG‑fil.

Att generera streckkodsbilder är en vanlig uppgift när man bygger lagersystem, kassaterminaler eller fraktetiketter. I slutet av den här handledningen kommer du att ha två färdiga PNG‑filer som demonstrerar olika bildförhållanden, och du kommer att förstå hur du kan utöka metoden till valfritt antal streckkoder.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare installerat  
* Visual Studio 2022 (eller någon IDE som stödjer C#)  
* En referens till ett streckkodsbibliotek som stödjer DataBar Stacked Omnidirectional (till exempel **Aspose.BarCode for .NET**). Kodsnuttarna använder Aspose‑API:t, men koncepten gäller för alla bibliotek med liknande egenskaper.

Du behöver ingen separat databas eller webbserver—detta är en enkel konsolapplikation.

## Steg 1: Ställ in konsolprojektet

Skapa ett nytt konsolprojekt och lägg till streckkodsbiblioteket via NuGet.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

`dotnet add package`‑kommandot hämtar den senaste stabila versionen av **Aspose.BarCode**, som tillhandahåller klassen `BarcodeGenerator` som används senare.

## Steg 2: Skriv hela programmet

Öppna *Program.cs* och ersätt dess innehåll med det kompletta exemplet nedan. Programmet skapar en **streckkodbild**, ändrar bildförhållandet och sparar två PNG‑filer.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // -----------------------------------------------------------------
            // 1️⃣ Create a DataBar Stacked Omnidirectional generator with sample data
            // -----------------------------------------------------------------
            // The EncodeTypes enum tells the generator which barcode symbology to use.
            // Here we use DataBar Stacked Omnidirectional (GS1 DataBar) and encode
            // a sample GTIN (01) followed by a 14‑digit numeric string.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // -----------------------------------------------------------------
            // 2️⃣ Configure common parameters (pixel size and X‑dimension)
            // -----------------------------------------------------------------
            // XDimension.Pixels controls the width of the smallest bar in the image.
            // A value of 2 gives a clear, high‑resolution output without increasing file size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // -----------------------------------------------------------------
            // 3️⃣ Set the first aspect ratio (15) and save the image
            // -----------------------------------------------------------------
            // AspectRatio influences the height of the barcode relative to its width.
            // An aspect ratio of 15 is typical for compact labels.
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;

            string outputFolder = "BarcodeOutputs/";
            System.IO.Directory.CreateDirectory(outputFolder); // Ensure folder exists

            string file15 = $"{outputFolder}DatabarAspectRatio15.png";
            generator.Save(file15, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with aspect ratio 15 → {file15}");

            // -----------------------------------------------------------------
            // 4️⃣ Change the aspect ratio to 30 and save a second image
            // -----------------------------------------------------------------
            // A larger aspect ratio (e.g., 30) produces a taller barcode, useful for
            // scanning devices that expect more vertical space.
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;

            string file30 = $"{outputFolder}DatabarAspectRatio30.png";
            generator.Save(file30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with aspect ratio 30 → {file30}");

            // -----------------------------------------------------------------
            // 5️⃣ Verify that both files exist
            // -----------------------------------------------------------------
            Console.WriteLine("\nVerification:");
            Console.WriteLine($"File 15 exists: {System.IO.File.Exists(file15)}");
            Console.WriteLine($"File 30 exists: {System.IO.File.Exists(file30)}");
        }
    }
}
```

### Varför varje del är viktig

* **Create barcode image** – `BarcodeGenerator`‑konstruktorn initierar objektet med den önskade symbologin och datan.  
* **c# barcode generator** – `Parameters`‑egenskapen ger dig full kontroll över renderingsalternativ; att sätta `XDimension.Pixels` säkerställer att varje stapel är skarp på skärmen.  
* **generate multiple barcodes** – Genom att ändra `DataBar.AspectRatio` mellan sparningar producerar samma generatorinstans två olika bilder utan att återskapa objektet, vilket är mer effektivt.

## Steg 3: Kör programmet och visa resultaten

Kör applikationen:

```bash
dotnet run
```

Du bör se konsolutdata liknande:

```
Saved barcode with aspect ratio 15 → BarcodeOutputs/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 → BarcodeOutputs/DatabarAspectRatio30.png

Verification:
File 15 exists: True
File 30 exists: True
```

Öppna mappen `BarcodeOutputs`. Du kommer att hitta två PNG‑filer:

* **DatabarAspectRatio15.png** – en kompakt streckkod lämplig för etiketter med begränsad höjd.  
* **DatabarAspectRatio30.png** – en högre streckkod som många skannrar läser mer pålitligt på avstånd.

Båda bilderna är klara att bäddas in i PDF‑filer, skrivas ut på kvitton eller skickas till en mobilapp.

## Steg 4: Utöka lösningen för att generera valfritt antal streckkoder

Mönstret som visas ovan skalar enkelt:

```csharp
int[] ratios = { 10, 15, 20, 30, 40 };
foreach (int ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    string path = $"{outputFolder}DatabarAspectRatio{ratio}.png";
    generator.Save(path, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved aspect ratio {ratio} → {path}");
}
```

* **generate multiple barcodes** – Loopen itererar över en array av bildförhållanden och skapar en distinkt **barcode image** för varje värde.  
* Justera `EncodeTypes` eller den kodade strängen för att producera QR‑koder, Code 128 eller andra symbologier utan att ändra den omgivande logiken.

## Praktiska tips och vanliga fallgropar

| Tip | Explanation |
|-----|-------------|
| **Reuse the same generator** | Att återinitiera `BarcodeGenerator` för varje bild lägger till onödig overhead. Att ändra parametrar mellan `Save`‑anrop är snabbare och använder mindre minne. |
| **Validate the output folder** | Anropa alltid `Directory.CreateDirectory` innan du sparar; annars kastar `Save` ett `DirectoryNotFoundException`. |
| **Choose an appropriate X‑dimension** | Mycket låga pixelvärden (t.ex. 1) kan göra streckkoden oläslig på lågupplösta skärmar. Värden på 2–3 fungerar bra för de flesta skrivare. |
| **Mind the encoding** | GS1 DataBar förväntar sig en inledande `(01)` för GTIN. Om du utelämnar parenteserna kan biblioteket generera en ogiltig streckkod. |
| **Test with a real scanner** | Visuell inspektion räcker inte. Testa PNG‑filerna med den faktiska skannerutrustning du planerar att använda. |

## Förväntat resultat (visuell beskrivning)

*Båda PNG‑filerna visar en mörk‑på‑ljus DataBar Stacked Omnidirectional‑streckkod. Versionen med bildförhållande 15 är kortare, medan versionen med bildförhållande 30 är ungefär dubbelt så hög.*  

Om du bäddar in bilderna i ett dokument kommer de att renderas skarpt eftersom vi satte `XDimension.Pixels = 2`.

## Slutsats

Du vet nu hur du **skapar streckkodbild**‑filer med en **C# streckkodsgenerator**, och du kan **generera flera streckkoder** genom att justera bildförhållandet eller någon annan parameter. Det kompletta, körbara exemplet visar bästa praxis såsom att återanvända generatorinstansen, hantera utdatamappar och verifiera filskapande.

Nästa steg kan vara att utforska:

* Lägga till anpassade färger med `generator.Parameters.Barcode.Color` (sekundärt nyckelord: **c# barcode generator**)  
* Exportera till andra format som JPEG eller SVG (`BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Svg`)  
* Integrera streckkodsskapande logik i ett Web API för att leverera bilder på begäran (sekundärt nyckelord

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Skapa streckkod PNG – DataMatrix Bildförhållande – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [barcode generator tutorial c# – Anpassa Code 16K streckkod bildförhållanden med Aspose.BarCode för .NET](/barcode/english/net/code-16k-encoding/code-16k-aspect-ratio-customization/)
- [Hur man genererar Aztec‑streckkod med anpassat bildförhållande med Aspose.BarCode för .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}