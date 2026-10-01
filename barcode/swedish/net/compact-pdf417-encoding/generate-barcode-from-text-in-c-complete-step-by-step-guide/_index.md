---
category: general
date: 2026-08-09
description: Generera streckkod från text i C# med Aspose.BarCode. Lär dig hur du
  genererar streckkod, hanterar specialtecken och snabbt skapar PDF417-streckkod i
  C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode from text
- how to generate barcode
- barcode with special characters
- barcode encode types
- create pdf417 barcode c#
language: sv
lastmod: 2026-08-09
og_description: Generera streckkod från text i C# med Aspose.BarCode. Denna handledning
  visar hur man genererar streckkod, stödjer specialtecken och skapar PDF417‑streckkod
  i C# med fullständig kod.
og_image_alt: Screenshot of a generated MicroPdf417 barcode saved as PNG
og_title: Generera streckkod från text i C# – snabb steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Generate barcode from text in C# with Aspose.BarCode. Learn how to
    generate barcode, handle special characters, and create PDF417 barcode C# quickly.
  headline: Generate barcode from text in C# – complete step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- Aspose
- encoding
title: Generera streckkod från text i C# – komplett steg‑för‑steg‑guide
url: /sv/net/compact-pdf417-encoding/generate-barcode-from-text-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera streckkod från text i C# – komplett steg‑för‑steg‑guide

Om du behöver **generera streckkod från text** i en .NET‑applikation, guidar den här guiden dig genom hela processen. Du kommer att se hur du genererar streckkod, hanterar specialtecken och skapar en PDF417‑streckkod C#‑implementation som fungerar direkt ur lådan.

Att generera en streckkod från text är ett vanligt krav för lagerhanteringssystem, biljettplattformar och dokumentarbetsflöden. I slutet av den här tutorialen har du en körbar C#‑konsolapp som producerar en MicroPdf417 PNG‑bild med Aspose.BarCode. Inga externa tjänster krävs, och koden hanterar Unicode‑tecken som “Å”, “©” och “é”.

## Förutsättningar

- .NET 6.0 SDK eller senare (koden fungerar också med .NET Core 3.1 och .NET Framework 4.7+)
- Visual Studio 2022 (eller någon IDE som stödjer C#)
- **Aspose.BarCode for .NET** NuGet‑paket  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Grundläggande kunskap om C#‑syntax

## Generera streckkod från text – konfigurera generatorn

Det första steget är att skapa en `BarcodeGenerator`‑instans som vet vilken **barcode encode type** du vill ha. I den här tutorialen använder vi `EncodeTypes.MicroPdf417`, vilket är en kompakt variant av PDF417 lämplig för korta datasträngar.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for MicroPdf417 with the desired text
        // This demonstrates "generate barcode from text" with Unicode characters.
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©"
        );

        // Continue with configuration (see next sections)
        ConfigureGenerator(generator);
        SaveBarcode(generator);
    }

    // Configuration is split into its own method for clarity.
    static void ConfigureGenerator(BarcodeGenerator generator)
    {
        // Step 2: Define the X dimension of the barcode modules (in pixels)
        // XDimension controls the width of the smallest bar; 2 px gives a clear image.
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 3: Set the number of columns for the PDF417 layout.
        // Fewer columns produce a taller barcode; 4 columns works well for short strings.
        generator.Parameters.Barcode.Pdf417.Columns = 4;
    }

    static void SaveBarcode(BarcodeGenerator generator)
    {
        // Step 4: Save the generated barcode as a PNG image.
        // You can change BarCodeImageFormat to Jpeg, Gif, etc., if needed.
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "MicroPdf417.png"
        );
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

**Varför detta fungerar:**  
- `EncodeTypes.MicroPdf417` talar om för biblioteket att använda PDF417‑familjen, vilket uppfyller kravet **create pdf417 barcode c#**.  
- Konstruktorn tar emot den råa texten, vilket är kärnan i **generate barcode from text**.  
- Unicode‑stöd är inbyggt, så tecken som “Å” och “©” kodas korrekt, vilket hanterar **barcode with special characters**.

## Så genererar du streckkod med specialtecken

När dina data innehåller icke‑ASCII‑symboler måste du säkerställa att generatorn använder UTF‑8‑kodning. Aspose.BarCode upptäcker automatiskt Unicode, men du kan explicit ange textkodning om du stöter på problem:

```csharp
generator.Parameters.Barcode.TextEncoding = Encoding.UTF8;
```

Att lägga till den här raden före `ConfigureGenerator` garanterar att **barcode with special characters** renderas korrekt på alla plattformar.

### Praktiskt tips
Om utdata ser förvrängda ut, verifiera att det teckensnitt som används av streckkodsgenereraren stödjer de nödvändiga glyferna. Du kan bädda in ett eget TrueType‑teckensnitt via:

```csharp
generator.Parameters.Barcode.Font.FontFamily = "Arial Unicode MS";
```

## Streckkodskodningstyper du kan välja

Aspose.BarCode stödjer dussintals **barcode encode types**, var och en lämpad för olika användningsområden:

| Encode type                | Typiskt användningsområde                     |
|----------------------------|-----------------------------------------------|
| `EncodeTypes.Code128`      | Fraktetiketter, lager                         |
| `EncodeTypes.QR`           | Mobila betalningar, URL:er                    |
| `EncodeTypes.Pdf417`       | Körkort, boardingkort                         |
| `EncodeTypes.MicroPdf417`  | Små datamängder, begränsat utrymme            |
| `EncodeTypes.DataMatrix`   | Små objekt, hög datadensitet                  |

Att byta kodningstyp är så enkelt som att byta enum‑värdet i konstruktorn:

```csharp
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

Detta ger dig möjlighet att svara på frågor om **barcode encode types** utan att lämna IDE:n.

## Skapa PDF417‑streckkod C# – sista stegen och verifiering

Efter att ha konfigurerat generatorn är den sista delen av **create pdf417 barcode c#** att spara bilden och bekräfta resultatet.

```csharp
// Save as PNG (lossless, ideal for further processing)
generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
```

Kör programmet (`dotnet run`) så bör du se ett konsolmeddelande liknande:

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\MicroPdf417.png
```

Öppna PNG‑filen; du ser en skarp MicroPdf417‑streckkod som kodar strängen “Åspóse.Barcóde©”. Att skanna den med en mobil streckkodsläsare (t.ex. ZXing) returnerar den ursprungliga texten, vilket bevisar att **generate barcode from text** fungerar även med specialtecken.

### Edge case: mycket lång text

MicroPdf417 har en maximal datakapacitet på 1 KB. Om ditt indata överskrider denna gräns kastar biblioteket ett `ArgumentException`. För att hantera detta på ett smidigt sätt:

```csharp
try
{
    generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Data too long for MicroPdf417: {ex.Message}");
}
```

För större nyttolaster, byt till den fullständiga `EncodeTypes.Pdf417` eller `EncodeTypes.DataMatrix`.

## Vanliga fallgropar och hur du undviker dem

| Problem                               | Orsak                                   | Lösning |
|---------------------------------------|-----------------------------------------|---------|
| Streckkoden blir suddig               | XDimension för låg (t.ex. 1 px)         | Öka `XDimension.Pixels` till 2‑3 px |
| Unicode‑tecken blir `?`               | Standardtextkodning är ASCII            | Set `TextEncoding = Encoding.UTF8` |
| Bildfilen skapades inte               | Utdatamappen finns inte                 | Use `Directory.CreateDirectory` before `Save` |
| Skannern kan inte läsa streckkoden    | För många kolumner för kort data        | Reduce `Pdf417.Columns` (e.g., 3‑4) |

## Fullständig källkod (klar att kopiera)

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create the generator – this is the core of "generate barcode from text"
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©"
        );

        // Ensure Unicode characters are handled correctly
        generator.Parameters.Barcode.TextEncoding = Encoding.UTF8;

        // Optional: set a font that contains the required glyphs
        generator.Parameters.Barcode.Font.FontFamily = "Arial Unicode MS";

        // Configure visual appearance
        generator.Parameters.Barcode.XDimension.Pixels = 2;
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // Prepare output directory
        string outputDir = Path.Combine(Environment.CurrentDirectory, "output");
        Directory.CreateDirectory(outputDir);
        string outputPath = Path.Combine(outputDir, "MicroPdf417.png");

        // Save the barcode image
        try
        {
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to: {outputPath}");
        }
        catch (ArgumentException ex)
        {
            Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
        }
    }
}
```

**Förväntad utdata:** en fil med namnet `MicroPdf417.png` i mappen `output`, innehållande en tydlig MicroPdf417‑streckkod som kodar den ursprungliga strängen med specialtecken.

## Slutsats

Du vet nu hur du **genererar streckkod från text** i C# med Aspose.BarCode, hur du hanterar **barcode with special characters**, och hur du **create pdf417 barcode c#** med full kontroll över kodningsalternativ. Genom att justera **barcode encode types** kan du producera QR‑koder, Code128, DataMatrix eller något annat stödformat.

Utforska sedan följande ämnen för att fördjupa din streckkodsexpertis:

- **Hur man genererar streckkod** i batch för tusentals poster (använd `Parallel.ForEach` för hastighet)
- Anpassa färger och lägga till logotyper i streckkoden
- Integrera streckkodsgenerering i ASP.NET Core‑API:er för dynamisk bildleverans
- Använda andra bibliotek som ZXing.Net eller IronBarcode för öppen‑källkods‑alternativ

Känn dig fri att experimentera med olika dimensioner, kolumninställningar och kodningstyper. Lycka till med kodandet, och må dina applikationer skanna felfritt!

## Vad bör du lära dig härnäst?

Följande tutorialer täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar streckkod – kompakt PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hur man genererar streckkod – Code 39‑konfiguration med Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Hur man genererar streckkod – endimensionella streckkodstyper](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}