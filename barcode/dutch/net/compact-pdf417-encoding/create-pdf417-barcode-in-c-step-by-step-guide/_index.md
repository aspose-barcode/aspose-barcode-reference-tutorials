---
category: general
date: 2026-08-03
description: Creëer snel een PDF417‑barcode in C#. Leer hoe je een PDF417‑barcode
  genereert en hoe je de barcode‑afbeelding opslaat als PNG met Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417 barcode
- how to save barcode image
language: nl
lastmod: 2026-08-03
og_description: Maak een PDF417-barcode in C# met Aspose.Barcode. Volg deze gids om
  een PDF417-barcode te genereren en hoe je de barcode‑afbeelding efficiënt opslaat.
og_image_alt: Screenshot of a generated compact PDF417 barcode saved as PNG
og_title: PDF417-barcode maken in C# – volledige programmeertutorial
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  headline: Create PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  name: Create PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: Why this matters
    text: '* **EncodeTypes.Pdf417** tells the library to use the PDF417 standard,
      which supports large data payloads and error correction. * Providing Unicode
      characters proves the generator handles non‑ASCII input without extra configuration.'
  - name: Practical tip
    text: If you need a taller barcode for limited horizontal space, increase `Columns`.
      Setting `Truncate` to `true` reduces the overall height by removing quiet zones,
      which is ideal for mobile screens.
  - name: Expected result
    text: Running the program creates `CompactPdf417.png` in the project folder. Opening
      the file shows a compact PDF417 barcode that encodes the string *Åspóse.Barcóde©*.
      The image can be embedded in HTML, PDF reports, or printed on labels.
  - name: Verifying the output
    text: 'After the program finishes, you can verify the file exists with a quick
      command:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: PDF417‑barcode maken in C# – stapsgewijze handleiding
url: /nl/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PDF417-streepjescode maken in C# – stapsgewijze handleiding

Als je een **PDF417-streepjescode** moet maken in een .NET‑applicatie, laat deze handleiding je precies zien hoe je een PDF417‑streepjescode genereert en hoe je de streepjescode‑afbeelding opslaat. Je krijgt een PNG‑bestand dat kan worden gebruikt in rapporten, tickets of mobiele scan‑apps.

De tutorial behandelt alles, van projectopzet tot het uiteindelijke PNG‑bestand. Er is geen externe documentatie nodig; volg gewoon de stappen en voer de code uit.

## Wat je nodig hebt

* .NET 6.0 SDK of later (de code werkt ook met .NET Framework 4.7+)
* Visual Studio 2022 of een IDE die C# ondersteunt
* Internettoegang om het **Aspose.Barcode for .NET** NuGet‑pakket te installeren

Deze vereisten zorgen ervoor dat de code compileert zonder extra configuratie.

## PDF417-streepjescode maken – projectopzet

1. Open een opdrachtprompt en maak een nieuw console‑project aan:

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. Voeg de Aspose.Barcode‑bibliotheek toe:

   ```bash
   dotnet add package Aspose.Barcode
   ```

3. Open het gegenereerde `Program.cs`‑bestand. De `using`‑statements bovenaan geven je toegang tot de streepjescode‑klassen:

   ```csharp
   using System;
   using Aspose.Barcode.Generation;
   using Aspose.Barcode;
   ```

Het project is nu klaar om **PDF417‑streepjescode te maken**.

## Hoe PDF417‑streepjescode te genereren met Aspose.Barcode

De kern van het maken van de streepjescode bevindt zich in de `BarcodeGenerator`‑klasse. Je specificeert de symbologie (`EncodeTypes.Pdf417`) en de gegevens die je wilt coderen.

```csharp
// Step 1: Initialise the generator with PDF417 symbology and sample text.
// The text includes Unicode characters to demonstrate full‑range support.
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

### Waarom dit belangrijk is

* **EncodeTypes.Pdf417** geeft de bibliotheek aan de PDF417‑standaard te gebruiken, die grote gegevenspayloads en foutcorrectie ondersteunt.
* Het verstrekken van Unicode‑tekens bewijst dat de generator niet‑ASCII‑invoer zonder extra configuratie kan verwerken.

## Hoe de weergave van de streepjescode te configureren

Je kunt de grootte van elke module, het aantal kolommen en of de streepjescode compacte (afgekorte) modus gebruikt, regelen. Deze instellingen beïnvloeden zowel de leesbaarheid als de bestandsgrootte.

```csharp
// Step 2: Set the module (X) dimension – each barcode element will be 2 pixels wide.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Configure PDF417‑specific options.
generator.Parameters.Barcode.Pdf417.Columns = 3;      // Number of columns (affects height)
generator.Parameters.Barcode.Pdf417.Truncate = true; // Enable compact mode
```

### Praktische tip

Als je een hogere streepjescode nodig hebt voor beperkte horizontale ruimte, verhoog dan `Columns`. Het instellen van `Truncate` op `true` verkleint de totale hoogte door de stille zones te verwijderen, wat ideaal is voor mobieltjeschermen.

## Hoe de streepjescode‑afbeelding op te slaan als PNG

Na het configureren van de generator roep je `Save` aan met een bestandspad en het gewenste afbeeldingsformaat. De methode schrijft de afbeelding direct naar de schijf.

```csharp
// Step 4: Save the generated barcode as a PNG image.
string outputPath = @"./CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

### Verwacht resultaat

Het uitvoeren van het programma maakt `CompactPdf417.png` aan in de projectmap. Het openen van het bestand toont een compacte PDF417‑streepjescode die de tekenreeks *Åspóse.Barcóde©* codeert. De afbeelding kan worden ingebed in HTML, PDF‑rapporten of afgedrukt op labels.

## Volledige broncode

Hieronder staat het volledige, uitvoerbare programma. Kopieer het naar `Program.cs` en voer `dotnet run` uit.

```csharp
using System;
using Aspose.Barcode.Generation;
using Aspose.Barcode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with PDF417 symbology and sample text.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // Set the module width to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Configure PDF417‑specific options.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Define the output file path.
            string outputPath = @"./CompactPdf417.png";

            // Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### De output verifiëren

Nadat het programma is voltooid, kun je met een snelle opdracht controleren of het bestand bestaat:

```bash
dotnet run && ls -l CompactPdf417.png
```

Als het bestand verschijnt, is het **PDF417‑streepjescode maken** proces geslaagd.

## Veelvoorkomende variaties en randgevallen

| Situation | Adjustment |
|-----------|------------|
| **Langere gegevensreeks** | Verhoog `Columns` of stel `Rows` in om meer codewoorden te huisvesten. |
| **Ander afbeeldingsformaat** | Vervang `BarCodeImageFormat.Png` door `Jpeg`, `Bmp` of `Gif`. |
| **Hogere resolutie** | Stel `generator.Parameters.ImageResolution` in vóór `Save`. |
| **Achtergrondkleur** | Gebruik `generator.Parameters.Barcode.ImageBackgroundColor = Color.White;` |
| **Foutafhandeling** | Plaats `generator.Save` in een `try/catch`‑blok om I/O‑fouten op te vangen. |

## Conclusie

Je weet nu hoe je een **PDF417‑streepjescode** in C# kunt **maken** met Aspose.Barcode, hoe je de weergave kunt configureren, en hoe je een **streepjescode‑afbeelding** als PNG‑bestand kunt **opslaan**. Het volledige voorbeeld toont elke benodigde stap, van projectopzet tot verificatie, zodat je barcode‑generatie kunt integreren in elke .NET‑oplossing.

Vervolgens kun je gerelateerde onderwerpen verkennen, zoals **hoe je QR‑codes genereert**, **streepjescodes in PDF‑documenten embedden**, of **barcode‑kleuren aanpassen**. Elk van deze bouwt voort op dezelfde generator‑API, waardoor je de scan‑mogelijkheden van je applicatie met minimale inspanning kunt uitbreiden. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze handleiding worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe een streepjescode te maken – Compact PDF417 met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hoe DataMatrix‑streepjescodes (ECC 200) te genereren met Aspose.BarCode voor .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Hoe een Aztec‑streepjescode te genereren met aangepaste beeldverhouding met Aspose.BarCode voor .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}