---
category: general
date: 2026-10-02
description: Maak snel een gestapelde databars‑barcode in C#. Leer hoe je XDimension
  instelt, de beeldverhouding aanpast en PNG‑afbeeldingen exporteert met een barcode‑generator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create stacked databars barcode
- C# barcode generator
- DataBar stacked omnidirectional
- barcode aspect ratio
- XDimension pixel size
- BarCodeImageFormat PNG
language: nl
lastmod: 2026-10-02
og_description: Maak een gestapelde databars-barcode in C# met een volledig codevoorbeeld.
  Pas XDimension aan, wijzig de beeldverhouding en sla PNG‑bestanden op in slechts
  een paar regels.
og_image_alt: Screenshot showing a create stacked databars barcode example generated
  with C#
og_title: Maak een gestapelde databars barcode in C# – snelle tutorial
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create stacked databars barcode in C# quickly. Learn to set XDimension,
    adjust aspect ratio, and export PNG images with a barcode generator.
  headline: Create stacked databars barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- Aspose
- image generation
title: Maak een gestapelde databars barcode in C# – stapsgewijze handleiding
url: /nl/python-java/general/create-stacked-databars-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak gestapelde databars barcode in C# – stapsgewijze handleiding

Als je een **gestapelde databars barcode** moet maken in een .NET‑project, laat deze tutorial je precies zien hoe. Je ziet hoe je de X‑dimensie configureert, aspectratio's wijzigt en het resultaat opslaat als PNG‑bestanden — allemaal met de Aspose.BarCode‑bibliotheek.

Het genereren van een gestapelde DataBar‑barcode vereist geen complexe grafische pijplijn. Aan het einde van deze gids heb je twee kant‑klaar PNG‑afbeeldingen die verschillende aspectratio's illustreren, en begrijp je waarom die parameters belangrijk zijn voor de scanbetrouwbaarheid.

## Wat je nodig hebt

- .NET 6.0 of later (de code werkt ook met .NET Framework 4.6+)
- Visual Studio 2022 of een andere C#‑IDE
- **Aspose.BarCode for .NET** NuGet‑pakket  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Schrijfrechten voor een map waarin de PNG‑bestanden worden opgeslagen

## Stap 1: Het project opzetten en namespaces importeren

Maak een nieuwe console‑applicatie (of voeg de code toe aan een bestaand project) en importeer de vereiste namespaces:

```csharp
using System;
using Aspose.BarCode.Generation;   // BarcodeGenerator lives here
using Aspose.BarCode;               // BarCodeImageFormat enum
```

> **Waarom dit belangrijk is:** `Aspose.BarCode.Generation` levert de `BarcodeGenerator`‑klasse, terwijl `Aspose.BarCode` de `BarCodeImageFormat`‑enumeratie bevat die wordt gebruikt voor het opslaan van afbeeldingen.

## Stap 2: Initialiseert de generator voor een gestapelde omnidirectionele DataBar

De waarde `EncodeTypes.DatabarStackedOmniDirectional` selecteert de gestapelde DataBar‑symbologie. De gegevensreeks moet voldoen aan het GS1 Application Identifier (AI)‑formaat; hier gebruiken we een dummy GTIN‑14‑waarde.

```csharp
// Initialise a generator for a stacked omnidirectional DataBar barcode
var barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

> **Waarom dit belangrijk is:** Het gekozen encode‑type vertelt de bibliotheek een *gestapelde* barcode te renderen, wat essentieel is voor hoog‑dichte etiketten waar verticale ruimte beperkt is.

## Stap 3: Definieer de module‑ (X‑dimensie) grootte in pixels

De X‑dimensie bepaalt de breedte van de kleinste balk (de “module”). Een waarde van 2 pixels werkt goed voor de meeste scherm‑resolutie‑outputs.

```csharp
// Set the X‑dimension to 2 pixels (module width)
barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Waarom dit belangrijk is:** Scanners interpreteren de module‑breedte als de basiseenheid. Een te kleine waarde kan vage afdrukken veroorzaken; een te grote verspilt ruimte.

## Stap 4: Sla de eerste afbeelding op met een aspectratio van 15

De eigenschap `AspectRatio` beïnvloedt de hoogte‑tot‑breedte‑verhouding van elk gestapeld segment. Een aspectratio van 15 is een veelvoorkomende standaard voor retail‑toepassingen.

```csharp
// Apply aspect ratio 15 and save the first PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **Waarom dit belangrijk is:** Een lagere aspectratio levert een plattere barcode op, die op bepaalde etikettenmaterialen makkelijker te scannen kan zijn. Het PNG‑formaat behoudt verliesvrije kwaliteit voor testen.

## Stap 5: Verander de aspectratio naar 30 en sla de tweede afbeelding op

Het verhogen van de aspectratio maakt elk gestapeld segment hoger, wat de scanbetrouwbaarheid op laag‑contrast achtergronden kan verbeteren.

```csharp
// Apply aspect ratio 30 and save the second PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

> **Waarom dit belangrijk is:** Verschillende retailers of logistieke partners kunnen specifieke barcode‑afmetingen vereisen. Het aanbieden van beide versies stelt je in staat snel de scanprestaties te vergelijken.

## Volledig, uitvoerbaar voorbeeld

Hieronder staat het volledige programma dat je kunt kopiëren‑plakken in `Program.cs`. Het compileert en draait zonder aanpassingen nadat het Aspose.BarCode NuGet‑pakket is geïnstalleerd.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace StackedDataBarDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for stacked omnidirectional DataBar
            var barcodeGen = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Define the module (X‑dimension) size in pixels
            barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Save first image with aspect ratio 15
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio15.png");

            // 4️⃣ Save second image with aspect ratio 30
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio30.png");
        }
    }
}
```

### Verwachte output

Het uitvoeren van het programma maakt twee bestanden aan in de uitvoermap:

| Bestandsnaam                  | Aspectratio  | Visuele beschrijving |
|-------------------------------|--------------|----------------------|
| `DatabarAspectRatio15.png`    | 15           | Korter, platter gestapelde barcode |
| `DatabarAspectRatio30.png`    | 30           | Hoger, meer langwerpig gestapelde barcode |

Je kunt de PNG‑bestanden openen met elke afbeeldingsviewer om te verifiëren dat de barcode correct wordt weergegeven.

![Voorbeeld van gestapelde databars barcode](placeholder-image.png){alt="Voorbeeld van gestapelde databars barcode"}

## Veelgestelde vragen en randgevallen

| Vraag | Antwoord |
|----------|--------|
| **Kan ik een andere X‑dimensie gebruiken?** | Ja. Typische waarden liggen tussen 1 en 4 pixels. Grotere waarden vergroten de barcode‑grootte, maar kunnen de leesbaarheid op printers met lage resolutie verbeteren. |
| **Wat als ik een andere symbologie nodig heb?** | Vervang `EncodeTypes.DatabarStackedOmniDirectional` door een andere `EncodeTypes`‑waarde, zoals `DatabarStacked` (niet‑omnidirectioneel) of `DatabarLimited`. |
| **Hoe wijzig ik het uitvoerformaat?** | Gebruik `BarCodeImageFormat.Jpeg`, `Gif` of `Bmp` in de `Save`‑aanroep. |
| **Is het GTIN‑14‑formaat verplicht?** | De DataBar‑symbologie verwacht een numerieke string voorafgegaan door een geschikte AI (bijv. `(01)` voor GTIN‑14). Pas de data aan op basis van jouw gebruikssituatie. |
| **Wat betreft DPI‑instellingen?** | De generator houdt rekening met de eigenschap `Resolution`. Voor afdrukken met hoge resolutie, stel `barcodeGen.Parameters.ImageResolution.DpiX` en `DpiY` dienovereenkomstig in. |

## Pro‑tips

- **Batch‑generatie:** Plaats de opslaalogica in een lus en geef een lijst met GTIN‑s door om duizenden barcodes automatisch te genereren.
- **Validatie:** Gebruik `barcodeGen.Validate()` vóór het opslaan om slecht gevormde data vroegtijdig te detecteren.
- **Prestaties:** Het hergebruiken van dezelfde `BarcodeGenerator`‑instantie (alleen parameters wijzigen) is sneller dan voor elke afbeelding een nieuw object aanmaken.

## Volgende stappen

Nu je **gestapelde databars barcode** kunt maken met aangepaste aspectratio's, overweeg dan het volgende:

- Het toevoegen van mens‑leesbare tekst onder de barcode (`barcodeGen.Parameters.Barcode.CodeText`).
- Exporteren naar **PDF** voor afdrukbare etiketten (`BarCodeImageFormat.Pdf`).
- De generator integreren in een web‑API om barcodes op aanvraag te leveren.
- Experimenteren met andere **secundaire trefwoorden** zoals *C# barcode generator* en *barcode aspect ratio* om je implementatie af te stemmen op specifieke hardware.

Veel programmeerplezier, en geniet van de flexibiliteit die Aspose.BarCode biedt voor je C#‑barcode‑projecten!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Maak gestapelde databar barcode in C# – stapsgewijze handleiding](/barcode/english/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/)
- [databar gestapelde omnidirectionele barcode in C# – Complete gids](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [Hoe maak je databar PNG‑afbeeldingen met C# en Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}