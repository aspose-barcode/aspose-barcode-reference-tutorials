---
category: general
date: 2026-10-18
description: Leer hoe u een PDF417-barcode maakt in C# met Aspose.BarCode. Deze tutorial
  behandelt basis-, compacte, macro- en micro-PDF417-generatie met volledige code.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to create pdf417
language: nl
lastmod: 2026-10-18
og_description: Maak PDF417-barcode in C# met Aspose.BarCode. Volg deze gids om stap
  voor stap basis-, compacte, macro- en micro‑PDF417-barcodes te genereren.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as an image file
og_title: PDF417-barcode maken in C# – volledige Aspose.BarCode‑tutorial
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to create PDF417 barcode in C# with Aspose.BarCode. This
    tutorial covers basic, compact, macro and micro PDF417 generation with full code.
  headline: Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
- aspose
title: PDF417-barcode maken in C# met Aspose.BarCode – stapsgewijze handleiding
url: /nl/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak PDF417 barcode in C# met Aspose.BarCode – stapsgewijze handleiding

Als je een **PDF417 barcode** moet maken in een .NET‑applicatie, leidt deze tutorial je door het volledige proces. Je ziet hoe je een basis‑barcode genereert, compacte modus inschakelt, macro‑metadata toevoegt en een micro‑variant maakt – allemaal met duidelijke uitleg en uitvoerbare code.

Het genereren van PDF417 barcodes is gebruikelijk in logistiek, ticketing en documentbeheer. Aan het einde van deze gids kun je barcode‑creatie integreren in elk C#‑project zonder externe tools.

## Vereisten

Voordat je begint, zorg dat je het volgende hebt:

* .NET 6.0 of later (de code werkt ook met .NET Framework 4.7+)
* Visual Studio 2022 of een andere C#‑IDE
* **Aspose.BarCode for .NET** NuGet‑pakket  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Schrijfrechten voor een map waar de gegenereerde PNG‑bestanden worden opgeslagen

Er is geen extra configuratie nodig; de bibliotheek behandelt alle low‑level coderingsdetails.

## Stap 1: Maak een basis‑PDF417 barcode

De eerste stap maakt een reguliere PDF417 barcode met aangepaste grootte en kolomaantal.

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator for a standard PDF417 barcode
BarcodeGenerator basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

// Adjust the X‑dimension (module width) to 2 pixels for higher resolution
basicGen.Parameters.Barcode.XDimension.Pixels = 2;

// Set the number of columns – three columns keep the barcode compact yet readable
basicGen.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image
basicGen.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Waarom deze instellingen belangrijk zijn**

* `XDimension.Pixels` bepaalt de fysieke grootte van elk barcode‑element. Een waarde van 2 levert een duidelijk beeld op de meeste schermen en printers.
* `Pdf417.Columns` bepaalt hoeveel datakolommen de barcode bevat. Minder kolommen verkleinen de breedte; meer kolommen verhogen de gegevenscapaciteit.

Het uitvoeren van de code maakt `Pdf417Basic.png`, die eruitziet als een typische PDF417‑symbool met drie datakolommen en een volledige metadata‑kolom aan de rechterkant.

## Stap 2: Schakel compacte (afgekorte) modus in

Compacte modus verwijdert de metadata‑kolom aan de rechterkant, waardoor de barcode smaller wordt. Dit is handig wanneer de ruimte beperkt is maar de gegevens kunnen worden gereconstrueerd uit de resterende rijen.

```csharp
// Turn on truncated mode to omit the metadata column
basicGen.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version
basicGen.Save(@"YOUR_DIRECTORY\CompactPdf417.png", BarCodeImageFormat.Png);
```

**Waarom afkappen?**  
Wanneer `Truncate` `true` is, laat de generator de optionele rechterkolom weg die fout‑correctie‑ en bestands‑metadata opslaat. De resulterende barcode neemt minder kolommen in beslag en blijft toch scanbaar met de meeste PDF417‑lezers.

## Stap 3: Maak een Macro PDF417 barcode met bestands‑niveau metadata

Macro PDF417 breidt het standaardformaat uit met segment‑identifiers, waardoor een groot document kan worden opgesplitst in meerdere barcodes. Dit is handig voor het coderen van lange tekenreeksen of meer‑pagina‑bestanden.

```csharp
// Initialize a generator for Macro PDF417
BarcodeGenerator macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");

// Set column count for better readability
macroGen.Parameters.Barcode.Pdf417.Columns = 5;

// Assign macro-specific identifiers
macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Unique file identifier
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;      // Current segment number
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total segments

// Save the macro barcode
macroGen.Save(@"YOUR_DIRECTORY\MacroPdf417.png", BarCodeImageFormat.Png);
```

**Uitleg van macro‑velden**

| Eigenschap | Doel |
|------------|------|
| `MacroPdf417FileID` | Unieke identifier voor het gehele bestand; alle segmenten delen deze waarde. |
| `MacroPdf417SegmentID` | Index van het huidige segment (begint bij 1). |
| `MacroPdf417SegmentsCount` | Totaal aantal segmenten dat de volledige dataset vormt. |

Een scanner die Macro PDF417 begrijpt, kan de oorspronkelijke data opnieuw samenstellen door alle segmenten te lezen en deze identifiers te gebruiken.

## Stap 4: Maak een Micro PDF417 barcode voor korte data

Micro PDF417 is een compacte versie ontworpen voor kleine payloads (tot 90 tekens). Het beperkt het kolombereik tot 1‑4, waardoor de barcode geschikt is voor kleine labels of apparaten met een beperkt display‑gebied.

```csharp
// Initialize a generator for Micro PDF417
BarcodeGenerator microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");

// Set a fine X‑dimension for crisp rendering
microGen.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a column count within the allowed range (1‑4)
microGen.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode
microGen.Save(@"YOUR_DIRECTORY\MicroPdf417.png", BarCodeImageFormat.Png);
```

**Wanneer Micro PDF417 te gebruiken**  
Gebruik deze variant wanneer de gegevenspayload kort is en je de kleinste mogelijke barcode nodig hebt. Het is ideaal voor voorraad‑tags, toegangspassen of elke situatie waarin schermruimte schaars is.

## Volledig werkend voorbeeld

Hieronder vind je een zelfstandige console‑applicatie die alle vier barcode‑typen in één keer genereert. Kopieer de code naar een nieuw C#‑project, vervang `YOUR_DIRECTORY` door een bestaand map‑pad, en voer het uit.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Adjust this path to a writable folder on your machine
            string outputPath = @"C:\Barcodes";

            // ---------- Basic PDF417 ----------
            var basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            basicGen.Parameters.Barcode.XDimension.Pixels = 2;
            basicGen.Parameters.Barcode.Pdf417.Columns = 3;
            basicGen.Save($"{outputPath}\\Pdf417Basic.png", BarCodeImageFormat.Png);

            // ---------- Compact PDF417 ----------
            basicGen.Parameters.Barcode.Pdf417.Truncate = true;
            basicGen.Save($"{outputPath}\\CompactPdf417.png", BarCodeImageFormat.Png);

            // ---------- Macro PDF417 ----------
            var macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");
            macroGen.Parameters.Barcode.Pdf417.Columns = 5;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
            macroGen.Save($"{outputPath}\\MacroPdf417.png", BarCodeImageFormat.Png);

            // ---------- Micro PDF417 ----------
            var microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");
            microGen.Parameters.Barcode.XDimension.Pixels = 2;
            microGen.Parameters.Barcode.Pdf417.Columns = 4; // valid range: 1‑4
            microGen.Save($"{outputPath}\\MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("All PDF417 barcodes have been generated successfully.");
        }
    }
}
```

**Verwachte output**

Het uitvoeren van het programma maakt vier PNG‑bestanden aan in de opgegeven map:

* `Pdf417Basic.png` – standaard barcode met drie kolommen
* `CompactPdf417.png` – dezelfde data, afgekorte rechterkolom
* `MacroPdf417.png` – macro‑barcode met segment‑metadata
* `MicroPdf417.png` – compacte micro‑barcode voor korte tekenreeksen

Open een van de afbeeldingen met een beeldviewer; je ziet de karakteristieke PDF417‑patronen. Het scannen ervan met een mobiele barcode‑lezer (bijv. ZXing, Scandit) geeft de oorspronkelijke tekst‑strings terug.

## Veelgestelde vragen en tips

* **Wat als de barcode er onscherp uitziet?**  
  Verhoog `XDimension.Pixels` naar 3 of 4. Grotere module‑groottes leveren hogere resolutie‑afbeeldingen, ten koste van een groter bestand.

* **Kan ik SVG in plaats van PNG exporteren?**  
  Ja. Vervang `BarCodeImageFormat.Png` door `BarCodeImageFormat.Svg` in de `Save`‑aanroepen.

* **Moet ik het fout‑correctieniveau handmatig instellen?**  
  Aspose.BarCode kiest automatisch een optimaal niveau. Voor gespecialiseerde gevallen kun je `Pdf417.ErrorCorrectionLevel` aanpassen.

* **Hoe embed ik de barcode in een PDF‑document?**  
  Gebruik `Aspose.Pdf` om de gegenereerde PNG of SVG als een afbeeldingselement op een PDF‑pagina toe te voegen.

* **Is de bibliotheek thread‑safe?**  
  Elke `BarcodeGenerator`‑instantie is onafhankelijk; je kunt generators op meerdere threads aanmaken zonder gedeelde staat.

## Conclusie

Je weet nu hoe je een **PDF417 barcode** kunt maken in C# met Aspose.BarCode, inclusief basis‑, compacte, macro‑ en micro‑varianten.

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe maak je een pdf417 barcode in C# – stapsgewijze handleiding](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [Hoe maak je een PDF417 barcode in C# met compacte modus](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [Hoe maak je een macro PDF417 barcode in C# met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}