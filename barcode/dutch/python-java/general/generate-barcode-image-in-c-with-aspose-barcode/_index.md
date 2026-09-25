---
category: general
date: 2026-08-06
description: Genereer barcode‑afbeelding in C# met Aspose.BarCode. Leer hoe je Databar
  genereert, de aangepaste barcode‑grootte aanpast en de barcode‑hoogte wijzigt met
  eenvoudige code.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- how to generate databar
- custom barcode size
- create databar barcode
- change barcode height
language: nl
lastmod: 2026-08-06
og_description: Genereer barcode‑afbeelding in C# met Aspose.BarCode. Deze tutorial
  laat zien hoe je een Databar Omnidirectional‑barcode maakt, de grootte aanpast en
  de barcodehoogte efficiënt wijzigt.
og_image_alt: Screenshot of a Databar barcode generated with custom height in C#
og_title: Barcode‑afbeelding genereren in C# – volledige Aspose.BarCode‑gids
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Generate barcode image in C# using Aspose.BarCode. Learn how to generate
    Databar, adjust custom barcode size, and change barcode height with simple code.
  headline: Generate barcode image in C# with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: The evaluation version of Aspose.BarCode works without a license but adds
      a small watermark. For production use, apply a purchased license using `License
      license = new License(); license.SetLicense("Aspose.BarCode.lic");`.
    question: Can I generate a barcode without installing a license?
  - answer: Yes. Very small X‑dimensions can make the barcode unreadable on low‑resolution
      printers. A minimum of 1 px for screen rendering is recommended; for print,
      use at least 0.25 mm.
    question: Does changing the X‑dimension affect readability?
  - answer: 'Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. You
      may also set `generator.Parameters.ImageQuality` to control compression. ##
      Conclusion You now know how to **generate barcode image** in C# using Aspose.BarCode,
      how to **create Databar barcode**, adjust a **custom barcode size**, '
    question: What if I need to generate a barcode in JPEG format?
  type: FAQPage
tags:
- barcode
- C#
- Aspose.BarCode
title: Barcode‑afbeelding genereren in C# met Aspose.BarCode
url: /nl/python-java/general/generate-barcode-image-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Genereer barcode‑afbeelding in C# met Aspose.BarCode

Als je programmatically **barcode‑afbeelding moet genereren**, laat deze gids je precies zien hoe. Of je nu een retail‑voorraadsysteem of een logistiek‑trackingportaal bouwt, je ziet de volledige workflow voor het maken van een Databar Omnidirectional barcode, het aanpassen van de afmetingen en het opslaan van het resultaat als een PNG‑bestand.

Het genereren van een barcode‑afbeelding is een veelvoorkomende eis, maar ontwikkelaars vragen zich vaak af **hoe ze Databar** kunnen genereren met de exacte grootte die ze nodig hebben. In deze tutorial leer je een Databar‑barcode te maken, de breedte en hoogte aan te passen, en de barcode‑hoogte te wijzigen zonder de hele generator opnieuw te schrijven.

## Voorvereisten

* .NET 6.0 SDK of later (de code werkt met .NET Core en .NET Framework)
* Visual Studio 2022 (of elke IDE die C# ondersteunt)
* Een geldige Aspose.BarCode for .NET‑licentie (de gratis evaluatie werkt voor testen)
* Basiskennis van C#‑syntaxis

## Stap 1: Installeer Aspose.BarCode

Voeg het Aspose.BarCode NuGet‑pakket toe aan je project:

```bash
dotnet add package Aspose.BarCode
```

Het pakket bevat de `BarcodeGenerator`‑klasse die door de hele tutorial wordt gebruikt. Na de installatie herstel je het project om de afhankelijkheden binnen te halen.

## Stap 2: Maak een basis barcode‑generator

De eerste regel code maakt een **barcode‑generator** die een Databar Omnidirectional‑symbool produceert. De `EncodeTypes.DatabarOmniDirectional`‑enum vertelt de bibliotheek welke symbologie te gebruiken, en de gegevensreeks volgt de GS1 Application Identifier‑syntaxis.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a Databar Omnidirectional barcode
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231"); // GS1-14 data (example GTIN)
```

**Waarom dit belangrijk is:** Het `BarcodeGenerator`‑object is het startpunt voor elke barcode‑bewerking. Door `DatabarOmniDirectional` te selecteren, zorg je ervoor dat de output voldoet aan de GS1‑standaard voor retail‑scanning.

## Stap 3: Stel een aangepaste X‑dimensie in (module‑breedte)

De X‑dimensie bepaalt de breedte van de smalste balk. Een kleine pixelwaarde levert een compacte barcode op, terwijl grotere waarden de totale breedte vergroten.

```csharp
        // Step 3: Define a custom X‑dimension (module width) of 2 px
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Uitleg:** Een X‑dimensie van 2 pixel is een veelgebruikte keuze voor hoge‑resolutieschermen. Pas deze waarde aan als je een dichtere of lossere visuele dichtheid nodig hebt.

## Stap 4: Genereer de eerste barcode‑afbeelding met een specifieke hoogte

Barcode‑hoogte is onafhankelijk van de X‑dimensie. Hier stellen we de balkhoogte in op **30 px**, en slaan we de afbeelding op als PNG.

```csharp
        // Step 4: Set bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Resultaat:** Je hebt nu een bestand genaamd `DatabarBarHeight30Pixels.png` dat een Databar‑barcode van 30 px hoogte toont. Dit demonstreert de **aangepaste barcode‑grootte**‑functionaliteit voor een specifiek gebruiksgeval, zoals een klein label.

## Stap 5: Wijzig de barcode‑hoogte voor een grotere versie

Als dezelfde barcode op een groter label moet verschijnen, hoef je alleen de hoogte‑eigenschap aan te passen en dezelfde generator‑instantie opnieuw te gebruiken.

```csharp
        // Step 5: Increase the bar height to 60 px for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
    }
}
```

**Waarom je de generator kunt hergebruiken:** Het wijzigen van `BarHeight.Pixels` werkt de interne lay-out bij zonder het object opnieuw te creëren, wat geheugen bespaart en de gegevensreeks intact houdt. Dit is de aanbevolen manier om **barcode‑hoogte** dynamisch te **wijzigen**.

## Stap 6: Verifieer de output

Open de twee PNG‑bestanden in een willekeurige afbeeldingsviewer. Je zou twee Databar Omnidirectional‑barcodes moeten zien die dezelfde GTIN coderen maar verschillen in verticale grootte:

* `DatabarBarHeight30Pixels.png` – 30 px hoog, geschikt voor compacte kassabonnen.
* `DatabarBarHeight60Pixels.png` – 60 px hoog, ideaal voor grotere schap‑rand‑labels.

Beide afbeeldingen behouden dezelfde X‑dimensie, zodat de balk‑naar‑spatie‑verhouding consistent blijft terwijl de totale hoogte schaalt.

## Veelvoorkomende variaties en randgevallen

| Situatie | Hoe je het aanpakt |
|-----------|--------------------|
| **Andere barcode‑symbologie** | Vervang `EncodeTypes.DatabarOmniDirectional` door een andere enum‑waarde (bijv. `EncodeTypes.Code128`). De rest van de code blijft ongewijzigd. |
| **Niet‑pixel afmetingen** | Gebruik `generator.Parameters.Barcode.XDimension.Millimeters` of `BarHeight.Millimeters` als je fysieke metingen nodig hebt voor print‑klare output. |
| **Transparante achtergrond** | Stel `generator.Parameters.ImageBackgroundColor = Color.Transparent;` in vóór het aanroepen van `Save`. |
| **High‑resolution output** | Verhoog zowel `XDimension.Pixels` als `BarHeight.Pixels` proportioneel, of sla op als `BarCodeImageFormat.Tiff` voor verliesvrije kwaliteit. |
| **Meerdere barcodes in één afbeelding** | Maak afzonderlijke `BarcodeGenerator`‑instanties, render elk naar een `Bitmap`, en combineer ze vervolgens met `Graphics.DrawImage`. |

**Pro tip:** Test de gegenereerde barcode altijd met een echte scanner voordat je deze in productie neemt. Scanners kunnen zeer dunne balken anders interpreteren, afhankelijk van verlichting en sensorkwaliteit.

## Volledige broncode ter referentie

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator for a Databar Omnidirectional barcode
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231"); // Example GTIN

            // Custom X‑dimension (module width) – 2 px
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // Second image: 60 px height (larger barcode)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

Kopieer de code naar een nieuw console‑project, voer het uit, en je ziet de twee PNG‑bestanden verschijnen in de output‑map.

## Veelgestelde vragen

**Q: Kan ik een barcode genereren zonder een licentie te installeren?**  
A: De evaluatieversie van Aspose.BarCode werkt zonder licentie, maar voegt een klein watermerk toe. Voor productie‑gebruik pas je een aangeschafte licentie toe met `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`.

**Q: Heeft het wijzigen van de X‑dimensie invloed op de leesbaarheid?**  
A: Ja. Zeer kleine X‑dimensies kunnen de barcode onleesbaar maken op laag‑resolutie‑printers. Een minimum van 1 px voor schermweergave wordt aanbevolen; voor print gebruik je minstens 0,25 mm.

**Q: Wat als ik een barcode in JPEG‑formaat moet genereren?**  
A: Vervang `BarCodeImageFormat.Png` door `BarCodeImageFormat.Jpeg`. Je kunt ook `generator.Parameters.ImageQuality` instellen om de compressie te regelen.

## Conclusie

Je weet nu hoe je **barcode‑afbeelding kunt genereren** in C# met Aspose.BarCode, hoe je een **Databar‑barcode maakt**, een **aangepaste barcode‑grootte** aanpast, en **barcode‑hoogte** op aanvraag wijzigt. Het volledige voorbeeld toont de meest voorkomende workflow, en de variatietabel helpt je real‑world randgevallen aan te pakken.

Vervolgens kun je gerelateerde onderwerpen verkennen, zoals **barcodes in PDF‑documenten insluiten**, **batch‑generatie van meerdere barcodes**, en **QR‑codes voor mobiele betalingen**. Elk van deze scenario’s bouwt voort op dezelfde principes die hier behandeld zijn, zodat je deze kennis vol vertrouwen kunt uitbreiden.

Veel programmeerplezier, en moge je barcodes feilloos scannen!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Genereer barcode‑afbeelding – GS1 Coupon UPC‑A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Hoe een Aztec‑barcode te genereren met aangepaste beeldverhouding met Aspose.BarCode voor .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Hoe een Barcode te genereren – Code 39‑configuratie met Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}