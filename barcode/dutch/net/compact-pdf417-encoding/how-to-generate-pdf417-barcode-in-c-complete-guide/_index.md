---
category: general
date: 2026-09-26
description: Genereer PDF417‑barcode in C# met Aspose.BarCode. Volg deze stapsgewijze
  tutorial om kolommen te configureren, compacte modus in te schakelen en op te slaan
  als PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- pdf417 barcode generator c#
- Aspose.BarCode C#
- barcode image format PNG
- compact PDF417 mode
language: nl
lastmod: 2026-09-26
og_description: Genereer PDF417-barcode in C# met Aspose.BarCode. Deze gids laat zien
  hoe je kolommen instelt, compacte modus inschakelt en het resultaat exporteert als
  een PNG-afbeelding.
og_image_alt: Screenshot of a generated PDF417 barcode saved as PNG
og_title: Genereer PDF417‑barcode in C# – stapsgewijze tutorial
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Generate PDF417 barcode in C# with Aspose.BarCode. Follow this step‑by‑step
    tutorial to configure columns, enable compact mode, and save as PNG.
  headline: How to generate PDF417 barcode in C# – complete guide
  type: TechArticle
tags:
- C#
- barcode
- Aspose
- PDF417
title: Hoe PDF417-barcode te genereren in C# – volledige gids
url: /nl/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417 barcode genereren in C# – volledige gids

Als je een **PDF417 barcode moet genereren** in een .NET‑applicatie, laat deze tutorial je een kant‑klaar werkende oplossing zien. Je ziet hoe je de barcode‑grootte, het aantal kolommen en de compacte modus kunt configureren, en vervolgens het resultaat opslaat als een PNG‑bestand van hoge kwaliteit.

Het genereren van een barcode is een veelvoorkomende eis voor voorraadsystemen, ticketplatforms en documentcodering. Aan het einde van deze gids heb je een zelfstandige C#‑programma dat een compacte PDF417 barcode produceert met behulp van de **pdf417 barcode generator C#** bibliotheek van Aspose.

## Wat je nodig hebt

- .NET 6.0 SDK of later (de code werkt ook met .NET Framework 4.7+)
- Een geldige Aspose.BarCode for .NET‑licentie (de gratis evaluatie werkt voor testen)
- Een IDE of editor zoals Visual Studio 2022, Rider, of VS Code
- Basiskennis van C# console‑projecten

> **Pro tip:** Als je de gratis evaluatie gebruikt, zal de gegenereerde afbeelding een klein Aspose‑watermerk bevatten. Een aangeschafte licentie verwijdert het watermerk en ontgrendelt de volledige functionaliteit.

## Stap 1: Installeer de Aspose.BarCode‑bibliotheek

Maak een nieuw console‑project aan en voeg het Aspose.BarCode NuGet‑pakket toe.

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Het pakket levert de `BarcodeGenerator`‑klasse, die de kern vormt van de **pdf417 barcode generator C#** workflow.

## Stap 2: Schrijf het volledige barcode‑generatieprogramma

Open `Program.cs` en vervang de inhoud door de volgende code. Het programma toont elke benodigde stap, van het initialiseren van de generator tot het opslaan van de afbeelding.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace Pdf417Demo
{
    internal class Program
    {
        private static void Main()
        {
            // Step 2.1: Create a generator for PDF417 with Unicode text.
            // The text contains special characters to prove Unicode handling.
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // Step 2.2: Define the module (pixel) size of each barcode element.
            // XDimension controls the width of a single bar; 2 pixels gives a clear image.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.3: Set the number of columns.
            // PDF417 can automatically choose columns, but fixing it to 3 produces a compact layout.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.4: Enable compact mode.
            // Truncate reduces the amount of data stored, making the barcode smaller.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.5: Choose the output format and file path.
            // PNG preserves the exact pixel dimensions without compression artifacts.
            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### Waarom elke regel belangrijk is

| Regel | Doel |
|------|------|
| `new BarcodeGenerator(EncodeTypes.Pdf417, "...")` | Instantieert een PDF417‑generator en stelt de te coderen tekst in. PDF417 ondersteunt grote datasets en Unicode, waardoor het geschikt is voor complexe identifiers. |
| `XDimension.Pixels = 2` | Regelt de visuele dichtheid. Kleinere waarden produceren fijnere strepen; grotere waarden verbeteren de leesbaarheid op schermen met lage resolutie. |
| `Pdf417.Columns = 3` | Negeert de automatische kolomcalculatie. Vaste kolommen zijn handig wanneer je de barcode in een vooraf gedefinieerde ruimte moet passen. |
| `Pdf417.Truncate = true` | Activeert compacte modus, die onnodige opvulling verwijdert en de totale grootte verkleint. |
| `Save(..., BarCodeImageFormat.Png)` | Schrijft de barcode naar een PNG‑bestand, een verliesvrij formaat dat ideaal is voor verdere verwerking of insluiting in PDF‑bestanden. |

## Stap 3: Voer het programma uit en controleer de output

Bouw en voer het project uit:

```bash
dotnet run
```

Je zou een console‑bericht moeten zien dat de bestandslocatie bevestigt, en een bestand met de naam **CompactPdf417.png** zal verschijnen in de projectmap.

![Generated PDF417 barcode example](images/compact-pdf417.png){.img-responsive alt="Voorbeeld van gegenereerde PDF417 barcode"}

*De afbeelding toont een compacte PDF417 barcode die de tekenreeks “Åspóse.Barcóde©” codeert.*

Als je de PNG opent in een afbeeldingsviewer, zie je drie kolommen van gestapelde datablocks, elke staaf 2 pixels breed. Het scannen van de barcode met een standaard PDF417‑lezer geeft de oorspronkelijke tekst terug, wat bevestigt dat de generator naar verwachting werkt.

## Veelvoorkomende valkuilen en hoe ze te vermijden

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| Barcode is onscherp | XDimension is te laag ingesteld voor de doel‑DPI | Verhoog `XDimension.Pixels` naar 3 of 4, of render op een hogere resolutie met `generator.Save(..., BarCodeImageFormat.Tiff)` |
| Unicode‑tekens gaan verloren | De invoertekenreeks is niet gecodeerd als UTF‑8 | Zorg ervoor dat het bronbestand is opgeslagen met UTF‑8‑codering; de generator verwerkt Unicode automatisch wanneer het type `string` is. |
| Truncate veroorzaakt een uitzondering | De gegevensgrootte overschrijdt het maximum voor het gekozen aantal kolommen | Verhoog `Pdf417.Columns` of stel `Pdf417.Truncate = false` in zodat de generator voldoende ruimte toewijst. |
| Licentie niet toegepast | Evaluatieversie voegt een watermerk toe | Pas een geldig licentiebestand toe via `Aspose.BarCode.License` voordat de generator wordt aangemaakt. |

## De oplossing uitbreiden

Zodra je de basisstroom **generate PDF417 barcode** hebt, kun je extra functies verkennen:

- **Foutcorrectieniveau** – Pas `generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel` aan om de veerkracht tegen beschadiging te verhogen.
- **Kleuraanpassing** – Gebruik `generator.Parameters.Barcode.ForegroundColor` en `BackgroundColor` om te voldoen aan merkrichtlijnen.
- **Insluiten in PDF's** – Combineer Aspose.PDF met Aspose.BarCode om de barcode direct in een PDF‑document te plaatsen.
- **Batch‑generatie** – Loop over een verzameling identifiers om meerdere PNG‑bestanden in één uitvoering te produceren.

Al deze opties zijn gedocumenteerd in de Aspose.BarCode API‑referentie en volgen hetzelfde patroon als hierboven getoond.

## Conclusie

Je weet nu hoe je een **PDF417 barcode kunt genereren** in C# met Aspose.BarCode, kolommen kunt configureren, compacte modus kunt inschakelen en het resultaat kunt exporteren als een PNG‑afbeelding. Het volledige voorbeeld werkt direct en kan worden aangepast voor grotere projecten, zoals ticketingsystemen, voorraadlabels of veilige documentcodering.

Probeer vervolgens de geavanceerde instellingen van de **pdf417 barcode generator C#**, zoals foutcorrectie en kleuraanpassing, of integreer de barcode in een PDF‑rapport met Aspose.PDF. Experimenteer met verschillende `XDimension`‑waarden en kolomaantallen om de optimale balans tussen grootte en scanbetrouwbaarheid voor jouw specifieke geval te vinden. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [PDF417 barcode genereren in C# – volledige gids met compacte lay-out](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide-with-compact-lay/)
- [Aspose barcode voorbeeld: Macro PDF417 genereren in C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Hoe barcode opslaan in C# – PDF417 barcodes genereren](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}