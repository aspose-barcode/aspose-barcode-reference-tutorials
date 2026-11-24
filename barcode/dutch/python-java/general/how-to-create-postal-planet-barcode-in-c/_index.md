---
category: general
date: 2026-11-23
description: Maak een postal planet barcode in C# met Aspose.BarCode. Leer hoe je
  een planet barcode genereert, de X‑dimensie instelt en gevulde of lege staven opslaat.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal planet barcode
- how to generate planet barcode
- Aspose.BarCode C#
- postal barcode example
- Planet barcode settings
language: nl
lastmod: 2026-11-23
og_description: Maak een postale planet barcode in C# en leer hoe je een planet barcode
  genereert met Aspose.BarCode. Volg het volledige voorbeeld om gevulde en lege balken
  te produceren.
og_image_alt: Example of a created postal planet barcode with filled bars
og_title: Hoe maak je een Postal Planet‑barcode in C# – stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  headline: How to create postal planet barcode in C#
  type: TechArticle
- description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  name: How to create postal planet barcode in C#
  steps:
  - name: Changing the image format
    text: If your downstream system prefers JPEG, replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. JPEG introduces compression artifacts, so use
      it only when file size is a critical constraint.
  - name: Scaling the barcode
    text: 'You can enlarge the barcode while preserving the module width by adjusting
      the `Resolution` property:'
  - name: Using a custom background color
    text: 'The background can be set with:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Hoe maak je een Postal Planet‑barcode in C#
url: /nl/python-java/general/how-to-create-postal-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe maak je een postal planet barcode in C#

Als je een **postal planet barcode** moet maken in een .NET‑applicatie, laat deze gids je precies zien **hoe je een planet barcode genereert** met behulp van de Aspose.BarCode‑bibliotheek. Je ziet hoe je de X‑dimension configureert, schakelt tussen gevulde en lege staven, en de afbeeldingen opslaat in PNG‑formaat.

Het genereren van een Planet‑barcode is gebruikelijk voor postdiensten die hoge dichtheid en machinaal leesbare symbolen vereisen. Aan het einde van deze tutorial heb je twee PNG‑bestanden—een met solide staven en een met holle staven—klaar voor integratie in elke verzendworkflow.

## Vereisten

* .NET 6.0 SDK of later geïnstalleerd.
* Visual Studio 2022 (of een andere C#‑editor) geconfigureerd voor .NET‑ontwikkeling.
* Een actieve NuGet‑licentie voor **Aspose.BarCode for .NET**. Installeer het pakket met:

```bash
dotnet add package Aspose.BarCode
```

Er zijn geen extra externe services vereist; de bibliotheek voert alle codering lokaal uit.

## Stap 1 – maak een postal planet barcode

De eerste handeling is het instantieren van een `BarcodeGenerator` voor de **Planet**‑symbologie en het leveren van de te coderen gegevens. De gegevensreeks moet numeriek zijn en mag maximaal 12 cijfers bevatten volgens de post‑specificatie.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Het aanmaken van de generator reserveert alle interne structuren die nodig zijn voor het renderen. De enum‑waarde `EncodeTypes.Planet` selecteert het juiste coderingsalgoritme voor het postformaat.

## Stap 2 – stel de X‑dimension in voor betere zichtbaarheid

De X‑dimension bepaalt de breedte van één module (het kleinste staaf‑element). Een waarde van 4 pixels biedt een duidelijke visuele weergave zonder de totale afbeelding te vergroten.

```csharp
// Step 2: Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
```

Het aanpassen van de X‑dimension is essentieel wanneer de barcode wordt afgedrukt op media met lage resolutie. Dezelfde instelling wordt opnieuw gebruikt voor de lege‑staven‑versie om beide afbeeldingen consistent te houden.

## Stap 3 – sla de barcode op met gevulde staven

Standaard rendert de generator **gevulde staven** (solide zwarte modules). Het opslaan van de afbeelding gebeurt met één methode‑aanroep die het PNG‑bestand naar schijf schrijft.

```csharp
// Step 3: Save the barcode with the default setting (filled bars)
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Vervang `YOUR_DIRECTORY` door het daadwerkelijke pad waar je de uitvoerbestanden wilt opslaan. De enumeratie `BarCodeImageFormat.Png` garandeert verliesloze compressie, wat ideaal is voor verdere verwerking.

## Stap 4 – maak een tweede Planet barcode‑generator voor lege staven

Om een versie te maken die **lege staven** gebruikt (witte modules op een zwarte achtergrond), heb je een tweede `BarcodeGenerator`‑instantie nodig. Het hergebruiken van dezelfde gegevensreeks zorgt ervoor dat beide afbeeldingen dezelfde postcode weergeven.

```csharp
// Step 4: Create another Planet barcode generator for the same data
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Het aanmaken van een aparte generator isoleert de eigenschap `FilledBars`, waardoor je de visuele stijl kunt schakelen zonder de eerste afbeelding te beïnvloeden.

## Stap 5 – configureer de generator om lege staven te renderen

De `FilledBars`‑vlag schakelt de rendermodus. Door deze op `false` te zetten, wordt de bibliotheek geïnstrueerd de staven als leeg (transparant) te tekenen terwijl de achtergrond solide blijft.

```csharp
// Step 5: Apply the same X‑dimension and configure empty bars
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
planetEmpty.Parameters.Barcode.FilledBars = false;
```

Het behouden van dezelfde X‑dimension als de gevulde versie garandeert dat beide PNG‑bestanden dezelfde afmetingen hebben, wat de lay‑outberekeningen in afdruksjablonen vereenvoudigt.

## Stap 6 – sla de barcode op die lege staven rendert

Schrijf tenslotte de lege‑staven‑afbeelding naar schijf. Hetzelfde PNG‑formaat wordt gebruikt, maar je kunt overschakelen naar JPEG of BMP door de waarde van `BarCodeImageFormat` te wijzigen.

```csharp
// Step 6: Save the barcode that renders empty bars
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

Op dit punt heb je twee bestanden:

* `PostalPlanetFilledBars.png` – solide zwarte staven.
* `PostalPlanetEmptyBars.png` – holle staven op een zwarte achtergrond.

Beide voldoen aan de post‑specificatie voor de Planet‑symbologie.

## Complete broncode

Alle stappen samenvoegen levert een compacte console‑applicatie op die je direct kunt uitvoeren.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a Planet barcode with filled bars
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Create a Planet barcode with empty bars
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

Compileer en voer het programma uit:

```bash
dotnet run
```

De console drukt *Barcodes generated successfully.* af en de twee PNG‑bestanden verschijnen in de projectmap.

## Verwachte uitvoer

Hieronder zie je een visuele weergave van de afbeelding met gevulde staven. Het lege‑staven‑tegenovergestelde ziet er identiek uit, behalve dat de staven transparant zijn.

![Voorbeeld van een gemaakte postal planet barcode met gevulde staven](postal-planet-filled.png)

*Afbeeldings‑alt‑tekst:* **Voorbeeld van een gemaakte postal planet barcode met gevulde staven** (bevat het primaire trefwoord).

Beide afbeeldingen zijn standaard 150 × 150 pixels, maar je kunt de totale grootte regelen met de parameters `ImageWidth` en `ImageHeight` als een andere resolutie vereist is.

## Optionele variaties

### Het wijzigen van het afbeeldingformaat

Als je downstream‑systeem JPEG verkiest, vervang dan `BarCodeImageFormat.Png` door `BarCodeImageFormat.Jpeg`. JPEG introduceert compressie‑artefacten, dus gebruik het alleen wanneer de bestandsgrootte een kritieke beperking is.

### De barcode schalen

Je kunt de barcode vergroten terwijl je de module‑breedte behoudt door de eigenschap `Resolution` aan te passen:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI
```

Hogere DPI‑waarden verbeteren de afdrukkwaliteit op laserprinters.

### Een aangepaste achtergrondkleur gebruiken

De achtergrond kan worden ingesteld met:

```csharp
planetEmpty.Parameters.Barcode.BackColor = System.Drawing.Color.LightGray;
```

Dit is nuttig voor visuele tests, maar moet worden vermeden bij productie‑postlabels, die een witte achtergrond vereisen.

## Veelgestelde vragen

**Werkt dit met .NET Core?**  
Ja. De Aspose.BarCode‑bibliotheek richt zich op .NET Standard 2.0, wat compatibel is met .NET 5, .NET 6 en .NET Core 3.1.

**Wat als de gegevensreeks niet‑numerieke tekens bevat?**  
Planet‑barcodes accepteren alleen numerieke invoer. Het leveren van letters of symbolen veroorzaakt een `BarcodeException`. Valideer de invoer voordat je de generator maakt.

**Kan ik een barcode in het geheugen genereren zonder naar schijf te schrijven?**  
Gebruik de methode `GenerateBarCodeImage` om een `System.Drawing.Image`‑object te verkrijgen, en stream deze vervolgens direct naar een response of database.

## Conclusie

Je weet nu hoe je een **postal planet barcode** in C# maakt en begrijpt **hoe je een planet barcode** genereert met zowel gevulde als lege staaf‑stijlen. De tutorial besprak de volledige workflow—van het initialiseren van de generator, het configureren van de X‑dimension, het schakelen van de `FilledBars`‑vlag, tot het opslaan van PNG‑bestanden. Experimenteer met afbeeldingformaten, DPI‑instellingen en achtergrondkleuren om de barcode aan te passen aan jouw specifieke verzendsysteem.

Voor de volgende stap, verken andere post‑symbologieën zoals **POSTNET** of **Intelligent Mail** met dezelfde Aspose.BarCode‑API. Het aanpassen van parameters zoals `EncodeTypes.Postnet` volgt hetzelfde patroon dat hier wordt getoond, waardoor je een uitgebreide barcode‑generatiesuite kunt bouwen in één code‑basis.

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Maak een lege planet barcode, genereer postal barcode in C#](/barcode/english/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/)
- [Hoe breedte instellen en een Planet barcode genereren in C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Genereer Postal Barcode in C# – Complete gids met Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}