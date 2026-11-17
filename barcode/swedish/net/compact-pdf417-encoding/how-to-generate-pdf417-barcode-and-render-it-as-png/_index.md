---
category: general
date: 2026-11-17
description: Lär dig hur du genererar PDF417‑streckkod, ställer in streckkodens storlek
  och renderar streckkoden till en bild med C#. Komplett steg‑för‑steg‑guide.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- render barcode to image
- how to set barcode size
language: sv
lastmod: 2026-11-17
og_description: Generera PDF417-streckkod i C# och rendera streckkoden till en bild.
  Följ den här guiden för att ställa in streckkodens storlek och spara en PNG-fil.
og_image_alt: Screenshot of a generated PDF417 barcode saved as a PNG image
og_title: Generera PDF417-streckkod och rendera som PNG – C#‑guide
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to generate PDF417 barcode, set barcode size, and render
    barcode to image using C#. Complete step‑by‑step guide.
  headline: How to generate PDF417 barcode and render it as PNG
  type: TechArticle
- description: Learn how to generate PDF417 barcode, set barcode size, and render
    barcode to image using C#. Complete step‑by‑step guide.
  name: How to generate PDF417 barcode and render it as PNG
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a smartphone barcode scanning app that supports PDF417 (e.g., Google
      Lens, QR & Barcode Scanner).
    text: Use a smartphone barcode scanning app that supports PDF417 (e.g., Google
      Lens, QR & Barcode Scanner).
  - name: Scan the image; the app should return the text *Layout demo*.
    text: Scan the image; the app should return the text *Layout demo*.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- image generation
title: Hur man genererar PDF417-streckkod och renderar den som PNG
url: /sv/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar PDF417-streckkod och renderar den som PNG

Om du behöver **generera PDF417-streckkod** i en .NET-applikation visar den här handledningen exakt hur du gör. Du kommer att se hur du ställer in streckkodens storlek, konfigurerar layouten och **renderar streckkod till bild** med bara några rader C#-kod.

Att generera en PDF417-streckkod är vanligt när du vill koda stora mängder data för skanning på mobila enheter eller skrivare. I slutet av den här guiden har du en färdig‑att‑använda PNG-fil som du kan bädda in i rapporter, e‑post eller webbsidor.

## Förutsättningar

- .NET 6.0 SDK eller senare installerat  
- En C#‑IDE såsom Visual Studio 2022 (valfri editor fungerar)  
- **Aspose.BarCode for .NET** NuGet‑paketet (eller något kompatibelt bibliotek som tillhandahåller `BarcodeGenerator`)  

Du kan lägga till paketet med:

```bash
dotnet add package Aspose.BarCode
```

## Steg 1: Skapa ett C#-konsolprojekt

Först, skapa en minimal konsolapplikation som kommer att innehålla koden för streckkodsgenerering.

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
            // The barcode generation logic will be placed here.
        }
    }
}
```

> **Proffstips:** Håll `Main`-metoden kort och delegera det tunga arbetet till hjälpfunktioner. Detta förbättrar läsbarheten och gör enhetstestning enklare.

## Steg 2: Generera PDF417-streckkod med anpassad storlek

Nu kommer vi att **generera PDF417-streckkod** och ange modulens (X‑dimension) storlek. X‑dimensionen styr hur bred varje liten ruta i streckkoden är, vilket i praktiken bestämmer streckkodens totala storlek.

```csharp
static void GeneratePdf417(string text, string outputPath)
{
    // Initialize a PDF417 barcode generator with the desired text
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, text);

    // Set the size of a single barcode module (X‑dimension) in pixels
    generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

    // Optional: adjust the number of columns and rows for layout control
    generator.Parameters.Barcode.Pdf417.Columns = 4;   // 4 columns
    generator.Parameters.Barcode.Pdf417.Rows    = 9;   // 9 rows

    // Render the barcode and save it as a PNG image
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

### Varför ange X‑dimensionen?

Steget **hur man ställer in streckkodens storlek** är viktigt eftersom en för liten X‑dimension kan göra streckkoden oläslig på lågupplösta skannrar, medan ett för stort värde slösar med utrymme. Ett värde på `2` pixlar fungerar bra för de flesta skärmvisningar och utskriftsscenarier.

## Steg 3: Anropa genereringsmetoden från `Main`

Koppla ihop allt genom att anropa `GeneratePdf417` med den önskade texten och utskriftsplatsen.

```csharp
static void Main(string[] args)
{
    string barcodeText = "Layout demo";
    string outputFile = @"C:\Barcodes\LayoutPdf417.png";

    GeneratePdf417(barcodeText, outputFile);

    Console.WriteLine($"PDF417 barcode saved to {outputFile}");
}
```

När programmet körs skapas `LayoutPdf417.png` som innehåller streckkoden:

![Genererad PDF417-streckkod](/images/layout-pdf417.png "PDF417-streckkod genererad av handledningskoden"){: .align-center alt="Genererad PDF417-streckkod sparad som PNG"}

> **Förväntat resultat:** En PNG-fil på ungefär 200 × 100 px (beroende på kolumn-/radinställningar) som visar ett tydligt PDF417-mönster redo för skanning.

## Steg 4: Verifiera att streckkoden fungerar

För att säkerställa att streckkoden är giltig:

1. Öppna PNG-filen i någon bildvisare.  
2. Använd en smartphone‑app för streckkodsskanning som stöder PDF417 (t.ex. Google Lens, QR & Barcode Scanner).  
3. Skanna bilden; appen bör returnera texten *Layout demo*.

Om skanningen misslyckas, dubbelkolla X‑dimensionen samt kolumn‑/radvärden—större moduler förbättrar läsbarheten på lågupplösta kameror.

## Vanliga variationer och kantfall

| Scenario | Justering |
|----------|------------|
| **Mer data** (t.ex. en URL) | Öka `Columns` eller `Rows` för att rymma extra kodord. |
| **Utskrift med hög upplösning** | Höj `XDimension.Pixels` till 3‑4 px för skarpare staplar. |
| **Transparent background** | Använd `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })`. |
| **Annat bildformat** | Byt ut `BarCodeImageFormat.Png` mot `Jpeg` eller `Bmp` vid behov. |

Dessa variationer svarar på frågan **hur man genererar PDF417** för olika krav samtidigt som kärnlogiken förblir identisk.

## Slutsats

Du vet nu hur man **genererar PDF417-streckkod**, **ställer in streckkodens storlek** och **renderar streckkod till bild** med C#. Det kompletta, körbara exemplet skapar en PNG-fil som kan bäddas in var du än behöver en maskinläsbar streckkod.

Nästa steg, utforska relaterade ämnen som **bädda in PNG i en PDF** (sök efter *render barcode to PDF*), eller **generera andra 2‑D-streckkoder** som QR‑koder. Justera layoutparametrarna för att passa din UI‑design och experimentera med färgalternativ för varumärkesprofilering.

Lycka till med kodandet, och låt dina streckkoder göra det tunga arbetet!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar PDF417-streckkod i C# – komplett steg‑för‑steg‑guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Hur man genererar micro PDF417-streckkod i C# – steg‑för‑steg‑guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [Hur man ställer in felnivå i PDF417-streckkod – komplett guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}