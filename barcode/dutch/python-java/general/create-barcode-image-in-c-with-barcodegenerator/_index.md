---
category: general
date: 2026-08-12
description: Maak een barcode-afbeelding in C# met BarCodeGenerator. Leer hoe je DataBar
  genereert, de grootte van de barcode-afbeelding regelt en efficiënt meerdere barcodes
  maakt.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- create multiple barcodes
- how to generate databar
- barcode image size
language: nl
lastmod: 2026-08-12
og_description: Maak een barcode‑afbeelding in C# met BarCodeGenerator. Deze tutorial
  laat stap‑voor‑stap zien hoe je DataBar‑codes genereert, de grootte van de barcode‑afbeelding
  aanpast en meerdere barcodes maakt.
og_image_alt: Screenshot of a generated DataBar barcode image saved as PNG
og_title: Barcode‑afbeelding maken in C# – volledige BarCodeGenerator‑gids
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  headline: Create barcode image in C# with BarCodeGenerator
  type: TechArticle
- description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  name: Create barcode image in C# with BarCodeGenerator
  steps:
  - name: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
    text: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
  - name: Adjusting **barcode image size** by changing X‑dimension and bar height.
    text: Adjusting **barcode image size** by changing X‑dimension and bar height.
  - name: Using a loop to **create multiple barcodes** with different heights.
    text: Using a loop to **create multiple barcodes** with different heights.
  - name: Saving the images as PNG files and verifying the output.
    text: Saving the images as PNG files and verifying the output.
  type: HowTo
tags:
- barcode
- csharp
- barcodegenerator
- databar
- image-processing
title: Barcode-afbeelding maken in C# met BarCodeGenerator
url: /nl/python-java/general/create-barcode-image-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode-afbeelding maken in C# met BarCodeGenerator

Als je een **barcode-afbeelding** moet maken in een .NET‑applicatie, laat deze gids je precies zien hoe je dat doet met de `BarCodeGenerator`‑klasse. Of je nu een retail‑POS‑systeem of een voorraad‑volgtool bouwt, je leert DataBar‑symbolen genereren, de grootte van de barcode‑afbeelding regelen en meerdere barcodes in één keer produceren.

Je ontdekt ook hoe de **barcode generator c#**‑API je in staat stelt afmetingen aan te passen, uitvoerformaten te wisselen en randgevallen zoals ongeldige gegevensreeksen af te handelen. Aan het einde van de tutorial kun je vol vertrouwen **meerdere barcodes maken** zonder repetitieve code te schrijven.

## Vereisten

- .NET 6.0 of later geïnstalleerd  
- Een ontwikkelomgeving (Visual Studio, Rider of VS Code)  
- Het Aspose.BarCode for .NET NuGet‑pakket (of een compatibele bibliotheek die `BarCodeGenerator` levert)  

Je kunt het pakket toevoegen met:

```bash
dotnet add package Aspose.BarCode
```

## Wat deze tutorial behandelt

1. Een **barcode generator c#**‑instantie instellen voor DataBar Omni‑directionele codering.  
2. De **barcode‑afbeeldingsgrootte** aanpassen door X‑dimensie en balkhoogte te wijzigen.  
3. Een lus gebruiken om **meerdere barcodes** met verschillende hoogtes te **maken**.  
4. De afbeeldingen opslaan als PNG‑bestanden en de output verifiëren.  

Alle code‑fragmenten zijn compleet en klaar om te kopiëren‑en‑plakken in een nieuw console‑project.

![Create barcode image example](barcode-example.png){alt="Voorbeeld van barcode‑afbeelding maken"}

## Stap 1: Initialiseer de generator – basis van barcode‑afbeelding maken

De eerste stap is om `BarCodeGenerator` te instantieren met de gewenste symbologie. Voor een DataBar Omni‑directionaal symbool gebruik je `EncodeTypes.DatabarOmniDirectional`.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for DataBar Omni‑directional.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarCodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // The rest of the steps are performed below.
        }
    }
}
```

**Waarom dit belangrijk is:** Het instantieren van de generator definieert de coderingsregels en de gegevenspayload. Als je de juiste `EncodeTypes`‑waarde weglaat, zal de bibliotheek een niet‑ondersteunde barcode produceren of een uitzondering werpen.

## Stap 2: X‑dimensie en balkhoogte configureren – barcode‑afbeeldingsgrootte regelen

De visuele grootte van een barcode wordt bepaald door twee parameters:

| Parameter | Wat het regelt | Typisch bereik |
|-----------|----------------|----------------|
| `x_dimension.pixels` | Breedte van de kleinste module (de “dot”) | 1 – 4 px |
| `bar_height.pixels`  | Hoogte van de verticale balken                | 30 – 150 px |

```csharp
// Set the module width to 2 px for a crisp, readable image.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set an initial bar height of 30 px.
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**Pro tip:** Een kleinere X‑dimensie levert een hogere resolutie‑afbeelding op, maar kan moeilijker te scannen zijn op printers van lage kwaliteit. Pas de waarde aan op basis van je beoogde scanapparatuur.

## Stap 3: Sla de eerste barcode op – barcode‑afbeelding maken voor 30 px hoogte

Nu kun je de afbeelding genereren en naar schijf schrijven. De `Save`‑methode accepteert een bestandspad en een afbeeldingsformaat‑enum.

```csharp
// Save the 30 px high barcode as a PNG file.
string outputFolder = @"C:\Barcodes";
generator.Save($"{outputFolder}\\Databar30.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar30.png (30 px height)");
```

**Verwacht resultaat:** Een PNG‑bestand met de naam `Databar30.png` verschijnt in `C:\Barcodes`. Het openen van het bestand toont een DataBar Omni‑directionaal symbool met een duidelijk, hoog‑contrast patroon.

## Stap 4: Verander de hoogte en genereer extra afbeeldingen – meerdere barcodes maken

Om **meerdere barcodes** met verschillende afmetingen te **maken**, hoef je alleen de `BarHeight`‑eigenschap aan te passen en `Save` opnieuw aan te roepen. Dit voorkomt het opnieuw instantieren van de generator, wat geheugen en CPU‑tijd bespaart.

```csharp
// Increase the bar height to 60 px for a larger barcode.
generator.Parameters.Barcode.BarHeight.Pixels = 60;
generator.Save($"{outputFolder}\\Databar60.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar60.png (60 px height)");

// You can repeat the process for any height you need.
int[] heights = { 90, 120 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputFolder}\\Databar{h}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved Databar{h}.png ({h} px height)");
}
```

**Waarom dit werkt:** Het `BarCodeGenerator`‑object bewaart alle configuratiestatus. Het wijzigen van één eigenschap werkt de renderengine bij voor de volgende `Save`‑aanroep, waardoor je **meerdere barcodes** efficiënt kunt **maken**.

## Stap 5: Geavanceerd – hoe DataBar te genereren met aangepaste data

Het bovenstaande voorbeeld gebruikt een statische GS1‑payload. In real‑world scenario's moet je vaak variabele productidentifiers insluiten. De bibliotheek accepteert elke string die voldoet aan de DataBar‑specificatie.

```csharp
string[] gtins = { "01234567890123", "98765432109876", "12345678901234" };
foreach (var gtin in gtins)
{
    // GS1 Application Identifier (01) + GTIN
    generator.CodeText = $"(01){gtin}";
    generator.Parameters.Barcode.BarHeight.Pixels = 50; // uniform height
    generator.Save($"{outputFolder}\\Databar_{gtin}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode for GTIN {gtin}");
}
```

**Belangrijk punt:** Het instellen van `generator.CodeText` werkt de gecodeerde data bij zonder het object opnieuw te maken. Dit is het aanbevolen **hoe je databar genereert**‑patroon bij het verwerken van grote datasets.

## Stap 6: Verifiëren en oplossen – zorgen voor correcte barcode‑afbeeldingsgrootte

Na het genereren van de afbeeldingen wil je mogelijk programmatisch bevestigen dat de afmetingen overeenkomen met je verwachtingen. De `Image`‑klasse uit `System.Drawing` kan het bestand lezen en de grootte rapporteren.

```csharp
using System.Drawing;

// Verify image dimensions
string[] files = { "Databar30.png", "Databar60.png", "Databar90.png" };
foreach (var file in files)
{
    using var img = Image.FromFile($"{outputFolder}\\{file}");
    Console.WriteLine($"{file}: {img.Width}px × {img.Height}px");
}
```

Als de hoogte niet overeenkomt met de ingestelde waarde, controleer dan:

- **X‑dimensie**: Een zeer kleine waarde kan ervoor zorgen dat de renderer de hoogte afrondt.
- **Afbeeldingsformaat**: Sommige formaten (bijv. JPEG) passen compressie toe die de pixelafmetingen bij het opslaan kan wijzigen. PNG behoudt exacte afmetingen.

## Stap 7: Best practices voor barcode‑afbeeldingsgrootte en prestaties

| Aanbeveling | Reden |
|------------|-------|
| Houd `x_dimension.pixels` tussen 2 – 3 px voor de meeste scanners. | Balans tussen leesbaarheid en bestandsgrootte. |
| Gebruik PNG voor lossless output wanneer de afbeelding wordt afgedrukt. | Garandeert exacte afmetingen en scherpe randen. |
| Hergebruik een enkele `BarCodeGenerator`‑instantie bij het genereren van veel barcodes. | Vermindert overhead van objectallocatie. |
| Valideer de invoerstring tegen de GS1‑standaard voordat je deze toewijst aan `CodeText`. | Voorkomt runtime‑exceptions en ongeldige scans. |
| Sla gegenereerde afbeeldingen op in een speciale map met een duidelijke naamgevingsconventie (bijv. `Databar_{GTIN}.png`). | Vereenvoudigt downstream verwerking en audit‑trails. |

## Volledig werkend voorbeeld

Hieronder staat het volledige programma dat alle stappen van initialisatie tot verificatie bevat. Kopieer de code naar een nieuw console‑project en voer het uit.



## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Barcode‑afbeelding genereren – GS1 Coupon UPC‑A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [DotCode barcode‑afbeelding maken – rijen & kolommen (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Hoe een Barcode Quiet Zone te maken voor ITF‑14 met Aspose.BarCode voor .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}