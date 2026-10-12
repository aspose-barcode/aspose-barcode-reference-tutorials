---
category: general
date: 2026-09-19
description: Hur man genererar streckkod i C# med en steg‑för‑steg‑guide. Lär dig
  anpassa PDF417‑streckkodinställningar och skapa en streckkodsbild som C#‑utvecklare
  kan använda omedelbart.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- customize pdf417 barcode
- create barcode image c#
language: sv
lastmod: 2026-09-19
og_description: Hur man genererar streckkod i C# med detaljerade instruktioner. Anpassa
  PDF417‑streckkodens parametrar och skapa en streckkodsbild som C#‑projekt kan använda
  idag.
og_image_alt: Screenshot of a generated MicroPDF417 barcode image created with C#
  code
og_title: Hur man genererar streckkod och anpassar PDF417‑streckkod i C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  headline: How to generate barcode and customize PDF417 barcode in C#
  type: TechArticle
- description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  name: How to generate barcode and customize PDF417 barcode in C#
  steps:
  - name: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
    text: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
  - name: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
    text: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
  - name: Increase `ErrorLevel` to improve tolerance.
    text: Increase `ErrorLevel` to improve tolerance.
  type: HowTo
tags:
- barcode
- C#
- pdf417
title: Hur man genererar streckkod och anpassar PDF417‑streckkod i C#
url: /sv/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar streckkod och anpassar PDF417-streckkod i C#

Om du behöver **how to generate barcode** i en .NET-applikation, visar den här handledningen en komplett, färdig‑att‑köra lösning. Du kommer att lära dig hur du anpassar PDF417-streckkodens dimensioner, väljer antalet kolumner och slutligen **create barcode image C#** projekt kan bädda in direkt.

Att generera en streckkod kräver ingen komplex byggpipeline. I slutet av den här guiden kommer du att ha en PNG‑fil som innehåller en MicroPDF417‑streckkod som matchar exakt den storlek och upplösning du behöver.

## Förutsättningar

* .NET 6.0 SDK eller senare (koden fungerar också med .NET Framework 4.6+)
* Visual Studio 2022 (eller någon C#‑redigerare du föredrar)
* Aspose.BarCode för .NET NuGet‑paket – installera med  
  `dotnet add package Aspose.BarCode`

Inga ytterligare externa verktyg krävs.

## Steg 1: Skapa projektet och importera namnrymder

Skapa ett nytt konsolprojekt och lägg till Aspose.BarCode‑referensen.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Öppna `Program.cs` och lägg till de nödvändiga `using`‑direktiven:

```csharp
using System;
using Aspose.BarCode.Generation;   // Provides BarcodeGenerator and EncodeTypes
using Aspose.BarCode;               // Contains BarCodeImageFormat enum
```

Dessa namnrymder exponerar klasserna som låter dig **how to generate barcode** och kontrollera PDF417‑specifika alternativ.

## Steg 2: Initiera MicroPDF417‑generatorn med önskad text

Den första raden skapar en `BarcodeGenerator`‑instans konfigurerad för MicroPDF417‑symbologin. Konstruktorn tar kodningstypen och datasträngen du vill koda.

```csharp
// Step 2: Create a MicroPDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");
```

**Varför detta är viktigt:** MicroPDF417 är en kompakt variant av den fullständiga PDF417‑standarden, idealisk för små etiketter eller mobila skärmar. Att initiera generatorn med rätt `EncodeTypes` säkerställer att biblioteket använder rätt kodningsalgoritm.

## Steg 3: Anpassa X‑dimensionen (modulbredd) för finare upplösning

X‑dimensionen styr bredden på en enskild streckkodmodul (det minsta svarta eller vita strecket). Att sätta den till ett lågt pixelvärde ger en bild med högre upplösning.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Varför detta är viktigt:** En större X‑dimension gör streckkoden lättare för lågupplösta skannrar att läsa, medan ett mindre värde packar mer data i ett begränsat utrymme. Justera detta värde baserat på skannermiljön.

## Steg 4: Definiera antalet kolumner för att kontrollera streckkodens storlek

MicroPDF417 tillåter 1‑4 kolumner. Fler kolumner ger en kortare, bredare streckkod; färre kolumner skapar en högre, smalare.

```csharp
// Step 4: Define the number of columns (1‑4 are allowed) to control barcode size
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Varför detta är viktigt:** Att välja rätt antal kolumner låter dig passa streckkoden i ett specifikt UI‑element eller en tryckt etikett utan manuell skalning.

## Steg 5: Spara streckkoden som en PNG‑bild

Till sist, skriv den genererade streckkoden till disk. PNG bevarar förlustfri kvalitet, vilket är viktigt för skarp avläsning.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\MicroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Om målkatalogen inte finns, kastar `Save`‑metoden ett `ArgumentException`. Du kan skydda dig mot detta med en enkel kontroll:

```csharp
if (!System.IO.Directory.Exists(@"C:\Barcodes"))
{
    System.IO.Directory.CreateDirectory(@"C:\Barcodes");
}
```

### Fullständig källkod

När vi sätter ihop bitarna, är här det kompletta, körbara programmet:

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
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");

            // 2️⃣ Set the X‑dimension (module width) in pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Define the number of columns (1‑4 are allowed) to control barcode size
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Ensure the output folder exists
            string folder = @"C:\Barcodes";
            if (!System.IO.Directory.Exists(folder))
                System.IO.Directory.CreateDirectory(folder);

            // 4️⃣ Save the generated barcode as a PNG image
            string outputPath = System.IO.Path.Combine(folder, "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

När du kör detta program skapas en fil med namnet **MicroPdf417.png** som ser ut som skärmdumpen nedan (bild utelämnad för korthet). Streckkoden kodar texten *Sample* och respekterar X‑dimensionen och kolumninställningarna du definierade.

## Anpassa andra PDF417‑alternativ

Även om den här guiden fokuserar på **customize pdf417 barcode**‑parametrar som påverkar storlek, erbjuder Aspose.BarCode många ytterligare inställningar du kan behöva:

| Property | Purpose | Typical values |
|----------|---------|----------------|
| `generator.Parameters.Barcode.Pdf417.Rows` | Styr antalet rader (höjd) | 3‑30 |
| `generator.Parameters.Barcode.Pdf417.ErrorLevel` | Ställer in felkorrigeringsnivå (högre = mer tolerant) | 0‑8 |
| `generator.Parameters.Barcode.Pdf417.Truncated` | Genererar en trunkerad streckkod (ingen stoppmönster) | `true`/`false` |
| `generator.Parameters.Barcode.Pdf417.CompactionMode` | Väljer numerisk, text‑ eller byte‑kompaktion | `CompactionModes.Numeric`, etc. |

**Proffstips:** När du behöver en streckkod som passar en fast bredd, börja med att öka `Columns` och minska `XDimension`. Om skannern rapporterar saknade symboler, höj `ErrorLevel` för att förbättra redundansen.

## Hantera kantfall

* **Text too long for MicroPDF417:** Micro‑varianten stödjer upp till 1 KB data. Om din sträng överskrider denna gräns, byt till den fullständiga `Pdf417`‑symbologin genom att ändra `EncodeTypes.MicroPdf417` till `EncodeTypes.Pdf417`.
* **Unsupported image format:** `BarCodeImageFormat` stödjer också `Jpeg`, `Bmp` och `Gif`. Välj ett format som matchar din efterföljande behandlingspipeline.
* **Cross‑platform paths:** Använd `Path.Combine` istället för hårdkodade bakstreck när du riktar mot Linux eller macOS.

## Verifiera streckkoden

Du kan verifiera den genererade bilden med någon standard‑streckkodsläsarapp (mobil eller desktop). Läsaren bör returnera originaltexten **Sample**. Om den misslyckas:

1. Kontrollera att X‑dimensionen inte är inställd under 1 pixel (vissa läsare kan inte lösa sub‑pixel‑moduler).
2. Säkerställ att utdatafilen inte är korrupt – kör programmet igen och jämför filstorlekar.
3. Höj `ErrorLevel` för att förbättra toleransen.

## Slutsats

Du vet nu **how to generate barcode** i C# med Aspose.BarCode, hur du **customize pdf417 barcode** dimensioner och kolumnantal, och hur du **create barcode image C#** projekt kan bädda in direkt. Det kompletta exemplet visar ett praktiskt arbetsflöde från projektuppsättning till slutlig PNG‑utdata.

Nästa steg, utforska andra symbologier som QR, Code128 eller DataMatrix genom att byta `EncodeTypes`‑enum‑värdet. Att justera ytterligare parametrar som `Resolution` eller `Margin` låter dig finjustera varje streckkod för ditt specifika program.

Lycka till med kodningen, och låt dina streckkoder driva ditt nästa automationsprojekt!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}