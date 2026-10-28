---
category: general
date: 2026-10-28
description: Maak een barcode‑afbeelding in C# en leer hoe je de hoogte kunt aanpassen
  met de BarcodeGenerator‑API. Stapsgewijze handleiding voor aangepaste barcode‑hoogte
  en het wijzigen van de balkhoogte.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust height
- c# barcode generator
- custom barcode height
- change barcode height
language: nl
lastmod: 2026-10-28
og_description: Maak een barcode‑afbeelding in C# en zie direct hoe je de hoogte kunt
  aanpassen. Volg dit volledige voorbeeld om een aangepaste barcodehoogte in te stellen
  met de BarcodeGenerator.
og_image_alt: Screenshot showing a generated barcode image with a custom height
og_title: Maak barcode‑afbeelding met aangepaste hoogte in C# – volledige gids
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode image in C# and learn how to adjust height using the
    BarcodeGenerator API. Step‑by‑step guide for custom barcode height and changing
    bar height.
  headline: Create barcode image with custom height in C#
  type: TechArticle
tags:
- barcode
- C#
- image generation
- GS1‑Databar
title: Barcode‑afbeelding maken met aangepaste hoogte in C#
url: /nl/python-java/general/create-barcode-image-with-custom-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak barcode‑afbeelding met aangepaste hoogte in C#

Als je een **barcode‑afbeelding moet maken** en de afmetingen ervan wilt beheersen, laat deze gids je precies zien hoe. Met de Aspose.BarCode .NET‑bibliotheek kun je een GS1‑Databar Omni‑Directional barcode genereren, en vervolgens **hoe je de hoogte kunt aanpassen** om aan elke lay-outvereiste te voldoen.

Je doorloopt een compleet, uitvoerbaar programma dat een **c# barcode generator** demonstreert, elke eigenschap die je instelt uitlegt, en twee verschillende uitvoer toont — één met een balkhoogte van 30 pixel en een andere met een balkhoogte van 60 pixel. Aan het einde kun je **de barcode‑hoogte** programmatisch wijzigen voor elk barcodetype dat door de bibliotheek wordt ondersteund.

## Vereisten

- .NET 6.0 SDK of later (de code werkt ook met .NET Framework 4.6+)
- Visual Studio 2022 of een andere editor die C#‑projecten kan bouwen
- Aspose.BarCode for .NET NuGet‑pakket (`Install-Package Aspose.BarCode`)
- Basiskennis van C#‑syntaxis

> **Pro tip:** Als je een CI‑pipeline gebruikt, voeg dan het NuGet‑pakket toe aan je `csproj`‑bestand zodat de build het automatisch herstelt.

## Stap 1: Het project opzetten en namespaces importeren

Maak een nieuw console‑project aan en voeg de benodigde `using`‑statements toe. De namespaces geven je toegang tot `BarcodeGenerator`, `EncodeTypes` en helpers voor afbeeldingsformaten.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // The rest of the tutorial code lives here.
        }
    }
}
```

> **Waarom dit belangrijk is:** Het importeren van de juiste namespaces voorkomt compile‑time fouten en maakt de API vindbaar in IntelliSense.

## Stap 2: Initialiseer de **c# barcode generator** voor een GS1‑Databar Omni‑Directional code

De constructor neemt twee argumenten: het barcodetype (`EncodeTypes.DatabarOmniDirectional`) en de gegevensreeks. De gegevensreeks moet het GS1 Application Identifier‑formaat volgen, bijv. `(01)12345678901231`.

```csharp
// Create a barcode generator for a GS1‑Databar Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional,
    "(01)12345678901231");
```

> **Uitleg:** Het `BarcodeGenerator`‑object is het startpunt voor alle barcode‑gerelateerde instellingen. Zodra je deze instantie hebt, kun je afmetingen, kleuren en het uitvoerformaat aanpassen.

## Stap 3: Definieer een gemeenschappelijke X‑dimensie (pixelbreedte van de smalste balk)

Een X‑dimensie van 2 pixel is een goed uitgangspunt voor de meeste scherm‑weergavescenario's.

```csharp
// Set a 2‑pixel X‑dimension (width of the smallest bar)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Waarom X‑dimensie instellen?** Het bepaalt de totale breedte van de barcode. Consistent houden zorgt ervoor dat het wijzigen van de balkhoogte de visuele balans niet vervormt.

## Stap 4: **Maak barcode‑afbeelding** met een balkhoogte van 30 pixel

Nu configureren we de balkhoogte, slaan we de eerste afbeelding op, en wijzigen we vervolgens de hoogte voor de tweede.

```csharp
// Configure a 30‑pixel bar height
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the first image
string output30 = "DatabarBarHeight30Pixels.png";
barcodeGenerator.Save(output30, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 30 px height to {output30}");
```

> **Resultaat:** Je krijgt een PNG‑bestand waarin elke verticale balk 30 pixel hoog is. De X‑dimensie blijft 2 pixel, zodat de totale breedte ongewijzigd blijft.

## Stap 5: **Hoe de hoogte aan te passen** – wijzig de balkhoogte naar 60 pixel

Om **aangepaste barcode‑hoogte** te demonstreren, wijs je eenvoudig een nieuwe waarde toe aan dezelfde eigenschap en sla je opnieuw op.

```csharp
// Change the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second image
string output60 = "DatabarBarHeight60Pixels.png";
barcodeGenerator.Save(output60, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 60 px height to {output60}");
```

> **Belangrijk inzicht:** De eigenschap `BarHeight` is wijzigbaar; je hoeft de `BarcodeGenerator`‑instantie niet opnieuw te maken. Hierdoor is het goedkoop om meerdere groottes te genereren in een lus of batch‑proces.

## Stap 6: Verifieer de uitvoer

Voer het console‑programma uit (`dotnet run`). Na uitvoering zou je twee PNG‑bestanden in de output‑map van het project moeten zien:

- `DatabarBarHeight30Pixels.png` – korte balken (30 px)
- `DatabarBarHeight60Pixels.png` – lange balken (60 px)

Beide afbeeldingen bevatten dezelfde gecodeerde gegevens, maar de visuele hoogte verschilt, wat nuttig is bij het integreren van barcodes in formulieren, productetiketten of UI‑componenten met verschillende ruimtebeperkingen.

![Maak barcode‑afbeelding met aangepaste hoogte](barcode-example.png){.align-center width="600" alt="Maak barcode‑afbeelding met aangepaste hoogte"}

> **Tip:** Open de PNG‑bestanden in een willekeurige afbeeldingsviewer. De hogere barcode moet precies dubbel zo groot zijn in verticale afmeting als de kortere, terwijl de horizontale spatiëring identiek blijft.

## Stap 7: Veelvoorkomende variaties en randgevallen

| Situatie | Aanbevolen instelling |
|-----------|---------------------|
| **Afdrukken op een high‑resolution labelprinter** | Gebruik een grotere X‑dimensie (bijv. 4 px) en verhoog `BarHeight` evenredig. |
| **Weergeven op een low‑dpi scherm** | Houd `XDimension` op 1 px en `BarHeight` tussen 20‑40 px voor leesbaarheid. |
| **Genereren van QR‑codes of 2‑D barcodes** | De eigenschap `BarHeight` wordt genegeerd; gebruik `EncodeTypes.QR` en pas `ImageHeight` aan. |
| **Batch‑genereren van vele hoogtes** | Loop over een array van hoogtes en roep `Save` aan binnen de lus; er is geen noodzaak om de generator elke iteratie opnieuw te maken. |

### Omgaan met ongeldige hoogtes

De bibliotheek gooit een `ArgumentOutOfRangeException` als je `BarHeight` instelt op een niet‑positieve waarde. Bescherm hiertegen met een eenvoudige controle:

```csharp
int desiredHeight = 0; // example invalid value
if (desiredHeight <= 0)
{
    throw new ArgumentException("Bar height must be greater than zero.");
}
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

## Volledige broncode (klaar om te kopiëren)

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the barcode generator for GS1‑Databar Omni‑Directional
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set a common 2‑pixel X‑dimension
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = "DatabarBarHeight30Pixels.png";
            barcodeGenerator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 30 px height to {path30}");

            // 4️⃣ Second image – 60 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = "DatabarBarHeight60Pixels.png";
            barcodeGenerator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 60 px height to {path60}");
        }
    }
}
```

> **Waarom dit werkt:** Alle benodigde instellingen (`EncodeTypes`, `XDimension`, `BarHeight`) worden toegepast vóór elke `Save`‑aanroep. Dezelfde `BarcodeGenerator`‑instantie wordt hergebruikt, wat zowel geheugen‑efficiënt als gemakkelijk leesbaar is.

## Conclusie

Je weet nu hoe je **barcode‑afbeeldingen** kunt maken in C# en nauwkeurig **de barcode‑hoogte** kunt wijzigen met de `BarcodeGenerator`‑API. Door `BarHeight.Pixels` aan te passen bereik je een **aangepaste barcode‑hoogte** zonder de generator opnieuw te bouwen, waardoor de oplossing ideaal is voor dynamische labelcreatie, UI‑rendering of batch‑verwerkings‑pipelines.

Vervolgens kun je gerelateerde onderwerpen verkennen, zoals **hoe je de breedte aanpast**, **het toevoegen van mens‑leesbare tekst**, of **exporteren naar SVG voor schaalbaar webgebruik**. Hetzelfde patroon — een eigenschap instellen, `Save` aanroepen — geldt voor die scenario's, waardoor je dit voorbeeld met vertrouwen kunt uitbreiden.

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe de barcode‑hoogte te wijzigen in C# – Complete gids](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Barcode‑generator voorbeeld – maak Planet‑ en RM4SCC‑barcodes met aangepaste hoogte](/barcode/english/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/)
- [Hoe rm4scc‑barcode te maken en de hoogte te regelen in C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-control-its-height-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}