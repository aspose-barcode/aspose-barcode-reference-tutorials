---
category: general
date: 2026-11-27
description: Skapa streckkodbild i C# och spara bilden i PNG‑format med Aspose.BarCode
  – steg‑för‑steg‑guide.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- save image PNG format
- Aspose.BarCode C#
- Macro PDF417 barcode
- barcode generation .NET
language: sv
lastmod: 2026-11-27
og_description: Skapa en streckkodsbild i C# och spara bilden i PNG-format med Aspose.BarCode.
  Följ den här handledningen för att steg för steg generera en Macro PDF417‑streckkod.
og_image_alt: Screenshot of a created barcode image saved as PNG
og_title: Skapa streckkodsbild och spara i PNG-format i C# – komplett guide
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Create barcode image in C# and save image PNG format with Aspose.BarCode
    – step‑by‑step guide.
  headline: Create barcode image and save PNG format in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Skapa en streckkodsbild och spara i PNG‑format i C#
url: /sv/net/one-dimensional-barcode-types/create-barcode-image-and-save-png-format-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa streckkodbild och spara i PNG-format i C#

Om du behöver **skapa streckkodbild** i en .NET-applikation visar den här guiden hur du genererar en Macro PDF417-streckkod och **sparar bilden i PNG-format** med Aspose.BarCode. Du får ett komplett, körbart exempel och en förklaring av varje inställning så att du kan anpassa koden efter dina egna krav.

Att generera en streckkod är mer än att anropa en enda metod; du måste konfigurera modulstorlek, makroparametrar och utdataformatet. I slutet av den här handledningen kommer du att förstå varför varje egenskap är viktig, hur du hanterar vanliga edge‑cases och hur du verifierar att PNG‑filen har skrivits korrekt.

## Vad du behöver

- .NET 6.0 eller senare (koden fungerar också med .NET Framework 4.6+)
- Aspose.BarCode för .NET (tillgänglig via NuGet: `Install-Package Aspose.BarCode`)
- En IDE såsom Visual Studio 2022 eller Visual Studio Code
- Skrivbehörighet till en mapp där PNG‑filen ska sparas

## Steg 1: Initiera streckkodsgeneratorn

Det första steget är att skapa en `BarcodeGenerator`‑instans som specificerar symbologin `EncodeTypes.MacroPdf417` och den text du vill koda.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Initialize a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps go here
}
```

**Varför detta är viktigt:**  
`EncodeTypes.MacroPdf417` talar om för biblioteket att använda PDF417‑makrovarianten, som stöder filsegmentering och ytterligare metadata. Konstruktorn tar också emot den mänskligt läsbara texten som kommer att kodas i streckkoden.

## Steg 2: Definiera modulstorlek (X‑dimension)

X‑dimensionen styr bredden på en enskild streckkodmodul (det minsta svart/vita elementet). Ett värde på `2` pixlar fungerar bra för PNG‑bilder som visas på skärm.

```csharp
    // Step 2: Define the module size (X‑dimension) in pixels
    generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Praktiskt tips:**  
Om du planerar att skriva ut streckkoden, öka pixelvärdet (t.ex. `4` eller `5`) för att undvika suddig utskrift på lågupplösta skrivare.

## Steg 3: Konfigurera PDF417‑makroparametrar

Macro PDF417 lägger till flera valfria fält som hjälper till att identifiera källfilen, segmentordning och integritetskontroller. Nedan är en komplett uppsättning typiska parametrar; du kan utelämna de du inte behöver.

```csharp
    // Step 3: Set PDF417 macro parameters
    generator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // Current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;  // Approximate file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**Varför dessa fält är användbara:**  

| Parameter | Syfte |
|-----------|-------|
| `Columns` | Styr streckkodens bredd; färre kolumner ger en högre streckkod. |
| `MacroPdf417FileID` | Unik identifierare som binder alla segment tillsammans. |
| `MacroPdf417SegmentID` | Position för detta segment i hela filen. |
| `MacroPdf417SegmentsCount` | Totalt antal segment; krävs för återuppbyggnad. |
| `MacroPdf417FileName` | Mänskligt läsbart namn som kan visas av skanningsappar. |
| `MacroPdf417Checksum` | Hjälper mottagare att verifiera dataintegritet (CCITT‑16). |
| `MacroPdf417FileSize` | Valfri storleksindikator för originalfilen. |
| `MacroPdf417TimeStamp` | Tidsstämpel för originalfilens skapande. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Metadata för routning eller ägandeskap. |
| `MacroPdf417Terminator` | Anger om detta är det sista segmentet (`Set`) eller ett mellanliggande (`Unset`). |

**Edge case:** Om du genererar en enkelsegment‑streckkod, sätt `MacroPdf417SegmentsCount` till `1` och `MacroPdf417Terminator` till `Unset`. Biblioteket kommer automatiskt att utelämna segmentrelaterade fält som inte är tillämpliga.

## Steg 4: Spara den genererade streckkoden som en PNG‑bild

Slutligen, anropa `Save` med en filsökväg och enum‑värdet `BarCodeImageFormat.Png`. Metoden skriver bilden till disk i förlustfri PNG‑format.

```csharp
    // Step 4: Save the generated barcode as a PNG image
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

**Varför PNG?**  
PNG bevarar exakta pixelvärden, vilket är avgörande för streckkodsläsare som förlitar sig på skarp kontrast. JPEG‑komprimering kan introducera artefakter som förstör streckkodsmönstret.

### Verifiera utdata

När programmet har körts bör du se en fil med namnet `ExtPDF417Meta.png` i körningsmappen. Att öppna den med någon bildvisare visar en tät, rektangulär streckkod. Du kan verifiera korrektheten genom att skanna bilden med en mobil streckkodsläsare som stöder PDF417‑macro; appen visar vanligtvis den inbäddade metadata (fil‑ID, segmentnummer, osv.).

## Vanliga fallgropar och hur man undviker dem

| Symptom | Trolig orsak | Åtgärd |
|---------|--------------|--------|
| Streckkoden är suddig | X‑dimensionen är för låg för vald DPI | Öka `XDimension.Pixels` eller rendera med högre DPI (`generator.Parameters.ImageResolution`). |
| Skannern rapporterar “checksum error” | Felaktigt `MacroPdf417Checksum`‑värde | Låt Aspose beräkna kontrollsumman automatiskt genom att utelämna egenskapen, eller säkerställ att värdet matchar CCITT‑16‑algoritmen. |
| PNG‑filen är tom eller skapades inte | Ogiltig utskrivningssökväg eller saknad skrivbehörighet | Använd `Path.Combine` med en känd skrivbar mapp (t.ex. `Environment.GetFolderPath(Environment.SpecialFolder.Desktop)`). |
| Makrofält ignoreras | `EncodeTypes` är satt till vanlig `Pdf417` istället för `MacroPdf417` | Verifiera att `EncodeTypes.MacroPdf417` används i konstruktorn. |

## Fullt, körbart exempel

Nedan är det kompletta programmet som du kan kopiera in i en konsolapplikation. Det kompileras med .NET 6.0 och producerar PNG‑filen som beskrivs ovan.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize a Macro PDF417 barcode generator with the desired text
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // Define the module size (X-dimension) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set PDF417 macro parameters
            generator.Parameters.Barcode.Pdf417.Columns = 5;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 checksum
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

**Förväntad utdata (konsol):**

```
Barcode image saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Att öppna `ExtPDF417Meta.png` visar en tydlig Macro PDF417‑streckkod klar för skanning.

## Nästa steg

- **Ändra bildformatet** – ersätt `BarCodeImageFormat.Png` med `Jpeg` eller `Bmp` om du behöver en annan filtyp. Kom ihåg att JPEG introducerar komprimeringsartefakter, vilket kan påverka skanningspålitligheten.
- **Justera upplösning** – använd

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar streckkodbild med Aspose.Barcode i C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Hur man skapar PDF417‑streckkodbild i C# med Macro PDF417‑alternativ](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Hur man läser streckkoder från bild med C# och Aspose.BarCode – steg‑för‑steg‑guide](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}