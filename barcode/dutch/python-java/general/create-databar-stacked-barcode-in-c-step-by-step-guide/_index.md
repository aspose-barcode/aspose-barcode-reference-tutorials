---
category: general
date: 2026-08-06
description: Maak snel een gestapelde DataBar-barcode in C#. Leer de X‑dimensie instellen,
  de beeldverhouding aanpassen en PNG‑bestanden exporteren met de DataBar Stacked
  Omnidirectional‑generator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode aspect ratio
- BarcodeGenerator C#
- BarCodeImageFormat PNG
language: nl
lastmod: 2026-08-06
og_description: Maak een gestapelde databarcode in C# met Aspose.BarCode. Deze tutorial
  laat zien hoe je de X-dimensie configureert, de beeldverhouding wijzigt en PNG-afbeeldingen
  opslaat.
og_image_alt: Screenshot of two PNG files generated from a DataBar Stacked Omnidirectional
  barcode with different aspect ratios
og_title: Maak een gestapelde Databar-barcode in C# – volledige programmeergids
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Create databar stacked barcode in C# quickly. Learn to set X dimension,
    adjust aspect ratio, and export PNG files using the DataBar Stacked Omnidirectional
    generator.
  headline: Create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Maak een gestapelde Databar-barcode in C# – stapsgewijze handleiding
url: /nl/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak een databar stacked barcode in C# – stap‑voor‑stap gids

Als je **databar stacked barcode** afbeeldingen in C# moet maken, laat deze gids je precies zien hoe je dit doet met de Aspose.BarCode bibliotheek. Je leert de X‑dimensie in te stellen, de aspectratio van de barcode te wijzigen en het resultaat op te slaan als PNG‑bestanden—alles in een paar beknopte stappen.

Het genereren van een DataBar Stacked barcode is gebruikelijk wanneer je GS1‑128‑gegevens moet coderen voor retail‑scanning of logistieke tracking. In de volgende secties behandelen we alles van project‑opzet tot het verifiëren van de output, zodat je de oplossing in elke .NET‑applicatie kunt integreren zonder een detail te missen.

## Vereisten

* **.NET 6.0** (of later) geïnstalleerd – de code richt zich op de moderne SDK.
* Een **gelicentieerde** kopie van **Aspose.BarCode for .NET**. De gratis evaluatie werkt voor testen maar voegt een watermerk toe.
* Een IDE zoals **Visual Studio 2022** of **VS Code** met de C#‑extensie.
* Basiskennis van **C#**‑syntaxis en het concept van GS1 Application Identifiers.

> **Pro tip:** Als je de NuGet package manager gebruikt, lost het commando `dotnet add package Aspose.BarCode` alle afhankelijkheden automatisch op.

## Stap 1: Maak een nieuw console‑project

Open een terminal of de Package Manager Console en voer uit:

```bash
dotnet new console -n DatabarStackedDemo
cd DatabarStackedDemo
dotnet add package Aspose.BarCode
```

Het commando `dotnet new console` maakt een minimale **Program.cs**‑file aan. Het toevoegen van het **Aspose.BarCode**‑pakket maakt de `BarcodeGenerator`‑klasse beschikbaar.

## Stap 2: Initialiseert de DataBar Stacked Omnidirectional generator

Open **Program.cs** en vervang de standaardinhoud door de volgende code. De eerste regel maakt een **BarcodeGenerator** aan die is geconfigureerd voor de **DataBar Stacked Omnidirectional**‑symbool en levert een GS1‑128‑payload.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a DataBar Stacked Omnidirectional barcode
        // "(01)12345678901231" encodes a GTIN‑14 with Application Identifier (01)
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Continue with configuration...
```

**Waarom dit belangrijk is:** De enum‑waarde `EncodeTypes.DatabarStackedOmniDirectional` vertelt de bibliotheek om een **databar stacked barcode** te produceren, de gestapelde variant van de omnidirectionele DataBar‑familie. Deze symbool kan tot 14 numerieke tekens bevatten, waardoor hij ideaal is voor GTIN‑14‑codes.

## Stap 3: Stel de X‑dimensie in (module‑breedte)

De X‑dimensie bepaalt de breedte van de kleinste balk (de module). Een te kleine waarde kan slecht renderen op printers met lage resolutie, terwijl een te grote waarde de labelruimte kan overschrijden.

```csharp
        // Step 3: Define the module width – 2 pixels gives a crisp, printable barcode
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Tip:** De eigenschap `Pixels` is handig voor tests op het scherm. Voor print‑gerichte scenario's gebruik je in plaats daarvan `generator.Parameters.Barcode.XDimension.Millimeters`.

## Stap 4: Pas de aspectratio aan en sla de eerste afbeelding op

De **aspectratio** beïnvloedt de hoogte‑tot‑breedte‑verhouding van de gestapelde barcode. Het DataBar Stacked Omnidirectional‑type ondersteunt ratio’s van 10 tot 30. We zullen twee afbeeldingen genereren om de visuele impact te illustreren.

```csharp
        // Step 4a: Set aspect ratio to 15 (default is 15) and save as PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

De aanroep van `generator.Save` schrijft een **PNG**‑bestand naar de huidige werkmap. De enum `BarCodeImageFormat.Png` zorgt voor verliesloze compressie, wat ideaal is voor verdere verwerking of insluiting in PDF‑bestanden.

## Stap 5: Verander de aspectratio naar 30 en sla de tweede afbeelding op

Nu verhogen we de hoogte van de gestapelde balken door de aspectratio naar **30** te wijzigen. Dit maakt de barcode hoger zonder de X‑dimensie te veranderen.

```csharp
        // Step 5a: Increase aspect ratio to 30 for a taller barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been generated:");
        Console.WriteLine(" • DatabarAspectRatio15.png");
        Console.WriteLine(" • DatabarAspectRatio30.png");
    }
}
```

Het uitvoeren van het programma genereert nu twee PNG‑bestanden:

* **DatabarAspectRatio15.png** – een compacte barcode geschikt voor kleine labels.
* **DatabarAspectRatio30.png** – een hogere barcode die de scanbetrouwbaarheid op oppervlakken met laag contrast verbetert.

Je kunt de afbeeldingen in elke viewer openen om te verifiëren dat de balken correct gestapeld zijn en dat de gecodeerde data overeenkomt met de oorspronkelijke GS1‑string.

## Stap 6: Verifieer de gecodeerde waarde (optioneel)

Als je wilt bevestigen dat de barcode daadwerkelijk de invoerstring vertegenwoordigt, kun je deze decoderen met dezelfde bibliotheek:

```csharp
        // Optional: Decode the generated PNG to ensure correctness
        var decoder = new BarCodeReader("DatabarAspectRatio15.png", DecodeType.DatabarStackedOmniDirectional);
        foreach (BarCodeResult result in decoder.ReadBarCodes())
        {
            Console.WriteLine($"Decoded text: {result.CodeText}");
        }
```

De decoder zou `(01)12345678901231` moeten weergeven, wat bewijst dat het **create databar stacked barcode**‑proces de data heeft behouden.

## Veelvoorkomende valkuilen en hoe ze te vermijden

| Issue | Why it happens | Fix |
|-------|----------------|-----|
| Barcode is onscherp | X‑dimensie te laag ingesteld voor de uitvoerresolutie | Verhoog `XDimension.Pixels` of gebruik `Millimeters` voor print |
| Scanner meldt “symbool niet gevonden” | Aspectratio buiten het ondersteunde bereik 10‑30 | Houd de ratio tussen 10 en 30; 15 en 30 zijn veilige standaardwaarden |
| PNG bevat een watermerk | Gebruik van de gratis evaluatielicentie van Aspose.BarCode | Koop een volledige licentie of gebruik de proefversie alleen voor testen |
| Decodering mislukt op de tweede afbeelding | De decoder was geconfigureerd voor de verkeerde symbool | Gebruik `DecodeType.DatabarStackedOmniDirectional` bij het lezen van gestapelde barcodes |

## Volgende stappen

Nu je **databar stacked barcode** afbeeldingen kunt maken, wil je misschien:

* **Integreer de PNG‑bestanden in PDF‑facturen** met een PDF‑bibliotheek zoals **Aspose.PDF**.
* **Genereer barcodes on‑the‑fly in een web‑API** – retourneer de PNG‑bytes direct vanuit een ASP.NET Core‑controller.
* **Experimenteer met andere DataBar‑varianten** (bijv. `DatabarExpanded`, `DatabarLimited`) door de `EncodeTypes`‑enum te wijzigen.
* **Pas kleuren aan** door `generator.Parameters.Barcode.ForeColor` en `BackColor` in te stellen voor merkspecifieke ontwerpen.

Elk van deze onderwerpen bouwt voort op dezelfde kernconcepten die hier behandeld zijn: het initialiseren van `BarcodeGenerator`, het configureren van visuele parameters, en het opslaan van het resultaat met `BarCodeImageFormat`.

---

### Conclusie

Deze tutorial liet zien hoe je **databar stacked barcode** afbeeldingen in C# kunt maken met Aspose.BarCode. Je leerde de **X‑dimensie** in te stellen, de **barcode aspect ratio** aan te passen, en het resultaat te exporteren als **PNG**‑bestanden met `BarcodeGenerator`. Met de optionele decodeerstap kun je bovendien verifiëren dat de gecodeerde GS1‑data correct is. Pas deze patronen toe in je eigen voorraad‑, verzend‑ of point‑of‑sale‑applicaties, en ontdek de vele aanpassingsmogelijkheden die de bibliotheek biedt. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Een-dimensionale Databar barcode hoogte‑aanpassing](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Genereer barcode‑afbeelding – GS1 Coupon UPC‑A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}