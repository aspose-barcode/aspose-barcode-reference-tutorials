---
category: general
date: 2026-07-18
description: Maak snel een PDF417‑barcode met C#. Leer hoe je een barcode genereert,
  parameters instelt en afbeeldingsbestanden opslaat – inclusief AI 10‑afhandeling.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate barcode
- how to set parameters
- how to save image
- barcode ai 10
language: nl
lastmod: 2026-07-18
og_description: Maak PDF417‑barcode in C# met een volledige walkthrough. Ontdek hoe
  je een barcode genereert, instellingen aanpast en afbeeldingen opslaat, terwijl
  je AI 10 afhandelt.
og_image_alt: Screenshot illustrating create pdf417 barcode code in C#
og_title: PDF417-barcode maken in C# – Snelle, flexibele, volledige code‑voorbeeld
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  headline: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  name: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  steps:
  - name: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
    text: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
  - name: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
    text: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
  - name: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
    text: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspnet
- barcode-generation
title: PDF417‑barcode maken in C# – Complete stapsgewijze handleiding
url: /nl/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PDF417-barcode maken in C# – Complete stapsgewijze gids

Heb je ooit **pdf417 barcode maken** nodig gehad maar wist je niet welke bibliotheek of instellingen je moet kiezen? Je bent niet alleen—veel ontwikkelaars lopen tegen die muur aan wanneer ze voor het eerst met GS1‑Micro‑PDF417 spelen. Het goede nieuws is dat je met een paar regels C# een perfect opgemaakte barcode kunt genereren, het uiterlijk kunt aanpassen en de afbeelding direct naar schijf kunt wegschrijven.

In deze tutorial lopen we stap voor stap door **hoe barcode te genereren** met de Aspose.BarCode bibliotheek, laten we **hoe parameters in te stellen** zien, zoals X‑dimension en kolomaantal, en demonstreren we **hoe afbeelding op te slaan** voor zowel AI 10 als AI 21 varianten. Aan het einde heb je een herbruikbare codefragment die je in elk .NET‑project kunt gebruiken.

## Vereisten

- .NET 6+ of .NET Framework 4.7.2 (elke recente runtime werkt)
- Visual Studio 2022 of je favoriete C#‑editor
- Het **Aspose.BarCode for .NET** NuGet‑pakket (`Install-Package Aspose.BarCode`)
- Een beschrijfbare map op schijf waar de PNG‑bestanden terechtkomen

Dat is alles—geen extra tools, geen complexe configuratie. Klaar? Laten we beginnen.

## Stap 1: PDF417-barcode maken met GS1‑Micro-formaat

Het eerste wat we doen is een **pdf417 barcode maken** object aanmaken en het de initiële AI‑gegevens geven. In GS1‑Micro‑PDF417 is AI 10 (batch/lot‑nummer) vaak het startpunt, dus we coderen het meteen.

```csharp
using Aspose.BarCode.Generation;

// Define where the PNGs will be saved
string outputDir = @"C:\Barcodes\";

// Instantiate the generator for GS1‑Micro‑PDF417
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.GS1MicroPdf417,
    "(10)ABCD12345(240)ABCD");   // AI 10 + additional data
```

> **Waarom dit belangrijk is:** De `EncodeTypes.GS1MicroPdf417` vertelt de bibliotheek om de GS1‑Micro‑specificatie te volgen, die automatisch de AI‑haakjes toevoegt. Als je dit overslaat, krijg je een generieke PDF417 die mogelijk niet scanbaar is in retailomgevingen.

## Stap 2: Hoe parameters in te stellen voor de barcode

Nu we een barcode‑instantie hebben, moeten we de visuele kenmerken fijn afstemmen. Hier komt **hoe parameters in te stellen** om de hoek kijken. We passen drie veelvoorkomende instellingen aan:

1. **X‑dimension** – bepaalt de breedte van de kleinste balk (in pixels)
2. **Column count** – beïnvloedt de algehele vorm; minder kolommen = hogere barcode
3. **IsLinked** – schakelt de optionele linkmodule in die de barcode aan de gegevensreeks koppelt

```csharp
// X‑dimension: 2 pixels per module (good balance of size vs readability)
barcode.Parameters.Barcode.XDimension.Pixels = 2;

// Columns: 3 columns makes the barcode compact yet readable
barcode.Parameters.Barcode.Pdf417.Columns = 3;

// Enable linking (adds a special pattern that some scanners use)
barcode.Parameters.Barcode.Pdf417.IsLinked = true;
```

> **Pro tip:** Als je richt op mobiel scannen, verhoog de X‑dimension tot 3‑4 pixels; grotere modules overleven lage‑resolutiecamera's beter.

## Stap 3: Hoe afbeelding op te slaan – Eerste versie (AI 10)

Met de generator geconfigureerd, kunnen we eindelijk **hoe afbeelding op te slaan**. De `Save`‑methode schrijft de barcode naar een bestand in het opgegeven formaat. Hier gebruiken we PNG omdat het scherpe randen behoudt zonder compressie‑artefacten.

```csharp
// Save the barcode that encodes AI 10
barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
```

Op dit moment zou je een bestand met de naam `GS1MicroPdf417_AI10.png` in je `outputDir` moeten zien. Open het met een willekeurige afbeeldingsviewer—je ziet een schone, hoog‑contrast PDF417 klaar voor afdrukken.

## Stap 4: Overschakelen naar een andere AI (AI 21) en opnieuw opslaan

Vaak moet je een andere toepassingsidentificator coderen, zoals AI 21 (serienummer). Het wijzigen van de `CodeText`‑eigenschap is alles wat nodig is. Dit toont **barcode ai 10** versus **barcode ai 21** afhandeling in één keer.

```csharp
// Change the encoded data – now using AI 21
barcode.CodeText = "(21)ABCD12345(240)ABCD";

// Save the new variant
barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
```

> **Wat als je meer AI's nodig hebt?** Voeg ze gewoon samen in dezelfde string, bijv. `"(10)ABCD(21)12345(240)XYZ"`. De bibliotheek verwerkt de haakjes automatisch.

## Volledig werkend voorbeeld

Alles samenvoegend, hier is een zelfstandige programma dat je kunt kopiëren‑plakken in een console‑applicatie:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Output folder – change to suit your environment
        string outputDir = @"C:\Barcodes\";

        // 2️⃣ Create generator with initial AI 10 data
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(10)ABCD12345(240)ABCD");

        // 3️⃣ Set visual parameters
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // how to set parameters
        barcode.Parameters.Barcode.Pdf417.Columns = 3;
        barcode.Parameters.Barcode.Pdf417.IsLinked = true;

        // 4️⃣ Save first image (AI 10)
        barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 10 barcode.");

        // 5️⃣ Switch to AI 21 and save second image
        barcode.CodeText = "(21)ABCD12345(240)ABCD";
        barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 21 barcode.");
    }
}
```

**Verwachte output:** Twee PNG‑bestanden verschijnen in `C:\Barcodes\`—`GS1MicroPdf417_AI10.png` en `GS1MicroPdf417_AI21.png`. Beide bevatten een scanbare PDF417; de eerste codeert AI 10, de tweede AI 21.

## Veelvoorkomende valkuilen & hoe ze te vermijden

- **Ontbrekende maprechten:** Als `Save` een `UnauthorizedAccessException` gooit, controleer dan dubbel of het pad bestaat en je app schrijfrechten heeft.
- **Onjuiste AI‑opmaak:** Het vergeten van de haakjes (`(10)`) zorgt ervoor dat de barcode als gewone data wordt behandeld, waardoor GS1‑validatie mislukt.
- **Te kleine X‑dimension:** Balken dunner dan 1 pixel kunnen verdwijnen wanneer de afbeelding wordt geschaald. Houd minimaal 2 pixels aan voor weergave op scherm.

## Volgende stappen & gerelateerde onderwerpen

Nu je weet **hoe barcode te genereren**, **hoe parameters in te stellen**, en **hoe afbeelding op te slaan**, wil je misschien verkennen:

- [Hoe barcode maken – Compact PDF417 met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hoe barcode stille zone maken voor ITF-14 met Aspose.BarCode voor .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Hoe Aztec-barcode maken met foutcorrectie in .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)

---

### Snelle samenvatting

- **pdf417 barcode maken** met `BarcodeGenerator` en `EncodeTypes.GS1MicroPdf417`
- **Hoe parameters in te stellen** zoals X‑dimension, kolommen en koppeling
- **Hoe afbeelding op te slaan** als PNG voor zowel AI 10 als AI 21 varianten
- Verwerkte **barcode ai 10** en verwisselde naar **barcode ai 21** met een enkele eigenschapswijziging

Probeer het, pas de instellingen aan, en je hebt een robuuste barcode‑engine klaar voor productie. Heb je vragen of wil je dieper ingaan? Laat een reactie achter—veel plezier met coderen!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}