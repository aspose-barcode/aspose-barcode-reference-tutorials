---
category: general
date: 2026-08-12
description: Maak snel een barcode‑PNG in C# met Aspose.BarCode. Leer hoe je een PDF417‑barcode
  in C# genereert en beheers het gebruik van de barcodegenerator in één tutorial.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode PNG
- generate PDF417 barcode C#
- barcode generator usage
- GS1 Micro PDF417 example
- Aspose.BarCode C#
language: nl
lastmod: 2026-08-12
og_description: Maak barcode PNG in C# met Aspose.BarCode. Deze tutorial laat zien
  hoe je een PDF417-barcode in C# genereert en de barcodegenerator effectief gebruikt.
og_image_alt: create barcode PNG example showing a GS1 Micro PDF417 code
og_title: Barcode PNG maken in C# – stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode PNG in C# quickly with Aspose.BarCode. Learn how to
    generate PDF417 barcode C# and master barcode generator usage in a single tutorial.
  headline: Create barcode PNG in C# – full guide to GS1 Micro PDF417
  type: TechArticle
- description: Create barcode PNG in C# quickly with Aspose.BarCode. Learn how to
    generate PDF417 barcode C# and master barcode generator usage in a single tutorial.
  name: Create barcode PNG in C# – full guide to GS1 Micro PDF417
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `EncodeTypes.Gs1MicroPdf417` | Selects
      the specific PDF417 variant required for GS1 applications. | | Data string `"(01)12345678901231(10)ABC123"`
      | Demonstrates the GS1 AI syntax for a GTIN (01) and a lot number (10). | |
      `XDimension.Pixels = 2` | Controls the '
  - name: Expected visual result
    text: The PNG contains a rectangular barcode with evenly spaced black modules.
      Scanning it with a GS1‑compatible scanner returns the string `(01)12345678901231(10)ABC123`,
      confirming that **generate PDF417 barcode C#** succeeded.
  - name: Changing the symbology
    text: 'If you need a regular PDF417 instead of the micro version, replace the
      encode type:'
  - name: Adjusting image format
    text: 'Aspose.BarCode supports many formats. To create a JPEG instead:'
  - name: Saving to a stream (useful for web APIs)
    text: '```csharp using (var ms = new MemoryStream()) { generator.Save(ms, BarCodeImageFormat.Png);
      // ms.ToArray() now contains the PNG bytes – return them from an API endpoint.
      } ```'
  - name: What’s next?
    text: '* Explore **barcode reader integration** to verify generated images automatically.
      * Experiment with **custom colors** and **logo embedding** for brand‑aware barcodes.
      * Review the Aspose.BarCode documentation for advanced error‑correction settings
      and multi‑page PDF417 generation.'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Maak barcode PNG in C# – volledige gids voor GS1 Micro PDF417
url: /nl/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode PNG maken in C# – volledige gids voor GS1 Micro PDF417

Als je een **barcode PNG** moet maken in een .NET‑applicatie, laat deze gids je precies zien hoe je dat doet. Je leert een PDF417‑barcode genereren in C# en ziet de **barcode generator usage**‑patronen die in productie werken.

Het genereren van een barcode‑afbeelding is een veelvoorkomende eis voor voorraadsystemen, verzendetiketten en ticketplatformen. Aan het einde van deze tutorial heb je een zelfstandige console‑programma dat een PNG‑bestand schrijft met een GS1 Micro PDF417‑barcode, klaar voor verdere verwerking.

## Vereisten

* .NET 6.0 SDK of later geïnstalleerd (de code werkt ook met .NET Framework 4.7.2+).
* Een recente versie van het **Aspose.BarCode for .NET** NuGet‑pakket. Installeer het met  
  `dotnet add package Aspose.BarCode`.
* Basiskennis van C#‑consoleprojecten.
* Schrijfrechten voor een map waar de PNG wordt opgeslagen.

Deze vereisten houden het voorbeeld lichtgewicht terwijl ze een real‑world‑opstelling weerspiegelen.

## Stap 1: Het C#‑project opzetten

Maak een nieuw console‑project aan en voeg de Aspose.BarCode‑referentie toe:

```bash
dotnet new console -n BarcodePngDemo
cd BarcodePngDemo
dotnet add package Aspose.BarCode
```

De `dotnet`‑CLI maakt een `Program.cs`‑bestand aan en herstelt het NuGet‑pakket. Deze stap is essentieel voor **barcode generator usage** omdat de bibliotheek de `BarcodeGenerator`‑klasse bevat die we gaan gebruiken.

## Stap 2: Schrijf de volledige barcode‑generatiecode

Vervang de inhoud van `Program.cs` door de volgende code. Het bevat elke regel die je nodig hebt om **barcode PNG** te maken van begin tot eind.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -------------------------------------------------
            // 1️⃣ Create a BarcodeGenerator for GS1 Micro PDF417
            // -------------------------------------------------
            // EncodeTypes.Gs1MicroPdf417 tells Aspose.BarCode to use the
            // GS1 Micro PDF417 symbology. The data string follows the
            // Application Identifier (AI) format required by GS1.
            var generator = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(10)ABC123");

            // -------------------------------------------------
            // 2️⃣ Adjust the X‑dimension (module width)
            // -------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // Lower values produce a smaller image; higher values increase
            // readability on low‑resolution scanners.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // -------------------------------------------------
            // 3️⃣ (Optional) Set image resolution and background
            // -------------------------------------------------
            // Higher DPI yields a sharper PNG, useful when the image
            // will be printed. BackgroundColor can be set to Transparent.
            generator.Parameters.ImageResolution = 300;      // DPI
            generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent;

            // -------------------------------------------------
            // 4️⃣ Save the barcode as a PNG file
            // -------------------------------------------------
            // The Save method writes the image to disk. You can also
            // choose other formats such as Jpeg, Bmp, or Gif.
            string outputPath = "output.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode PNG created at: {outputPath}");
        }
    }
}
```

### Waarom elke regel belangrijk is

| Regel | Reden |
|------|--------|
| `EncodeTypes.Gs1MicroPdf417` | Selecteert de specifieke PDF417‑variant die nodig is voor GS1‑toepassingen. |
| Data‑string `"(01)12345678901231(10)ABC123"` | Demonstreert de GS1‑AI‑syntaxis voor een GTIN (01) en een lotnummer (10). |
| `XDimension.Pixels = 2` | Regelt de fysieke grootte van de barcode; een veelvoorkomende standaard voor schermweergave. |
| `ImageResolution = 300` | Verhoogt de DPI, waardoor de PNG er scherp uitziet bij afdrukken. |
| `BackgroundColor = Transparent` | Maakt de PNG geschikt voor overlay in UI‑composities. |
| `Save(..., BarCodeImageFormat.Png)` | Slaat de barcode op als PNG, wat voldoet aan het **create barcode PNG**‑doel. |

## Stap 3: Voer het programma uit en controleer de output

Voer de console‑app uit:

```bash
dotnet run
```

Je zou het bevestigingsbericht moeten zien en `output.png` in de projectmap vinden. Het openen van het bestand toont een GS1 Micro PDF417‑barcode die de voorbeeldgegevens codeert.

![voorbeeld van barcode PNG maken](barcode-example.png)

*Alt‑tekst: voorbeeld van barcode PNG maken met een GS1 Micro PDF417‑code.*

### Verwacht visueel resultaat

De PNG bevat een rechthoekige barcode met gelijkmatig verdeelde zwarte modules. Het scannen ervan met een GS1‑compatibele scanner retourneert de string `(01)12345678901231(10)ABC123`, wat bevestigt dat **generate PDF417 barcode C#** geslaagd is.

## Stap 4: Verken veelvoorkomende variaties

### De symbologie wijzigen

Als je een reguliere PDF417 in plaats van de micro‑versie nodig hebt, vervang dan het encode‑type:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Your data here");
```

### Het afbeeldingsformaat aanpassen

Aspose.BarCode ondersteunt vele formaten. Om in plaats daarvan een JPEG te maken:

```csharp
generator.Save("output.jpg", BarCodeImageFormat.Jpeg);
```

### Opslaan naar een stream (handig voor web‑API's)

```csharp
using (var ms = new MemoryStream())
{
    generator.Save(ms, BarCodeImageFormat.Png);
    // ms.ToArray() now contains the PNG bytes – return them from an API endpoint.
}
```

Deze fragmenten illustreren flexibel **barcode generator usage** buiten het basis‑bestand‑opslaan scenario.

## Pro‑tips en valkuilen

* **Validate data length** – GS1 Micro PDF417 heeft een maximale gegevenscapaciteit; overschrijding veroorzaakt een uitzondering. Gebruik `generator.Parameters.Barcode.IsValidData(data)` om vooraf te controleren.
* **Avoid tiny XDimension values** – waarden onder 1 pixel kunnen onleesbare barcodes opleveren op apparaten met lage resolutie.
* **Set `QuietZone`** als je de PNG in een grotere afbeelding embedt; de standaard quiet zone zorgt ervoor dat scanners de start/stop‑patronen kunnen vinden.
* **Thread safety** – `BarcodeGenerator`‑instanties zijn niet thread‑safe. Maak per verzoek een nieuwe generator aan in een webservice.

## Conclusie

Je weet nu hoe je **barcode PNG**‑bestanden in C# kunt maken met Aspose.BarCode, hoe je **generate PDF417 barcode C#** kunt uitvoeren met de GS1 Micro‑variant, en de essentiële patronen voor effectieve **barcode generator usage**. Het volledige, uitvoerbare voorbeeld kan in elk .NET‑project worden geplaatst, en je kunt het uitbreiden met verschillende symbologieën, afbeeldingsformaten of streaming‑outputs.

### Wat volgt?

* Verken **barcode reader integration** om gegenereerde afbeeldingen automatisch te verifiëren.  
* Experimenteer met **custom colors** en **logo embedding** voor merk‑bewuste barcodes.  
* Bekijk de Aspose.BarCode‑documentatie voor geavanceerde fout‑correctie‑instellingen en multi‑page PDF417‑generatie.

Veel programmeerplezier, en laat je applicaties de taal van machines spreken met scherpe, betrouwbare barcode PNG‑bestanden!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe barcode maken – Compact PDF417 met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hoe PNG opslaan met DataMatrix C40 met Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [Hoe barcode genereren – Code 39 configuratie met Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}