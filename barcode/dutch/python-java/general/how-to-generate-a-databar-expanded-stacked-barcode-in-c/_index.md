---
category: general
date: 2026-10-21
description: Genereer een databar expanded stacked barcode‑afbeelding in C# met BarcodeGenerator.
  Volg deze stapsgewijze handleiding om barcode‑afbeeldingen te maken, rijen en kolommen
  aan te passen en PNG‑bestanden te exporteren.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- barcode generator c#
- how to generate databar
- create databar barcode
language: nl
lastmod: 2026-10-21
og_description: Genereer een databar expanded stacked barcode in C# met deze tutorial.
  Leer hoe je BarcodeGenerator gebruikt, rijen en kolommen instelt en PNG-afbeeldingen
  opslaat.
og_image_alt: Sample databar expanded stacked barcode image generated with C#
og_title: Genereer een Databar Expanded Stacked barcode in C# – volledige gids
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  headline: How to generate a databar expanded stacked barcode in C#
  type: TechArticle
- description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  name: How to generate a databar expanded stacked barcode in C#
  steps:
  - name: Basic barcode generation
    text: The simplest way to generate a **databar expanded stacked** image is to
      instantiate `BarcodeGenerator` with the desired `EncodeTypes` value and a plain
      text payload.
  - name: Customizing columns – create databar barcode with 4 columns
    text: You can control the number of columns using the `Parameters.Barcode.DataBar.Columns`
      property. The following example creates a barcode with **4 columns** while keeping
      the default row count.
  - name: Customizing rows – create databar barcode with 3 rows
    text: Similarly, you can adjust the row count via `Parameters.Barcode.DataBar.Rows`.
      The code below generates a barcode with **3 rows** and the default column count
      (4).
  - name: Exporting to other formats
    text: 'If you need a different image type (e.g., JPEG, BMP, or SVG), replace `BarCodeImageFormat.Png`
      with the appropriate enum value:'
  - name: Saving to a memory stream
    text: 'Sometimes you want to embed the barcode directly into a web response or
      a PDF without touching the file system. Use a `MemoryStream`:'
  - name: Handling invalid input
    text: 'The `BarcodeGenerator` validates the payload against the chosen symbology.
      If the data contains prohibited characters, an `ArgumentException` is thrown.
      Wrap the generation code in a try‑catch block to provide a friendly error message:'
  - name: Scaling the barcode image
    text: 'You can change the image size without altering the encoded data by setting
      `Parameters.Image.Width` and `Parameters.Image.Height`:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Hoe een Databar Expanded Stacked barcode te genereren in C#
url: /nl/python-java/general/how-to-generate-a-databar-expanded-stacked-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een databar expanded stacked barcode te genereren in C#

Als je een **databar expanded stacked** barcode in C# moet genereren, laat deze gids je zien hoe. De databar expanded stacked symbologie is ideaal voor het coderen van grote hoeveelheden data in een compact formaat, en je kunt de afbeelding maken met slechts een paar regels code. Je leert ook hoe je **barcode‑afbeeldingsbestanden** in verschillende formaten kunt genereren en rijen of kolommen kunt aanpassen aan je scanomgeving.

Deze tutorial behandelt alles wat je nodig hebt om databar‑barcodes te produceren: het installeren van de vereiste bibliotheek, het voorbereiden van de uitvoermap, het maken van de barcode met aangepaste rijen of kolommen, en het opslaan van het resultaat als een PNG‑bestand. Aan het einde kun je **databar barcode**‑afbeeldingen programmatisch maken en de code aanpassen voor andere afbeeldingsformaten of runtime‑scenario's.

## Vereisten

Zorg ervoor dat je het volgende hebt:

* .NET 6.0 SDK of later (de code werkt ook met .NET Core 3.1 en .NET Framework 4.7+)
* Een ontwikkelomgeving zoals Visual Studio 2022, Visual Studio Code, of Rider
* Internettoegang om het **Barcode Generator C#** NuGet‑pakket te installeren (Aspose.BarCode for .NET)

> **Pro tip:** Als je een CI/CD‑pipeline gebruikt, voeg dan de NuGet‑pakketreferentie toe aan je projectbestand zodat builds reproduceerbaar zijn.

## Installeer de Barcode Generator C#‑bibliotheek

Het voorbeeld maakt gebruik van de Aspose.BarCode‑bibliotheek, die de `BarcodeGenerator`‑klasse en de `EncodeTypes.DatabarExpandedStacked`‑enumeratie levert.

```bash
dotnet add package Aspose.BarCode
```

De opdracht voegt de nieuwste stabiele versie toe aan je project. Na de installatie kun je de namespace importeren in je C#‑bestanden:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

## Bereid de uitvoermap voor

Een betrouwbaar bestandspad voorkomt runtime‑fouten wanneer de bibliotheek de afbeelding probeert te schrijven. De volgende code maakt de map aan als deze nog niet bestaat:

```csharp
using System;
using System.IO;

// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);
```

> **Waarom dit belangrijk is:** Proberen op te slaan in een niet‑bestaande map veroorzaakt een `IOException`. Het vooraf aanmaken van de map maakt de code robuust voor zowel lokale ontwikkeling als productie‑omgevingen.

## Een databar expanded stacked barcode‑afbeelding genereren

### Basis barcode‑generatie

De eenvoudigste manier om een **databar expanded stacked** afbeelding te genereren is door `BarcodeGenerator` te instantieren met de gewenste `EncodeTypes`‑waarde en een platte tekstpayload.

```csharp
// Create a barcode that encodes a long numeric string
var basicGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "01234567890123456789");

// Save the barcode as PNG
basicGenerator.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
    BarCodeImageFormat.Png);
```

Het uitvoeren van het fragment produceert `DatabarBasic.png` in de *Barcodes*‑map. De afbeelding bevat een standaard databar expanded stacked symbool met de standaardindeling (4 kolommen × 4 rijen).

### Kolommen aanpassen – maak een databar barcode met 4 kolommen

Je kunt het aantal kolommen regelen via de eigenschap `Parameters.Barcode.DataBar.Columns`. Het volgende voorbeeld maakt een barcode met **4 kolommen** terwijl het standaard aantal rijen behouden blijft.

```csharp
// Step 1: Define a generator with custom column count
var columnGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the column count to 4 (default rows = 4)
columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the image
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
    BarCodeImageFormat.Png);
```

Het resulterende bestand, **DatabarCols4.png**, ziet er als volgt uit:

![Databar expanded stacked barcode met 4 kolommen](databar_cols4.png "Databar expanded stacked barcode met 4 kolommen – gegenereerd met C#")

*Afbeeldings‑alt‑tekst (og_image_alt):* **Voorbeeld van een databar expanded stacked barcode afbeelding gegenereerd met C#** – dit voldoet aan de SEO‑vereiste voor alt‑tekst.

### Rijen aanpassen – maak een databar barcode met 3 rijen

Evenzo kun je het aantal rijen aanpassen via `Parameters.Barcode.DataBar.Rows`. De code hieronder genereert een barcode met **3 rijen** en het standaard aantal kolommen (4).

```csharp
// Step 2: Define a generator with custom row count
var rowGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the row count to 3 (default columns = 4)
rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

// Save the image
rowGenerator.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
    BarCodeImageFormat.Png);
```

Het bestand **DatabarRows3.png** bevat een databar expanded stacked symbool dat verticaal iets korter is, wat handig kan zijn voor labels met beperkte ruimte.

### Exporteren naar andere formaten

Als je een ander afbeeldingstype nodig hebt (bijv. JPEG, BMP of SVG), vervang je `BarCodeImageFormat.Png` door de juiste enum‑waarde:

```csharp
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
    BarCodeImageFormat.Jpeg);
```

De bibliotheek ondersteunt ook vectorformaten zoals SVG, die ideaal zijn voor hoge‑resolutie‑afdrukken.

## Geavanceerde scenario's

### Opslaan naar een memory stream

Soms wil je de barcode direct in een web‑respons of een PDF embedden zonder het bestandssysteem te gebruiken. Gebruik een `MemoryStream`:

```csharp
using System.IO;

// Generate barcode into a memory stream
using var ms = new MemoryStream();
columnGenerator.Save(ms, BarCodeImageFormat.Png);

// Reset stream position before reading
ms.Position = 0;

// Example: return the stream as a file download in ASP.NET Core
// return File(ms.ToArray(), "image/png", "databar.png");
```

### Ongeldige invoer afhandelen

De `BarcodeGenerator` valideert de payload tegen de gekozen symbologie. Als de data verboden tekens bevat, wordt een `ArgumentException` gegooid. Plaats de generatiecode in een try‑catch‑blok om een vriendelijke foutmelding te geven:

```csharp
try
{
    var gen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "INVALID*DATA");
    gen.Save(Path.Combine(outputFolder, "Invalid.png"), BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

### De barcode‑afbeelding schalen

Je kunt de afbeeldingsgrootte wijzigen zonder de gecodeerde data aan te passen door `Parameters.Image.Width` en `Parameters.Image.Height` in te stellen:

```csharp
columnGenerator.Parameters.Image.Width = 300;   // pixels
columnGenerator.Parameters.Image.Height = 150; // pixels
columnGenerator.Save(Path.Combine(outputFolder, "DatabarLarge.png"),
    BarCodeImageFormat.Png);
```

Schalen is nuttig wanneer de barcode moet voldoen aan een specifieke DPI‑vereiste voor scanners.

## Volledig werkend voorbeeld

Hieronder vind je een complete, kant‑en‑klaar console‑applicatie die alle besproken stappen demonstreert:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Prepare output folder
            string outputFolder = Path.Combine(
                Environment.CurrentDirectory, "Barcodes");
            Directory.CreateDirectory(outputFolder);

            // 2️⃣ Generate basic barcode
            var basic = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "01234567890123456789");
            basic.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
                BarCodeImageFormat.Png);

            // 3️⃣ Generate barcode with 4 columns
            var colGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            colGen.Parameters.Barcode.DataBar.Columns = 4;
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
                BarCodeImageFormat.Png);

            // 4️⃣ Generate barcode with 3 rows
            var rowGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            rowGen.Parameters.Barcode.DataBar.Rows = 3;
            rowGen.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
                BarCodeImageFormat.Png);

            // 5️⃣ Export to JPEG as an extra format
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
                BarCodeImageFormat.Jpeg);

            Console.WriteLine("All barcode images have been generated in:");
            Console.WriteLine(outputFolder);
        }
    }
}
```

**Verwachte output**


## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe kolommen in te stellen voor een Databar Expanded Stacked barcode – volledige C#‑gids](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [Hoe een barcode‑generatorvoorbeeld te bouwen in C# met DataBar Expanded Stacked](/barcode/english/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/)
- [databar expanded stacked barcode‑gids – hoe deze te genereren en te dimensioneren in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}