---
category: general
date: 2026-10-02
description: Maak een barcode van tekst in C# met Aspose.BarCode. Leer hoe je een
  PDF417‑barcode genereert en zie hoe je een PDF417‑barcode in compacte modus genereert.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate pdf417 barcode
- how to generate pdf417 barcode
language: nl
lastmod: 2026-10-02
og_description: Maak een barcode van tekst in C# met Aspose.BarCode. Deze gids laat
  zien hoe je een PDF417-barcode genereert en hoe je een PDF417-barcode in compacte
  modus genereert.
og_image_alt: Screenshot showing create barcode from text output as a PNG image
og_title: Barcode maken vanuit tekst in C# – stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  headline: How to create barcode from text in C# with Aspose.BarCode
  type: TechArticle
- description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  name: How to create barcode from text in C# with Aspose.BarCode
  steps:
  - name: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
    text: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
  - name: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
    text: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
  - name: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
    text: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Hoe een barcode te maken van tekst in C# met Aspose.BarCode
url: /nl/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een barcode te maken vanuit tekst in C# met Aspose.BarCode

Als je een **barcode moet maken vanuit tekst** in een .NET‑applicatie, leidt deze gids je door het volledige proces. Je ziet een kant‑klaar voorbeeld dat **PDF417 barcode** genereert en ook beantwoordt **hoe PDF417 barcode te genereren** in een compact layout.

Een barcode programmatisch genereren verwijdert handmatige stappen en garandeert consistentie in alle documenten. Aan het einde van deze tutorial heb je een PNG‑bestand met een PDF417 barcode dat je kunt insluiten in facturen, tickets of identiteitskaarten.

## Wat je nodig hebt

- .NET 6.0 SDK of later (de code werkt ook met .NET Framework 4.7.2+)
- Visual Studio 2022 of een editor die C# ondersteunt
- Een NuGet‑licentie voor **Aspose.BarCode for .NET** (een gratis proefversie werkt voor testen)

> **Pro tip:** Voeg het NuGet‑pakket toe via de CLI om het project schoon te houden:  
> `dotnet add package Aspose.BarCode`

## Stap 1: Een console‑project opzetten

Maak een nieuwe console‑applicatie en verwijs naar de Aspose.BarCode‑bibliotheek.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Het commando `dotnet new console` genereert een `Program.cs`‑bestand dat we hieronder zullen vervangen door het volledige voorbeeld.

## Stap 2: Hoe een barcode te maken vanuit tekst – kerncode

Open `Program.cs` en vervang de inhoud door de volgende code. Elke regel is becommentarieerd om uit te leggen waarom deze bestaat.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Image;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Define the text that will be encoded.
            // The PDF417 symbology supports a wide range of Unicode characters.
            string textToEncode = "Åspóse.Barcóde©";

            // 2️⃣ Create a BarcodeGenerator for PDF417 using the desired text.
            // This object holds all settings and performs the rendering.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, textToEncode);

            // 3️⃣ Adjust module (X) dimension for better readability on screen.
            // XDimension defines the width of a single barcode column in pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Set the number of columns – a smaller column count yields a denser image.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 5️⃣ Enable compact mode by truncating the data.
            // Truncate = true removes padding, making the barcode smaller while preserving scannability.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 6️⃣ Choose the output path. Adjust the folder to match your environment.
            string outputPath = "CompactPdf417.png";

            // 7️⃣ Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Waarom elke instelling belangrijk is

| Instelling | Doel |
|------------|------|
| `EncodeTypes.Pdf417` | Selecteert de PDF417‑symbologie, die grote hoeveelheden data kan opslaan in een tweedimensionale matrix. |
| `XDimension.Pixels = 2` | Regelt de breedte van elk module; een waarde van 2 pixels biedt een balans tussen leesbaarheid en bestandsgrootte. |
| `Pdf417.Columns = 3` | Vermindert het aantal kolommen, waardoor de barcode compacter wordt zonder data te verliezen. |
| `Pdf417.Truncate = true` | Activeert compacte modus, verwijdert onnodige padding en verkort de barcode. |
| `BarCodeImageFormat.Png` | PNG behoudt lossless kwaliteit, ideaal voor verdere verwerking of afdrukken. |

## Stap 3: PDF417 barcode genereren – het voorbeeld uitvoeren

Bouw en voer het project uit:

```bash
dotnet run
```

Wanneer de uitvoering klaar is zie je:

```
Barcode saved to CompactPdf417.png
```

Open `CompactPdf417.png` om het resultaat te bekijken. De afbeelding bevat een PDF417 barcode die de tekenreeks **Åspóse.Barcóde©** codeert.

![Create barcode from text example](barcode-example.png)

*Alt text: barcode maken vanuit tekst – PDF417 barcode opgeslagen als PNG*

## Stap 4: Hoe PDF417 barcode te genereren met aangepaste foutcorrectie (optioneel)

Als je scanomgeving ruis bevat, kun je het foutcorrectieniveau verhogen:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // Levels 0–5, higher = more redundancy
```

Het verhogen van het foutniveau maakt de barcode groter, maar verbetert de weerstand tegen schade.

## Stap 5: Veelvoorkomende valkuilen en afhandeling van randgevallen

1. **Ongeldige tekens** – PDF417 ondersteunt Unicode, maar sommige oudere scanners kunnen niet‑ASCII‑symbolen weigeren. Test met je doelhardware.  
2. **Bestandspad‑rechten** – Zorg ervoor dat de map waarin je schrijft schrijfbaar is; anders gooit `Save` een `UnauthorizedAccessException`.  
3. **Afbeeldingsgrootte** – Zeer hoge `XDimension`‑waarden produceren grote PNG‑bestanden. Houd de pixelgrootte tussen 1 en 4 voor de meeste scherm‑weergavescenario's.

## Samenvatting

Je weet nu hoe je **barcode kunt maken vanuit tekst** in C# met Aspose.BarCode, hoe je **PDF417 barcode kunt genereren** met een compact layout, en de exacte stappen voor **hoe PDF417 barcode te genereren** met aangepaste instellingen. De volledige, uitvoerbare code hierboven kan worden gekopieerd naar elk .NET‑project en aangepast aan verschillende tekstinvoer of uitvoerformaten (bijv. JPEG, BMP).

## Volgende stappen

- Verken andere symbologieën zoals QR Code of Code128 door `EncodeTypes` te wijzigen.  
- Integreer de gegenereerde PNG in een PDF met Aspose.PDF voor end‑to‑end documentcreatie.  
- Experimenteer met `generator.Parameters.Barcode.Pdf417.Rows` om de verticale dichtheid te regelen.

Voel je vrij om het voorbeeld aan te passen, de barcode in je eigen applicaties in te sluiten, en je resultaten te delen met de community. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [How to generate PDF417 barcode in C# – compact example](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-compact-example/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [How to generate PDF417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}