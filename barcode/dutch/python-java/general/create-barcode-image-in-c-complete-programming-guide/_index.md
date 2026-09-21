---
category: general
date: 2026-08-09
description: Maak een barcode‑afbeelding in C# met deze stapsgewijze handleiding.
  Leer hoe je een barcode genereert, de hoogte van de barcode in pixels aanpast en
  efficiënt meerdere barcodes maakt.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create multiple barcodes
- barcode height pixels
language: nl
lastmod: 2026-08-09
og_description: Maak snel een barcode‑afbeelding in C#. Volg deze tutorial om te leren
  hoe je een barcode genereert, de barcodehoogte in pixels instelt en meerdere barcodes
  maakt.
og_image_alt: Screenshot of barcode images generated with C# code showing different
  heights
og_title: Barcode-afbeelding maken in C# – volledige gids voor ontwikkelaars
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  headline: Create barcode image in C# – complete programming guide
  type: TechArticle
- description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  name: Create barcode image in C# – complete programming guide
  steps:
  - name: Define the output folder
    text: Choose a folder where the generated PNG files will be stored. Using an absolute
      path avoids permission surprises.
  - name: Instantiate the barcode generator
    text: For a DataBar Omnidirectional barcode, pass `EncodeTypes.DatabarOmniDirectional`
      and the GS1‑128 data string.
  - name: Set common barcode parameters
    text: The most common visual tweaks are the X‑dimension (module width) and the
      bar height. Both are expressed in pixels.
  - name: Save the first barcode image
    text: '```csharp // Step 4: Save the barcode image with a 30 px height string
      file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"); barcode.Save(file30,
      BarCodeImageFormat.Png); ```'
  - name: Adjust the barcode height pixels
    text: Changing the height does not require a new `BarcodeGenerator` instance—just
      modify the parameter.
  - name: Save the second barcode image
    text: '```csharp // Step 6: Save the barcode image with the new 60 px height string
      file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"); barcode.Save(file60,
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'After running the full sample, the `Barcodes` folder contains:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Barcode‑afbeelding maken in C# – volledige programmeergids
url: /nl/python-java/general/create-barcode-image-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcodeafbeelding maken in C# – volledige programmeergids

Als je een **barcode-afbeelding** moet maken in een .NET‑applicatie, laat deze gids je precies zien **hoe je een barcode genereert** met de Aspose.BarCode‑bibliotheek. Je ziet hoe je de **barcode‑hoogte in pixels** kunt regelen, de afbeelding opslaat en **meerdere barcodes** maakt zonder code te dupliceren.

De tutorial behandelt alles, van het installeren van het pakket tot het aanpassen van afmetingen, zodat je vandaag nog een kant‑klaar voorbeeld kunt kopiëren‑plakken in je project.

## Vereisten

* .NET 6.0 SDK of later geïnstalleerd  
* Visual Studio 2022 (of een andere C#‑IDE)  
* NuGet‑pakket `Aspose.BarCode` – installeren met  

```bash
dotnet add package Aspose.BarCode
```

Er zijn geen extra afhankelijkheden nodig.

## Hoe een barcode‑afbeelding te genereren met BarcodeGenerator C#

De kernklasse voor het maken van een barcode‑afbeelding is `BarcodeGenerator`. Deze omvat het coderings‑type, de gegevensreeks en alle weergave‑parameters.

### Stap 1: Definieer de uitvoermap

Kies een map waarin de gegenereerde PNG‑bestanden worden opgeslagen. Het gebruik van een absoluut pad voorkomt verrassingen met rechten.

```csharp
// Step 1: Define the output folder
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputFolder);
```

> **Waarom?** Het programmatically aanmaken van de map garandeert dat de daaropvolgende `Save`‑aanroepen slagen, zelfs op een nieuwe machine.

### Stap 2: Instantieer de barcode‑generator

Voor een DataBar Omnidirectional‑barcode, geef `EncodeTypes.DatabarOmniDirectional` en de GS1‑128‑gegevensreeks door.

```csharp
// Step 2: Create a DataBar Omnidirectional barcode generator with the data to encode
var barcode = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

> **Opmerking:** Het `BarcodeGenerator`‑object is herbruikbaar; je kunt de parameters tussen opslagen wijzigen om **meerdere barcodes** uit dezelfde gegevens te **maken**.

### Stap 3: Stel algemene barcode‑parameters in

De meest voorkomende visuele aanpassingen zijn de X‑dimensie (module‑breedte) en de balkhoogte. Beide worden uitgedrukt in pixels.

```csharp
// Step 3: Set common barcode parameters (X‑dimension and initial height)
barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin modules for sharper output
barcode.Parameters.Barcode.BarHeight.Pixels = 30;  // initial height – 30 px
```

> **Waarom X‑dimensie instellen?** Een kleinere X‑dimensie levert een hogere resolutie op, wat belangrijk is wanneer de afbeelding wordt afgedrukt of weergegeven op schermen met hoge DPI.

### Stap 4: Sla de eerste barcode‑afbeelding op

```csharp
// Step 4: Save the barcode image with a 30 px height
string file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png");
barcode.Save(file30, BarCodeImageFormat.Png);
```

Het bestand `DatabarBarHeight30Pixels.png` bevat nu een DataBar Omnidirectional‑barcode van 30 pixels hoog.

### Stap 5: Pas de barcode‑hoogte in pixels aan

Het wijzigen van de hoogte vereist geen nieuwe `BarcodeGenerator`‑instantie—pas gewoon de parameter aan.

```csharp
// Step 5: Change the bar height to 60 px for the same barcode
barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

### Stap 6: Sla de tweede barcode‑afbeelding op

```csharp
// Step 6: Save the barcode image with the new 60 px height
string file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png");
barcode.Save(file60, BarCodeImageFormat.Png);
```

Nu heb je twee PNG‑bestanden met verschillende **barcode‑hoogte in pixels**, wat laat zien hoe eenvoudig het is om **barcode‑afbeeldingen** te variëren.

## Barcode‑hoogte in pixels dynamisch instellen

Vaak heb je een reeks barcodes nodig met hoogtes die passen bij UI‑elementen of afgedrukte labels. De volgende hulpfunctie abstraheert de hoogte‑aanpassing:

```csharp
/// <summary>
/// Saves a barcode image with a custom height.
/// </summary>
/// <param name="generator">Configured BarcodeGenerator instance.</param>
/// <param name="heightPx">Desired bar height in pixels.</param>
/// <param name="fileName">Target file name (including path).</param>
void SaveBarcodeWithHeight(BarcodeGenerator generator, int heightPx, string fileName)
{
    generator.Parameters.Barcode.BarHeight.Pixels = heightPx;
    generator.Save(fileName, BarCodeImageFormat.Png);
}
```

Je kunt nu `SaveBarcodeWithHeight(barcode, 45, "BarHeight45.png");` aanroepen om een **barcode‑afbeelding** met een hoogte van 45 pixels in één regel te **maken**.

## Meerdere barcodes maken in een lus

Wanneer je een verzameling product‑identifiers hebt, verwijdert een `foreach`‑lus repetitieve code. Dit voorbeeld laat zien hoe je **meerdere barcodes** uit een array van GTIN‑s kunt **maken**.

```csharp
string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
int[] heights = { 30, 45, 60 }; // different heights for visual variety

for (int i = 0; i < gtins.Length; i++)
{
    // Encode each GTIN as a DataBar Omnidirectional barcode
    var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                   $"(01){gtins[i]}");

    // Reuse the X‑dimension setting for consistency
    gen.Parameters.Barcode.XDimension.Pixels = 2;

    // Choose a height from the heights array (or calculate dynamically)
    int height = heights[i % heights.Length];
    string filePath = Path.Combine(outputFolder,
        $"Databar_{gtins[i]}_Height{height}px.png");

    SaveBarcodeWithHeight(gen, height, filePath);
}
```

De lus produceert drie PNG‑bestanden, elk met een verschillende **barcode‑hoogte in pixels**. Omdat de `SaveBarcodeWithHeight`‑helper de hoogte‑wijziging encapsuleert, blijft de hoofd‑lus overzichtelijk en gericht op de data.

### Verwachte output

Na het uitvoeren van het volledige voorbeeld bevat de map `Barcodes`:

```
DatabarBarHeight30Pixels.png
DatabarBarHeight60Pixels.png
Databar_01234567890123_Height30px.png
Databar_09876543210987_Height45px.png
Databar_12345098765432_Height60px.png
```

Het openen van een PNG toont een scherpe DataBar Omnidirectional‑barcode die kan worden gescand met standaard mobiele apps.

## Veelvoorkomende valkuilen en pro‑tips

| Probleem | Waarom het gebeurt | Hoe te vermijden |
|----------|--------------------|------------------|
| **Verkeerde EncodeTypes** | Het gebruik van een 1D‑type voor een DataBar levert een onleesbare afbeelding op. | Kies altijd `EncodeTypes.DatabarOmniDirectional` (of een andere DataBar‑variant) voor GS1‑128‑payloads. |
| **Onvoldoende X‑dimensie** | Een zeer lage X‑dimensie kan dunne balken laten verdwijnen op monitoren met lage resolutie. | Houd `XDimension.Pixels` ≥ 2 voor schermweergave; verhoog naar 3‑4 voor afdrukken. |
| **Bestandspad‑fouten** | Relatieve paden kunnen naar onverwachte mappen verwijzen. | Gebruik `Path.Combine` en `Environment.CurrentDirectory` om absolute paden te bouwen. |
| **Afbeeldingen overschrijven** | Het hergebruiken van dezelfde bestandsnaam in een lus overschrijft eerdere resultaten. | Voeg unieke identifiers (bijv. GTIN of tijdstempel) toe aan de bestandsnaam. |
| **Ontbrekend NuGet‑pakket** | Code compileert maar gooit `FileNotFoundException` tijdens runtime. | Controleer of `Aspose.BarCode` geïnstalleerd is en het project ernaar verwijst. |

## Volledig werkend voorbeeld

Hieronder staat het volledige programma dat je kunt kopiëren naar een console‑applicatie. Het bevat alle stappen, hulpmethoden en foutafhandeling.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Prepare output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // ---------- Single barcode with two heights ----------
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        barcode.Parameters.Barcode.XDimension.Pixels = 2;
        barcode.Parameters.Barcode.BarHeight.Pixels = 30;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);

        // ---------- Helper for dynamic heights ----------
        void SaveBarcodeWithHeight(BarcodeGenerator gen, int heightPx, string fileName)
        {
            gen.Parameters.Barcode.BarHeight.Pixels = heightPx;
            gen.Save(fileName, BarCodeImageFormat.Png);
        }

        // ---------- Multiple barcodes ----------
        string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
        int[] heights = { 30, 45, 60 };

        for (int i = 0; i < gtins.Length; i++)
        {
            var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                           $"(01){gtins[i]}");
            gen.Parameters.Barcode.XDimension.Pixels = 2;

            int height = heights[i % heights.Length];
            string filePath = Path.Combine(outputFolder,
                $"Databar_{gtins[i]}_Height{height}px.png");

            SaveBarcodeWithHeight(gen, height, filePath);
        }

        Console.WriteLine($"Barcode images created in: {outputFolder}");
    }
}
```

Dit programma uitvoeren

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Barcode met aangepaste hoogte maken – Eén-dimensionale barcodes](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Barcode‑afbeelding maken C# – GS1 DataMatrix‑voorbeeld](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [DotCode‑barcode‑afbeelding maken – rijen & kolommen (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}