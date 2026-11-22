---
category: general
date: 2026-11-20
description: Maak een barcode‑afbeelding in C# met Aspose.BarCode. Leer hoe je een
  PDF417‑barcode met een aangepaste lay‑out kunt genereren en opslaan als PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- generate pdf417 barcode
- how to generate pdf417
language: nl
lastmod: 2026-11-20
og_description: Maak barcode‑afbeelding in C# met Aspose.BarCode. Deze gids laat zien
  hoe je een PDF417‑barcode genereert, de lay‑out aanpast en exporteert naar PNG.
og_image_alt: Screenshot of generated barcode image created with PDF417 using C#
og_title: Maak een barcode‑afbeelding met PDF417 in C# – volledige tutorial
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
title: Hoe maak je een barcode‑afbeelding met PDF417 in C# – stapsgewijze handleiding
url: /nl/net/compact-pdf417-encoding/how-to-create-barcode-image-with-pdf417-in-c-step-by-step-gu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een barcode‑afbeelding te maken met PDF417 in C# – stapsgewijze handleiding

Als je een **barcode‑afbeelding moet maken** in een .NET‑applicatie, laat deze gids je precies zien **hoe je een PDF417‑barcode genereert** met een aangepaste lay-out en opslaat als een PNG‑bestand. Je ziet de volledige, uitvoerbare code, begrijpt waarom elke instelling belangrijk is, en leert veelvoorkomende valkuilen zodat je barcode betrouwbaar werkt in productie.

In deze tutorial leer je:

* De Aspose.BarCode‑generator initialiseren voor PDF417.
* Kolom‑ en rij‑aantallen configureren om de vorm van de barcode te bepalen.
* Het resultaat exporteren als een PNG‑afbeelding van hoge kwaliteit.
* Optionele instellingen verkennen voor foutcorrectie en datalengte.

Het enige vereiste is een recente .NET‑SDK (.NET 6 of hoger) en een licentie of gratis proefversie van **Aspose.BarCode for .NET**.

---

## Vereisten en installatie

Zorg ervoor dat je het volgende hebt voordat je begint:

| Vereiste | Waarom het belangrijk is |
|----------|--------------------------|
| .NET 6 SDK of nieuwer | Biedt de runtime voor de C# console‑applicatie. |
| Visual Studio 2022 (of VS Code) | Geeft je een IDE met IntelliSense voor de Aspose‑API. |
| Aspose.BarCode for .NET NuGet‑pakket | Levert `BarcodeGenerator`, `EncodeTypes` en hulpmiddelen voor afbeeldingsexport. |
| Schrijfrechten voor de doelmap | De generator schrijft het PNG‑bestand naar de schijf. |

Je kunt het NuGet‑pakket toevoegen met het volgende commando:

```bash
dotnet add package Aspose.BarCode
```

---

## Stap 1: Maak een nieuw console‑project

Maak eerst een eenvoudige console‑applicatie die de barcode‑generatielogica host.

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

### Waarom deze code werkt

* **`BarcodeGenerator`** is het toegangspunt voor alle barcode‑typen. Door `EncodeTypes.Pdf417` door te geven, vertel je de bibliotheek een PDF417‑symbool te produceren.
* **Kolommen en rijen** zijn de belangrijkste hefbomen voor de lay-out. Minder kolommen geven een hogere barcode; meer kolommen maken deze breder. Pas deze waarden aan om te passen in de ruimte waar de afbeelding wordt weergegeven (bijv. een labelprinter versus een webpagina).
* **Foutcorrectie** verbetert de scanbetrouwbaarheid wanneer de barcode vlekkerig kan zijn of wordt afgedrukt op media van lage kwaliteit. Het standaardniveau is 0; het iets verhogen (2–4) is een goede afweging tussen grootte en robuustheid.
* **`Save`** schrijft de afbeelding naar de schijf in PNG‑formaat, wat scherpe randen behoudt en werkt in browsers en mobiele apparaten.

Wanneer je het programma uitvoert (`dotnet run`), maakt het `CustomPdf417.png` aan in de projectmap. De PNG ziet er als volgt uit:

![Generated PDF417 barcode image](https://example.com/images/pdf417-sample.png "Screenshot of generated barcode image created with PDF417 using C#")

*Alt‑tekst:* **create barcode image** – PDF417‑barcode gegenereerd in C# en opgeslagen als PNG.

---

## Stap 2: Fijn‑afstellen van de barcode voor real‑world scenario's

### Aanpassen van de datalengte

PDF417 kan tot 1.850 tekens coderen. Als je langere tekenreeksen moet coderen, overweeg dan de data over meerdere barcodes te verdelen of de **compact mode** te gebruiken:

```csharp
generator.Parameters.Barcode.Pdf417.CompactMode = true;
```

Compact mode vermindert het aantal rijen maar kan de visuele dichtheid verhogen, test dus met je scanner.

### Beheersen van de afbeeldingsgrootte

De standaardafbeeldingsgrootte wordt berekend op basis van de module‑grootte (het kleinste vierkant in de barcode). Je kunt expliciet de DPI instellen of de afbeelding na generatie schalen:

```csharp
generator.Parameters.ImageResolution = new Resolution(300); // 300 DPI for printing.
```

Of, na het opslaan, de grootte aanpassen met System.Drawing als je een miniatuur nodig hebt.

### Omgaan met speciale tekens

PDF417 ondersteunt de volledige ASCII‑set. Als je data Unicode‑tekens bevat, zorg er dan voor dat je de tekenreeks encodeert als UTF‑8:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, System.Text.Encoding.UTF8.GetString(bytes));
```

---

## Stap 3: Veelvoorkomende valkuilen en hoe ze te vermijden

| Valkuil | Symptoom | Oplossing |
|---------|----------|-----------|
| Te veel kolommen voor de gegeven data | Barcode wordt afgekapt of geeft een uitzondering. | Verminder `Columns` of laat de bibliotheek automatisch de grootte bepalen door de instelling weg te laten. |
| Lage foutcorrectie op een ruisende printer | Scanners kunnen de barcode af en toe niet lezen. | Verhoog `ErrorCorrectionLevel` tot minimaal 2. |
| Opslaan naar een alleen‑lezen map | `UnauthorizedAccessException` tijdens uitvoering. | Gebruik een schrijfbare map zoals `Environment.CurrentDirectory` of `Path.GetTempPath()`. |
| Een verouderde versie van Aspose.BarCode gebruiken | Ontbrekende eigenschappen zoals `CompactMode`. | Werk het NuGet‑pakket bij naar de nieuwste stabiele release. |

---

## Stap 4: Verifieer het resultaat

Om te bevestigen dat de barcode correct is gegenereerd, kun je:

1. Open `CustomPdf417.png` in een willekeurige afbeeldingsviewer – de barcode moet scherp zijn, met duidelijke zwarte modules op een witte achtergrond.
2. Gebruik een gratis PDF417‑scanner‑app (beschikbaar voor iOS en Android) om de afbeelding te scannen. De app moet **“Sample data for PDF417 barcode”** weergeven.
3. (Optioneel) Laad de afbeelding in een unit‑test met `System.Drawing.Bitmap` en controleer dat de pixel op `(0,0)` zwart is, wat bevestigt dat de afbeelding niet leeg is.

```csharp
using System.Drawing;

Bitmap bmp = new Bitmap("CustomPdf417.png");
bool topLeftIsBlack = bmp.GetPixel(0, 0).R == 0;
Console.WriteLine($"Top‑left pixel black? {topLeftIsBlack}");
```

Als de controle slaagt, heb je met succes **create barcode image** en **generate PDF417 barcode** programmatisch uitgevoerd.

---

## Conclusie

Je weet nu hoe je **create barcode image** in C# kunt doen door **generating PDF417 barcode** met een aangepaste lay-out, foutcorrectie aan te passen en te exporteren naar PNG. Het volledige voorbeeld toont elke benodigde stap — van het initialiseren van `BarcodeGenerator` tot het opslaan van de uiteindelijke afbeelding — zodat je het kunt kopiëren, plakken en uitvoeren in je eigen project.

Vervolgens kun je verkennen:

* **De PNG insluiten in een web‑API** zodat clients barcodes op aanvraag kunnen opvragen (`generate pdf417` als een service).
* **Batch‑generatie** voor grote datasets — loop over een lijst met strings en sla elke PNG op in een database.
* **Alternatieve uitvoerformaten** (SVG, JPEG) door `BarCodeImageFormat` te wijzigen.

Voel je vrij om te experimenteren met kolom/rij‑verhoudingen, fout‑correctieniveaus en afbeeldingsresolutie om te voldoen aan de exacte eisen van je scanner‑hardware of UI‑ontwerp. Veel plezier met coderen!

---

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe een PDF417‑barcode‑afbeelding te maken in C# – volledige gids](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)
- [Hoe een PDF417‑barcode‑afbeelding te maken in C# met Macro PDF417‑opties](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Hoe een micro‑pdf417‑barcode te maken en PNG te genereren in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}