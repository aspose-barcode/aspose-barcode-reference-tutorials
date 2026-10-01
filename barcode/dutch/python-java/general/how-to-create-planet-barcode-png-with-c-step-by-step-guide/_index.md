---
category: general
date: 2026-09-07
description: Maak snel een planet barcode PNG in C#. Leer hoe je planet barcode‑afbeeldingen
  kunt genereren met Aspose.BarCode met gevulde en lege strepen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode png
- how to generate planet barcode
language: nl
lastmod: 2026-09-07
og_description: Maak snel een planeetbarcode PNG in C#. Volg deze handleiding om te
  leren hoe je planeetbarcode‑afbeeldingen met gevulde en lege staven kunt genereren
  met Aspose.BarCode.
og_image_alt: Planet barcode PNG image showing filled bars and empty‑bars version
og_title: Maak planet barcode PNG in C# – volledige programmeertutorial
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  headline: How to create planet barcode PNG with C# – step‑by‑step guide
  type: TechArticle
- description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  name: How to create planet barcode PNG with C# – step‑by‑step guide
  steps:
  - name: What if I need a different data format?
    text: 'Planet barcodes accept numeric strings up to 12 digits. If you pass a non‑numeric
      value, Aspose throws an `ArgumentException`. Validate the input before creating
      the generator:'
  - name: How do I change the image size without altering bar thickness?
    text: 'Use the `Resolution` property or scale the resulting bitmap after saving:'
  - name: Can I generate other image formats?
    text: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`, `Bmp`,
      or `Gif`. The API supports all common raster formats.
  - name: What about color customization?
    text: 'Set `BarColor` and `BackColor` on the `Barcode` parameters:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Hoe maak je een planet barcode PNG met C# – stapsgewijze handleiding
url: /nl/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe maak je planet barcode PNG met C# – stapsgewijze handleiding

Als je **planet barcode PNG**‑bestanden in C# moet maken, laat deze gids je de exacte stappen zien. Of je nu een integratie voor een postdienst bouwt of een logistiek dashboard, je leert **hoe je planet barcode**‑afbeeldingen genereert met zowel gevulde als lege staven met behulp van de Aspose.BarCode‑bibliotheek.

In deze tutorial leer je:

* De uitvoermap voor je afbeeldingen instellen.  
* Een `BarcodeGenerator` configureren voor de Planet‑symbologie.  
* Een PNG produceren met de standaard gevulde‑staven‑stijl.  
* Een PNG produceren met lege staven voor visueel contrast.  

Er zijn geen externe services nodig — alles draait lokaal op .NET 6 of hoger.

## Prerequisites

Voordat je begint, zorg dat je het volgende hebt:

| Vereiste | Waarom het belangrijk is |
|----------|--------------------------|
| .NET 6 SDK (of nieuwer) | Biedt de runtime voor de C# console‑applicatie. |
| Visual Studio 2022 of VS Code | Elke IDE die C#‑projecten kan compileren. |
| Aspose.BarCode for .NET (NuGet‑pakket `Aspose.BarCode`) | Levert de `BarcodeGenerator`‑klasse die wordt gebruikt om Planet‑barcodes te renderen. |
| Schrijfrechten voor een map op schijf | De PNG‑bestanden worden op deze locatie opgeslagen. |

Installeer het NuGet‑pakket met het volgende commando:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Create a new console project

Open een terminal en voer uit:

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
```

Dit maakt een minimale C# console‑applicatie met de naam **PlanetBarcodeDemo**.

## Step 2: Define the output directory

Het eerste stukje code bepaalt waar de gegenereerde PNG‑bestanden worden opgeslagen. Een absoluut of relatief pad werkt; zorg er alleen voor dat de map bestaat of laat het programma deze aanmaken.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Define the output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputDir); // Guarantees the folder exists
```

*Waarom deze stap?* Het scheiden van output en broncode houdt je project overzichtelijk en voorkomt accidentele overschrijvingen.

## Step 3: Generate a filled‑bars Planet barcode

Een Planet‑barcode bestaat uit concentrische cirkels (standaard gevuld). We configureren de X‑dimensie (pixelbreedte van elke staaf) en slaan vervolgens de afbeelding op als PNG.

```csharp
        // Step 3: Create a Planet barcode with the default (filled) bars
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4; // Controls bar thickness

        // Save the filled‑bars barcode as PNG
        string filledPath = Path.Combine(outputDir, "PostalPlanetFilledBars.png");
        planetFilled.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to: {filledPath}");
```

**Explanation**

* `EncodeTypes.Planet` vertelt Aspose om de Planet‑symbologie te gebruiken, die veel voorkomt bij postdiensten.  
* `XDimension.Pixels = 4` levert een duidelijke, afdrukbare grootte zonder handmatige schaalvergroting.  
* De `Save`‑methode schrijft een PNG‑bestand; je kunt ook JPEG of BMP kiezen door `BarCodeImageFormat` aan te passen.

## Step 4: Generate an empty‑bars Planet barcode

Soms is een visualisatie met lege (transparante) staven nodig — bijvoorbeeld wanneer de barcode over een gekleurde achtergrond wordt gelegd. Door `FilledBars` op `false` te zetten, ontstaat deze stijl.

```csharp
        // Step 4: Create a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false; // Switch to empty‑bars mode

        // Save the empty‑bars barcode as PNG
        string emptyPath = Path.Combine(outputDir, "PostalPlanetEmptyBars.png");
        planetEmpty.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to: {emptyPath}");
```

**Explanation**

* `FilledBars = false` schakelt de solide cirkels uit, waardoor alleen de omtrekken zichtbaar blijven.  
* Alle andere instellingen (X‑dimensie, data‑string) blijven identiek, zodat beide afbeeldingen dezelfde data weergeven.

## Step 5: Run the program and verify the output

Compileer en voer uit:

```bash
dotnet run
```

Je zou console‑berichten moeten zien die bevestigen dat de bestanden zijn opgeslagen, en de map `Barcodes` zal bevatten:

* `PostalPlanetFilledBars.png` – een klassieke gevulde‑staven Planet‑barcode.  
* `PostalPlanetEmptyBars.png` – dezelfde data weergegeven met lege staven.

Open de PNG‑bestanden in een willekeurige afbeeldingsviewer. Beide afbeeldingen coderen de numerieke string **123456** en kunnen worden gescand door standaard post‑barcodelezers.

## Common questions and edge‑case handling

### What if I need a different data format?

Planet‑barcodes accepteren numerieke strings tot 12 cijfers. Als je een niet‑numerieke waarde doorgeeft, gooit Aspose een `ArgumentException`. Valideer de invoer voordat je de generator maakt:

```csharp
if (!Regex.IsMatch(data, @"^\d{1,12}$"))
    throw new ArgumentException("Planet barcode data must be numeric and up to 12 digits.");
```

### How do I change the image size without altering bar thickness?

Gebruik de `Resolution`‑eigenschap of schaal de resulterende bitmap na het opslaan:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI for high‑resolution print
```

### Can I generate other image formats?

Ja. Vervang `BarCodeImageFormat.Png` door `BarCodeImageFormat.Jpeg`, `Bmp` of `Gif`. De API ondersteunt alle gangbare rasterformaten.

### What about color customization?

Stel `BarColor` en `BackColor` in op de `Barcode`‑parameters:

```csharp
planetFilled.Parameters.Barcode.BarColor = Color.DarkBlue;
planetFilled.Parameters.Barcode.BackColor = Color.LightYellow;
```

Deze opties werken zowel voor de gevulde als de lege‑staven‑versies.

## Pro tips for production use

* **Cache the generator** wanneer je veel barcodes met dezelfde instellingen moet renderen — het herhaaldelijk initialiseren van het object veroorzaakt extra overhead.  
* **Dispose** `BarcodeGenerator`‑objecten als je er veel in een lus maakt (ze implementeren `IDisposable`).  
* **Validate the output folder** vroegtijdig om runtime‑exceptions op schrijf‑beveiligde directories te voorkomen.  

## Conclusion

Je weet nu hoe je **planet barcode PNG**‑bestanden in C# kunt **maken** en begrijpt **hoe je planet barcode**‑afbeeldingen genereert met zowel gevulde als lege staafstijlen. Het volledige, uitvoerbare voorbeeld laat zien hoe je de uitvoermap instelt, de `BarcodeGenerator` configureert en de resultaten opslaat als PNG‑bestanden.

Vervolgens kun je verkennen:

* Het toevoegen van **menselijk leesbare tekst** onder de barcode (`planetFilled.Parameters.Caption.Visible = true`).  
* Het integreren van de gegenereerde PNG‑bestanden in een **PDF‑factuur** met Aspose.PDF.  
* Overschakelen naar andere post‑symbologieën zoals **IMB** of **ITF** (`EncodeTypes.IMB`, `EncodeTypes.ITF`).  

Voel je vrij om te experimenteren met staafdikte, kleuren en afbeeldingsresoluties om aan je specifieke toepassingsvereisten te voldoen. Veel programmeerplezier!

## What Should You Learn Next?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Create Planet Barcode Image in C# – How to Generate Postal Barcode](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Generate PNG Barcode with Aspose.BarCode for .NET: One-Dimensional Filled Bars](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-filled-bars-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}