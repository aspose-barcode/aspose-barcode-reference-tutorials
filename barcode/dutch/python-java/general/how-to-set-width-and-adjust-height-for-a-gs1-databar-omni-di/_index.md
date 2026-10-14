---
category: general
date: 2026-09-29
description: Hoe de breedte van een GS1 DataBar Omni‑Directional barcode in te stellen
  en de hoogte te wijzigen met C#. Volg een stapsgewijze handleiding met volledige
  code.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to change height
language: nl
lastmod: 2026-09-29
og_description: Hoe de breedte van een GS1 DataBar Omni‑Directional barcode in te
  stellen en hoe de hoogte in C# te wijzigen. Leer de exacte API‑aanroepen en bekijk
  een volledig uitvoerbaar voorbeeld.
og_image_alt: Screenshot of two GS1 DataBar barcodes with different heights
og_title: Hoe de breedte van een GS1 DataBar‑barcode in te stellen – C#‑gids
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  headline: How to set width and adjust height for a GS1 DataBar Omni‑Directional
    barcode in C#
  type: TechArticle
- description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  name: How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode
    in C#
  steps:
  - name: Why the X‑dimension matters
    text: '* **Scanner tolerance** – Most scanners expect a minimum module width;
      too small a value can cause read errors. * **Print resolution** – When printing
      at 300 dpi, a 2 px module translates to ~0.17 mm, which is within the recommended
      range for GS1 DataBar. * **Image size** – Larger X‑dimension values'
  - name: Tips for reliable width settings
    text: '* **Never set XDimension below 1 px** – the library will clamp the value,
      but the resulting barcode may be unreadable. * **Match the target DPI** – if
      you render to a high‑resolution format (e.g., TIFF at 600 dpi), increase XDimension
      proportionally. * **Test with a real scanner** – after changing t'
  - name: Understanding bar height
    text: '* **Visual balance** – Taller bars improve readability on low‑contrast
      backgrounds but increase the image’s vertical footprint. * **Regulatory limits**
      – Some standards (e.g., retail labeling) specify a maximum bar height; adjust
      accordingly. * **Aspect ratio** – Changing height does not affect the '
  - name: Edge‑case handling for height adjustments
    text: '| Situation | Recommended approach | |-----------|----------------------|
      | Height < 10 px | Increase to at least 10 px; very short bars may be ignored
      by scanners. | | Very tall bars (≥ 100 px) | Verify that the output medium (paper,
      label) can accommodate the extra space. | | Need proportional sca'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
- GS1 DataBar
title: Hoe de breedte in te stellen en de hoogte aan te passen voor een GS1 DataBar
  omnidirectionele barcode in C#
url: /nl/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe breedte instellen en hoogte aanpassen voor een GS1 DataBar Omni‑Directional barcode in C#

Het instellen van de breedte van een GS1 DataBar Omni‑Directional barcode is een veelvoorkomende taak wanneer je exacte afmetingen nodig hebt voor scanapparatuur. In deze tutorial leer je ook **hoe je de hoogte wijzigt** zodat de barcode perfect in je lay-out past. De gids leidt je door het volledige proces, van projectconfiguratie tot een volledig uitvoerbaar code‑voorbeeld.

We behandelen:

* Het vereiste NuGet‑pakket en .NET‑versie.
* Waarom X‑dimension (module‑breedte) belangrijk is voor de leesbaarheid van de barcode.
* De exacte API‑aanroepen om **hoe de breedte in te stellen** en **hoe de hoogte te wijzigen**.
* Afhandeling van randgevallen zoals minimale module‑breedte en high‑resolution rendering.
* Een compleet copy‑and‑paste voorbeeld dat twee PNG‑bestanden produceert met verschillende balkhoogtes.

## Vereisten

| Vereiste | Reden |
|------------|--------|
| .NET 6.0 SDK or later | Het voorbeeld gebruikt moderne C#‑functies en draait op Windows, Linux of macOS. |
| Visual Studio 2022 (or any C# IDE) | Biedt IntelliSense voor de Aspose.Barcode API. |
| **Aspose.Barcode for .NET** NuGet package | Bevat `BarcodeGenerator`, `EncodeTypes` en ondersteuning voor beeldformaten. Installeer met `dotnet add package Aspose.Barcode`. |
| Write permission to a folder where PNG files will be saved | De generator schrijft de uitvoerafbeeldingen naar schijf. |

## Hoe de breedte van de barcode in te stellen

De stap **hoe de breedte in te stellen** wordt uitgevoerd door de `XDimension`‑eigenschap van de barcode‑parameters te configureren. `XDimension` vertegenwoordigt de module‑breedte (de kleinste balk of spatie) in pixels, points of millimeters. Het correct instellen zorgt ervoor dat de barcode voldoet aan de specificaties van de scanner.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a generator for a GS1 DataBar Omni‑Directional barcode.
            // The value "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ **How to set width**: define the module width (X‑dimension) in pixels.
            // A value of 2 px is a common choice that balances readability and image size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // The remaining steps (height, saving) are shown in the next section.
```

### Waarom de X‑dimensie belangrijk is

* **Scanner tolerantie** – De meeste scanners verwachten een minimale module‑breedte; een te kleine waarde kan leesfouten veroorzaken.
* **Printresolutie** – Bij afdrukken op 300 dpi komt een 2 px module overeen met ~0,17 mm, wat binnen het aanbevolen bereik voor GS1 DataBar valt.
* **Afbeeldingsgrootte** – Grotere X‑dimensie‑waarden vergroten de totale barcode‑breedte, wat invloed kan hebben op lay‑outbeperkingen.

### Tips voor betrouwbare breedte‑instellingen

* **Stel XDimension nooit lager dan 1 px** – de bibliotheek zal de waarde begrenzen, maar de resulterende barcode kan onleesbaar zijn.
* **Stem de DPI af op het doel** – als je rendert naar een hoge‑resolutieformaat (bijv. TIFF op 600 dpi), verhoog XDimension evenredig.
* **Test met een echte scanner** – na het wijzigen van de breedte, valideer de barcode op het apparaat dat deze zal lezen.

## Hoe de hoogte van de barcode te wijzigen

Zodra de breedte is gedefinieerd, kun je de verticale grootte regelen met de `BarHeight`‑eigenschap. De volgende code toont **hoe je de hoogte wijzigt** van 30 px naar 60 px en twee afzonderlijke afbeeldingen opslaat.

```csharp
            // 3️⃣ Set the first bar height to 30 pixels and save the image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ **How to change height**: increase the bar height to 60 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            // The program ends here; two PNG files are written to the execution folder.
        }
    }
}
```

### Inzicht in balkhoogte

* **Visueel evenwicht** – Hogere balken verbeteren de leesbaarheid op laag‑contrast achtergronden, maar vergroten de verticale afdruk van de afbeelding.
* **Regelgevende limieten** – Sommige normen (bijv. retail‑etikettering) specificeren een maximale balkhoogte; pas dit dienovereenkomstig aan.
* **Aspectratio** – Het wijzigen van de hoogte beïnvloedt de module‑breedte niet; je kunt beide onafhankelijk fijn afstellen.

### Afhandeling van randgevallen voor hoogte‑aanpassingen

| Situatie | Aanbevolen aanpak |
|-----------|----------------------|
| Height < 10 px | Verhoog tot minimaal 10 px; zeer korte balken kunnen door scanners worden genegeerd. |
| Very tall bars (≥ 100 px) | Controleer of het uitvoermedium (papier, label) de extra ruimte kan opvangen. |
| Need proportional scaling | Bereken `BarHeight = XDimension * desiredRatio` om visuele consistentie te behouden. |

## Volledig, uitvoerbaar voorbeeld

Hieronder staat het volledige programma dat de stappen **hoe de breedte in te stellen** en **hoe de hoogte te wijzigen** combineert. Kopieer de code naar een nieuw console‑project, herstel het Aspose.Barcode NuGet‑pakket en voer het uit. Er verschijnen twee PNG‑bestanden in de map `bin/Debug/net6.0`.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // Initialize the barcode generator (GS1 DataBar Omni‑Directional)
            // ------------------------------------------------------------
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // ------------------------------------------------------------
            // **How to set width** – define the module width (X‑dimension)
            // ------------------------------------------------------------
            generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px = ~0.17 mm at 300 dpi

            // ------------------------------------------------------------
            // First image: bar height = 30 px
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight30Pixels.png");

            // ------------------------------------------------------------
            // **How to change height** – increase to 60 px and save again
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight60Pixels.png");

            // ------------------------------------------------------------
            // End of demo
            // ------------------------------------------------------------
        }
    }
}
```

**Verwachte output**

Het uitvoeren van het programma produceert twee PNG‑bestanden:

* `DatabarBarHeight30Pixels.png` – een barcode 30 px hoog, 2 px brede modules.
* `DatabarBarHeight60Pixels.png` – dezelfde barcode met het dubbele van de verticale grootte.

Open een van beide afbeeldingen in een viewer; je ziet een nette GS1 DataBar Omni‑Directional symbool klaar om te scannen.

## Veelgestelde vragen beantwoord

| Vraag | Antwoord |
|----------|--------|
| *Kan ik millimeters gebruiken in plaats van pixels?* | Ja. Stel `generator.Parameters.Barcode.XDimension.Millimeters` en `BarHeight.Millimeters` in. De bibliotheek converteert naar apparaat‑pixels op basis van de DPI van de afbeelding. |
| *Wat als ik een ander barcode‑type nodig heb?* | Vervang `EncodeTypes.DatabarOmniDirectional` door een andere `EncodeTypes`‑waarde (bijv. `EncodeTypes.QR`). Breedte‑ en hoogte‑eigenschappen werken op dezelfde manier. |
| *Is er een manier om SVG in plaats van PNG te genereren?* | Gebruik `BarCodeImageFormat.Svg` in de `Save`‑aanroep. De breedte/hoogte‑instellingen blijven van toepassing. |
| *Moet ik `generator.Dispose()` aanroepen?* | De `BarcodeGenerator` implementeert `IDisposable`. In een console‑app kun je het in een `using`‑blok plaatsen, maar voor kort‑levende voorbeelden is het optioneel. |

## Conclusie

Je weet nu **hoe de breedte in te stellen** van een GS1 DataBar Omni‑Directional barcode en **hoe de hoogte te wijzigen** met de Aspose.Barcode API in C#. Het volledige voorbeeld laat zien hoe je een generator maakt, `XDimension` en `BarHeight` configureert, en PNG‑bestanden opslaat met verschillende verticale afmetingen.  

Vanaf hier kun je:

* Experimenteren met andere `EncodeTypes` (bijv. QR, Code128).
* Renderen naar hoge‑resolutieformaten zoals TIFF voor afdrukken.
* De generator integreren in een web‑API die barcodes on‑the‑fly retourneert.

Happy coding, and may your barcodes always scan cleanly!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe de barcode‑hoogte te wijzigen in C# – Complete gids](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Barcode‑generator voorbeeld in C# – breedte en hoogte instellen](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [Hoe een barcode‑generator C# te gebruiken om DataBar Omni‑directional barcodes te maken](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}