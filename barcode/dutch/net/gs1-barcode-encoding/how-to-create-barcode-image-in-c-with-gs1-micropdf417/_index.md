---
category: general
date: 2026-11-14
description: Leer hoe je een barcode‑afbeelding maakt in C# met Aspose.BarCode. Deze
  stapsgewijze handleiding behandelt de barcode‑generator C#‑configuratie, GS1‑opmaak
  en PNG‑export.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create gs1 barcode
- barcode image from data
language: nl
lastmod: 2026-11-14
og_description: Maak snel een barcode‑afbeelding in C#. Volg deze gids om te leren
  hoe je een barcode genereert, de barcode‑generator in C# gebruikt en een GS1 MicroPDF417‑PNG
  exporteert.
og_image_alt: Screenshot of a GS1 MicroPDF417 barcode generated in C#
og_title: Barcode‑afbeelding maken in C# – volledige gids voor GS1 MicroPDF417
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create barcode image in C# using Aspose.BarCode. This
    step‑by‑step guide covers barcode generator c# setup, GS1 formatting and PNG export.
  headline: How to create barcode image in C# with GS1 MicroPDF417
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Hoe maak je een barcode‑afbeelding in C# met GS1 MicroPDF417
url: /nl/net/gs1-barcode-encoding/how-to-create-barcode-image-in-c-with-gs1-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een barcode‑afbeelding maken in C# met GS1 MicroPDF417

Als je een **barcode‑afbeelding wilt maken** in C#, laat deze gids je een complete, kant‑klaar oplossing zien. Je ziet **hoe je barcode‑gegevens** genereert die voldoen aan de GS1‑standaard, configureert de generator en exporteert een hoogwaardige PNG‑bestand.

De tutorial behandelt alles van het installeren van de benodigde bibliotheek tot het omgaan met veelvoorkomende valkuilen in gegevensformaten. Aan het einde kun je een **barcode‑afbeelding uit gegevens** maken met slechts een paar regels code, en begrijp je waarom elke instelling belangrijk is.

## Vereisten

Voordat je begint, zorg dat je het volgende hebt:

* .NET 6.0 of later geïnstalleerd (de code werkt ook met .NET Framework 4.7+).
* Een IDE zoals Visual Studio 2022 of Visual Studio Code.
* Het **Aspose.BarCode for .NET** NuGet‑pakket. Installeer het met:

```bash
dotnet add package Aspose.BarCode
```

* Basiskennis van C#‑syntaxis en het GS1 Application Identifier (AI)‑formaat.

> **Pro tip:** Houd de bibliotheekversie up‑to‑date; de nieuwste release voegt ondersteuning toe voor nieuwere barcode‑symbologieën en prestatie‑verbeteringen.

## Barcode‑afbeelding maken met BarcodeGenerator

Dit gedeelte bevat de kernimplementatie. De code maakt een **barcode generator c#**‑instantie, configureert de X‑dimensie voor leesbaarheid en slaat het resultaat op als een PNG‑bestand.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialise the generator with the GS1 MicroPDF417 symbology
// The data string follows the GS1 syntax: (01)GTIN(21)SerialNumber
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,
    "(01)12345678901234(21)ABC123");

// Step 2: Adjust the module width (X‑dimension) to improve scan reliability
// A value of 2 pixels works well for most screen‑displayed barcodes.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Export the barcode as a PNG image
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "GS1MicroPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
```

### Waarom elke regel belangrijk is

* **EncodeTypes.MicroPdf417** vertelt de bibliotheek om de GS1 MicroPDF417‑symbologie te gebruiken, die compact is en ideaal voor mobiel scannen.
* De **data‑string** moet beginnen met de GS1 AI `(01)` voor het Global Trade Item Number (GTIN) gevolgd door `(21)` voor het serienummer. Als het formaat onjuist is, gooit de generator een uitzondering.
* **XDimension.Pixels** bepaalt de breedte van de kleinste balk. Een hogere waarde verbetert de leesbaarheid op lage‑resolutie‑schermen, terwijl een lagere waarde de afbeeldingsgrootte verkleint.
* **BarCodeImageFormat.Png** levert een verliesvrije afbeelding, waardoor de scherpe randen behouden blijven die nodig zijn voor betrouwbaar scannen.

Het uitvoeren van het programma maakt `GS1MicroPdf417.png` op je bureaublad. Het openen van het bestand toont een dichte, zwart‑op‑wit barcode die het GTIN `12345678901234` en het serienummer `ABC123` codeert.

## Hoe een barcode genereren met GS1 MicroPDF417

Als je nieuw bent met GS1‑formattering, zijn hier de essentiële regels:

| GS1 AI | Betekenis                     | Voorbeeld |
|--------|------------------------------|-----------|
| (01)   | Global Trade Item Number     | 12345678901234 |
| (21)   | Serienummer (optioneel)      | ABC123 |

Wanneer je de AI’s met hun waarden aan elkaar plakt, zet je elke AI tussen haakjes en plaats je de waarden direct erna. De resulterende string kan zonder verdere codering aan de **barcode generator c#** worden doorgegeven.

### Veelvoorkomende valkuilen

* **Ontbrekende haakjes** – De generator behandelt de string als ruwe data en past geen GS1‑controles toe.
* **Overschrijding van lengtelimieten** – MicroPDF417 ondersteunt maximaal 155 tekens. Verwijder onnodige spaties.
* **Ongeldige tekens** – Alleen numerieke tekens zijn toegestaan voor het GTIN; het serienummer mag hoofdletters en cijfers bevatten.

## De barcode‑afbeelding aanpassen op basis van gegevens

Naast de basis‑X‑dimensie biedt Aspose.BarCode vele visuele aanpassingen. Hieronder staan enkele instellingen die je kunt toepassen, afhankelijk van de eisen van je project.

```csharp
// Set background to transparent (useful for overlaying on UI)
generator.Parameters.ImageBackgroundColor = Color.Transparent;

// Change foreground color to dark blue for branding
generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);

// Increase image resolution to 300 dpi for print‑ready output
generator.Parameters.ImageResolution = 300;
```

Elke instelling is optioneel; de standaardwaarden leveren al een nette, scanbare **barcode‑afbeelding** op. Experimenteer pas met kleuren en resoluties nadat je hebt bevestigd dat scanners de code nog steeds kunnen lezen.

## De barcode opslaan in andere formaten

Hoewel PNG het meest gebruikte formaat is voor web en mobiel, kun je ook JPEG, BMP of SVG nodig hebben. De `Save`‑methode accepteert elke `BarCodeImageFormat`‑waarde.

```csharp
generator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

* JPEG verkleint de bestandsgrootte maar introduceert compressie‑artefacten die de leesbaarheid kunnen beïnvloeden.
* SVG behoudt vector‑kwaliteit en is ideaal voor responsieve webontwerpen.

## De gegenereerde barcode verifiëren

Een snelle manier om te bevestigen dat de stap **create barcode image** geslaagd is, is een mobiele scanner‑app te gebruiken die GS1 MicroPDF417 ondersteunt. Scan de opgeslagen PNG; de app zou moeten tonen:

```
GTIN: 12345678901234
Serial: ABC123
```

Als de scanner een fout meldt, controleer dan de AI‑formattering en de X‑dimensie‑waarde nogmaals.

## Volledig voorbeeld – een zelfstandige console‑applicatie

Hieronder vind je een compleet programma dat je kunt kopiëren, plakken en uitvoeren zonder aanpassingen (behalve de NuGet‑installatiestap).

```csharp
using System;
using System.IO;
using System.Drawing;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with GS1 MicroPDF417 and sample data
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "(01)12345678901234(21)ABC123");

            // Improve readability by setting module width
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Optional visual customisation
            generator.Parameters.ImageBackgroundColor = Color.Transparent;
            generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);
            generator.Parameters.ImageResolution = 300;

            // Define output path (Desktop folder)
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "GS1MicroPdf417.png");

            // Save the barcode as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

Wanneer je het programma uitvoert, print de console het volledige bestandspad en verschijnt de PNG op je bureaublad. Dit voorbeeld laat zien **hoe je barcode‑gegevens genereert**, het uiterlijk aanpast en een **barcode‑afbeelding uit gegevens** exporteert in één samenhangende workflow.

## Veelgestelde vragen

| Vraag | Antwoord |
|----------|--------|
| *Kan ik andere GS1‑symbologieën genereren?* | Ja. Vervang `EncodeTypes.MicroPdf417` door `EncodeTypes.Pdf417`, `EncodeTypes.DataMatrix`, enz., en pas de data‑string dienovereenkomstig aan. |
| *Wat als mijn gegevens de capaciteit van MicroPDF417 overschrijden?* | Schakel over naar de reguliere PDF417‑symbologie, die langere payloads ondersteunt. |
| *Heb ik een licentie nodig voor Aspose.BarCode?* | Een gratis evaluatielicentie werkt voor ontwikkeling. Voor productie moet je een licentie aanschaffen om het evaluatiewatermerk te verwijderen. |
| *Is de PNG geschikt voor het afdrukken op etiketten?* | Verhoog `ImageResolution` naar 300 dpi of hoger, en overweeg opslaan als TIFF voor industriële printers. |

## Conclusie

Je weet nu hoe je een **barcode‑afbeelding maakt** in C# met de **barcode generator c#**‑aanpak, gegevens formatteert voor een **create gs1 barcode**‑scenario, en het resultaat exporteert als PNG of een ander afbeeldingsformaat. Het volledige voorbeeld toont elke stap – van gegevensvoorbereiding tot visuele aanpassing – zodat je barcode‑creatie kunt integreren in elke .NET‑applicatie.

Ga vervolgens aan de slag met gerelateerde onderwerpen zoals **barcode image from data** voor QR‑codes, meerdere barcodes toevoegen aan één PDF, of batch‑generatie automatiseren voor voorraadbeheersystemen. Experimenteer met verschillende X‑dimensie‑waarden en afbeeldingsformaten om de optimale balans te vinden voor jouw specifieke scan‑omgeving.

Veel programmeerplezier, en laat je applicaties **barcode‑afbeeldingen maken** die betrouwbaar werken in de echte wereld!


## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [How to create barcode image with Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [How to create postal barcode image in C# using Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)
- [How to create PDF417 barcode image in C# – complete guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}