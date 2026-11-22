---
category: general
date: 2026-11-20
description: Leer hoe je een PDF417‑barcode genereert in C# met BarcodeGenerator.
  Deze stapsgewijze gids behandelt X‑dimensie, kolominstellingen en PNG‑export.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- PDF417 barcode in C#
- BarcodeGenerator EncodeTypes
- set XDimension pixels
- configure PDF417 columns
- save barcode as PNG
language: nl
lastmod: 2026-11-20
og_description: Genereer snel een PDF417-barcode in C#. Volg deze gids om de afmetingen,
  kolommen in te stellen en de barcode als PNG-afbeelding te exporteren.
og_image_alt: Screenshot of C# code that generates a PDF417 barcode and saves it as
  a PNG file
og_title: PDF417‑barcode genereren in C# – volledige stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  headline: How to generate PDF417 barcode in C# with BarcodeGenerator
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  name: How to generate PDF417 barcode in C# with BarcodeGenerator
  steps:
  - name: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
    text: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
  - name: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
    text: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
  - name: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
    text: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
  - name: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
    text: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose.BarCode
title: Hoe PDF417-barcode te genereren in C# met BarcodeGenerator
url: /nl/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417‑barcode te genereren in C# met BarcodeGenerator

Als je **PDF417‑barcode** moet **genereren** in een .NET‑applicatie, laat deze gids je precies zien hoe je dat doet. Je ziet een volledig, uitvoerbaar voorbeeld dat de X‑Dimension instelt, het aantal kolommen kiest en het resultaat opslaat als een PNG‑afbeelding.

Het genereren van een PDF417‑barcode is gebruikelijk wanneer je veel gegevens moet coderen — bijvoorbeeld een rijbewijs, boardingpass of voorraadrecord — in een compacte, machinaal leesbare afbeelding. In deze tutorial gebruiken we de **BarcodeGenerator**‑klasse uit de Aspose.BarCode‑bibliotheek, maar de concepten gelden voor elke bibliotheek die PDF417 ondersteunt.

Aan het einde van dit artikel kun je:

* Een `BarcodeGenerator` initialiseren voor PDF417‑codering.  
* De module‑grootte aanpassen met **set XDimension pixels**.  
* De lay‑out regelen met **configure PDF417 columns**.  
* **Barcode opslaan als PNG** voor gebruik op webpagina’s, mobiele apps of gedrukt materiaal.  

> **Prerequisites**  
> * .NET 6.0 of hoger (de code werkt ook met .NET Framework 4.7+).  
> * Een referentie naar het **Aspose.BarCode**‑NuGet‑pakket (`Install-Package Aspose.BarCode`).  
> * Basiskennis van C# en Visual Studio (of een andere IDE naar keuze).

---

## Hoe PDF417‑barcode te genereren in C#

De kern van de oplossing is een kort vier‑stappen‑proces. Elke stap staat in een eigen methode zodat je de logica kunt hergebruiken in grotere projecten.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialize the generator with the desired text
            var generator = CreateGenerator("Åspóse.Barcóde©");

            // 2️⃣ Adjust the X‑Dimension (module size)
            SetXDimension(generator, 2);

            // 3️⃣ Define how many columns the barcode should have
            SetPdf417Columns(generator, 3);

            // 4️⃣ Save the barcode as a PNG file
            SaveAsPng(generator, @"YOUR_DIRECTORY\Pdf417Basic.png");

            Console.WriteLine("PDF417 barcode generated successfully.");
        }

        // ---------------------------------------------------------
        // Step 1: Create a BarcodeGenerator for PDF417
        // ---------------------------------------------------------
        private static BarcodeGenerator CreateGenerator(string text)
        {
            // EncodeTypes.Pdf417 tells the library to use the PDF417 symbology.
            return new BarcodeGenerator(EncodeTypes.Pdf417, text);
        }

        // ---------------------------------------------------------
        // Step 2: Set the X‑Dimension (size of a single module)
        // ---------------------------------------------------------
        private static void SetXDimension(BarcodeGenerator generator, int pixels)
        {
            // XDimension controls the width of the smallest black/white bar.
            // A value of 2 pixels works well for most screen resolutions.
            generator.Parameters.Barcode.XDimension.Pixels = pixels;
        }

        // ---------------------------------------------------------
        // Step 3: Configure the number of columns in the PDF417 barcode
        // ---------------------------------------------------------
        private static void SetPdf417Columns(BarcodeGenerator generator, int columns)
        {
            // Columns affect the barcode’s aspect ratio.
            // Small numbers (e.g., 3) produce a tall barcode; larger numbers make it wider.
            generator.Parameters.Barcode.Pdf417.Columns = columns;
        }

        // ---------------------------------------------------------
        // Step 4: Export the barcode as a PNG image
        // ---------------------------------------------------------
        private static void SaveAsPng(BarcodeGenerator generator, string outputPath)
        {
            // BarCodeImageFormat.Png ensures lossless quality.
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Waarom deze vier stappen belangrijk zijn

1. **Generator initialiseren** – De `BarcodeGenerator` koppelt de gekozen symbologie (`EncodeTypes.Pdf417`) aan de gegevens die je wilt coderen. Zonder dit object kun je geen verdere configuratie uitvoeren.  
2. **X‑Dimension instellen** – PDF417 bestaat uit kleine rechthoekige modules. Door `XDimension.Pixels` te wijzigen, bepaal je de visuele dichtheid van de barcode, wat cruciaal is voor leesbaarheid op lage‑resolutie‑schermen of printers.  
3. **Kolommen configureren** – PDF417 kan zijn codewoorden in een variabel aantal kolommen rangschikken. Minder kolommen geven een hogere barcode, meer kolommen maken deze platter. Pas dit aan op de ruimte waar de afbeelding komt te staan.  
4. **Opslaan als PNG** – PNG is een verliesvrij formaat, waardoor de scherpe randen behouden blijven die nodig zijn voor nauwkeurige scanning. Je kunt ook JPEG of BMP kiezen, maar PNG is de veiligste standaard.

---

## Barcode‑dimensies configureren (X‑Dimension)

De stap **set XDimension pixels** beïnvloedt direct hoe scanners de barcode interpreteren. Als de module te klein is, missen lage‑kwaliteit camera’s individuele balken; als hij te groot is, wordt de barcode onnodig groot.

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 2; // 2‑pixel modules
```

**Best practice:** Test de gegenereerde afbeelding op de beoogde afdrukgrootte. Voor hoge‑dichtheid‑printen (300 dpi of meer) werkt een waarde van `1` of `2` goed. Voor weergave op schermen met 96 dpi geeft `2`–`3` een duidelijk beeld.

---

## PDF417‑kolommen instellen

De stap **configure PDF417 columns** laat je de vorm van de barcode bepalen.

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 3; // three columns → tall barcode
```

### Wanneer het aantal kolommen aanpassen

| Kolommen | Resulterende vorm | Typisch gebruik |
|----------|-------------------|-----------------|
| 1–3      | Hoog, smal        | Labels met beperkte breedte |
| 4–9      | Gebalanceerd      | Algemeen scannen |
| 10+      | Breed, kort       | Grote borden of web‑graphics |

Als je gegevenspayload de standaardcapaciteit overschrijdt, voegt de bibliotheek automatisch extra rijen toe, maar je kunt nog steeds de beeldverhouding beïnvloeden door het aantal kolommen aan te passen.

---

## Barcode exporteren naar PNG

De barcode opslaan als PNG‑afbeelding is eenvoudig:

```csharp
generator.Save(@"C:\Barcodes\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Waarom PNG?**  
* Lossless‑compressie behoudt de scherpe randen die barcode‑lezers nodig hebben.  
* PNG ondersteunt transparantie, wat handig kan zijn als je de barcode later over een gekleurde achtergrond legt.

Als je een ander formaat nodig hebt, vervang je `BarCodeImageFormat.Png` door `Jpeg`, `Bmp` of `Svg` — de API handelt de conversie automatisch af.

---

## Veelvoorkomende valkuilen en probleemoplossing

| Probleem | Waarschijnlijke oorzaak | Oplossing |
|----------|--------------------------|-----------|
| Barcode is onscherp | X‑Dimension te klein voor de uitvoerresolutie | Verhoog `XDimension.Pixels` naar 3 of 4. |
| Scanner kan de code niet lezen | Unicode‑tekens niet ondersteund door het gekozen lettertype | Zorg dat het lettertype van de bibliotheek de tekens ondersteunt, of vervang ze door ASCII‑equivalenten. |
| Uitvoerbestand niet aangemaakt | Ongeldig pad of ontbrekende schrijfrechten | Gebruik een absoluut pad en controleer schrijfrechten op de map. |
| Te veel rijen, barcode wordt hoog | Kolomtelling te laag voor de gegevenslengte | Verhoog `Pdf417.Columns` naar een hoger getal (bijv. 6). |

---

## Volledig werkend voorbeeld samenvatting

Hieronder staat het **complete programma** dat je kunt kopiëren‑plakken in een nieuw console‑project. Er is geen extra code nodig naast de `using`‑statements en het Aspose.BarCode‑pakket.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
            Console.WriteLine("PDF417 barcode generated and saved as PNG.");
        }
    }
}
```

**Verwacht resultaat:** Een bestand met de naam `Pdf417Basic.png` dat een duidelijke PDF417‑barcode bevat die de string `Åspóse.Barcóde©` codeert. Bij openen toont de afbeelding een reeks gestapelde rechthoekige balken met een hogere dichtheid aan de linkerkant (door de drie‑koloms‑lay‑out).

---

## Conclusie

Je weet nu hoe je **PDF417‑barcode** kunt **genereren** in C# met de `BarcodeGenerator`‑klasse. De tutorial behandelde het initialiseren van de generator, **set XDimension pixels**, **configure PDF417 columns**, en **save barcode as PNG** — de essentiële stappen voor elke productie‑klare barcode‑workflow.

Vanaf hier kun je:

* Experimenteren met verschillende `EncodeTypes` (bijv. QR, Code128).  
* Foutcorrectieniveaus toevoegen via `generator.Parameters.Barcode.Pdf417.ErrorLevel`.  
* De barcode direct renderen naar een `MemoryStream` voor web‑API’s.  

Voel je vrij om de code aan te passen aan je eigen project, en deel je resultaten in de reacties of op Stack Overflow met de tag `#pdf417`. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids zijn gedemonstreerd. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Generate PDF417 barcode as PNG in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-as-png-in-c-step-by-step-guide/)
- [How to generate PDF417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}