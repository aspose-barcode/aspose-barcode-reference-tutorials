---
category: general
date: 2026-08-19
description: Leer hoe je een barcode‑PNG‑bestand genereert in C# en de hoogte ervan
  aanpast, met uitleg over het genereren van barcode‑afbeeldingen en het eenvoudig
  wijzigen van de barcodehoogte.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode png file
- how to generate barcode
- adjust barcode height
- change barcode height
language: nl
lastmod: 2026-08-19
og_description: Maak een barcode‑PNG‑bestand in C# en leer hoe je barcode‑afbeeldingen
  genereert, de barcodehoogte aanpast en de barcodehoogte wijzigt voor optimale scans.
og_image_alt: barcode PNG file showing Databar OmniDirectional barcode at two heights
og_title: Maak een barcode PNG‑bestand in C# – stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Learn how to generate a barcode PNG file in C# and adjust its height,
    covering how to generate barcode images and change barcode height easily.
  headline: How to create a barcode PNG file with adjustable height in C#
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`,
      `BarCodeImageFormat.Bmp`, etc.
    question: Can I generate other image formats (JPEG, BMP)?
  - answer: Serve the generated PNG via an HTTP endpoint or convert it to a Base64
      string and place it in an `<img>` tag’s `src` attribute.
    question: How do I embed the PNG in a web page?
  - answer: 'Use `generator.Parameters.Image.BackgroundColor = Color.White;` (or any
      `System.Drawing.Color`). ## Conclusion You now know how to **generate a barcode
      PNG file** in C# and precisely **adjust barcode height** to meet scanning or
      design requirements. By changing the `BarHeight.Pixels` property you ca'
    question: Is there a way to set the background color?
  type: FAQPage
tags:
- barcode
- C#
- image generation
title: Hoe maak je een barcode PNG‑bestand met verstelbare hoogte in C#
url: /nl/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe maak je een barcode PNG‑bestand met verstelbare hoogte in C#

Als je een **barcode PNG‑bestand** in C# moet maken, laat deze gids je precies zien hoe. Je ziet een volledig, uitvoerbaar voorbeeld dat demonstreert **hoe je barcode‑afbeeldingen genereert** en hoe je de **barcode‑hoogte kunt aanpassen** voor verschillende gebruikssituaties.

Het genereren van een barcode PNG‑bestand is een veelvoorkomende eis voor voorraadbeheersystemen, kassaterminals en elke applicatie die machine‑leesbare gegevens moet afdrukken of weergeven. Aan het einde van deze tutorial kun je de barcode‑hoogte wijzigen, meerdere PNG‑bestanden opslaan en de impact van hoogte op scan‑betrouwbaarheid begrijpen.

## Vereisten

Voordat je begint, zorg dat je het volgende hebt:

* .NET 6.0 SDK of later geïnstalleerd  
* Visual Studio 2022 (of een IDE die .NET ondersteunt)  
* Het **Aspose.BarCode for .NET** NuGet‑pakket (de code‑voorbeeld gebruikt deze bibliotheek)  

Je kunt het pakket toevoegen via de opdrachtregel:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** De gratis evaluatieversie van Aspose.BarCode werkt voor ontwikkeling en testen. Voor productie moet je een gelicentieerde sleutel verkrijgen.

## Installeer de barcode‑bibliotheek

De eerste stap is om de bibliotheek in je project te refereren. Voeg de volgende `using`‑directieven toe aan de bovenkant van je C#‑bestand:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Deze namespaces geven je toegang tot `BarcodeGenerator`, `EncodeTypes` en `BarCodeImageFormat`.

## Maak het barcode PNG‑bestand

Nu maken we een `BarcodeGenerator`‑instantie die een **barcode PNG‑bestand** zal produceren. Het voorbeeld gebruikt de Databar OmniDirectional‑symbologie, maar je kunt `EncodeTypes.DatabarOmniDirectional` vervangen door elk ondersteund type.

```csharp
// Step 1: Create a DataBar Omnidirectional generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

De string `"(01)12345678901231"` volgt het GS1 Application Identifier‑formaat voor een 14‑cijferige GTIN. Pas de gegevens aan zodat ze overeenkomen met jouw eigen product‑identifiers.

## Stel de X‑dimensie in (optioneel)

De X‑dimensie bepaalt de breedte van één barcode‑module. Een pixel‑gebaseerde waarde geeft je precieze controle over de afbeeldingsgrootte.

```csharp
// Optional: Set the pixel size of the X‑dimension (module width)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Een waarde van `2` pixels werkt goed voor de meeste schermweergaven. Verhoog deze als je een grotere barcode nodig hebt bij afdrukken.

## Pas de barcode‑hoogte aan en sla het barcode PNG‑bestand op

De eigenschap **BarHeight** regelt de verticale grootte van de strepen. Door deze waarde te wijzigen kun je de **barcode‑hoogte aanpassen** zonder de gecodeerde data te beïnvloeden.

```csharp
// Step 2: Generate a 30‑pixel‑high barcode and save it as PNG
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Het bestand `DatabarBarHeight30Pixels.png` is nu een **barcode PNG‑bestand** dat 30 pixels hoog is.  

Om de **barcode‑hoogte te wijzigen** en een tweede afbeelding te maken, wijs je simpelweg een nieuwe waarde toe en roep je `Save` opnieuw aan:

```csharp
// Step 3: Change the height to 60 pixels and save the new image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
barcodeGenerator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Je hebt nu twee PNG‑bestanden — één van 30 px en een andere van 60 px — die laten zien hoe je **barcode‑hoogte** dynamisch kunt **aanpassen**.

### Waarom bar‑hoogte belangrijk is

* **Leesbaarheid:** Scanners verwachten een minimale hoogte voor betrouwbare detectie. Een te korte barcode kan gemist worden, vooral bij lage‑resolutiecamera's.  
* **Esthetiek:** Het afstemmen van de barcode‑hoogte op omliggende designelementen zorgt voor een nettere UI.  
* **Printbeperkingen:** Sommige labelprinters hebben vaste hoogte‑sleuven; door de barcode‑hoogte aan te passen, zorg je dat deze past.  

**Best practice:** Houd de hoogte een veelvoud van de X‑dimensie (bijv. 30 px wanneer X‑dimensie 2 px is) om de proportie te behouden en vervorming te voorkomen.

## Volledig voorbeeld

Hieronder staat het volledige, zelfstandige programma dat je in een console‑applicatie kunt plakken en direct kunt uitvoeren.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator with Databar OmniDirectional data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set a reasonable X‑dimension (module width)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First height: 30 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Second height: 60 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

**Verwachte output**

Het uitvoeren van het programma maakt twee bestanden aan in de werkmap van de executable:

* `DatabarBarHeight30Pixels.png` – een 30‑pixel‑hoge barcode PNG‑bestand  
* `DatabarBarHeight60Pixels.png` – een 60‑pixel‑hoge barcode PNG‑bestand  

Open een van beide PNG‑bestanden met een willekeurige afbeeldingsviewer; je ziet een duidelijke Databar OmniDirectional barcode die klaar is om te scannen.

## Randgevallen en probleemoplossing

| Situatie | Wat te controleren | Aanbevolen oplossing |
|-----------|-------------------|----------------------|
| Barcode is onscherp | X‑dimensie te laag voor gekozen hoogte | Verhoog `XDimension.Pixels` (bijv. van 2 naar 3) |
| Scanner faalt bij lage barcode‑hoogte | Hoogte onder het minimum van de scanner | Stel `BarHeight.Pixels` in op minstens 30 px (of volgens de specificaties van de scanner) |
| PNG‑bestand is leeg of corrupt | Uitvoerpad ongeldig of schrijfrechten ontbreken | Gebruik een absoluut pad of zorg dat de app schrijfrechten heeft |
| Andere symbologie nodig | Huidige `EncodeTypes` niet geschikt | Vervang `EncodeTypes.DatabarOmniDirectional` door een andere enum‑waarde (bijv. `EncodeTypes.Code128`) |

## Veelgestelde vragen

**V: Kan ik andere afbeeldingsformaten genereren (JPEG, BMP)?**  
A: Ja. Vervang `BarCodeImageFormat.Png` door `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp`, enz.

**V: Hoe embed ik de PNG in een webpagina?**  
A: Serveer de gegenereerde PNG via een HTTP‑endpoint of converteer deze naar een Base64‑string en plaats deze in het `src`‑attribuut van een `<img>`‑tag.

**V: Is er een manier om de achtergrondkleur in te stellen?**  
A: Gebruik `generator.Parameters.Image.BackgroundColor = Color.White;` (of een andere `System.Drawing.Color`).

## Conclusie

Je weet nu hoe je een **barcode PNG‑bestand** in C# kunt **genereren** en de **barcode‑hoogte** nauwkeurig kunt **aanpassen** om te voldoen aan scan‑ of ontwerpeisen. Door de eigenschap `BarHeight.Pixels` te wijzigen kun je de **barcode‑hoogte** dynamisch veranderen en meerdere PNG‑assets uit één code‑basis produceren.

Verken vervolgens andere aanpassingsopties zoals voorgrondkleur, marges en het toevoegen van mens‑leesbare tekst. Je kunt ook experimenteren met verschillende symbologieën (`EncodeTypes.Code128`, `EncodeTypes.QR`) om het scala aan gegevens dat je kunt coderen uit te breiden.

Veel programmeerplezier, en moge je barcodes altijd bij de eerste poging scannen!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}