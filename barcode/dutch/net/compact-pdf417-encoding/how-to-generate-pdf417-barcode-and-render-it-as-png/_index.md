---
category: general
date: 2026-11-17
description: Leer hoe je een PDF417‑barcode genereert, de barcodegrootte instelt en
  de barcode rendert naar een afbeelding met C#. Complete stapsgewijze handleiding.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- render barcode to image
- how to set barcode size
language: nl
lastmod: 2026-11-17
og_description: Genereer PDF417-barcode in C# en render de barcode naar een afbeelding.
  Volg deze gids om de barcodegrootte in te stellen en een PNG-bestand op te slaan.
og_image_alt: Screenshot of a generated PDF417 barcode saved as a PNG image
og_title: Genereer PDF417-barcode en render als PNG – C#-gids
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
title: Hoe PDF417-barcode te genereren en als PNG weer te geven
url: /nl/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417-barcode te genereren en weer te geven als PNG

Als je een **PDF417-barcode wilt genereren** in een .NET‑applicatie, laat deze tutorial je precies zien hoe. Je ziet hoe je de barcode‑grootte instelt, de lay‑out configureert en **barcode naar afbeelding rendert** met slechts een paar regels C#‑code.

Het genereren van een PDF417-barcode is gebruikelijk wanneer je grote hoeveelheden data wilt coderen voor scanning op mobiele apparaten of printers. Aan het einde van deze gids heb je een kant‑klaar PNG‑bestand dat je kunt insluiten in rapporten, e‑mails of webpagina's.

## Vereisten

- .NET 6.0 SDK of later geïnstalleerd  
- Een C#‑IDE zoals Visual Studio 2022 (elke editor werkt)  
- Het **Aspose.BarCode for .NET** NuGet‑pakket (of een andere compatibele bibliotheek die `BarcodeGenerator` levert)  

Je kunt het pakket toevoegen met:

```bash
dotnet add package Aspose.BarCode
```

## Stap 1: Maak een C#‑consoleproject

Eerst, zet een minimale console‑applicatie op die de barcode‑generatiecode zal hosten.

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

> **Pro tip:** Houd de `Main`‑methode kort en delegeer het zware werk aan hulpfuncties. Dit verbetert de leesbaarheid en maakt unit‑testen makkelijker.

## Stap 2: Genereer PDF417-barcode met aangepaste grootte

Nu gaan we **PDF417-barcode genereren** en de module‑grootte (X‑dimensie) opgeven. De X‑dimensie bepaalt hoe breed elk klein vierkantje van de barcode is, waardoor de totale barcode‑grootte wordt ingesteld.

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

### Waarom de X‑dimensie instellen?

De stap **hoe barcode‑grootte in te stellen** is belangrijk omdat een te kleine X‑dimensie de barcode onleesbaar kan maken op laag‑resolutie‑scanners, terwijl een te grote waarde ruimte verspilt. Een waarde van `2` pixels werkt goed voor de meeste schermweergaven en afdruksituaties.

## Stap 3: Roep de generatiemethode aan vanuit `Main`

Koppel alles samen door `GeneratePdf417` aan te roepen met de gewenste tekst en uitvoerlocatie.

```csharp
static void Main(string[] args)
{
    string barcodeText = "Layout demo";
    string outputFile = @"C:\Barcodes\LayoutPdf417.png";

    GeneratePdf417(barcodeText, outputFile);

    Console.WriteLine($"PDF417 barcode saved to {outputFile}");
}
```

Het uitvoeren van het programma maakt `LayoutPdf417.png` aan die de barcode bevat:

![Gegenereerde PDF417-barcode](/images/layout-pdf417.png "PDF417-barcode gegenereerd door de tutorialcode"){: .align-center alt="Gegenereerde PDF417-barcode opgeslagen als PNG"}

> **Verwachte output:** Een PNG‑bestand van ongeveer 200 × 100 px (afhankelijk van kolom‑/rij‑instellingen) dat een duidelijk PDF417‑patroon toont, klaar om gescand te worden.

## Stap 4: Verifieer dat de barcode werkt

Om te verzekeren dat de barcode geldig is:

1. Open het PNG‑bestand in een willekeurige afbeeldingsviewer.  
2. Gebruik een smartphone‑barcode‑scanapp die PDF417 ondersteunt (bijv. Google Lens, QR & Barcode Scanner).  
3. Scan de afbeelding; de app zou de tekst *Layout demo* moeten teruggeven.

Als het scannen mislukt, controleer dan de X‑dimensie en kolom‑/rij‑waarden nogmaals—grotere modules verbeteren de leesbaarheid op laag‑resolutie‑camera's.

## Veelvoorkomende variaties en randgevallen

| Scenario | Aanpassing |
|----------|------------|
| **Meer data** (bijv. een URL) | Verhoog `Columns` of `Rows` om extra codewoorden te huisvesten. |
| **Print met hoge resolutie** | Verhoog `XDimension.Pixels` naar 3‑4 px voor scherpere balken. |
| **Transparante achtergrond** | Gebruik `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })`. |
| **Ander afbeeldingsformaat** | Vervang `BarCodeImageFormat.Png` door `Jpeg` of `Bmp` indien nodig. |

Deze variaties beantwoorden de **hoe PDF417 te genereren** vraag voor verschillende eisen, terwijl de kernlogica identiek blijft.

## Conclusie

Je weet nu hoe je **PDF417-barcode kunt genereren**, **barcode‑grootte kunt instellen**, en **barcode naar afbeelding kunt renderen** met C#. Het volledige, uitvoerbare voorbeeld maakt een PNG‑bestand dat overal kan worden ingebed waar je een machinale leesbare barcode nodig hebt.

Vervolgens kun je gerelateerde onderwerpen verkennen, zoals **het PNG in een PDF insluiten** (zoek op *render barcode to PDF*), of **andere 2‑D barcodes genereren** zoals QR‑codes. Pas de lay‑out‑parameters aan om bij je UI‑ontwerp te passen, en experimenteer met kleuropties voor branding.

Veel programmeerplezier, en laat je barcodes het zware werk doen!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PDF417-barcode te genereren in C# – volledige stap‑voor‑stap gids](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Hoe micro‑PDF417-barcode te genereren in C# – stap‑voor‑stap gids](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [Hoe foutenniveau in PDF417-barcode in te stellen – volledige gids](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}