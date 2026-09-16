---
category: general
date: 2026-07-18
description: Lär dig hur du genererar PDF417‑streckkod med Aspose i C#. Steg‑för‑steg‑guide
  för att skapa streckkod med Aspose och anpassa makroalternativ.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- create barcode with aspose
language: sv
lastmod: 2026-07-18
og_description: Hur man genererar PDF417-streckkod med Aspose i C#. Följ den här guiden
  för att skapa streckkod med Aspose, ställa in makroalternativ och spara som PNG.
og_image_alt: Screenshot showing how to generate PDF417 barcode using Aspose in C#
og_title: Hur man genererar PDF417-streckkod med Aspose – Fullständig handledning
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to generate PDF417 barcode with Aspose in C#. Step‑by‑step
    guide to create barcode with Aspose and customize macro options.
  headline: How to Generate PDF417 Barcode with Aspose – Complete Guide
  type: TechArticle
- description: Learn how to generate PDF417 barcode with Aspose in C#. Step‑by‑step
    guide to create barcode with Aspose and customize macro options.
  name: How to Generate PDF417 Barcode with Aspose – Complete Guide
  steps:
  - name: Why These Settings Matter
    text: '- **Columns** – Controls the barcode''s width; fewer columns = taller barcode.
      - **FileID** – A 32‑bit identifier that ties all macro segments together. -
      **SegmentID / SegmentsCount** – Let the scanner reconstruct the original file
      from multiple barcode pieces. - **FileName, Sender, Addressee** – Op'
  - name: Expected Output
    text: 'Running the program prints:'
  - name: 1. What if I need to embed non‑ASCII text?
    text: Aspose automatically encodes Unicode characters, as demonstrated with `"Åspóse.Barcóde©"`.
      No extra steps are required—just pass the string directly.
  - name: 2. My barcode is too small for a scanner. What can I tweak?
    text: Increase the X dimension (`generator.Parameters.Barcode.XDimension.Pixels`)
      or raise the column count. Both actions enlarge the modules and improve readability.
  - name: 3. Do I have to set every macro field?
    text: No. Only `FileID`, `SegmentID`, and `SegmentsCount` are mandatory for a
      multi‑segment macro. The rest are optional but recommended for enterprise workflows.
  - name: 4. How do I generate multiple segments programmatically?
    text: Loop over your data, increment `MacroPdf417SegmentID` each iteration, keep
      `MacroPdf417FileID` constant, and set `MacroPdf417SegmentsCount` to the total
      number of segments. Save each barcode with a distinct filename.
  type: HowTo
tags:
- PDF417
- Aspose.BarCode
- C#
title: Hur man genererar PDF417-streckkod med Aspose – Komplett guide
url: /sv/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar PDF417-streckkod med Aspose – Komplett guide

Har du någonsin undrat **hur man genererar PDF417**-streckkod med Aspose utan att gräva igenom oändliga API-dokument? Du är inte ensam. Oavsett om du bygger ett biljettsystem, en fraktetikett eller ett säkert dokument, är det en praktisk färdighet för alla .NET‑utvecklare att behärska **hur man genererar PDF417**.

I den här handledningen går vi igenom allt du behöver för att **skapa streckkod med Aspose**, från att installera biblioteket till att finjustera macro‑PDF417‑alternativ och slutligen spara bilden. I slutet har du ett körbart C#‑exempel som du kan klistra in i ditt eget projekt.

## Vad du behöver

- .NET 6.0 eller senare (koden fungerar också på .NET Framework 4.7+)
- Visual Studio 2022 (eller någon annan editor du föredrar)
- En NuGet‑kompatibel internetanslutning för att hämta **Aspose.BarCode**‑paketet
- Grundläggande kunskap om C#‑syntax (ingen djup streckkodsexpertis krävs)

Har du allt? Bra – låt oss dyka in.

## Steg 1: Installera Aspose.BarCode NuGet‑paket

Innan du kan **hur man genererar PDF417**, behöver du Aspose.BarCode‑biblioteket som faktiskt utför det tunga arbetet.

```bash
dotnet add package Aspose.BarCode
```

Den enkla raden hämtar den senaste stabila versionen (för närvarande 23.12). Om du använder Visual Studio kan du också högerklicka på ditt projekt → Manage NuGet Packages → söka efter *Aspose.BarCode* och klicka på Install.

> **Proffstips:** Fäst paketversionen i din `.csproj` för att undvika oavsiktliga brytande förändringar när du uppdaterar senare.

## Steg 2: Skapa en Barcode Generator för PDF417

Nu när biblioteket är på plats, låt oss besvara kärnfrågan: **hur man genererar PDF417**. Den första kodraden skapar en `BarcodeGenerator`‑instans förkonfigurerad för `MacroPdf417`‑symbologi och fyller den med lite exempeltext som innehåller Unicode‑tecken.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 2: Create a barcode generator for Macro PDF417 with the desired text
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417, "Åspóse.Barcóde©");
```

Observera att vi använde typen **MacroPdf417** eftersom den stöder de extra makrofälten som vi kommer att konfigurera senare. Strängen `"Åspóse.Barcóde©"` visar att Aspose hanterar Unicode direkt – ett vanligt fallgropar när folk frågar **hur man genererar PDF417** med specialtecken.

## Steg 3: Definiera grundläggande utseende – X-dimension

Den visuella storleken på en PDF417‑streckkod styrs av modulbredden, även kallad X‑dimension. Att sätta den i pixlar ger dig pixel‑perfekt kontroll över den slutliga bilden.

```csharp
// Step 3: Set the X dimension (module width) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Ett värde på `2` fungerar bra för skärmvisning; öka det till `3` eller `4` om du behöver en större streckkod för utskrift.

## Steg 4: Konfigurera Macro‑PDF417‑alternativ

Här är där handledningen verkligen visar **hur man genererar PDF417** med avancerad makrodatan. Varje egenskap motsvarar ett specifikt fält definierat i PDF417‑specifikationen.

```csharp
// Step 4: Configure PDF417 macro options
generator.Parameters.Barcode.Pdf417.Columns = 4; // number of columns

generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;          // unique file identifier
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;            // segment number
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;       // total segments
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";       // logical file name
generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;          // checksum value
generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;       // file size in bytes
generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
    new DateTime(2019, 11, 1);                                            // timestamp
generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";      // addressee
generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";        // sender
generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
    Pdf417MacroTerminator.Set;                                            // terminator flag
```

### Varför dessa inställningar är viktiga

- **Columns** – Styr streckkodens bredd; färre kolumner = högre streckkod.
- **FileID** – En 32‑bit identifierare som binder alla makrosegment tillsammans.
- **SegmentID / SegmentsCount** – Låter skannern återskapa den ursprungliga filen från flera streckkodsbitar.
- **FileName, Sender, Addressee** – Valfri metadata som många företagsarbetsflöden förlitar sig på.
- **Checksum & FileSize** – Ger integritetskontroller; användbart när streckkoden är en del av ett säkert dokument.
- **TimeStamp** – Användbart för revisionsspår; formatet är en standard `DateTime`.
- **Terminator** – Signalerar slutet på makrosequensen; du sätter nästan alltid den till `Set`.

Om du hoppar över något av dessa fält kommer Aspose fortfarande att generera en giltig PDF417, men du utnyttjar inte hela kraften i makroläget. Det är därför många utvecklare frågar **hur man genererar PDF417** med all valfri data – svaret är exakt dessa rader.

## Steg 5: Spara streckkoden som en bild

Den sista delen av **hur man genererar PDF417** är att spara resultatet. Aspose stöder PNG, JPEG, BMP och många andra format. PNG är förlustfri, vilket gör den idealisk för vidare bearbetning.

```csharp
// Step 5: Save the generated barcode as a PNG image
generator.Save("MacroPdf417Optional.png", BarCodeImageFormat.Png);
```

Efter att den här raden har körts hittar du `MacroPdf417Optional.png` i ditt projekts output‑mapp.

## Fullt fungerande exempel

När vi sätter ihop allt, här är ett fristående program som du kan kopiera och klistra in i en konsolapp:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator with Macro PDF417 symbology
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MacroPdf417, "Åspóse.Barcóde©");

        // 2️⃣ Set visual size
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Macro‑PDF417 specific options
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
        generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
        generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
        generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
        generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
        generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
        generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
        generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
        generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
        generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

        // 4️⃣ Save as PNG
        generator.Save("MacroPdf417Optional.png", BarCodeImageFormat.Png);

        Console.WriteLine("PDF417 barcode generated successfully!");
    }
}
```

### Förväntad output

När programmet körs skrivs:

```
PDF417 barcode generated successfully!
```

…och skapar en PNG som ser ungefär ut så här:

![Hur man genererar PDF417 streckkod exempel](MacroPdf417Optional.png)

*(Bilden ovan är en platshållare; din faktiska streckkod kommer att spegla de data du angav.)*

## Vanliga frågor & edge‑cases

### 1. Vad händer om jag behöver bädda in icke‑ASCII‑text?

Aspose kodar automatiskt Unicode‑tecken, som demonstrerat med `"Åspóse.Barcóde©"`. Inga extra steg krävs – skicka bara strängen direkt.

### 2. Min streckkod är för liten för en scanner. Vad kan jag justera?

Öka X‑dimensionen (`generator.Parameters.Barcode.XDimension.Pixels`) eller höj kolumnantalet. Båda åtgärderna förstorar modulerna och förbättrar läsbarheten.

### 3. Måste jag sätta varje makrofält?

Nej. Endast `FileID`, `SegmentID` och `SegmentsCount` är obligatoriska för ett multi‑segment‑makro. Resten är valfria men rekommenderas för företagsarbetsflöden.

### 4. Hur genererar jag flera segment programatiskt?

Loopa över dina data, öka `MacroPdf417SegmentID` för varje iteration, håll `MacroPdf417FileID` konstant och sätt `MacroPdf417SegmentsCount` till det totala antalet segment. Spara varje streckkod med ett unikt filnamn.

## Proffstips för produktion

- **Cachea generatorn** om du skapar många streckkoder med identiska inställningar; endast `CodeText` behöver ändras.
- **Validera inmatningslängd** – PDF417 kan koda upp till ~1 800 tecken; att överskrida detta kastar ett undantag.
- **Använd `BarCodeImageFormat.Svg`** när du behöver en vektorutgång för skalning utan kvalitetsförlust.
- **Aktivera `QuietZone`** (`generator.Parameters.Barcode.QZ.X =

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar streckkod – Compact PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hur man genererar DataMatrix‑streckkod med Aspose.BarCode för .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Hur man genererar DataMatrix‑streckkoder (ECC 200) med Aspose.BarCode för .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}