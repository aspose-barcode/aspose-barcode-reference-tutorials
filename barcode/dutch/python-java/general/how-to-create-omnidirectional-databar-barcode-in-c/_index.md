---
category: general
date: 2026-09-29
description: Leer hoe je een omnidirectionele Databar‑barcode maakt in C# met Aspose.BarCode.
  Pas de X‑dimensie aan, stel de beeldverhouding in en sla PNG‑afbeeldingen op.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional databar barcode
- DataBar stacked omnidirectional barcode
- set barcode aspect ratio
- Aspose.BarCode C#
- generate barcode image
language: nl
lastmod: 2026-09-29
og_description: Maak een omnidirectionele Databar-barcode in C# met Aspose.BarCode.
  Leer hoe u de X‑dimensie instelt, de beeldverhouding aanpast en PNG‑bestanden exporteert.
og_image_alt: Screenshot showing two PNG files of an omnidirectional Databar barcode
  with different aspect ratios
og_title: Maak een omnidirectionele Databar‑barcode in C# – stap‑voor‑stap gids
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  headline: How to create omnidirectional Databar barcode in C#
  type: TechArticle
- description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  name: How to create omnidirectional Databar barcode in C#
  steps:
  - name: What if I need a different X‑dimension?
    text: You can assign any integer value to `XDimension.Pixels`. Values below `1`
      are ignored, and values above `10` may produce oversized modules that exceed
      printer margins. Test the visual output after each change.
  - name: How do I encode other AI‑generated data (e.g., UPC, EAN)?
    text: Replace the data string in the `BarcodeGenerator` constructor with the appropriate
      Application Identifier (AI). For a UPC‑A code, use `"012345678905"` without
      an AI prefix.
  - name: Can I export to formats other than PNG?
    text: Yes. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`,
      `BarCodeImageFormat.Tiff`, and `BarCodeImageFormat.Bmp`. Choose the format that
      matches your downstream workflow.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Hoe maak je een omnidirectionele Databar-barcode in C#
url: /nl/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe maak je een omnidirectionele Databar barcode in C#

Als je een **omnidirectionele Databar barcode** moet maken in een .NET‑applicatie, laat deze gids je de exacte stappen zien. Je ziet hoe je een DataBar stacked omnidirectional barcode initialiseert, de X‑dimension configureert, de aspectratio wijzigt en PNG‑afbeeldingen genereert met Aspose.BarCode.

Het genereren van een **DataBar stacked omnidirectional barcode** is gebruikelijk wanneer je productidentifiers moet coderen voor retail‑scanners. In deze tutorial leer je hoe je de **barcode aspect ratio** instelt, de modulegrootte beheert en het resultaat exporteert zonder de IDE te verlaten.

## Vereisten

- .NET 6.0 of later geïnstalleerd
- Visual Studio 2022 (of een andere C#‑compatibele IDE)
- Het **Aspose.BarCode for .NET** NuGet‑pakket (versie 23.12 of nieuwer)

Je kunt het pakket toevoegen via de NuGet Package Manager:

```bash
dotnet add package Aspose.BarCode
```

## Stap 1: Initialise de omnidirectionele Databar barcode

De eerste stap is het maken van een `BarcodeGenerator`‑instantie die zich richt op de **DataBar stacked omnidirectional**‑symbologie. De constructor ontvangt het encode‑type en de gegevensreeks.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialise a DataBar stacked omnidirectional barcode with GTIN data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Waarom dit belangrijk is:** De waarde `EncodeTypes.DatabarStackedOmniDirectional` vertelt Aspose.BarCode om het specifieke omnidirectionele Databar‑formaat te renderen, wat nodig is voor scannen in beide richtingen.

## Stap 2: Definieer de X‑dimension (modulegrootte)

De X‑dimension bepaalt de breedte van een enkele barcode‑module in pixels. Een waarde van `2` pixels werkt goed voor weergave op het scherm en de meeste printers.

```csharp
        // Set the basic size of the barcode modules (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Waarom dit belangrijk is:** Een consistente X‑dimension zorgt ervoor dat de barcode voldoet aan de minimale groottespecificaties voor retail‑scanners, terwijl de bestandsgrootte van de afbeelding beheersbaar blijft.

## Stap 3: Stel de eerste aspectratio in en sla de afbeelding op

De **aspectratio** bepaalt de hoogte‑tot‑breedteverhouding van de DataBar. Een aspectratio van `15` levert een compacte, hoge barcode op die ideaal is voor smalle labelruimtes.

```csharp
        // Apply aspect ratio 15 and save the first PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Waarom dit belangrijk is:** Het aanpassen van de aspectratio stelt je in staat de barcode in verschillende labelindelingen te passen zonder de leesbaarheid op te offeren. De opgeslagen PNG kan in elke afbeeldingsviewer worden bekeken.

## Stap 4: Wijzig de aspectratio en genereer een tweede afbeelding

Soms is een bredere barcode nodig — bijvoorbeeld wanneer het label meer horizontale ruimte heeft. Het wijzigen van de ratio naar `30` creëert een platter uiterlijk.

```csharp
        // Change aspect ratio to 30 and save a second PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Waarom dit belangrijk is:** Door de eigenschap **set barcode aspect ratio** beschikbaar te stellen, kun je meerdere barcode‑variaties produceren vanuit één code‑basis, waardoor geautomatiseerde labelgeneratie‑pijplijnen worden vereenvoudigd.

## Verwachte output

Het uitvoeren van het programma genereert twee PNG‑bestanden in de output‑map van de applicatie:

| Bestandnaam                | Aspectratio | Visuele beschrijving |
|----------------------------|-------------|----------------------|
| `DatabarAspectRatio15.png` | 15          | Hoge, smalle barcode geschikt voor smalle labels |
| `DatabarAspectRatio30.png` | 30          | Bredere barcode die meer horizontale ruimte vult |

Je kunt deze afbeeldingen in rapporten insluiten, afdrukken op productverpakkingen, of naar een webservice sturen voor verdere verwerking.

![Voorbeeld van een omnidirectionele Databar barcode](databar-example.png "Voorbeeld van een omnidirectionele Databar barcode")

*De screenshot toont de twee gegenereerde PNG‑bestanden naast elkaar.*

## Veelgestelde vragen en randgevallen

### Wat als ik een andere X‑dimension nodig heb?

Je kunt elke gehele waarde toewijzen aan `XDimension.Pixels`. Waarden onder `1` worden genegeerd, en waarden boven `10` kunnen te grote modules veroorzaken die de printermarges overschrijden. Test de visuele output na elke wijziging.

### Hoe codeer ik andere AI‑gegenereerde gegevens (bijv. UPC, EAN)?

Vervang de gegevensreeks in de `BarcodeGenerator`‑constructor door de juiste Application Identifier (AI). Voor een UPC‑A‑code gebruik je `"012345678905"` zonder een AI‑prefix.

### Kan ik exporteren naar andere formaten dan PNG?

Ja. De `Save`‑methode accepteert `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`, `BarCodeImageFormat.Tiff` en `BarCodeImageFormat.Bmp`. Kies het formaat dat past bij je downstream‑workflow.

## Pro‑tip: hergebruik de generator voor batchverwerking

Als je tientallen barcodes moet genereren met verschillende aspectratio's, houd dan de `BarcodeGenerator`‑instantie actief en wijzig alleen `DataBar.AspectRatio` vóór elke `Save`. Dit voorkomt de overhead van het opnieuw instantiëren van de generator voor elke afbeelding.

```csharp
var ratios = new[] { 10, 15, 20, 30 };
foreach (var ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    generator.Save($"DatabarAspectRatio{ratio}.png", BarCodeImageFormat.Png);
}
```

## Conclusie

Je weet nu hoe je een **omnidirectionele Databar barcode** in C# kunt **maken** met Aspose.BarCode. Door een `BarcodeGenerator` te initialiseren, de X‑dimension in te stellen, de **set barcode aspect ratio** aan te passen en PNG‑bestanden op te slaan, kun je barcode‑afbeeldingen produceren die voldoen aan diverse labelvereisten.  

Vervolgens kun je gerelateerde onderwerpen verkennen, zoals **generate barcode image** voor QR‑codes, **DataBar stacked omnidirectional barcode** validatie, of het integreren van de gegenereerde PNG‑bestanden in PDF‑facturen met Aspose.PDF. Experimenteer met verschillende aspectratio's en modulegroottes om de optimale configuratie voor jouw specifieke printerhardware te vinden.

---

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe een barcode‑generator C# te gebruiken om DataBar Omni‑directional barcodes te maken](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [databar stacked omnidirectional barcode in C# – Complete Gids](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [Hoe een barcode te genereren in C# – barcode‑afbeelding maken c# met DataBar Expanded](/barcode/english/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}