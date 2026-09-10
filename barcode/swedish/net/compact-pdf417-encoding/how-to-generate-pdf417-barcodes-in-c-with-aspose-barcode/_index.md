---
category: general
date: 2026-09-10
description: Hur man genererar PDF417‑streckkoder i C# med Aspose.BarCode. Följ en
  steg‑för‑steg‑guide för att skapa Macro PDF417, justera parametrar och exportera
  som PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- macro pdf417 barcode
- aspose.barcode for .net
- c# barcode generator
- pdf417 barcode parameters
- barcode image export
language: sv
lastmod: 2026-09-10
og_description: Hur man genererar PDF417‑streckkoder i C# med Aspose.BarCode. Lär
  dig hela arbetsflödet från installation till att spara en Macro PDF417 PNG‑bild.
og_image_alt: Screenshot of a generated Macro PDF417 barcode saved as a PNG file
og_title: Hur man genererar PDF417-streckkoder i C# – komplett guide till Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: How to generate PDF417 barcodes in C# using Aspose.BarCode. Follow
    a step‑by‑step guide to create Macro PDF417, adjust parameters, and export as
    PNG.
  headline: How to generate PDF417 barcodes in C# with Aspose.BarCode
  type: TechArticle
- description: How to generate PDF417 barcodes in C# using Aspose.BarCode. Follow
    a step‑by‑step guide to create Macro PDF417, adjust parameters, and export as
    PNG.
  name: How to generate PDF417 barcodes in C# with Aspose.BarCode
  steps:
  - name: '**Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode
      to use the macro version of PDF417, which supports splitting a large payload
      across multiple symbols.'
    text: '**Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode
      to use the macro version of PDF417, which supports splitting a large payload
      across multiple symbols.'
  - name: '**Adjust basic appearance** – `XDimension` controls the module (dot) width;
      `Columns` defines how many columns each symbol will contain, influencing both
      size and readability.'
    text: '**Adjust basic appearance** – `XDimension` controls the module (dot) width;
      `Columns` defines how many columns each symbol will contain, influencing both
      size and readability.'
  - name: '**Set macro‑specific fields** – These properties (`MacroPdf417FileID`,
      `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification
      to re‑assemble the original data on the scanner side.'
    text: '**Set macro‑specific fields** – These properties (`MacroPdf417FileID`,
      `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification
      to re‑assemble the original data on the scanner side.'
  - name: '**Export the image** – `BarCodeImageFormat.Png` provides a lossless image
      that works well for web, print, and mobile scenarios.'
    text: '**Export the image** – `BarCodeImageFormat.Png` provides a lossless image
      that works well for web, print, and mobile scenarios.'
  - name: '**Visual verification** – Open `MacroPdf417.png` in any image viewer. You
      should see a stacked set of vertical bars with a small text caption (the encoded
      data).'
    text: '**Visual verification** – Open `MacroPdf417.png` in any image viewer. You
      should see a stacked set of vertical bars with a small text caption (the encoded
      data).'
  - name: '**Scanner test** – Use a mobile barcode scanner app that supports PDF417.
      Scan the image; the app should return the original “Sample text” plus macro
      metadata (file ID, segment ID, etc.).'
    text: '**Scanner test** – Use a mobile barcode scanner app that supports PDF417.
      Scan the image; the app should return the original “Sample text” plus macro
      metadata (file ID, segment ID, etc.).'
  - name: '**Error handling** – If the scanner reports “checksum error,” double‑check
      `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly
      on the last segment.'
    text: '**Error handling** – If the scanner reports “checksum error,” double‑check
      `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly
      on the last segment.'
  - name: '**Performance** – Generating many segments in a loop can be CPU‑intensive.
      Re‑use a single `BarcodeGenerator` instance and only update the macro fields
      between saves to improve throughput.'
    text: '**Performance** – Generating many segments in a loop can be CPU‑intensive.
      Re‑use a single `BarcodeGenerator` instance and only update the macro fields
      between saves to improve throughput.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspose
title: Hur man genererar PDF417‑streckkoder i C# med Aspose.BarCode
url: /sv/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar PDF417‑streckkoder i C# med Aspose.BarCode

Om du behöver **hur man genererar pdf417** i ett .NET‑projekt visar den här handledningen hela arbetsflödet. Du får se hur du skapar en Macro PDF417‑streckkod, finjusterar dess inställningar och exporterar resultatet som en PNG‑bild – allt med Aspose.BarCode för .NET.

Att generera PDF417‑streckkoder är vanligt inom logistik, biljettförsäljning och säkra dokumentarbetsflöden. I slutet av den här guiden har du en färdig C#‑generator för streckkoder som du kan släppa in i vilken applikation som helst.

## Vad du behöver

- **Visual Studio 2022** (eller någon annan C#‑IDE)  
- **.NET 6.0** eller senare  
- **Aspose.BarCode for .NET** NuGet‑paket (`Install-Package Aspose.BarCode`)  
- Grundläggande kunskap om C#‑syntax  

> **Pro tip:** Använd den senaste versionen av Aspose.BarCode för att få de nyaste Macro PDF417‑funktionerna och buggfixarna.

---

## Hur man genererar PDF417‑streckkoder i C#  

Nedan är ett fullt körbart exempel som skapar en **Macro PDF417**‑streckkod, konfigurerar dess macro‑specifika fält och sparar bilden.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // STEP 1 – create a Macro PDF417 generator with the desired text
        using (BarcodeGenerator generator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // STEP 2 – adjust basic barcode appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
            generator.Parameters.Barcode.Pdf417.Columns = 5;     // number of columns

            // STEP 3 – configure Macro PDF417 specific fields
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp =
                new DateTime(2023, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // STEP 4 – save the generated barcode as a PNG image
            generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Macro PDF417 barcode generated: MacroPdf417.png");
    }
}
```

### Varför varje steg är viktigt

1. **Skapa en Macro PDF417‑generator** – `EncodeTypes.MacroPdf417` talar om för Aspose.BarCode att använda macro‑versionen av PDF417, som stödjer att dela en stor datamängd över flera symboler.  
2. **Justera grundläggande utseende** – `XDimension` styr modulens (prickens) bredd; `Columns` bestämmer hur många kolumner varje symbol ska innehålla, vilket påverkar både storlek och läsbarhet.  
3. **Ställ in macro‑specifika fält** – Dessa egenskaper (`MacroPdf417FileID`, `MacroPdf417SegmentID` osv.) krävs av PDF417‑macrospecifikationen för att återmontera originaldata på skannerns sida.  
4. **Exportera bilden** – `BarCodeImageFormat.Png` ger en förlustfri bild som fungerar bra för webb, utskrift och mobila scenarier.

---

## Installera Aspose.BarCode för .NET (C#‑streckkodsgenerator)

Innan du kan köra koden ovan måste du lägga till Aspose.BarCode‑biblioteket i ditt projekt:

```bash
dotnet add package Aspose.BarCode
```

*NuGet‑paketet innehåller alla beroenden, så inga extra DLL‑filer behövs.*  
Om du riktar dig mot .NET Framework fungerar samma `Install-Package Aspose.BarCode`‑kommando från Package Manager Console.

### Vanliga fallgropar

- **Saknad licens** – Som standard kör Aspose i evalueringsläge, vilket lägger till ett vattenmärke på streckkoden. Registrera en licensfil (`License license = new License(); license.SetLicense("Aspose.BarCode.lic");`) för att ta bort den.  
- **Fel `EncodeTypes`** – Att använda `EncodeTypes.Pdf417` istället för `EncodeTypes.MacroPdf417` ignorerar alla macro‑fält och bryter återuppbyggnaden av flera segment.

---

## Konfigurera Macro PDF417‑streckkodens parametrar

Macro‑fälten låter dig dela ett stort dokument i flera PDF417‑symboler. Här är en snabb referens:

| Property | Syfte | Typiskt intervall |
|----------|-------|-------------------|
| `MacroPdf417FileID` | Unik identifierare för hela filen | 0‑2³¹‑1 |
| `MacroPdf417SegmentID` | Index för aktuellt segment (börjar på 0) | 0‑254 |
| `MacroPdf417SegmentsCount` | Totalt antal segment i filen | 1‑255 |
| `MacroPdf417FileName` | Valfritt mänskligt läsbart namn | 0‑255 tecken |
| `MacroPdf417Checksum` | CCITT‑16‑kontrollsumma för felupptäckt | 0‑65535 |
| `MacroPdf417FileSize` | Originalfilens storlek i byte | 0‑2³¹‑1 |
| `MacroPdf417TimeStamp` | Skapelsestämpel (valfritt) | `DateTime`‑värde |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Valfri metadata för routning | Valfri sträng |
| `MacroPdf417Terminator` | Anger sista segmentet (`Set` eller `Unset`) | `Pdf417MacroTerminator`‑enum |

Justera dessa värden så att de matchar den data du kodar. Till exempel, om du delar en 2 MB‑fil i 20 segment, sätt `MacroPdf417FileSize` till `2_000_000` och `MacroPdf417SegmentsCount` till `20`.

---

## Exportera streckkoden som PNG‑bild (barcode image export)

Att spara streckkoden som PNG är det vanligaste exportformatet eftersom det bevarar skarpa kanter och stödjer transparens. Aspose.BarCode stödjer också JPEG, BMP, GIF och TIFF – välj det som passar ditt efterföljande flöde.

```csharp
generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
```

**Tips för högkvalitativ output**

- Öka `XDimension.Pixels` för större moduler när du skriver ut på högupplöst media.  
- Använd `BarCodeImageFormat.Tiff` med CCITT Group 4‑komprimering för fax‑kompatibla PDF‑filer.  
- Ställ in `generator.Parameters.ImageOptions.Resolution` om du behöver ett specifikt DPI (t.ex. 300 dpi för utskrift).

---

## Testa och felsöka din PDF417‑streckkod

1. **Visuell verifiering** – Öppna `MacroPdf417.png` i någon bildvisare. Du bör se en staplad uppsättning vertikala staplar med en liten textcaption (den kodade datan).  
2. **Skannertest** – Använd en mobil streckkodsläsarapp som stödjer PDF417. Skanna bilden; appen bör returnera den ursprungliga “Sample text” plus macro‑metadata (fil‑ID, segment‑ID osv.).  
3. **Felsökning** – Om skannern rapporterar “checksum error”, dubbelkolla `MacroPdf417Checksum` och säkerställ att `MacroPdf417Terminator` är korrekt inställd på sista segmentet.  
4. **Prestanda** – Att generera många segment i en loop kan vara CPU‑intensivt. Återanvänd en enda `BarcodeGenerator`‑instans och uppdatera bara macro‑fälten mellan sparningar för att förbättra genomströmning.

---

## Slutsats

Du vet nu **hur man genererar PDF417**‑streckkoder i C# med Aspose.BarCode, från installation av biblioteket till konfiguration av Macro PDF417‑fält och export av en ren PNG‑bild. Den kompletta lösningen visar:

- Hur du sätter upp en **C#‑streckkodsgenerator** med Macro PDF417‑typen  
- Anpassning av **PDF417‑streckkodens parametrar** för data i flera segment  
- Hur du utför **barcode image export** för vidare användning  

Härifrån kan du utforska avancerade ämnen som att bädda in streckkoden i PDF‑dokument, generera QR‑kod‑kompanjoner eller automatisera batch‑bearbetning av stora filer.

**Nästa steg**

- Prova olika `BarCodeImageFormat`‑värden (t.ex. `Tiff` för högupplösta utskrifter).  
- Kombinera Macro PDF417 med andra symbologier i samma dokument med `generator.Parameters.Barcode.Symbology`.  
- Läs igenom [Aspose.BarCode‑dokumentationen](https://docs.aspose.com/barcode/net/) för djupare anpassningsalternativ som felkorrigeringsnivå och kodningslägen.

Happy coding!


## Vad bör du lära dig härnäst?


Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Generate barcode with text – Full PDF417 Macro Guide](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)
- [adjust barcode size – C# guide to generate PDF417 barcodes](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}