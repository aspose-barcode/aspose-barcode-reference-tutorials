---
category: general
date: 2026-08-12
description: Barcodegenerator‑voorbeeld dat laat zien hoe je een barcode genereert
  met precieze pixelgrootte. Leer hoe je de modulebreedte, balkhoogte instelt en Planet‑barcodes
  maakt.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to generate barcode
- barcode pixel size
- generate planet barcode
- barcode height setting
language: nl
lastmod: 2026-08-12
og_description: Barcode‑generatorvoorbeeld toont hoe je een barcode met exacte pixelafmetingen
  genereert. Volg deze gids om de modulebreedte en balkhoogte voor Planet‑ en RM4SCC‑codes
  te regelen.
og_image_alt: Screenshot of a barcode generator example showing a Planet barcode with
  custom pixel size
og_title: barcode‑generatorvoorbeeld – pas pixelgrootte aan in C#
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: barcode generator example that shows how to generate barcode with precise
    pixel size. Learn to set module width, bar height and create Planet barcodes.
  headline: barcode generator example – step‑by‑step guide for custom pixel sizes
  type: TechArticle
- description: barcode generator example that shows how to generate barcode with precise
    pixel size. Learn to set module width, bar height and create Planet barcodes.
  name: barcode generator example – step‑by‑step guide for custom pixel sizes
  steps:
  - name: Install the Aspose.BarCode package
    text: 'Open a terminal in your project folder and run:'
  - name: Add the necessary `using` directives
    text: '```csharp using Aspose.BarCode.Generation; using Aspose.BarCode.BarCodeImageFormat;
      ```'
  - name: – generate a Planet barcode with automatically calculated height
    text: '```csharp // Step 1: Generate a Planet barcode with automatically calculated
      height BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet,
      "123456");'
  - name: – generate a Planet barcode with an explicit 100‑pixel height
    text: '```csharp // Step 2: Generate a Planet barcode with an explicit 100‑pixel
      height BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet,
      "123456");'
  - name: – generate an RM4SCC barcode with the same explicit height
    text: '```csharp // Step 3: Generate an RM4SCC barcode with the same explicit
      height BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC,
      "123456");'
  - name: What is **barcode pixel size**?
    text: '*Pixel size* refers to the physical number of screen or printer pixels
      that represent a single module (`XDimension`). A larger pixel size yields a
      bigger barcode, which can be easier for low‑resolution scanners but consumes
      more label real‑estate.'
  - name: How does `BarHeight` affect readability?
    text: The `BarHeight` property controls the vertical length of the bars. Standards
      for most 1‑D barcodes (including Planet and RM4SCC) recommend a minimum height
      of 10 mm when printed at 300 dpi, which translates to roughly 118 pixels. Setting
      a height below that can cause read errors, especially on mobil
  - name: When should you let the library calculate height automatically?
    text: If you’re generating barcodes for on‑screen display only, the automatic
      calculation keeps the aspect ratio consistent and reduces the amount of manual
      tweaking needed. For printed labels that must meet strict ISO specifications,
      you should **explicitly set the bar height**.
  - name: Pro tip on performance
    text: When generating thousands of barcodes in a batch job, reuse a single `BarcodeGenerator`
      instance and only change the `CodeText` and size parameters between saves. This
      avoids repeated allocation of internal rendering objects and can cut execution
      time by up to 30 %.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: barcodegenerator‑voorbeeld – stapsgewijze handleiding voor aangepaste pixelgroottes
url: /nl/python-java/general/barcode-generator-example-step-by-step-guide-for-custom-pixe/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# barcode generator voorbeeld – stapsgewijze gids voor aangepaste pixelgroottes

Als je een **barcode generator voorbeeld** nodig hebt dat je elke pixel kunt laten controleren, laat deze gids precies zien hoe je dat doet. Je leert de modulebreedte in te stellen, een vaste balkhoogte te definiëren en zowel Planet- als RM4SCC-barcodes te genereren met voorspelbare afmetingen.

De meeste ontwikkelaars worstelen met “how to generate barcode” afbeeldingen die er op elk scherm of elke printer hetzelfde uitzien. De code‑fragmenten hieronder lossen dat probleem op door de pixel‑niveau parameters van de Aspose.BarCode for .NET bibliotheek bloot te leggen, zodat je consistente output kunt produceren zonder giswerk.

## Wat je zult leren

* Hoe het vereiste NuGet‑pakket te installeren.
* Hoe een Planet‑barcode te genereren met automatisch berekende hoogte.
* Hoe een Planet‑barcode te genereren met een expliciete hoogte van 100 pixel.
* Hoe een RM4SCC‑barcode te genereren met dezelfde expliciete hoogte.
* Waarom **barcode pixel size** belangrijk is voor de betrouwbaarheid van het scannen.
* Tips voor het oplossen van veelvoorkomende problemen bij het genereren van Planet‑barcode‑afbeeldingen.

Je hebt alleen .NET 6 of later nodig, een basis C#‑ontwikkelomgeving, en een internetverbinding om het NuGet‑pakket te downloaden.

---

## barcode generator voorbeeld – ontwikkelomgeving instellen

Voordat je code schrijft, zorg ervoor dat de Aspose.BarCode‑bibliotheek beschikbaar is voor je project.

### Installeer het Aspose.BarCode‑pakket

Open een terminal in je projectmap en voer uit:

```bash
dotnet add package Aspose.BarCode
```

Het commando voegt de nieuwste stabiele versie van **Aspose.BarCode** toe aan je `csproj`. Nadat het herstel is voltooid, kun je de `BarcodeGenerator`‑klasse gaan gebruiken.

> **Pro tip:** Richt je op .NET 6 of .NET 7 om te profiteren van de nieuwste prestatie‑verbeteringen en de standaard UTF‑8‑afhandeling.

### Voeg de benodigde `using`‑directieven toe

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;
```

Deze namespaces maken de `BarcodeGenerator`‑klasse en de `BarCodeImageFormat`‑enum beschikbaar die later in de tutorial worden gebruikt.

## Hoe een barcode te genereren met aangepaste pixelgrootte

De volgende drie stappen illustreren het volledige **barcode generator voorbeeld**. Elke stap bouwt voort op de vorige, zodat je het hele blok kunt kopiëren‑plakken in een console‑app en ongewijzigd kunt uitvoeren.

### Stap 1 – genereer een Planet‑barcode met automatisch berekende hoogte

```csharp
// Step 1: Generate a Planet barcode with automatically calculated height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set module width (x‑dimension) to 4 pixels
planetAuto.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG
planetAuto.Save("PlanetAuto.png", BarCodeImageFormat.Png);
```

**Waarom dit werkt:**  
*De `XDimension`‑eigenschap definieert de breedte van een enkele barcode‑module (het kleinste zwarte of witte element). Wanneer je `BarHeight` weglaten, berekent de bibliotheek een hoogte die de standaard beeldverhouding voor Planet‑codes behoudt.*

**Verwachte output:** Een PNG‑bestand met de naam `PlanetAuto.png` dat een schone Planet‑barcode bevat. De hoogte past zich aan de 4‑pixel module‑breedte aan, meestal rond de 60 pixels voor een payload van zes tekens.

### Stap 2 – genereer een Planet‑barcode met een expliciete hoogte van 100 pixel

```csharp
// Step 2: Generate a Planet barcode with an explicit 100‑pixel height
BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same module width
planetFixed.Parameters.Barcode.XDimension.Pixels = 4;

// Force the bar height to 100 pixels
planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the image
planetFixed.Save("PlanetHeight100.png", BarCodeImageFormat.Png);
```

**Waarom je dit nodig zou kunnen hebben:**  
Soms verwacht de scanapparatuur een minimale balkhoogte voor betrouwbare detectie. Door `BarHeight.Pixels` in te stellen, garandeer je dat elke gegenereerde afbeelding aan die eis voldoet, ongeacht de lengte van de gecodeerde gegevens.

**Verwachte output:** `PlanetHeight100.png` toont dezelfde gegevens als eerder, maar de balken zijn precies 100 pixels hoog, waardoor je volledige controle hebt over de visuele grootte.

### Stap 3 – genereer een RM4SCC‑barcode met dezelfde expliciete hoogte

```csharp
// Step 3: Generate an RM4SCC barcode with the same explicit height
BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Use the same module width for consistency
rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;

// Apply the 100‑pixel bar height
rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the image
rm4sccFixed.Save("RM4SCCHeight100.png", BarCodeImageFormat.Png);
```

**Waarom dit belangrijk is:**  
`EncodeTypes.RM4SCC` is een gestapelde lineaire barcode die in de logistiek wordt gebruikt. Het afstemmen van de balkhoogte op die van de Planet‑barcode vereenvoudigt batchverwerking wanneer beide symbolen op hetzelfde label verschijnen.

**Verwachte output:** `RM4SCCHeight100.png` toont een perfect formaat RM4SCC‑barcode, die overeenkomt met de 100‑pixel hoogte die je voor de Planet‑code hebt ingesteld.

> **Resultaatverificatie:** Open elke PNG in een afbeeldingsviewer en bevestig dat de zwarte balken precies 4 pixels breed zijn en, waar je dat hebt opgegeven, 100 pixels hoog. Je kunt de bestanden ook aan een barcode‑scanner‑app voeren om te controleren of ze decoderen naar “123456”.

---

## Begrijpen van barcode pixelgrootte en balkhoogte

### Wat is **barcode pixel size**?

*Pixelgrootte* verwijst naar het fysieke aantal scherm‑ of printerpixels dat een enkele module (`XDimension`) representeert. Een grotere pixelgrootte levert een grotere barcode op, wat gemakkelijker kan zijn voor scanners met lage resolutie, maar meer labelruimte verbruikt.

### Hoe beïnvloedt `BarHeight` de leesbaarheid?

De `BarHeight`‑eigenschap regelt de verticale lengte van de balken. Normen voor de meeste 1‑D‑barcodes (inclusief Planet en RM4SCC) bevelen een minimale hoogte van 10 mm aan bij afdrukken op 300 dpi, wat ongeveer 118 pixels is. Een hoogte lager dan dat kan leesfouten veroorzaken, vooral bij mobiele camera's.

### Wanneer moet je de bibliotheek de hoogte automatisch laten berekenen?

Als je barcodes alleen voor weergave op het scherm genereert, houdt de automatische berekening de beeldverhouding consistent en vermindert het de hoeveelheid handmatige aanpassingen die nodig zijn. Voor afgedrukte labels die moeten voldoen aan strikte ISO‑specificaties, moet je **expliciet de balkhoogte instellen**.

## Veelvoorkomende valkuilen en best practices bij het genereren van Planet‑barcode

| Valkuil | Waarom het gebeurt | Oplossing |
|---------|--------------------|-----------|
| Balken verschijnen te dun of te dik | `XDimension` blijft op de standaardwaarde (1 pixel) op hoge‑resolutie displays | Stel `XDimension.Pixels` in op minimaal 3‑4 voor visuele duidelijkheid |
| Scanner kan de code niet lezen | `BarHeight` is te klein voor de brandpuntsafstand van de scanner | Gebruik `BarHeight.Pixels` ≥ 100 voor de meeste mobiele scanners |
| Afbeelding is onscherp na schalen | Opslaan als JPEG introduceert compressie‑artefacten | Sla op als PNG (`BarCodeImageFormat.Png`) voor verliesvrije output |
| Onverwacht barcode‑type | Verkeerde `EncodeTypes`‑enumwaarde | Controleer dubbel of je `EncodeTypes.Planet` gebruikt voor Planet‑symboliek |

### Pro tip voor prestaties

Wanneer je duizenden barcodes genereert in een batch‑taak, hergebruik dan een enkele `BarcodeGenerator`‑instantie en wijzig alleen de `CodeText`‑ en grootte‑parameters tussen opslagen. Dit voorkomt herhaalde toewijzing van interne renderobjecten en kan de uitvoeringstijd met tot 30 % verkorten.

## Volledig werkend voorbeeld – alles samenvoegen

Maak een nieuw console‑project (`dotnet new console -n BarcodeDemo`) en vervang de inhoud van `Program.cs` door het volgende:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Directory where PNG files will be saved
            string outputDir = Environment.CurrentDirectory;

            // ---------- Planet barcode – automatic height ----------
            var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
            planetAuto.Save($"{outputDir}/PlanetAuto.png", BarCodeImageFormat.Png);
            Console.WriteLine("PlanetAuto.png generated.");

            // ---------- Planet barcode – fixed 100‑pixel height ----------
            var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            planetFixed.Save($"{outputDir}/PlanetHeight100.png", BarCodeImageFormat.Png);
            Console.WriteLine("PlanetHeight100.png generated.");

            // ---------- RM4SCC barcode – same fixed height ----------
            var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccFixed.Save($"{outputDir}/RM4SCCHeight100.png", BarCodeImageFormat.Png);
            Console.WriteLine("RM4SCCHeight100.png generated.");

            Console.WriteLine("All barcodes created successfully.");
        }
    }
}
```

Voer het programma uit met `dotnet run`. Na uitvoering vind je drie PNG‑bestanden in de projectmap, elk illustrerend een ander **barcode generator voorbeeld** scenario.

## Volgende stappen en gerelateerde onderwerpen

* **How to generate barcode in other formats** – verken `EncodeTypes.Code128`, `EncodeTypes.QR` en `EncodeTypes.DataMatrix` voor 2‑D‑behoeften.
* **Embedding barcodes in PDFs** – combineer Aspose.BarCode met Aspose.PDF om barcodes direct op factuursjablonen te plaatsen.
* **Dynamic barcode size based on user input** – bereken

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe barcode genereren java: Maak een exacte barcode‑afbeelding](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)
- [Hoe barcode genereren in Java: Maak en stel de grootte in voor de volledige afbeelding](/barcode/english/java/barcode-basics/creating-setting-size-whole-picture-barcode/)
- [Hoe een code128‑barcode maken in Java en de balkhoogte instellen](/barcode/english/java/barcode-configuration/setting-bars-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}