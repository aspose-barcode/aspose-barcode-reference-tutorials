---
category: general
date: 2026-08-25
description: Leer hoe je een PDF417‑barcode genereert in C# met de barcode‑generator
  C# PDF417‑bibliotheek – stapsgewijze codevoorbeelden.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- barcode generator C# PDF417
- PDF417 barcode C#
- barcode resolution C#
- Aspose.BarCode PDF417
language: nl
lastmod: 2026-08-25
og_description: Genereer PDF417‑barcode in C# met de barcode‑generator C# PDF417‑bibliotheek.
  Volg deze beknopte tutorial voor volledige code en best practices.
og_image_alt: Generated PDF417 barcode example
og_title: PDF417-barcode genereren in C# – volledige gids
schemas:
- author: Aspose
  dateModified: '2026-08-25'
  description: Learn how to generate PDF417 barcode in C# with the barcode generator
    C# PDF417 library – step-by-step code examples.
  headline: How to generate PDF417 barcode in C# with Barcode Generator
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Hoe PDF417-barcode te genereren in C# met Barcode Generator
url: /nl/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417‑streepjescode te genereren in C# met Barcode Generator

Als je **PDF417‑streepjescode** moet **genereren** in een .NET‑applicatie, laat deze gids je een kant‑en‑klaar werkende oplossing zien. Met de **barcode generator C# PDF417**‑bibliotheek kun je afmetingen, kolommen, rijen en afbeeldingsformaat regelen met slechts een paar regels code.

Je leert hoe je hoge‑resolutie‑streepjescodes maakt, de lay‑out aanpast en het resultaat opslaat als PNG‑bestanden — allemaal zonder je IDE te verlaten.

## Wat je nodig hebt

- .NET 6.0 of later (de code werkt ook met .NET Framework 4.6+)
- Het Aspose.BarCode for .NET‑pakket (installeren via NuGet: `Install-Package Aspose.BarCode`)
- Een map waarin de gegenereerde PNG‑afbeeldingen worden opgeslagen
- Basiskennis van C#‑syntaxis

## Stap 1: Het project opzetten en namespaces importeren

Maak een nieuwe console‑applicatie (of voeg de code toe aan een bestaand project) en voeg de benodigde using‑directives toe:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

De namespace `Aspose.BarCode.Generation` levert `BarcodeGenerator`, terwijl `Aspose.BarCode` de `BarCodeImageFormat`‑enum bevat.

## Stap 2: De PDF417‑streepjescodengenerator initialiseren

Instantieer `BarcodeGenerator` met het PDF417‑encodeertype en de tekst die je wilt coderen. Het voorbeeld gebruikt een string met niet‑ASCII‑tekens om Unicode‑ondersteuning te demonstreren.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**Waarom dit belangrijk is:**  
`EncodeTypes.Pdf417` vertelt de bibliotheek een PDF417‑streepjescodes te produceren, een gestapelde lineaire code die ideaal is voor het opslaan van grote hoeveelheden data. Het meegeven van de tekst bij de constructie zorgt ervoor dat de generator direct klaar is om te renderen.

## Stap 3: Resolutie verbeteren met X‑dimension

De X‑dimension (module‑breedte) bepaalt hoeveel pixels elke kleine balk inneemt. Een grotere waarde levert een scherper beeld op, vooral bij afdrukken.

```csharp
// Step 3: Define the module (X) dimension in pixels for better resolution
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

`Pixels = 2` geeft een goede balans tussen grootte en leesbaarheid. Je kunt deze waarde verhogen voor high‑DPI‑output, maar let op grotere bestandsgroottes.

## Stap 4: Een streepjescodes genereren met een vast aantal kolommen

Een PDF417‑streepjescodes kan worden gerangschikt in een specifiek aantal kolommen. Hier vragen we **2 kolommen** en laten we de bibliotheek het aantal rijen automatisch bepalen.

```csharp
// Step 4: Generate a barcode with 2 columns and save it as PNG
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 2;   // columns = 2, rows = auto
barcodeGenerator.Save("Pdf417Columns2.png", BarCodeImageFormat.Png);
```

**Resultaat:** `Pdf417Columns2.png` bevat een compacte code met twee verticale stapels.

## Stap 5: Laat de generator kolommen bepalen en stel een vast aantal rijen in

Wanneer je een bepaald aantal rijen nodig hebt — bijvoorbeeld om in een labelhoogte te passen — kun je rijen instellen terwijl je kolommen op *auto* laat.

```csharp
// Step 5: Generate a barcode with 6 rows (columns set to auto) and save it
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 0;   // columns = auto
barcodeGenerator.Parameters.Barcode.Pdf417.Rows = 6;      // rows = 6
barcodeGenerator.Save("Pdf417Rows6.png", BarCodeImageFormat.Png);
```

De bibliotheek berekent het optimale aantal kolommen om de data binnen zes rijen te passen.

## Stap 6: Zowel kolommen als rijen specificeren voor een aangepaste lay‑out

Soms heb je strikte lay‑outbeperkingen (bijvoorbeeld een voorgeprinte vorm). Je kunt beide dimensies expliciet instellen:

```csharp
// Step 6: Generate a barcode with 4 columns and 9 rows, then save it
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;   // columns = 4
barcodeGenerator.Parameters.Barcode.Pdf417.Rows = 9;      // rows = 9
barcodeGenerator.Save("Pdf417Rows9Columns4.png", BarCodeImageFormat.Png);
```

Dit produceert een code die exact overeenkomt met een 4 × 9‑rooster, handig voor uitlijning met fysieke sjablonen.

## Volledig uitvoerbaar voorbeeld

Hieronder staat een compleet programma dat alle vijf stappen opeenvolgend uitvoert. Kopieer het naar `Program.cs` en voer het project uit.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with sample text containing Unicode characters
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // Improve image sharpness
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 1️⃣ Two columns, rows auto
            generator.Parameters.Barcode.Pdf417.Columns = 2;
            generator.Parameters.Barcode.Pdf417.Rows = 0; // explicit auto
            generator.Save("Pdf417Columns2.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: Pdf417Columns2.png");

            // 2️⃣ Six rows, columns auto
            generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
            generator.Parameters.Barcode.Pdf417.Rows = 6;
            generator.Save("Pdf417Rows6.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: Pdf417Rows6.png");

            // 3️⃣ Custom layout: 4 columns × 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows = 9;
            generator.Save("Pdf417Rows9Columns4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: Pdf417Rows9Columns4.png");
        }
    }
}
```

**Verwachte output**

Het uitvoeren van het programma maakt drie PNG‑bestanden aan in de output‑map van het project:

- `Pdf417Columns2.png` – een code met twee verticale kolommen.
- `Pdf417Rows6.png` – een code uitgerekt over zes rijen.
- `Pdf417Rows9Columns4.png` – een code gerangschikt in een 4 × 9‑rooster.

Je kunt elk van de afbeeldingen openen met een standaardviewer om te verifiëren dat de code correct wordt gescand met een PDF417‑scannerapp.

## Pro‑tips en veelvoorkomende valkuilen

- **Unicode‑verwerking**: De generator codeert Unicode‑tekens automatisch, maar zorg ervoor dat de doel‑scanner de gebruikte tekenset ondersteunt.
- **Afbeeldingsformaat**: PNG behoudt verliesvrije kwaliteit. Als je een vectorformaat (bijv. SVG) nodig hebt voor schaalbaarheid, vervang je `BarCodeImageFormat.Png` door `BarCodeImageFormat.Svg`.
- **Prestaties**: Het hergebruiken van dezelfde `BarcodeGenerator`‑instantie (zoals getoond) is efficiënter dan voor elke lay‑out een nieuwe instantie aan te maken.
- **Foutafhandeling**: Plaats `Save`‑aanroepen in een `try/catch`‑blok om I/O‑fouten op te vangen, vooral bij het schrijven naar beschermde mappen.
- **Afdrukoverwegingen**: Verhoog voor afgedrukte labels `XDimension.Pixels` naar 3 of 4 om pixelatie bij typische DPI (300 dpi) te voorkomen.

## Conclusie

Je weet nu hoe je **PDF417‑streepjescodes** kunt **genereren** in C# met de **barcode generator C# PDF417**‑bibliotheek. De tutorial behandelde het instellen van resolutie, het regelen van kolommen en rijen, en het opslaan van de resultaten als PNG‑bestanden.

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids zijn getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PDF417‑streepjescodes genereren – Compacte PDF417‑codering](/barcode/english/net/compact-pdf417-encoding/)
- [Hoe een streepjescodes maken – Compacte PDF417 met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [java barcode library – Streepjescodes toevoegen aan PDF met Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}