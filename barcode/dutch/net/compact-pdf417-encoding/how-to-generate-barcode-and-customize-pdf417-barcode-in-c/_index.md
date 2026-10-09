---
category: general
date: 2026-09-19
description: Hoe je een barcode genereert in C# met een stapsgewijze handleiding.
  Leer PDF417‑barcode‑instellingen aanpassen en een barcode‑afbeelding maken die C#‑ontwikkelaars
  direct kunnen gebruiken.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- customize pdf417 barcode
- create barcode image c#
language: nl
lastmod: 2026-09-19
og_description: Hoe je een barcode genereert in C# met gedetailleerde instructies.
  Pas PDF417‑barcodeparameters aan en maak een barcode‑afbeelding die C#‑projecten
  vandaag kunnen gebruiken.
og_image_alt: Screenshot of a generated MicroPDF417 barcode image created with C#
  code
og_title: Hoe een barcode te genereren en een PDF417-barcode aan te passen in C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  headline: How to generate barcode and customize PDF417 barcode in C#
  type: TechArticle
- description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  name: How to generate barcode and customize PDF417 barcode in C#
  steps:
  - name: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
    text: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
  - name: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
    text: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
  - name: Increase `ErrorLevel` to improve tolerance.
    text: Increase `ErrorLevel` to improve tolerance.
  type: HowTo
tags:
- barcode
- C#
- pdf417
title: Hoe barcode te genereren en PDF417-barcode aan te passen in C#
url: /nl/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een barcode te genereren en PDF417 barcode aan te passen in C#

Als je **how to generate barcode** nodig hebt in een .NET‑applicatie, laat deze tutorial je een complete, kant‑klaar oplossing zien. Je leert hoe je PDF417‑barcode‑dimensies kunt aanpassen, het aantal kolommen kunt kiezen, en uiteindelijk **create barcode image C#** projecten direct kunt insluiten.

Het genereren van een barcode vereist geen complexe build‑pipeline. Aan het einde van deze gids heb je een PNG‑bestand met een MicroPDF417‑barcode die exact de grootte en resolutie heeft die je nodig hebt.

## Vereisten

* .NET 6.0 SDK of later (de code werkt ook met .NET Framework 4.6+)
* Visual Studio 2022 (of een C#‑editor naar keuze)
* Aspose.BarCode for .NET NuGet‑package – install with  
  `dotnet add package Aspose.BarCode`

Er zijn geen extra externe tools vereist.

## Stap 1: Het project opzetten en namespaces importeren

Maak een nieuw console‑project aan en voeg de Aspose.BarCode‑referentie toe.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Open `Program.cs` en voeg de benodigde `using`‑directieven toe:

```csharp
using System;
using Aspose.BarCode.Generation;   // Provides BarcodeGenerator and EncodeTypes
using Aspose.BarCode;               // Contains BarCodeImageFormat enum
```

Deze namespaces maken de klassen beschikbaar die je **how to generate barcode** laten uitvoeren en PDF417‑specifieke opties beheren.

## Stap 2: Initialise de MicroPDF417‑generator met de gewenste tekst

De eerste regel maakt een `BarcodeGenerator`‑instantie aan die is geconfigureerd voor de MicroPDF417‑symbologie. De constructor neemt het coderings‑type en de gegevensreeks die je wilt coderen.

```csharp
// Step 2: Create a MicroPDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");
```

**Waarom dit belangrijk is:** MicroPDF417 is een compacte variant van de volledige PDF417‑standaard, ideaal voor kleine etiketten of mobiele schermen. Het initialiseren van de generator met de juiste `EncodeTypes` zorgt ervoor dat de bibliotheek het juiste coderingsalgoritme gebruikt.

## Stap 3: Pas de X‑dimensie (module‑breedte) aan voor fijnere resolutie

De X‑dimensie bepaalt de breedte van één barcode‑module (de kleinste zwarte of witte balk). Een lage pixelwaarde instellen levert een afbeelding met hogere resolutie op.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Waarom dit belangrijk is:** Een grotere X‑dimensie maakt de barcode makkelijker leesbaar voor scanners met lage resolutie, terwijl een kleinere waarde meer data in een beperkte ruimte kan plaatsen. Pas deze waarde aan op basis van de scanomgeving.

## Stap 4: Definieer het aantal kolommen om de barcode‑grootte te regelen

MicroPDF417 ondersteunt 1‑4 kolommen. Meer kolommen geven een kortere, bredere barcode; minder kolommen creëren een hogere, smallere barcode.

```csharp
// Step 4: Define the number of columns (1‑4 are allowed) to control barcode size
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Waarom dit belangrijk is:** Het kiezen van het juiste aantal kolommen stelt je in staat de barcode in een specifiek UI‑element of afgedrukt label te passen zonder handmatige schaalvergroting.

## Stap 5: Sla de barcode op als PNG‑afbeelding

Schrijf tenslotte de gegenereerde barcode naar de schijf. PNG behoudt verliesvrije kwaliteit, wat belangrijk is voor scherpe scans.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\MicroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Als de doelmap niet bestaat, gooit de `Save`‑methode een `ArgumentException`. Je kunt dit voorkomen met een eenvoudige controle:

```csharp
if (!System.IO.Directory.Exists(@"C:\Barcodes"))
{
    System.IO.Directory.CreateDirectory(@"C:\Barcodes");
}
```

### Volledige broncode

Door de onderdelen samen te voegen, hier is het volledige, uitvoerbare programma:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");

            // 2️⃣ Set the X‑dimension (module width) in pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Define the number of columns (1‑4 are allowed) to control barcode size
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Ensure the output folder exists
            string folder = @"C:\Barcodes";
            if (!System.IO.Directory.Exists(folder))
                System.IO.Directory.CreateDirectory(folder);

            // 4️⃣ Save the generated barcode as a PNG image
            string outputPath = System.IO.Path.Combine(folder, "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Het uitvoeren van dit programma produceert een bestand met de naam **MicroPdf417.png** dat eruitziet als de screenshot hieronder (afbeelding weggelaten voor beknoptheid). De barcode codeert de tekst *Sample* en houdt rekening met de X‑dimensie en kolominstellingen die je hebt gedefinieerd.

## Andere PDF417‑opties aanpassen

Hoewel deze gids zich richt op **customize pdf417 barcode**‑parameters die de grootte beïnvloeden, biedt Aspose.BarCode veel extra instellingen die je mogelijk nodig hebt:

| Eigenschap | Doel | Typische waarden |
|------------|------|------------------|
| `generator.Parameters.Barcode.Pdf417.Rows` | Controls the number of rows (height) | 3‑30 |
| `generator.Parameters.Barcode.Pdf417.ErrorLevel` | Sets error‑correction level (higher = more tolerant) | 0‑8 |
| `generator.Parameters.Barcode.Pdf417.Truncated` | Generates a truncated barcode (no stop pattern) | `true`/`false` |
| `generator.Parameters.Barcode.Pdf417.CompactionMode` | Chooses numeric, text, or byte compaction | `CompactionModes.Numeric`, etc. |

**Pro tip:** Wanneer je een barcode nodig hebt die in een vaste breedte past, begin dan met het verhogen van `Columns` en het verlagen van `XDimension`. Als de scanner gemiste symbolen meldt, verhoog dan de `ErrorLevel` om de redundantie te verbeteren.

## Randgevallen afhandelen

* **Tekst te lang voor MicroPDF417:** De Micro‑variant ondersteunt tot 1 KB aan data. Als je tekenreeks deze limiet overschrijdt, schakel dan over naar de volledige `Pdf417`‑symbologie door `EncodeTypes.MicroPdf417` te wijzigen in `EncodeTypes.Pdf417`.
* **Niet‑ondersteund afbeeldingsformaat:** `BarCodeImageFormat` ondersteunt ook `Jpeg`, `Bmp` en `Gif`. Kies een formaat dat past bij je downstream verwerkings‑pipeline.
* **Cross‑platform paden:** Gebruik `Path.Combine` in plaats van hard‑gecodeerde backslashes wanneer je richt op Linux of macOS.

## De barcode verifiëren

Je kunt de gegenereerde afbeelding verifiëren met elke standaard barcode‑scanner‑app (mobiel of desktop). De scanner zou de oorspronkelijke tekst **Sample** moeten teruggeven. Als dit mislukt:

1. Controleer of de X‑dimensie niet onder 1 pixel is ingesteld (sommige scanners kunnen sub‑pixel modules niet resolven).
2. Zorg ervoor dat het uitvoerbestand niet corrupt is — voer het programma opnieuw uit en vergelijk de bestandsgroottes.
3. Verhoog `ErrorLevel` om de tolerantie te verbeteren.

## Conclusie

Je weet nu **how to generate barcode** in C# met Aspose.BarCode, hoe je **customize pdf417 barcode** dimensies en kolomtelling kunt aanpassen, en hoe je **create barcode image C#** projecten direct kunt insluiten. Het volledige voorbeeld toont een praktische workflow van projectopzet tot uiteindelijke PNG‑output.

Vervolgens kun je andere symbologieën verkennen, zoals QR, Code128 of DataMatrix, door de `EncodeTypes`‑enumwaarde te wijzigen. Het aanpassen van extra parameters zoals `Resolution` of `Margin` stelt je in staat elke barcode fijn af te stemmen op je specifieke toepassing.

Veel programmeerplezier, en laat je barcodes je volgende automatiseringsproject versterken!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat complete werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PDF417 Barcode-afbeelding te genereren in C# met Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Hoe PDF417 Barcode te maken met Aspose – Complete stapsgewijze gids](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Hoe Barcode op te slaan in C# – PDF417 Barcodes genereren](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}