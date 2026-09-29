---
category: general
date: 2026-09-29
description: Hur man sparar streckkod med Aspose.BarCode i C# och lär sig hur man
  genererar PDF417 med makrometadata. Följ steg‑för‑steg‑guiden.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- how to generate pdf417
- how to set pdf417
- generate barcode with aspose
language: sv
lastmod: 2026-09-29
og_description: Hur man sparar streckkod med Aspose.BarCode i C# är enkelt. Denna
  handledning visar hur man genererar PDF417 med makrometadata och ställer in alla
  nödvändiga parametrar.
og_image_alt: Screenshot showing how to save barcode as PNG with PDF417 macro metadata
og_title: Hur man sparar streckkod med Aspose – PDF417‑genereringsguide
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to save barcode using Aspose.BarCode in C# and learn how to generate
    PDF417 with macro metadata. Follow step‑by‑step guide.
  headline: How to save barcode and generate PDF417 with Aspose in C#
  type: TechArticle
- description: How to save barcode using Aspose.BarCode in C# and learn how to generate
    PDF417 with macro metadata. Follow step‑by‑step guide.
  name: How to save barcode and generate PDF417 with Aspose in C#
  steps:
  - name: '**Creating the generator** – The `BarcodeGenerator` constructor takes the
      barcode type (`EncodeTypes.MacroPdf417`) and the data to encode. Macro PDF417
      is a special variant that carries file‑transfer information, which is why we
      later fill macro fields.'
    text: '**Creating the generator** – The `BarcodeGenerator` constructor takes the
      barcode type (`EncodeTypes.MacroPdf417`) and the data to encode. Macro PDF417
      is a special variant that carries file‑transfer information, which is why we
      later fill macro fields.'
  - name: '**Appearance settings** – `XDimension.Pixels` controls the narrow bar width;
      adjusting it changes the overall image size without affecting data integrity.
      `Pdf417.Columns` defines the layout of the barcode matrix.'
    text: '**Appearance settings** – `XDimension.Pixels` controls the narrow bar width;
      adjusting it changes the overall image size without affecting data integrity.
      `Pdf417.Columns` defines the layout of the barcode matrix.'
  - name: '**Macro metadata** – These properties (`MacroPdf417FileID`, `MacroPdf417SegmentID`,
      etc.) are essential when you need to split a large file into multiple barcode
      segments. Setting them correctly ensures that a scanner can reconstruct the
      original file.'
    text: '**Macro metadata** – These properties (`MacroPdf417FileID`, `MacroPdf417SegmentID`,
      etc.) are essential when you need to split a large file into multiple barcode
      segments. Setting them correctly ensures that a scanner can reconstruct the
      original file.'
  - name: '**Saving the image** – The `Save` method writes the generated barcode to
      disk. You can choose any supported format (`Png`, `Jpeg`, `Bmp`, etc.). This
      line demonstrates the exact **how to save barcode** operation requested.'
    text: '**Saving the image** – The `Save` method writes the generated barcode to
      disk. You can choose any supported format (`Png`, `Jpeg`, `Bmp`, etc.). This
      line demonstrates the exact **how to save barcode** operation requested.'
  type: HowTo
tags:
- barcode
- PDF417
- Aspose
- C#
title: Hur man sparar streckkod och genererar PDF417 med Aspose i C#
url: /sv/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man sparar streckkod och genererar PDF417 med Aspose i C#

Att spara streckkod med Aspose.BarCode i C# är ett vanligt behov när du behöver bädda in data i en bildfil. Denna guide går igenom hela processen för att generera en PDF417‑streckkod med makro‑metadata och spara resultatet som en PNG‑bild. I slutet kommer du att veta **hur man genererar PDF417**, **hur man ställer in PDF417**‑alternativ, och, viktigast av allt, **hur man sparar streckkod**‑filer programatiskt.

Du kommer att se ett komplett, körbart exempel som täcker varje steg—från att lägga till Aspose.BarCode NuGet‑paketet till att konfigurera makrofält som fil‑ID, segmentantal och kontrollsumma. Ingen extern dokumentation krävs; koden kan kopieras in i ett nytt konsolprojekt och köras omedelbart. Handledningen förutsätter att du har Visual Studio 2022 (eller senare) och .NET 6.0 installerat.

## Förutsättningar

- .NET 6.0 SDK (eller någon .NET‑version som stöds av Aspose.BarCode 23.11+)
- Visual Studio 2022, VS Code, eller din föredragna C#‑IDE
- **Aspose.BarCode for .NET** NuGet‑paket  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Grundläggande kunskap om C#‑syntax och konsolapplikationer

> **Proffstips:** Använd den kostnadsfria utvecklarutvärderingslicensen från Aspose om du ännu inte har en kommersiell licens. Utvärderingen fungerar utan kodändringar.

## Så sparas streckkod – komplett exempel

Följande kod skapar en **Macro PDF417**‑streckkod, fyller i alla makrofält och sparar bilden som `ExtPDF417Meta.png`. Alla nödvändiga `using`‑direktiv är inkluderade så att du kan klistra in kodsnutten direkt i `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for Macro PDF417 with sample data
        using (BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MacroPdf417,          // EncodeTypes enum selects the barcode type
            "Åspóse.Barcóde©"))               // Sample data – Unicode characters are supported
        {
            // Step 2: Define basic barcode appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // narrow bar width (2 px)
            generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns per row

            // Step 3: Configure Macro PDF417 metadata
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Step 4: Save the generated barcode as a PNG image
            // This is the core of **how to save barcode** with Aspose.
            generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Barcode saved as ExtPDF417Meta.png");
    }
}
```

### Varför varje steg är viktigt

1. **Skapa generatorn** – `BarcodeGenerator`‑konstruktorn tar streckkodstypen (`EncodeTypes.MacroPdf417`) och den data som ska kodas. Macro PDF417 är en speciell variant som bär filöverföringsinformation, vilket är anledningen till att vi senare fyller i makrofält.
2. **Utseendeinställningar** – `XDimension.Pixels` styr den smala stapelns bredd; en justering ändrar den totala bildstorleken utan att påverka dataintegriteten. `Pdf417.Columns` definierar layouten av streckkodsmatrisen.
3. **Makro‑metadata** – Dessa egenskaper (`MacroPdf417FileID`, `MacroPdf417SegmentID` osv.) är avgörande när du behöver dela upp en stor fil i flera streckkodsegment. Att sätta dem korrekt säkerställer att en scanner kan återskapa den ursprungliga filen.
4. **Spara bilden** – `Save`‑metoden skriver den genererade streckkoden till disk. Du kan välja vilket stödformat som helst (`Png`, `Jpeg`, `Bmp` osv.). Denna rad demonstrerar den exakta **hur man sparar streckkod**‑operationen som efterfrågades.

> **Vanlig fråga:** *Vad händer om jag behöver ett annat bildformat?*  
> Ändra `BarCodeImageFormat.Png` till `BarCodeImageFormat.Jpeg` (eller något annat stödformat) och justera filändelsen därefter.

## Hur man genererar PDF417 med makro‑metadata

Om du bara behöver en vanlig PDF417 (utan makrodatan) kan du hoppa över makrosektorn och behålla den grundläggande generatorn:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample data"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 3;
    gen.Save("SimplePdf417.png", BarCodeImageFormat.Png);
}
```

Koden ovan illustrerar **hur man snabbt genererar PDF417**. Observera att `EncodeTypes.Pdf417`‑enumet väljer den icke‑makro versionen.

## Hur man ställer in PDF417 – avancerade alternativ

Aspose.BarCode exponerar många PDF417‑specifika parametrar. Här är några du kan behöva:

| Property | Description | Typical values |
|----------|-------------|----------------|
| `Pdf417.Columns` | Antal kolumner per rad | 1‑30 (standard 3) |
| `Pdf417.Rows` | Antal rader (auto‑beräknas om 0) | 0‑90 |
| `Pdf417.ErrorLevel` | Felkorrigeringsnivå (0‑8) | 2‑4 för balanserad storlek/robusthet |
| `Pdf417.RowsPerStrip` | Rader per remsa för stora streckkoder | 0 (auto) |
| `Pdf417.Pdf417MacroFileID` | Identifierare för filen vid användning av makro | Valfritt 32‑bit heltal |

Att sätta dessa värden följer samma mönster som visas i **Steg 2** i huvudexemplet. Justera dem innan du anropar `Save`.

## Förväntat resultat

När du kör hela programmet skapas `ExtPDF417Meta.png` i den körbara filens arbetskatalog. Bilden innehåller en högupplöst PDF417‑streckkod med alla makrofält inbäddade. Att skanna bilden med en PDF417‑kapabel scanner (eller en mobilapp) kommer att returnera den ursprungliga datasträngen "Åspóse.Barcóde©" tillsammans med makro‑metadata (fil‑ID, segment‑ID osv.).

![Streckkod sparad som PNG – exempel på hur man sparar streckkod](ExtPDF417Meta.png "Hur man sparar streckkod som PNG med makro‑PDF417‑metadata")

*Bildens alt‑text:* **hur man sparar streckkod som PNG med PDF417‑makro‑metadata** (matchar primär nyckelord).

## Slutsats

I den här handledningen har du lärt dig **hur man sparar streckkod** med Aspose.BarCode, **hur man genererar PDF417**, **hur man ställer in PDF417**‑parametrar, och **hur man genererar streckkod med Aspose** för både vanliga och makro‑aktiverade scenarier.

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar PDF417‑streckkod med Aspose – komplett guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Hur man genererar PDF417‑streckkodbild i C# med Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Hur man genererar streckkod i C# med Aspose.BarCode och lägger till metadata](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-in-c-with-aspose-barcode-and-add-met/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}