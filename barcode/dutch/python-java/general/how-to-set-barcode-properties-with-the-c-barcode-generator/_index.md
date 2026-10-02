---
category: general
date: 2026-09-10
description: Hoe een barcode in C# in te stellen met een Barcode Generator. Pas de
  modulebreedte van de barcode aan, genereer barcode‑afbeeldingen en leer hoe je barcodebestanden
  opslaat.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- c# barcode generator
- barcode module width
- how to generate barcode
- how to save barcode
language: nl
lastmod: 2026-09-10
og_description: Hoe een barcode in C# in te stellen met een Barcode Generator. Leer
  de modulebreedte aan te passen, een barcode te genereren en de barcode‑afbeelding
  efficiënt op te slaan.
og_image_alt: Screenshot showing a Planet barcode with filled and empty bars generated
  by C# code
og_title: Hoe barcode‑eigenschappen instellen met C# Barcode Generator
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: How to set barcode in C# using a Barcode Generator. Adjust barcode
    module width, generate barcode images, and learn how to save barcode files.
  headline: How to set barcode properties with the C# Barcode Generator
  type: TechArticle
tags:
- barcode
- c#
- image generation
title: Hoe barcode‑eigenschappen instellen met de C# Barcode Generator
url: /nl/python-java/general/how-to-set-barcode-properties-with-the-c-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe barcode‑eigenschappen in te stellen met de C# Barcode Generator

Hoe barcode‑eigenschappen in te stellen is essentieel wanneer je nauwkeurige controle nodig hebt over de visuele stijl van een barcode. Deze gids laat zien hoe je een Planet‑barcode genereert, de module‑breedte van de barcode aanpast en de barcode‑afbeelding opslaat met de C# Barcode Generator.

Je ziet een compleet, uitvoerbaar voorbeeld dat elke stap behandelt, van het maken van het barcode‑object tot het schrijven van de PNG‑bestanden naar de schijf. Geen externe documentatie nodig – alleen de onderstaande code en de Aspose.BarCode‑bibliotheek (of een andere compatibele barcode‑SDK). Aan het einde van de tutorial kun je vragen beantwoorden zoals “hoe een barcode met aangepaste afmetingen te genereren?” en “hoe een barcode in verschillende formaten op te slaan?”.

## Voorvereisten

Voordat je begint, zorg dat je het volgende hebt:

* .NET 6.0 of later geïnstalleerd  
* Visual Studio 2022 (of een andere C#‑IDE)  
* Het **Aspose.BarCode** NuGet‑pakket (of een andere bibliotheek die `BarcodeGenerator` levert)  

Je kunt het pakket toevoegen met de volgende opdracht:

```bash
dotnet add package Aspose.BarCode
```

## Hoe de barcode‑module‑breedte in te stellen

De *module‑breedte* (ook wel X‑dimensie genoemd) bepaalt de pixelgrootte van elke smalle balk in de barcode. Door deze waarde in te stellen kun je de totale grootte en leesbaarheid van de afbeelding beheersen.

```csharp
// Create a barcode generator for the Planet symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width to 4 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Waarom dit belangrijk is*: Een grotere X‑dimensie levert een grotere barcode op die makkelijker door scanners op afstand kan worden gelezen, terwijl een kleinere waarde de bestandsgrootte verkleint voor weergave op het scherm.

## Een barcode genereren met gevulde staven

De standaardstijl voor de Planet‑barcode gebruikt **gevulde staven** (solide zwarte balken). De volgende code maakt de afbeelding en slaat deze op als PNG.

```csharp
// Save the barcode with filled bars
barcodeGenerator.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

> **Resultaat**: `PostalPlanetFilledBars.png` bevat een standaard Planet‑barcode waarbij elke balk is gevuld.

## Een barcode met lege staven maken

Soms heb je een barcode nodig die alleen de contouren van de staven toont (lege staven). Om dit te bereiken, dupliceer je de generator, behoud je dezelfde module‑breedte en schakel je de `FilledBars`‑vlag uit.

```csharp
// Duplicate the generator for an empty‑bar version
BarcodeGenerator emptyBarGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Apply the same X‑dimension
emptyBarGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars so only the outlines are drawn
emptyBarGenerator.Parameters.Barcode.FilledBars = false;

// Save the empty‑bar barcode
emptyBarGenerator.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

> **Resultaat**: `PostalPlanetEmptyBars.png` toont dezelfde gegevens maar met niet‑gevulde staven, handig voor documenten met veel ontwerp waarbij je wilt dat de barcode opgaat in de achtergrond.

## Hoe barcode op te slaan in verschillende formaten

De `Save`‑methode accepteert elk formaat dat door de SDK wordt ondersteund, zoals **Jpeg**, **Bmp**, **Gif** of **Svg**. Het wijzigen van het formaat vereist alleen het vervangen van de `BarCodeImageFormat`‑enumwaarde.

```csharp
// Example: save as SVG for lossless scaling
barcodeGenerator.Save("YOUR_DIRECTORY/PostalPlanet.svg", BarCodeImageFormat.Svg);
```

*Tip*: Gebruik SVG wanneer je een vectorafbeelding nodig hebt die schaalt zonder pixelatie, vooral voor print‑klare PDF‑bestanden.

## Volledig, uitvoerbaar voorbeeld

Alle onderdelen samenvoegen levert een zelfstandige applicatie op die je in een console‑app kunt plakken.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Create a filled‑bar Planet barcode
        BarcodeGenerator filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        filledGenerator.Parameters.Barcode.XDimension.Pixels = 4; // barcode module width
        filledGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // 2. Create an empty‑bar version of the same barcode
        BarcodeGenerator emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4; // same module width
        emptyGenerator.Parameters.Barcode.FilledBars = false;   // how to set barcode to empty bars
        emptyGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

        // 3. Optional: save as SVG for scalable use
        filledGenerator.Save("PostalPlanet.svg", BarCodeImageFormat.Svg);
    }
}
```

**Verwachte output**

| Bestandsnaam                     | Beschrijving                                 |
|----------------------------------|----------------------------------------------|
| `PostalPlanetFilledBars.png`     | Planet‑barcode met solide zwarte staven       |
| `PostalPlanetEmptyBars.png`      | Zelfde data, staven weergegeven als contouren |
| `PostalPlanet.svg`               | Vectorversie voor schaalvergroting zonder verlies |

Voer het programma uit, open de gegenereerde bestanden en controleer of de barcodes overeenkomen met de numerieke tekenreeks “123456”.

## Veelvoorkomende variaties en randgevallen

| Situatie                                 | Aanpassing                                                               |
|------------------------------------------|---------------------------------------------------------------------------|
| Een dikkere barcode nodig               | Verhoog `XDimension.Pixels` (bijv. `8`)                                   |
| Een kleinere bestandsgrootte wensen     | Gebruik `BarCodeImageFormat.Jpeg` of verlaag de X‑dimensie                |
| Andere symbologieën genereren           | Vervang `EncodeTypes.Planet` door `EncodeTypes.Code128`, `QR`, etc.       |
| Afdrukken op hoge‑resolutie printers     | Sla op als `BarCodeImageFormat.Tiff` voor verliesvrije rasteroutput       |
| Uitvoeren op een headless server         | Geen UI‑code nodig; de generator werkt in een console‑ of service‑context  |

**Pro tip**: Valideer altijd de gegenereerde barcode met een scanner of een verificatietool voordat je deze in productie neemt. Een onjuiste module‑breedte of formaat kan scan‑fouten veroorzaken.

## Conclusie

Je weet nu hoe je barcode‑eigenschappen instelt met de C# Barcode Generator, hoe je de barcode‑module‑breedte beheert, zowel gevulde als lege balkstijlen genereert, en hoe je de barcode opslaat in PNG‑ of SVG‑formaten. Deze stappen vormen een solide basis om barcode‑creatie toe te voegen aan elke .NET‑applicatie.

Verken vervolgens gerelateerde onderwerpen zoals **c# barcode generator performance tuning**, **embedding barcodes in PDF documents**, en **creating QR codes with custom colors**. Experimenteer met verschillende `EncodeTypes` en afbeeldingsformaten om de beste oplossing voor jouw project te vinden.

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe barcode op te slaan in C# – PDF417‑barcodes genereren](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Barcode Generator Tutorial: Hoe PDF417‑barcode te genereren in C#](/barcode/english/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)
- [Hoe foutniveau in PDF417‑barcode in te stellen – Complete gids](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}