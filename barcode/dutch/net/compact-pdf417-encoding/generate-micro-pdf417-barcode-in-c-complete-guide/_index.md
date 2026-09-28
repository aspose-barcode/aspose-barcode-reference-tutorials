---
category: general
date: 2026-07-18
description: Genereer micro‑pdf417‑streepcode met Aspose.BarCode voor .NET – stap‑voor‑stap‑gids
  met kolommen, rijen en PNG‑output.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate micro pdf417 barcode
- Aspose.BarCode for .NET
- MicroPdf417 columns
- MicroPdf417 rows
- C# barcode generation
language: nl
lastmod: 2026-07-18
og_description: Genereer direct een micro‑pdf417‑barcode met Aspose.BarCode voor .NET.
  Leer hoe je kolommen, rijen kunt regelen en binnen enkele minuten als PNG kunt opslaan.
og_image_alt: Screenshot of a generated Micro PDF417 barcode saved as PNG
og_title: Genereer Micro PDF417-barcode – Volledige C#-handleiding
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate micro pdf417 barcode with Aspose.BarCode for .NET – step‑by‑step
    guide covering columns, rows, and PNG output.
  headline: Generate Micro PDF417 Barcode in C# – Complete Guide
  type: TechArticle
- description: Generate micro pdf417 barcode with Aspose.BarCode for .NET – step‑by‑step
    guide covering columns, rows, and PNG output.
  name: Generate Micro PDF417 Barcode in C# – Complete Guide
  steps:
  - name: 4.1 Two Columns, Auto‑Calculated Rows
    text: '```csharp // Force 2 columns, let rows auto‑adjust generator.Parameters.Barcode.Pdf417.Columns
      = 2; generator.Parameters.Barcode.Pdf417.Rows = 0; // 0 = auto generator.Save("MicroPdf417Columns2.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Columns2.png");
      ```'
  - name: 4.2 Six Rows, Auto‑Calculated Columns
    text: '```csharp // Switch to 6 rows, columns auto‑determined generator.Parameters.Barcode.Pdf417.Columns
      = 0; // auto columns generator.Parameters.Barcode.Pdf417.Rows = 6; generator.Save("MicroPdf417Rows6.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Rows6.png"); ```'
  - name: 4.3 Four Columns × Eight Rows (Fully Specified)
    text: '```csharp // Explicitly set both columns and rows generator.Parameters.Barcode.Pdf417.Columns
      = 4; generator.Parameters.Barcode.Pdf417.Rows = 8; generator.Save("MicroPdf417Rows8Columns4.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");
      ```'
  - name: Expected Output
    text: 'Running the program produces three PNG files:'
  type: HowTo
- questions:
  - answer: Call `Directory.CreateDirectory(path)` before the first `Save` to avoid
      a `DirectoryNotFoundException`.
    question: What if the output folder doesn’t exist?
  - answer: Absolutely. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif`
      as needed.
    question: Can I change the image format?
  - answer: MicroPdf417 can encode up to 1 KB of data, but practical limits depend
      on the chosen rows/columns. If you hit an error, increase rows or columns.
    question: Is there a limit to the text length?
  - answer: Use Aspose.Pdf to insert the generated PNG, or switch to `BarCodeImageFormat.Pdf`
      for a direct PDF output.
    question: How do I embed the barcode in a PDF?
  type: FAQPage
tags:
- barcode
- C#
- Aspose
title: Genereer Micro PDF417-barcode in C# – Complete gids
url: /nl/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Genereer Micro PDF417 Barcode in C# – Complete Gids

Heb je je ooit afgevraagd hoe je **micro pdf417 barcode** direct vanuit je C#‑applicatie kunt **genereren**? Je bent niet de enige. Of je nu voorraad labelt, korte URL’s codeert, of een aangepaste scanoplossing bouwt, het beheersen van deze kleine maar krachtige 2‑D‑code kan je veel gedoe besparen.

In deze tutorial lopen we een praktijkvoorbeeld door met **Aspose.BarCode for .NET**, waarbij we laten zien hoe je kolommen, rijen en module‑grootte kunt aanpassen en vervolgens het resultaat naar een PNG‑bestand kunt wegschrijven. Aan het einde heb je een kant‑klaar console‑programma dat drie verschillende barcode‑afbeeldingen genereert – geen mysterie meer.

## Wat je nodig hebt

- .NET 6 of later (de code werkt ook op .NET Framework 4.7+)
- Visual Studio 2022 (of een andere C#‑IDE naar keuze)
- Het **Aspose.BarCode** NuGet‑pakket (`Aspose.BarCode`)
- Een schrijfbare map op schijf voor de output‑PNGs

Als je dit al hebt, prima – laten we beginnen.

## Stap 1: Het project opzetten en Aspose.BarCode installeren

Maak eerst een nieuw console‑project aan:

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode
```

> **Pro tip:** Voer `dotnet restore` uit nadat je het pakket hebt toegevoegd om er zeker van te zijn dat alle afhankelijkheden zijn opgelost.

Open nu `Program.cs`. We beginnen met het importeren van de benodigde namespaces:

```csharp
using System;
using Aspose.BarCode.Generation;
```

Deze twee `using`‑statements geven ons toegang tot `BarcodeGenerator`, `EncodeTypes` en de enum voor het afbeeldingsformaat die we later nodig hebben.

## Stap 2: Initialiseert de MicroPdf417‑generator

Het hart van de operatie is het `BarcodeGenerator`‑object. We geven het het **MicroPdf417**‑encoderingstype en de tekst die we willen coderen – in ons geval het woord “ASPOSE”.

```csharp
// Initialise generator with MicroPdf417 and sample text
var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "ASPOSE");
```

Waarom `MicroPdf417`? In vergelijking met de volledige PDF417 past de micro‑versie meer data in een kleinere footprint, perfect voor labels met beperkte ruimte.

## Stap 3: Pas de module‑grootte (X‑Dimension) aan

De module‑grootte bepaalt hoeveel pixels elk klein vierkantje van de barcode inneemt. Een waarde van **2 pixels** levert een scherp, leesbaar beeld op zonder de bestandsgrootte te laten oplopen.

```csharp
// Set X‑dimension to 2 pixels per module
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Opmerking:** Als je een grotere barcode nodig hebt voor scannen op afstand, verhoog dit getal dan naar 3 of 4.

## Stap 4: Genereer barcodes met verschillende kolom‑/rij‑configuraties

### 4.1 Twee kolommen, automatisch berekende rijen

```csharp
// Force 2 columns, let rows auto‑adjust
generator.Parameters.Barcode.Pdf417.Columns = 2;
generator.Parameters.Barcode.Pdf417.Rows = 0; // 0 = auto
generator.Save("MicroPdf417Columns2.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Columns2.png");
```

### 4.2 Zes rijen, automatisch berekende kolommen

```csharp
// Switch to 6 rows, columns auto‑determined
generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
generator.Parameters.Barcode.Pdf417.Rows = 6;
generator.Save("MicroPdf417Rows6.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Rows6.png");
```

### 4.3 Vier kolommen × acht rijen (volledig gespecificeerd)

```csharp
// Explicitly set both columns and rows
generator.Parameters.Barcode.Pdf417.Columns = 4;
generator.Parameters.Barcode.Pdf417.Rows = 8;
generator.Save("MicroPdf417Rows8Columns4.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");
```

Elke `Save`‑aanroep schrijft een PNG‑bestand naar de werkmap van het project. Voel je vrij om het pad (`"YOUR_DIRECTORY/..."`) te wijzigen naar bijvoorbeeld `Path.Combine(Environment.CurrentDirectory, "output")` als je een speciale map wilt gebruiken.

## Stap 5: Volledig werkend voorbeeld

Alles bij elkaar, hier is het complete, kant‑klaar programma dat je kunt kopiëren en plakken:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise generator with MicroPdf417 and sample text
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "ASPOSE");

            // 2️⃣ Set module size – 2 pixels per module for a sharp image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Create three variants with different column/row settings

            // Variant A – 2 columns, rows auto‑adjust
            generator.Parameters.Barcode.Pdf417.Columns = 2;
            generator.Parameters.Barcode.Pdf417.Rows = 0; // auto rows
            generator.Save("MicroPdf417Columns2.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Columns2.png");

            // Variant B – 6 rows, columns auto‑determine
            generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
            generator.Parameters.Barcode.Pdf417.Rows = 6;
            generator.Save("MicroPdf417Rows6.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Rows6.png");

            // Variant C – 4 columns × 8 rows (full control)
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows = 8;
            generator.Save("MicroPdf417Rows8Columns4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");

            Console.WriteLine("All barcodes generated successfully!");
        }
    }
}
```

### Verwachte output

Het uitvoeren van het programma levert drie PNG‑bestanden op:

| Bestandsnaam | Ongeveer afmetingen (px) | Visuele aanwijzing |
|--------------|--------------------------|--------------------|
| `MicroPdf417Columns2.png` | 180 × 120 | Smalle, hogere barcode |
| `MicroPdf417Rows6.png` | 120 × 180 | Brede, kortere barcode |
| `MicroPdf417Rows8Columns4.png` | 160 × 160 | Bijna vierkant, gebalanceerde lay‑out |

Open een van deze bestanden in een afbeeldingsviewer – je ziet een scherpe **Micro PDF417**‑barcode klaar om gescand te worden.

## Veelgestelde vragen & randgevallen

- **Wat als de output‑map niet bestaat?**  
  Roep `Directory.CreateDirectory(path)` aan vóór de eerste `Save` om een `DirectoryNotFoundException` te voorkomen.

- **Kan ik het afbeeldingsformaat wijzigen?**  
  Zeker. Vervang `BarCodeImageFormat.Png` door `Jpeg`, `Bmp` of `Gif` naar wens.

- **Is er een limiet aan de tekstlengte?**  
  MicroPdf417 kan tot 1 KB data coderen, maar praktische limieten hangen af van het gekozen aantal rijen/kolommen. Als je een fout krijgt, vergroot dan het aantal rijen of kolommen.

- **Hoe embed ik de barcode in een PDF?**  
  Gebruik Aspose.Pdf om de gegenereerde PNG in te voegen, of schakel over naar `BarCodeImageFormat.Pdf` voor directe PDF‑output.

## Pro‑tips voor C#‑barcodegeneratie

1. **Cache de generator** wanneer je veel barcodes met dezelfde instellingen moet maken – alleen de tekst hoeft te veranderen, wat CPU‑cycli bespaart.  
2. **Fijn‑afstem foutcorrectie** via `generator.Parameters.Barcode.Pdf417.ErrorLevel` als je scanomgeving ruisig is.  
3. **Test vroeg met echte scanners**. Sommige handheld‑apparaten hebben moeite met zeer dichte micro‑barcodes; het aanpassen van `XDimension` kan een groot verschil maken.

## Conclusie

Je weet nu hoe je **micro pdf417 barcode** kunt **genereren** met **Aspose.BarCode for .NET**, hoe je **MicroPdf417‑kolommen** en **MicroPdf417‑rijen** kunt manipuleren, en hoe je het resultaat als PNG‑bestand opslaat – alles vanuit één net console‑applicatie in C#. Experimenteer met verschillende module‑groottes, foutniveaus of zelfs gekleurde output om aan de eisen van jouw project te voldoen.

Vervolgens kun je **C#‑barcodegeneratie** verkennen voor andere symbologieën zoals QR, Code128 of DataMatrix, of de afbeeldingen direct in PDFs embedden met Aspose.Pdf. De mogelijkheden zijn eindeloos zodra je de basis onder de knie hebt.

Happy coding, en moge je scans altijd fout‑vrij zijn!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}