---
category: general
date: 2026-10-05
description: Aspose Barcode Generator C# stelt je in staat om macro‑gegevens toe te
  voegen en PDF417‑barcodes moeiteloos te genereren. Leer stap voor stap hoe je macro‑metadata
  toevoegt en een PDF417‑afbeelding maakt.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode generator c#
- how to add macro
- how to generate pdf417
language: nl
lastmod: 2026-10-05
og_description: Aspose Barcode Generator C# laat je zien hoe je macro‑metadata kunt
  toevoegen en een PDF417‑barcode kunt genereren in een paar regels code.
og_image_alt: Screenshot of a MacroPdf417 barcode created with Aspose Barcode Generator
  C#
og_title: Aspose Barcode Generator C# – macro toevoegen & PDF417-barcode genereren
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Aspose Barcode Generator C# lets you add macro data and generate PDF417
    barcodes effortlessly. Learn step‑by‑step how to add macro metadata and create
    a PDF417 image.
  headline: How to use Aspose Barcode Generator C# for a MacroPdf417 barcode
  type: TechArticle
tags:
- barcode
- csharp
- aspose
title: Hoe gebruik je Aspose Barcode Generator C# voor een MacroPdf417‑barcode
url: /nl/net/compact-pdf417-encoding/how-to-use-aspose-barcode-generator-c-for-a-macropdf417-barc/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe gebruik je Aspose Barcode Generator C# voor een MacroPdf417 barcode

Als je een MacroPdf417 barcode in C# moet maken, biedt **Aspose Barcode Generator C#** een beknopte API die zowel de barcode‑afbeelding als de benodigde macro‑metadata afhandelt. Deze tutorial laat precies zien hoe je macro‑informatie toevoegt en een PDF417 barcode‑afbeelding genereert in slechts een paar stappen.

Je leert hoe je visuele parameters configureert, macro‑velden zoals bestand‑ID en tijdstempel embedt, en het resultaat opslaat als PNG. Er zijn geen externe tools nodig – alleen de Aspose.BarCode‑bibliotheek en een .NET‑ontwikkelomgeving.

## Prerequisites

Voordat je begint, zorg dat je het volgende hebt:

* .NET 6.0 of later geïnstalleerd  
* Visual Studio 2022 (of een andere C#‑IDE)  
* Een gelicentieerde of evaluatie‑kopie van **Aspose.BarCode for .NET**  

De code werkt op Windows, Linux en macOS omdat de bibliotheek platform‑agnostisch is.

## Step 1: Install the Aspose.BarCode NuGet package

Open je project in Visual Studio en voer vervolgens het volgende commando uit in de **Package Manager Console**:

```powershell
Install-Package Aspose.BarCode
```

Dit voegt de `Aspose.BarCode`‑assembly en de afhankelijkheden toe aan je project.

## Step 2: Create the barcode generator instance

De eerste regel maakt een `BarcodeGenerator`‑object aan voor de **MacroPdf417**‑symbologie en levert de tekst die je wilt coderen.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

// Step 2: Initialise the generator with MacroPdf417 and the payload text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // subsequent configuration goes here
}
```

*Waarom dit belangrijk is*: De waarde `EncodeTypes.MacroPdf417` vertelt de bibliotheek dat macro‑gerelateerde velden verwacht, die je in de volgende stap instelt.

## Step 3: Define visual appearance

Je kunt de grootte van elk module (het kleinste zwarte of witte vierkant) en het aantal kolommen in de PDF417‑matrix regelen. Het aanpassen van `XDimension` beïnvloedt de algehele beeldresolutie.

```csharp
    // Step 3: Visual settings
    generator.Parameters.Barcode.XDimension.Pixels = 2;          // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol
```

Het verhogen van `Columns` verkleint de barcode‑hoogte, terwijl een grotere `XDimension` de afbeelding scherper maakt op schermen met hoge DPI.

## Step 4: Add macro metadata (how to add macro)

MacroPdf417 vereist verschillende extra velden die het bronbestand en de segmentatie beschrijven. De volgende eigenschappen komen rechtstreeks overeen met de PDF417‑macro‑specificaties:

```csharp
    // Step 4: Macro fields – how to add macro data
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;               // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;                  // current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;              // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";             // optional file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                // CCITT‑16 placeholder
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                   // creation timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";            // recipient identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";               // sender identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                   // marks the last segment
```

*Waarom deze velden*:  
* `MacroPdf417FileID` koppelt alle segmenten aan elkaar, zodat een scanner het originele document kan reconstrueren.  
* `MacroPdf417SegmentID` en `MacroPdf417SegmentsCount` laten de decoder de volgorde en het totale aantal delen weten.  
* `MacroPdf417FileSize` en `MacroPdf417Checksum` bieden integriteitscontroles, wat waardevol is bij grote gegevensoverdrachten.

## Step 5: Save the barcode image (how to generate pdf417)

Schrijf tenslotte de barcode naar schijf. De `Save`‑methode accepteert een bestandspad en een afbeeldingsformaat. PNG behoudt de scherpe randen van de barcode zonder compressie‑artefacten.

```csharp
    // Step 5: Save the generated barcode – how to generate pdf417 image
    generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

Wanneer het programma wordt uitgevoerd, vind je **ExtPDF417Meta.png** in de output‑map. Het openen van de afbeelding toont een schone MacroPdf417 barcode, klaar om af te drukken of in een PDF te embedden.

### Expected output

| Bestandsnaam        | Formaat | Afmetingen (bij benadering) |
|---------------------|---------|-----------------------------|
| ExtPDF417Meta.png   | PNG     | 300 × 150 px (varieert met `XDimension`) |

Het scannen van de afbeelding met een PDF417‑compatibele lezer (bijv. ZXing, Aspose.BarCode for .NET) retourneert de oorspronkelijke tekst **“Åspóse.Barcóde©”** samen met alle macro‑velden.

## Common pitfalls and how to avoid them

| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| **Incorrect `EncodeTypes`** | Het gebruik van `EncodeTypes.Pdf417` in plaats van `EncodeTypes.MacroPdf417` schakelt macro‑velden uit. | Instantieer de generator altijd met `EncodeTypes.MacroPdf417`. |
| **Missing macro fields** | Sommige scanners negeren de barcode als verplichte macro‑velden ontbreken. | Vul minimaal `FileID`, `SegmentID`, `SegmentsCount` en `Terminator` in. |
| **Too small `XDimension`** | Een waarde onder 1 pixel kan een onleesbare barcode opleveren op lage‑resolutie displays. | Houd `XDimension` ≥ 2 pixels voor de meeste scherm‑ en printscenario's. |
| **File path errors** | Het opgeven van een relatief pad dat niet bestaat veroorzaakt een uitzondering. | Gebruik `Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png")` of een absoluut pad. |

## Full source code

Hieronder staat het volledige, uitvoerbare voorbeeld dat je kunt kopiëren naar een nieuw console‑project.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with MacroPdf417 and the payload text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns

                // Macro fields – how to add macro
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save the barcode – how to generate pdf417
                generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("MacroPdf417 barcode generated successfully.");
        }
    }
}
```

Voer het programma uit (`dotnet run`). Na uitvoering print de console een succesbericht en verschijnt het PNG‑bestand in de output‑map van het project.

## Next steps

* **Encode larger data** – Verhoog `Columns` of pas `Rows` aan (via `Pdf417.Rows`) om meer tekens te kunnen verwerken.  
* **Embed in PDF** – Gebruik Aspose.PDF om de gegenereerde PNG in een document te plaatsen.  
* **Scan verification** – Maak gebruik van `Aspose.BarCode.Reader` om de barcode te decoderen en macro‑velden programmatisch te bevestigen.  

Het verkennen van deze onderwerpen verdiept je begrip van **hoe je PDF417** barcodes genereert met rijke macro‑informatie en bereidt je voor op real‑world use‑cases zoals batch‑documentverwerking of veilige gegevensuitwisseling.

---

*Happy coding! If you found this guide useful, consider sharing it with teammates or starring the Aspose.BarCode repository on GitHub.*

## What Should You Learn Next?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [How to generate PDF417 barcode in C# with Barcode Generator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/)
- [Aspose barcode example: generate Macro PDF417 in C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}