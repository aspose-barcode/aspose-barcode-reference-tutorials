---
category: general
date: 2026-08-03
description: Maak een barcode‑PNG in C# en leer hoe je de beeldverhouding van DataBar‑afbeeldingen
  kunt aanpassen. Volg dit volledige voorbeeld met code en tips.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode PNG
- how to change aspect ratio
- Aspose.BarCode C#
- DataBar stacked omnidirectional
- barcode image format PNG
language: nl
lastmod: 2026-08-03
og_description: Maak een barcode‑PNG in C# en zie hoe je de beeldverhouding voor DataBar‑barcodes
  kunt aanpassen. Deze gids biedt kant‑klaar werkende code en praktische tips.
og_image_alt: Sample barcode PNG generated with aspect ratio 15
og_title: Barcode PNG maken in C# – volledig voorbeeld met aspect‑ratio‑controle
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  headline: Create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  name: Create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: How to change other visual properties?
    text: 'You can adjust foreground color, background color, or add human‑readable
      text through the `generator.Parameters.Barcode` object. For example:'
  - name: What if I need a different image format?
    text: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed.
      PNG remains the best choice for lossless barcode images.
  - name: Does the aspect ratio affect scanning speed?
    text: Higher aspect ratios increase the barcode’s height, which can improve scan
      reliability on devices that struggle with short stacked symbols. However, extremely
      tall barcodes may not fit on small labels, so test with your target hardware.
  - name: Can I generate multiple barcodes in a loop?
    text: Yes. Create a new `BarcodeGenerator` instance for each data string or reuse
      the same instance while updating `CodeText` and `DataBar.AspectRatio`. This
      approach reduces object allocation overhead.
  type: HowTo
tags:
- barcode
- C#
- PNG
- Aspose
title: Barcode PNG maken in C# – stapsgewijze handleiding
url: /nl/python-java/general/create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode PNG maken in C# – stapsgewijze handleiding

Als je een **barcode PNG** moet **maken** in C#, laat deze tutorial je precies zien hoe. Je genereert een gestapelde omnidirectionele DataBar‑barcode, slaat deze op als PNG‑bestand en leert **hoe je de beeldverhouding kunt aanpassen** aan verschillende scanomgevingen.

De gids behandelt alles wat je nodig hebt: vereiste pakketten, een compleet, uitvoerbaar programma en uitleg waarom elke instelling belangrijk is. Aan het einde heb je twee PNG‑bestanden – één met een beeldverhouding van 15 en een andere met 30 – klaar voor testen of productie.

## Vereisten

Zorg er voordat je begint voor dat je het volgende hebt:

- .NET 6.0 SDK of later geïnstalleerd
- Visual Studio 2022 (of een andere C#‑IDE)
- Een NuGet‑referentie naar **Aspose.BarCode** (de bibliotheek die `BarcodeGenerator` levert)
- Schrijfrechten in de map waar de PNG‑bestanden worden opgeslagen

Je kunt het Aspose.BarCode‑pakket toevoegen met het volgende commando:

```bash
dotnet add package Aspose.BarCode
```

## Stap 1: Het project opzetten en namespaces importeren

Maak een nieuwe console‑applicatie aan en importeer de namespaces die nodig zijn voor barcode‑generatie en bestands‑I/O.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main()
        {
            // All subsequent steps are inside Main
```

**Waarom dit belangrijk is:** Het importeren van `Aspose.BarCode.Generation` geeft je toegang tot `BarcodeGenerator`. Het plaatsen van de code binnen `Main` maakt het voorbeeld zelf‑voorzienend en eenvoudig uit te voeren.

## Stap 2: Een barcode‑generator maken voor een gestapelde omnidirectionele DataBar

Instantieer `BarcodeGenerator` met het type `EncodeTypes.DatabarStackedOmniDirectional` en een voorbeeld‑GS1‑128‑datastreek.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");
```

**Waarom dit belangrijk is:** Het gekozen encode‑type produceert een high‑density DataBar die door de meeste moderne scanners kan worden gelezen. De datastreek volgt het GS1 Application Identifier (01)‑formaat, dat veel wordt gebruikt voor product‑identifiers.

## Stap 3: De X‑dimensie (module‑breedte) in pixels definiëren

Stel de module‑breedte in om de totale grootte van de barcode te regelen zonder de leesbaarheid te beïnvloeden.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Waarom dit belangrijk is:** Een X‑dimensie van 2 pixels levert een barcode op die noch te klein is voor scanners, noch te groot voor typische labelruimtes.

## Stap 4: Het eerste PNG opslaan met een beeldverhouding van 15

Pas de DataBar‑beeldverhouding aan en sla vervolgens de afbeelding op als PNG‑bestand.

```csharp
            // Step 4: Set the DataBar aspect ratio to 15 and save the image
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            string outputPath15 = @"YOUR_DIRECTORY\DatabarAspectRatio15.png";
            generator.Save(outputPath15, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath15} (aspect ratio 15).");
```

**Waarom dit belangrijk is:** De beeldverhouding bepaalt de hoogte‑tot‑breedte‑relatie van de gestapelde DataBar. Een verhouding van 15 is een veelgebruikt standaard dat leesbaarheid en labelhoogte in balans brengt.

## Stap 5: De beeldverhouding wijzigen naar 30 en een tweede PNG opslaan

Wijzig dezelfde generator‑instantie om een grotere beeldverhouding te gebruiken en sla daarna de tweede afbeelding op.

```csharp
            // Step 5: Change the aspect ratio to 30 and save another image
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string outputPath30 = @"YOUR_DIRECTORY\DatabarAspectRatio30.png";
            generator.Save(outputPath30, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath30} (aspect ratio 30).");
        }
    }
}
```

**Waarom dit belangrijk is:** Een hogere beeldverhouding strekt de barcode verticaal uit, wat de scanbetrouwbaarheid kan verbeteren op apparaten met lage resolutie of wanneer het label op smal materiaal wordt afgedrukt.

## Verwachte output

Het uitvoeren van het programma maakt twee PNG‑bestanden aan:

| Bestand                              | Beeldverhouding | Geschatte afmetingen (pixels) |
|--------------------------------------|-----------------|------------------------------|
| `DatabarAspectRatio15.png`           | 15              | 200 × 300 (breedte × hoogte)  |
| `DatabarAspectRatio30.png`           | 30              | 200 × 600 (breedte × hoogte)  |

Beide afbeeldingen bevatten een duidelijke, scanbare DataBar‑barcode die de GS1‑identifier `(01)12345678901231` codeert.

## Veelgestelde vragen en randgevallen

### Hoe andere visuele eigenschappen wijzigen?

Je kunt de voorgrondkleur, achtergrondkleur of menselijk leesbare tekst aanpassen via het object `generator.Parameters.Barcode`. Bijvoorbeeld:

```csharp
generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
generator.Parameters.Barcode.CodeTextParameters.ShowCodeText = true;
```

### Wat als ik een ander afbeeldingsformaat nodig heb?

Vervang `BarCodeImageFormat.Png` door `Jpeg`, `Bmp` of `Gif` naar behoefte. PNG blijft de beste keuze voor verliesvrije barcode‑afbeeldingen.

### Heeft de beeldverhouding invloed op de scansnelheid?

Hogere beeldverhoudingen vergroten de hoogte van de barcode, wat de scanbetrouwbaarheid kan verbeteren op apparaten die moeite hebben met korte gestapelde symbolen. Zeer hoge barcodes passen echter mogelijk niet op kleine labels, dus test met je doelhardware.

### Kan ik meerdere barcodes in een lus genereren?

Ja. Maak een nieuwe `BarcodeGenerator`‑instantie voor elke datastreek of hergebruik dezelfde instantie terwijl je `CodeText` en `DataBar.AspectRatio` bijwerkt. Deze aanpak vermindert de overhead van objectallocatie.

## Pro‑tips

- **Herbruik de generator**: Alleen `CodeText` of `AspectRatio` wijzigen voorkomt het opnieuw instantieren van het object, wat batchverwerking versnelt.
- **Valideer de output**: Gebruik een handscanner of een mobiele app om te bevestigen dat de gegenereerde PNG correct wordt gelezen voordat je deze in productie neemt.
- **Bestandsnaamgeving**: Neem de beeldverhouding op in de bestandsnaam (zoals getoond) om variaties tijdens het testen bij te houden.

## Conclusie

Je weet nu hoe je **barcode PNG**‑bestanden kunt **maken** in C# en precies **de beeldverhouding kunt aanpassen** voor gestapelde omnidirectionele DataBar‑symbolen. Het volledige voorbeeld toont initialisatie, X‑dimensie‑instelling, beeldverhouding‑manipulatie en het opslaan van de afbeelding – alles in één enkel, uitvoerbaar programma.

Vanaf hier kun je extra barcode‑typen verkennen, experimenteren met kleuren, of de generator integreren in een groter rapportage‑ of voorraadbeheersysteem. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Customize Barcode - Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}