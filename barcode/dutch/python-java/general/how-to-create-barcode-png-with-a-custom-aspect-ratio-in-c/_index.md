---
category: general
date: 2026-10-05
description: Maak een barcode‑PNG in C# en leer hoe je de beeldverhouding 15 instelt
  voor gestapelde DataBar‑omnidirectionele barcodes.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to set aspect ratio
- set aspect ratio 15
language: nl
lastmod: 2026-10-05
og_description: Maak een barcode‑PNG in C# en ontdek hoe je de aspectratio 15 instelt
  voor gestapelde DataBar omnidirectionele barcodes in een paar stappen.
og_image_alt: Screenshot showing a generated barcode PNG with aspect ratio 15
og_title: Maak barcode PNG in C# – stel beeldverhouding 15 tutorial
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Create barcode PNG in C# and learn how to set aspect ratio 15 for stacked
    DataBar omnidirectional barcodes.
  headline: How to create barcode PNG with a custom aspect ratio in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Hoe een barcode PNG met een aangepaste beeldverhouding te maken in C#
url: /nl/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een barcode PNG te maken met een aangepaste beeldverhouding in C#

Als je een **barcode PNG** moet maken in C#, laat deze gids je zien **hoe je de beeldverhouding** 15 instelt voor een gestapelde DataBar omnidirectionele barcode. We lopen elke API‑aanroep door, leggen uit waarom de beeldverhouding belangrijk is, en geven je een compleet, uitvoerbaar voorbeeld dat je in elk .NET‑project kunt gebruiken.

Het genereren van een barcode‑afbeelding is een veelvoorkomende eis voor voorraadsystemen, verzendlabels en retail point‑of‑sale‑toepassingen. Aan het einde van deze tutorial heb je een PNG‑bestand dat voldoet aan de exacte visuele specificaties die je zakenpartner vereist. Geen externe tools, geen handmatige beeldbewerking—alleen code.

## Vereisten

* .NET 6.0 of later (het voorbeeld gebruikt .NET 6 maar werkt met .NET 5+)
* Visual Studio 2022 (of een IDE die .NET ondersteunt)
* Het **Aspose.BarCode for .NET** NuGet‑pakket  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Schrijfrechten voor de map waarin je het PNG‑bestand wilt opslaan

Deze vereisten zijn minimaal; dezelfde code werkt in .NET Core, .NET Framework, of een console‑applicatie.

## Maak barcode PNG met Aspose.BarCode

De eerste stap is om de `BarcodeGenerator`‑klasse te instantieren met het juiste barcode‑type. In dit geval gebruiken we `EncodeTypes.DatabarStackedOmniDirectional`, die een gestapelde DataBar produceert die vanuit elke richting gelezen kan worden.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

*Waarom dit belangrijk is:* De constructor neemt twee argumenten—**de barcode‑symbologie** en **de gegevensreeks**. Het DataBar‑formaat verwacht een GS1‑toepassingsidentificatie, daarom begint de voorbeelddata met `(01)`.

## Hoe de beeldverhouding in te stellen voor een gestapelde DataBar

De visuele breedte van een DataBar wordt geregeld door de **aspect ratio**‑eigenschap. Een hogere ratio maakt de strepen breder, wat de scanbetrouwbaarheid op laag‑resolutieprinters kan verbeteren.

```csharp
// Step 2: Define the module width (X‑dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

De `XDimension` definieert de grootte van één module (de kleinste streep of ruimte). Deze op 2 px houden geeft een scherp, hoog‑dichtheidsbeeld dat geschikt is voor de meeste labelprinters.

## Stel beeldverhouding 15 in – code‑overzicht

Nu passen we de **stel beeldverhouding 15 in**‑vereiste toe. Dit is de kern van de tutorial en toont de exacte API‑aanroep die je nodig hebt.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 for a wider appearance
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

*Waarom 15?* De standaard beeldverhouding voor gestapelde DataBar is 12. Verhogen naar 15 vergroot de breedte van elke streep met 25 %, wat vaak overeenkomt met de specificaties van logistieke providers die een bredere barcode vereisen voor sneller scannen.

## Sla de barcode op als PNG

Met de generator geconfigureerd, is de laatste stap om de afbeelding naar schijf te schrijven. De `Save`‑methode accepteert een bestandspad en een image‑format‑enum.

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Het PNG‑formaat behoudt verliesvrije kwaliteit, waardoor de barcode exact wordt weergegeven zoals ontworpen op elk scherm of printer.

## Volledig voorbeeld en verwachte output

Hieronder staat het volledige programma dat je kunt kopiëren in de `Main`‑methode van een console‑app. Het bevat alle hierboven beschreven stappen, plus een klein verificatie‑bericht.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with stacked DataBar (omnidirectional) and sample GS1 data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Set the DataBar aspect ratio to 15 – this is the key to a wider barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;

        // Choose a folder you have write access to
        string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";

        // Save the barcode as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode PNG created at: {outputPath}");
    }
}
```

**Verwachte output**

Het uitvoeren van het programma maakt een bestand genaamd `DatabarAspectRatio15.png` aan met een duidelijke, brede gestapelde DataBar‑barcode. Wanneer je de PNG opent, zie je een horizontaal uitgerekte barcode die nog steeds voldoet aan de GS1 DataBar‑specificaties.

![Barcode PNG with aspect ratio 15](barcode-aspect15.png)

*Image alt text:* **barcode PNG maken die een gestapelde DataBar met beeldverhouding 15 toont**

### Tips en veelvoorkomende valkuilen

| Situatie | Aanbeveling |
|-----------|----------------|
| **Afbeelding ziet er wazig uit** | Verhoog `XDimension.Pixels` naar 3 px of hoger, maar houd de totale afbeeldingsgrootte onder 500 px om te grote bestanden te vermijden. |
| **Scanner kan de code niet lezen** | Controleer of de gegevensreeks het GS1‑formaat volgt (`(01)`‑prefix). Zorg er ook voor dat de printerresolutie minimaal 300 dpi is. |
| **Een ander bestandsformaat nodig** | Vervang `BarCodeImageFormat.Png` door `Jpeg`, `Bmp` of `Gif`—de API ondersteunt alle belangrijke rasterformaten. |
| **Uitvoeren in een webapplicatie** | Gebruik `generator.Save(Stream, BarCodeImageFormat.Png)` om direct naar de HTTP‑respons te schrijven zonder het bestandssysteem aan te raken. |

### Voorbeeld uitbreiden

* **Meerdere barcodes in één afbeelding:** Maak extra `BarcodeGenerator`‑instanties aan en teken ze op één `Bitmap` met `Graphics`.  
* **Menselijke leesbare tekst toevoegen:** Stel `generator.Parameters.Caption.Visible = true` in en pas het lettertype aan via `generator.Parameters.Caption.Font`.  
* **Dynamische beeldverhouding:** Haal de ratio‑waarde uit een configuratie‑bestand of database om barcodes met variabele breedtes on‑the‑fly te genereren.

## Conclusie

In deze tutorial heb je geleerd hoe je **barcode PNG** maakt in C# en nauwkeurig **beeldverhouding** 15 instelt voor een gestapelde DataBar omnidirectionele barcode. De complete, uitvoerbare code toont elke vereiste API‑aanroep, legt uit waarom elke instelling belangrijk is, en biedt praktische tips voor real‑world implementaties.  

Vervolgens kun je **hoe je beeldverhouding** instelt voor andere barcode‑types (bijv. QR‑Code of Code 128) verkennen of de generator integreren in een ASP .NET Core‑service die barcode‑afbeeldingen op aanvraag retourneert. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe databar PNG‑afbeeldingen te maken met C# en Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Hoe een gestapelde databar barcode te maken in C# met Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [Databar gestapelde omnidirectionele beeldverhouding aanpassen in .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}