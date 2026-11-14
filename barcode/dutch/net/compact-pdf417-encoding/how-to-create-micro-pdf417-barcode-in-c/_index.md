---
category: general
date: 2026-11-14
description: Micro PDF417‑barcode maken in C# met Aspose.BarCode – stapsgewijze handleiding
  over generatorinstelling, X‑dimensie, kolommen en PNG‑export.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- micro pdf417 barcode generator
- set XDimension pixels
- define barcode columns
- save barcode as PNG
- Aspose.BarCode C# example
language: nl
lastmod: 2026-11-14
og_description: Maak een micro PDF417-barcode in C# met Aspose.BarCode. Leer hoe je
  de generator configureert, XDimension instelt, kolommen kiest en exporteert als
  PNG.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Maak een micro PDF417-barcode in C# – volledige programmeergids
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  headline: How to create micro PDF417 barcode in C#
  type: TechArticle
- description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  name: How to create micro PDF417 barcode in C#
  steps:
  - name: Open the PNG in an image viewer.
    text: Open the PNG in an image viewer.
  - name: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
    text: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
  - name: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
    text: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
- image generation
title: Hoe maak je een micro‑PDF417‑barcode in C#
url: /nl/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een micro PDF417 barcode te maken in C#  

Als je snel een **micro PDF417 barcode** wilt maken, laat deze gids je een complete, kant‑klaar oplossing zien. Je ziet hoe je de barcode‑generator instantiate, de X‑dimension configureert, het aantal kolommen kiest, en uiteindelijk het resultaat opslaat als een PNG‑afbeelding — allemaal met behulp van de Aspose.BarCode bibliotheek voor .NET.

Het genereren van een micro PDF417 barcode vereist geen complexe build‑pipeline. Aan het einde van deze tutorial heb je één C#‑bestand dat een hoogwaardige barcode‑afbeelding produceert die je kunt insluiten in rapporten, labels of mobiele apps.

## Vereisten  

Voordat je begint, zorg dat je het volgende hebt:

* .NET 6.0 SDK of later (de code werkt ook met .NET Framework 4.7+).  
* Een ontwikkelomgeving zoals Visual Studio 2022, VS Code of Rider.  
* Een Aspose.BarCode voor .NET‑licentie (of een gratis evaluatiesleutel). Je kunt deze verkrijgen via de [Aspose website](https://purchase.aspose.com/barcode/net).  

> **Pro tip:** Als je de evaluatieversie gebruikt, bevat de gegenereerde PNG een klein “Evaluation” watermerk. Een gelicentieerde versie verwijdert dit automatisch.

## Stap 1: Het project opzetten  

Maak een nieuw console‑project aan en voeg het Aspose.BarCode NuGet‑pakket toe.

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode --version 24.9.0
```

Het `dotnet add package`‑commando haalt de **Aspose.BarCode C# example**‑afhankelijkheden op, zodat je DLL’s niet handmatig hoeft te beheren.

## Stap 2: De volledige code schrijven  

Vervang de automatisch gegenereerde `Program.cs` door de volgende code. Deze laat zien hoe je **micro pdf417 barcode** van begin tot eind **maakt**.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text.
            // The text can contain Unicode characters; here we use a sample string.
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Åspóse.Barcóde©");

            // 2️⃣ Set the X‑dimension (module width) in pixels.
            // This determines the width of the smallest element (a bar or a space).
            generator.Parameters.Barcode.XDimension.Pixels = 2; // secondary keyword: set XDimension pixels

            // 3️⃣ Define the number of columns (allowed values: 1‑4 for MicroPDF417).
            // More columns mean a wider barcode but fewer rows, which can improve readability.
            generator.Parameters.Barcode.Pdf417.Columns = 4; // secondary keyword: define barcode columns

            // 4️⃣ Choose the output format and save the barcode as a PNG image.
            // PNG preserves the sharp edges of the barcode, which is ideal for scanning.
            string outputPath = "MicroPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png); // secondary keyword: save barcode as PNG

            Console.WriteLine($"Micro PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### Waarom elke regel belangrijk is  

* **BarcodeGenerator constructor** – Instantieert de **micro pdf417 barcode generator** met de tekst die je wilt coderen.  
* **XDimension.Pixels** – Regelt de module‑breedte; door deze op `2` pixels te zetten krijg je een dichte, hoge‑resolutie barcode die geschikt is voor de meeste scanners.  
* **Pdf417.Columns** – MicroPDF417 ondersteunt alleen 1‑4 kolommen. Het kiezen van `4` verkleint de barcode‑hoogte, wat handig is wanneer je beperkte verticale ruimte hebt.  
* **Save method** – Schrijft de barcode naar een PNG‑bestand. PNG is lossless, waardoor de scanner precies het patroon leest dat je hebt gegenereerd.

## Stap 3: Bouwen en uitvoeren  

Compileer en voer het programma uit:

```bash
dotnet run
```

Je zou de console‑output moeten zien:

```
Micro PDF417 barcode saved to MicroPdf417.png
```

Een bestand met de naam **MicroPdf417.png** verschijnt in de projectmap. Open het met een willekeurige afbeeldingsviewer; je ziet een scherpe micro PDF417 barcode die de string `"Åspóse.Barcóde©"` codeert.

![Voorbeeld van gegenereerde micro PDF417 barcode](MicroPdf417.png "Voorbeeld van gegenereerde micro PDF417 barcode"){.center-image width=400 alt="Voorbeeld van gegenereerde micro PDF417 barcode afbeelding"}

*De bovenstaande afbeelding is het resultaat van de code die in Stap 2 wordt getoond.*

## Stap 4: Veelvoorkomende variaties en randgevallen  

| Situatie | Hoe de code aan te passen |
|-----------|---------------------------|
| **Andere datalengte** | MicroPDF417 kan tot 1 200 tekens coderen. Verander simpelweg het tweede argument van `BarcodeGenerator`. |
| **Hogere resolutie** | Verhoog `XDimension.Pixels` naar `3` of `4`. Grotere modules verbeteren de leesbaarheid op low‑resolution scanners, maar vergroten de bestandsgrootte. |
| **Aangepaste kleuren** | Na het aanmaken van de generator, stel `generator.Parameters.Barcode.BarcodeColor = Color.Blue;` en `generator.Parameters.Barcode.BackgroundColor = Color.White;` in. |
| **Opslaan in andere formaten** | Vervang `BarCodeImageFormat.Png` door `Jpeg`, `Bmp` of `Gif` afhankelijk van je downstream‑vereisten. |
| **Inbedden in een PDF** | Gebruik `generator.Save("barcode.pdf", BarCodeImageFormat.Pdf);` en voeg de PDF vervolgens samen met andere documenten via Aspose.PDF. |

> **Let op:** Het instellen van `XDimension.Pixels` onder `1` veroorzaakt een `ArgumentOutOfRangeException`. Houd het altijd op `1` of hoger.

## Stap 5: De barcode verifiëren  

Om te zorgen dat de barcode correct wordt gescand:

1. Open de PNG in een afbeeldingsviewer.  
2. Gebruik een willekeurige smartphone‑barcode‑scan‑app die PDF417 ondersteunt (de meeste “QR‑code scanner” apps bevatten dit).  
3. Scan de afbeelding; de app zou de oorspronkelijke tekst `"Åspóse.Barcóde©"` moeten weergeven.

Als het scannen mislukt, controleer dan de **X‑dimension** en **column**‑instellingen – een te kleine module‑breedte of een niet‑ondersteund kolomaantal kan het patroon onleesbaar maken.

## Conclusie  

Je weet nu hoe je **micro pdf417 barcode** in C# maakt met Aspose.BarCode. De tutorial behandelde:

* Het instantieren van een **micro pdf417 barcode generator**.  
* **XDimension pixels instellen** om de module‑breedte te regelen.  
* **Barcode‑kolommen definiëren** om de vorm aan te passen.  
* **Barcode opslaan als PNG** voor lossless beeldoutput.  

Vanaf hier kun je extra functies verkennen, zoals kleur‑aanpassing, de barcode in PDF’s inbedden, of barcodes on‑the‑fly genereren in ASP.NET Core web‑API’s. Veel programmeerplezier!

## Wat moet je hierna leren?  

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids zijn gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Barcode PNG maken in C# – volledige gids voor GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Hoe een macro PDF417 barcode te maken in C# met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [PDF417 barcode maken in C# met Aspose.BarCode – stapsgewijze gids](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}