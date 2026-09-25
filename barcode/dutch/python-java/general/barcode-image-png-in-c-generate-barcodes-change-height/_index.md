---
category: general
date: 2026-08-15
description: Barcode‑afbeelding PNG in C# – leer hoe je postbarcodes genereert, een
  Planet‑barcode maakt en de barcodehoogte wijzigt met een eenvoudige generator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode image png
- barcode generator c#
- generate postal barcode
- create planet barcode
- change barcode height
language: nl
lastmod: 2026-08-15
og_description: Barcode-afbeelding PNG in C#-tutorial laat zien hoe je postbarcodes
  genereert, een Planet-barcode maakt en de barcodehoogte wijzigt met behulp van de
  BarcodeGenerator API.
og_image_alt: Screenshot of generated PNG barcode with custom height using C# BarcodeGenerator
og_title: Barcode‑afbeelding PNG in C# – genereer en pas barcodes aan
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Barcode image PNG in C# – learn how to generate postal barcodes, create
    a Planet barcode, and change barcode height with a simple generator.
  headline: Barcode image PNG in C# generate barcodes, change height
  type: TechArticle
tags:
- barcode
- C#
- PNG
- postal
- generator
title: Barcode‑afbeelding PNG in C# – barcodes genereren, hoogte wijzigen
url: /nl/python-java/general/barcode-image-png-in-c-generate-barcodes-change-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode-afbeelding PNG in C# – barcodes genereren, hoogte wijzigen

Als je een **barcode image PNG** in C# nodig hebt, leidt deze gids je door het volledige proces. Je leert hoe je postbarcodes genereert, een Planet‑barcode maakt en de barcodehoogte wijzigt zonder je IDE te verlaten.

Het genereren van betrouwbare PNG‑barcodes is een veelvoorkomende eis voor verzendetiketten, voorraadsystemen en geautomatiseerde postoplossingen. Aan het einde van deze tutorial heb je een herbruikbare code‑snippet die hoogwaardige PNG‑bestanden produceert voor zowel Planet‑ als RM4SCC‑formaten, en begrijp je hoe je de balkhoogte kunt aanpassen aan de postvoorschriften.

## Wat je nodig hebt

- .NET 6+ of .NET Framework 4.7.2 (de BarcodeGenerator API werkt met elke recente .NET runtime)  
- Een referentie naar het **Aspose.BarCode for .NET** NuGet‑pakket (of een compatibele bibliotheek die `BarcodeGenerator`, `EncodeTypes` en `BarCodeImageFormat` levert)  
- Basiskennis van C#‑syntaxis en bestands‑I/O  

Er zijn geen extra tools nodig; de code draait in Visual Studio, Rider of de `dotnet` CLI.

## Barcode image PNG – basisgeneratie

De eerste stap is het maken van een **barcode image PNG** met standaardafmetingen. Dit legt het basisbestand vast dat je later kunt aanpassen.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Define the output folder (replace with your own path)
string outputFolder = @"C:\Barcodes";

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);

// 1️⃣ Create a Planet barcode generator with default height
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width (X‑dimension) to 4 pixels – this defines the thin bar size
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG; this is the first **barcode image PNG** you’ll produce
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

**Waarom dit werkt:**  
- `EncodeTypes.Planet` vertelt de generator om de Planet‑symbologie te gebruiken, wat vereist is voor veel postdiensten.  
- `XDimension.Pixels` bepaalt de breedte van de kleinste balk; een waarde van 4 px levert een leesbare barcode op typische etiketgroottes.  
- De `Save`‑methode schrijft een **barcode image PNG**‑bestand naar schijf, waarbij alle vectorinformatie wordt bewaard als rasterpixels.

## Barcodehoogte wijzigen – de visuele weging aanpassen

Postrichtlijnen vereisen vaak een specifieke balkhoogte. De onderstaande snippet toont hoe je een aangepaste hoogte van 100 pixel instelt voor dezelfde Planet‑barcode.

```csharp
// 2️⃣ Apply a custom 100‑pixel bar height
planetGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Overwrite or save as a new file to keep both versions
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

**Waarom je de hoogte wijzigt:**  
Een hogere balk verbetert de scanbetrouwbaarheid op laag‑resolutieprinters, terwijl een kortere balk minder labelruimte inneemt. De `BarHeight.Pixels`‑eigenschap stelt je in staat dit attribuut nauwkeurig af te stemmen zonder de X‑dimensie te beïnvloeden.

## Postbarcode genereren – een RM4SCC‑voorbeeld maken

Het RM4SCC‑formaat is een andere veelgebruikte postbarcode in het Verenigd Koninkrijk. De generatie‑stappen spiegelen het Planet‑voorbeeld en versterken het **barcode generator c#**‑patroon.

```csharp
// 3️⃣ Create an RM4SCC barcode generator with default height
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Keep the same module width for consistency
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the default‑height PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

## Barcodehoogte wijzigen – RM4SCC‑variant

Net als bij de Planet‑barcode kun je de RM4SCC‑balkhoogte aanpassen. De onderstaande code stelt de hoogte in op 100 px, waardoor een tweede **barcode image PNG** voor dezelfde gegevensreeks wordt geproduceerd.

```csharp
// 4️⃣ Set a custom 100‑pixel bar height for RM4SCC
rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the customized PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

## Volledig, uitvoerbaar voorbeeld

Alle stappen samenvoegen levert een enkel, zelfstandig programma op dat vier PNG‑bestanden maakt:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        string outputFolder = @"C:\Barcodes";
        Directory.CreateDirectory(outputFolder);

        // Planet barcode – default height
        var planet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planet.Parameters.Barcode.XDimension.Pixels = 4;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // Planet barcode – custom 100‑pixel height
        planet.Parameters.Barcode.BarHeight.Pixels = 100;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – default height
        var rm4scc = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4scc.Parameters.Barcode.XDimension.Pixels = 4;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – custom 100‑pixel height
        rm4scc.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                    BarCodeImageFormat.Png);

        Console.WriteLine("All barcode PNG files have been generated in " +


## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Barcode met aangepaste hoogte maken – één-dimensionale barcodes](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Barcode PNG maken – DataMatrix-beeldverhouding – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [Barcode‑afbeelding C# maken – GS1 DataMatrix‑voorbeeld](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}