---
category: general
date: 2026-11-14
description: Barcode-generator C#‑tutorial die laat zien hoe je DataBar Omnidirectional‑barcodes
  maakt, de X‑dimensie instelt en de balkhoogte in pixels aanpast.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c# tutorial
- DataBar Omnidirectional
- set bar height
- XDimension pixels
- BarCodeImageFormat PNG
language: nl
lastmod: 2026-11-14
og_description: Barcode generator C# tutorial legt stap voor stap uit hoe je een DataBar
  Omnidirectional‑barcode genereert, XDimension in pixels definieert en de balkhoogte
  aanpast voor PNG‑uitvoer.
og_image_alt: Screenshot of barcode generator C# tutorial output showing a DataBar
  barcode
og_title: Barcode generator C# tutorial – maak DataBar-barcodes
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Barcode generator C# tutorial that shows how to create DataBar Omnidirectional
    barcodes, set X‑dimension, and adjust bar height in pixels.
  headline: 'Barcode generator C# tutorial: DataBar Omnidirectional'
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- tutorial
title: 'Barcodegenerator C#-tutorial: DataBar Omnidirectioneel'
url: /nl/python-java/general/barcode-generator-c-tutorial-databar-omnidirectional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator C# tutorial – maak DataBar Omnidirectional barcodes

Als je op zoek bent naar een **barcode generator C# tutorial**, ben je hier aan het juiste adres. Deze gids leidt je stap voor stap door het maken van een DataBar Omnidirectional barcode, het configureren van de XDimension in pixels en het aanpassen van de balkhoogte om PNG‑afbeeldingen te produceren.

Je ziet een volledig, uitvoerbaar voorbeeld dat alles behandelt, van het initialiseren van de generator tot het opslaan van meerdere afbeeldingen met verschillende balkhoogtes. Er is geen externe documentatie nodig – kopieer gewoon de code, voer deze uit en je hebt twee barcode‑bestanden klaar voor gebruik.

## Prerequisites

Voordat je begint, zorg dat je het volgende hebt:

* .NET 6.0 of later geïnstalleerd  
* Een referentie naar de barcode‑bibliotheek die `BarcodeGenerator`, `EncodeTypes` en `BarCodeImageFormat` levert (bijvoorbeeld Aspose.BarCode for .NET)  
* Basiskennis van C#‑syntaxis en Visual Studio of je favoriete IDE  

> **Pro tip:** Als je Aspose.BarCode gebruikt, voeg dan het NuGet‑pakket `Aspose.BarCode` toe aan je project.

## Barcode generator C# tutorial – stap 1: maak de generator

De eerste stap is het instantieren van een `BarcodeGenerator` met het `DatabarOmniDirectional`‑encode type en de data die je wilt coderen.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Omnidirectional barcode generator with the desired data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*Waarom dit belangrijk is:* `EncodeTypes.DatabarOmniDirectional` geeft de bibliotheek de opdracht een barcode te produceren die vanuit elke richting gelezen kan worden, wat ideaal is voor retailverpakkingen en logistiek.

## Stel XDimension-pixels in voor de barcode

De X‑dimension bepaalt de breedte van de kleinste module (de “pixel”) in de barcode. Het instellen in pixels geeft je precieze controle over de visuele dichtheid van de barcode.

```csharp
        // Step 2: Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Uitleg:* Een waarde van `2` pixels levert een barcode die scherp genoeg is voor de meeste scanners, terwijl de bestandsgrootte bescheiden blijft.

## Pas balkhoogte aan en sla afbeeldingen op

Balkhoogte bepaalt hoe hoog de balken verschijnen. Je kunt meerdere afbeeldingen met verschillende hoogtes genereren door de eigenschap `BarHeight.Pixels` te wijzigen en opnieuw `Save` aan te roepen.

```csharp
        // Step 3: Set the bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        string outputPath = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
```

De enum‑waarde `BarCodeImageFormat.Png` zorgt ervoor dat de output een loss‑less PNG‑bestand is, wat het aanbevolen **formaat** is voor barcode‑graphics omdat het exacte afmetingen behoudt.

## Verander balkhoogte om meerdere afbeeldingen te maken

Vaak heb je dezelfde barcode nodig in verschillende groottes – bijvoorbeeld één voor een klein label en een andere voor een groot poster. Verander de balkhoogte en hergebruik dezelfde generator‑instantie:

```csharp
        // Step 4: Change the bar height to 60 px and save a second image
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        outputPath = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

*Randgeval:* Als de balkhoogte te laag wordt ingesteld (bijv. onder 10 px), kunnen sommige scanners moeite hebben de code te lezen. Test altijd de gegenereerde afbeeldingen met je doel‑scannerhardware.

## Volledige broncode

Hieronder vind je het complete programma dat je kunt copy‑paste in een nieuw console‑project. Het bevat alle benodigde `using`‑directives en laat beide balkhoogte‑variaties zien.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a DataBar Omnidirectional barcode generator
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Set XDimension to 2 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image – 30 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
            generator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 30 px barcode to {path30}");

            // Second image – 60 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
            generator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 60 px barcode to {path60}");
        }
    }
}
```

Voer het programma uit, vervang `YOUR_DIRECTORY` door een geldig map‑pad, en je vindt twee PNG‑bestanden:

* `DatabarBarHeight30Pixels.png` – 30 px hoge balken  
* `DatabarBarHeight60Pixels.png` – 60 px hoge balken  

![barcode generator C# tutorial output](images/databar-example.png "Barcode generator C# tutorial showing two DataBar images")

## Veelgestelde vragen

| Question | Answer |
|----------|--------|
| **Can I change the image format?** | Ja. Vervang `BarCodeImageFormat.Png` door `Jpeg`, `Bmp` of `Gif` indien nodig. PNG heeft de voorkeur voor lossless kwaliteit. |
| **What if I need a different XDimension?** | Pas `generator.Parameters.Barcode.XDimension.Pixels` aan naar elk geheel getal. Grotere waarden vergroten de totale barcode‑breedte. |
| **Is the DataBar Omnidirectional suitable for mobile scanning?** | Ja, mits de afgedrukte grootte voldoet aan de minimale module‑grootte van de scanner (meestal 0.33 mm). De pixel‑gebaseerde XDimension helpt je aan die eis te voldoen. |
| **How do I embed the barcode in a PDF?** | Na het opslaan van de PNG, gebruik je een PDF‑bibliotheek (bijv. iTextSharp) om de afbeelding in een PDF‑pagina in te voegen. |

## Conclusie

Deze **barcode generator C# tutorial** heeft je laten zien hoe je een DataBar Omnidirectional barcode maakt, de XDimension in pixels instelt en PNG‑bestanden genereert met verschillende balkhoogtes. Je beschikt nu over een herbruikbare code‑snippet die je kunt aanpassen voor elk C#‑project dat barcode‑creatie vereist.

### Wat is het volgende?

* Verken andere `EncodeTypes` zoals `Code128` of `QR` om je barcode‑repertoire uit te breiden.  
* Combineer de gegenereerde PNG met een PDF‑generatiebibliotheek om afdrukbare facturen te maken.  
* Experimenteer met `generator.Parameters.Barcode.Color` om aangepaste kleuren toe te voegen, terwijl je binnen de specificaties van scanners blijft.

Voel je vrij om het voorbeeld aan te passen, extra balkhoogtes te proberen of het output‑formaat te wijzigen. Veel programmeerplezier!

## What Should You Learn Next?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids zijn gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [How to set barcode height, generate DataBar barcode in C#](/barcode/english/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/)
- [How to create omnidirectional Databar barcode in C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}