---
category: general
date: 2026-11-20
description: Skapa streckkodbild i C# med Aspose.BarCode. Lär dig hur du genererar
  PDF417‑streckkod med en anpassad layout och sparar den som PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- generate pdf417 barcode
- how to generate pdf417
language: sv
lastmod: 2026-11-20
og_description: Skapa streckkodbild i C# med Aspose.BarCode. Denna guide visar hur
  du genererar PDF417‑streckkod, anpassar layouten och exporterar till PNG.
og_image_alt: Screenshot of generated barcode image created with PDF417 using C#
og_title: Skapa streckkodbild med PDF417 i C# – komplett handledning
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create barcode image in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode with a custom layout and save it as PNG.
  headline: How to create barcode image with PDF417 in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode image in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode with a custom layout and save it as PNG.
  name: How to create barcode image with PDF417 in C# – step‑by‑step guide
  steps:
  - name: Why this code works
    text: '* **`BarcodeGenerator`** is the entry point for all barcode types. By passing
      `EncodeTypes.Pdf417` you tell the library to produce a PDF417 symbol. * **Columns
      and rows** are the primary levers for layout. Fewer columns produce a taller
      barcode; more columns make it wider. Adjust these values to fit'
  - name: Adjusting data length
    text: 'PDF417 can encode up to 1,850 characters. If you need to encode longer
      strings, consider splitting the data across multiple barcodes or using the **compact
      mode**:'
  - name: Controlling image size
    text: 'The default image size is calculated from the module size (the smallest
      square in the barcode). You can explicitly set the DPI or scale the image after
      generation:'
  - name: Handling special characters
    text: 'PDF417 supports the full ASCII set. If your data contains Unicode characters,
      ensure you encode the string as UTF‑8:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
title: Hur man skapar streckkodbild med PDF417 i C# – steg‑för‑steg‑guide
url: /sv/net/compact-pdf417-encoding/how-to-create-barcode-image-with-pdf417-in-c-step-by-step-gu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar streckkodbild med PDF417 i C# – steg‑för‑steg guide

Om du behöver **skapa streckkodbild** i en .NET‑applikation visar den här guiden exakt **hur man genererar PDF417‑streckkod** med en anpassad layout och sparar den som en PNG‑fil. Du får se den kompletta, körbara koden, förstå varför varje inställning är viktig, och lära dig vanliga fallgropar så att din streckkod fungerar pålitligt i produktion.

I den här handledningen kommer du att:

* Initiera Aspose.BarCode‑generatorn för PDF417.
* Konfigurera kolumn- och radantal för att styra streckkodens form.
* Exportera resultatet som en högkvalitativ PNG‑bild.
* Utforska valfria inställningar för felkorrigering och datalängd.

Det enda förutsättningen är ett aktuellt .NET‑SDK (.NET 6 eller senare) samt en licens eller gratis provversion av **Aspose.BarCode for .NET**.

---

## Förutsättningar och installation

Innan du börjar, se till att du har:

| Krav | Varför det är viktigt |
|------|------------------------|
| .NET 6 SDK eller nyare | Tillhandahåller runtime för C#‑konsolappen. |
| Visual Studio 2022 (eller VS Code) | Ger dig en IDE med IntelliSense för Aspose‑API:et. |
| Aspose.BarCode for .NET NuGet‑paket | Tillhandahåller `BarcodeGenerator`, `EncodeTypes` och hjälpfunktioner för bild‑export. |
| Skrivbehörighet till mål‑mappen | Generatorn skriver PNG‑filen till disk. |

Du kan lägga till NuGet‑paketet med följande kommando:

```bash
dotnet add package Aspose.BarCode
```

---

## Steg 1: Skapa ett nytt konsolprojekt

Börja med att skapa en enkel konsolapplikation som kommer att innehålla logiken för streckkodsgenerering.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The full barcode generation flow is encapsulated in GeneratePdf417().
            GeneratePdf417();
            Console.WriteLine("Barcode image created successfully.");
        }

        // -----------------------------------------------------------------
        // Generates a PDF417 barcode with a custom layout and saves it as PNG.
        // -----------------------------------------------------------------
        static void GeneratePdf417()
        {
            // -------------------------------------------------------------
            // Step 2: Initialize the barcode generator for PDF417 with text.
            // -------------------------------------------------------------
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample data for PDF417 barcode");

            // -------------------------------------------------------------
            // Step 3: Define a custom layout – set the number of columns and rows.
            // -------------------------------------------------------------
            generator.Parameters.Barcode.Pdf417.Columns = 4; // Controls horizontal density.
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // Controls vertical density.

            // Optional: increase error correction level for noisy environments.
            // Values: 0 (no correction) to 8 (maximum correction).
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 2;

            // -------------------------------------------------------------
            // Step 4: Save the generated barcode as a PNG image.
            // -------------------------------------------------------------
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "CustomPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Varför den här koden fungerar

* **`BarcodeGenerator`** är ingångspunkten för alla streckkodstyper. Genom att skicka `EncodeTypes.Pdf417` talar du om för biblioteket att producera en PDF417‑symbol.
* **Columns and rows** är de primära reglagen för layout. Färre kolumner ger en högre streckkod; fler kolumner gör den bredare. Justera dessa värden för att passa det utrymme där bilden ska visas (t.ex. en etikett‑skrivare vs. en webbsida).
* **Error correction** förbättrar läsligheten när streckkoden kan vara smutsig eller skriven på lågkvalitativt medium. Standardnivån är 0; att höja den något (2–4) är en bra avvägning mellan storlek och robusthet.
* **`Save`** skriver bilden till disk i PNG‑format, vilket bevarar skarpa kanter och fungerar i alla webbläsare och mobila enheter.

När du kör programmet (`dotnet run`) skapas `CustomPdf417.png` i projektmappen. PNG‑filen ser ut så här:

![Genererad PDF417‑streckkodbild](https://example.com/images/pdf417-sample.png "Skärmdump av genererad streckkod bild skapad med PDF417 i C#")

*Alt text:* **skapa streckkodbild** – PDF417‑streckkod genererad i C# och sparad som PNG.

---

## Steg 2: Finjustera streckkoden för verkliga scenarier

### Justera datalängd

PDF417 kan koda upp till 1 850 tecken. Om du behöver koda längre strängar, överväg att dela upp datan över flera streckkoder eller använda **compact mode**:

```csharp
generator.Parameters.Barcode.Pdf417.CompactMode = true;
```

Compact mode minskar antalet rader men kan öka den visuella densiteten, så testa med din scanner.

### Kontrollera bildstorlek

Standardbildstorleken beräknas från modulstorleken (den minsta kvadraten i streckkoden). Du kan explicit ange DPI eller skala bilden efter generering:

```csharp
generator.Parameters.ImageResolution = new Resolution(300); // 300 DPI for printing.
```

Eller, efter sparande, ändra storlek med System.Drawing om du behöver en miniatyr.

### Hantera specialtecken

PDF417 stödjer hela ASCII‑uppsättningen. Om din data innehåller Unicode‑tecken, se till att du kodar strängen som UTF‑8:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, System.Text.Encoding.UTF8.GetString(bytes));
```

---

## Steg 3: Vanliga fallgropar och hur man undviker dem

| Fallgrop | Symptom | Åtgärd |
|----------|---------|--------|
| För många kolumner för den givna datan | Streckkoden blir avklippt eller kastar ett undantag. | Minska `Columns` eller låt biblioteket auto‑storleksanpassa genom att utelämna inställningen. |
| Låg felkorrigering på en brusig skrivare | Scannrar misslyckas med att läsa streckkoden intermittent. | Öka `ErrorCorrectionLevel` till minst 2. |
| Sparar till en skrivskyddad katalog | `UnauthorizedAccessException` vid körning. | Använd en skrivbar mapp som `Environment.CurrentDirectory` eller `Path.GetTempPath()`. |
| Använder en föråldrad Aspose.BarCode‑version | Saknar egenskaper som `CompactMode`. | Uppdatera NuGet‑paketet till den senaste stabila versionen. |

---

## Steg 4: Verifiera resultatet

För att bekräfta att streckkoden genererades korrekt kan du:

1. Öppna `CustomPdf417.png` i någon bildvisare – streckkoden bör vara skarp, med tydliga svarta moduler på en vit bakgrund.
2. Använd en gratis PDF417‑scannerapp (tillgänglig på iOS och Android) för att skanna bilden. Appen bör visa **“Sample data for PDF417 barcode”**.
3. (Valfritt) Ladda bilden i ett enhetstest med `System.Drawing.Bitmap` och påstå att pixeln på `(0,0)` är svart, vilket bekräftar att bilden inte är tom.

```csharp
using System.Drawing;

Bitmap bmp = new Bitmap("CustomPdf417.png");
bool topLeftIsBlack = bmp.GetPixel(0, 0).R == 0;
Console.WriteLine($"Top‑left pixel black? {topLeftIsBlack}");
```

Om påståendet lyckas har du framgångsrikt **skapat streckkodbild** och **genererat PDF417‑streckkod** programmässigt.

---

## Slutsats

Du vet nu hur du **skapar streckkodbild** i C# genom att **generera PDF417‑streckkod** med en anpassad layout, justera felkorrigering och exportera till PNG. Det kompletta exemplet demonstrerar varje nödvändigt steg – från initiering av `BarcodeGenerator` till sparande av den slutgiltiga bilden – så att du kan kopiera, klistra in och köra det i ditt eget projekt.

Nästa steg kan vara att utforska:

* **Bädda in PNG‑filen i ett web‑API** så att klienter kan begära streckkoder på begäran (`generate pdf417` som en tjänst).
* **Batch‑generering** för stora datamängder – loopa över en lista med strängar och lagra varje PNG i en databas.
* **Alternativa utdataformat** (SVG, JPEG) genom att ändra `BarCodeImageFormat`.

Känn dig fri att experimentera med kolumn/rad‑förhållanden, felkorrigeringsnivåer och bildupplösning för att möta de exakta kraven för din scanner‑hardware eller UI‑design. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar PDF417‑streckkodbild i C# – komplett guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)
- [Hur man skapar PDF417‑streckkodbild i C# med Macro PDF417‑alternativ](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Hur man skapar micro PDF417‑streckkod och genererar PNG i C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}