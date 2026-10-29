---
category: general
date: 2026-10-28
description: Hoe een barcode met aangepaste tekst te genereren met Aspose.BarCode
  – stapsgewijze gids voor .NET‑ontwikkelaars om barcode‑Afbeeldingen van Aspose te
  maken.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- generate barcode custom text
- create barcode aspose
language: nl
lastmod: 2026-10-28
og_description: Hoe genereer je een barcode met aangepaste tekst in .NET met Aspose.BarCode.
  Volg deze volledige gids om een Macro PDF417‑barcode te maken en op te slaan.
og_image_alt: how to generate barcode example PNG image showing a Macro PDF417 barcode
og_title: Hoe een barcode met aangepaste tekst te genereren – Aspose.BarCode‑tutorial
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  headline: How to generate barcode with custom text using Aspose.BarCode for .NET
  type: TechArticle
- description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  name: How to generate barcode with custom text using Aspose.BarCode for .NET
  steps:
  - name: Why each line matters
    text: '* **EncodeTypes.MacroPdf417** – selects the Macro PDF417 symbology, which
      supports segmented data and metadata. * **XDimension.Pixels** – controls the
      size of each module; a value of 2 pixels yields a clear, scannable image. *
      **Pdf417.Columns** – reduces the overall width, making the barcode more c'
  - name: Using a different barcode type
    text: If you need to **generate barcode custom text** for a QR code instead of
      Macro PDF417, replace `EncodeTypes.MacroPdf417` with `EncodeTypes.QR`. The rest
      of the parameter structure stays the same, but QR codes do not support Macro
      metadata fields.
  - name: Handling Unicode characters
    text: The example already includes Unicode characters (`Å`, `ó`, `©`). Aspose.BarCode
      handles UTF‑8 input out of the box, but you should ensure the source file is
      saved with UTF‑8 encoding to avoid compile‑time warnings.
  - name: Saving to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG in addition to PNG. Change
      the `BarCodeImageFormat` enum value accordingly:'
  - name: Large data sets
    text: Macro PDF417 can split data across multiple segments. When the text exceeds
      the capacity of a single segment, increment `MacroPdf417SegmentID` and keep
      `MacroPdf417SegmentsCount` consistent across all generated parts. This approach
      is essential for **create barcode aspose** scenarios where the paylo
  - name: Error handling
    text: 'Wrap the generation logic in a try‑catch block to surface runtime issues
      such as invalid file paths or unsupported characters:'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- .NET
title: Hoe een barcode met aangepaste tekst genereren met Aspose.BarCode voor .NET
url: /nl/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een barcode met aangepaste tekst te genereren met Aspose.BarCode voor .NET

Hoe een barcode met aangepaste tekst te genereren is een veelvoorkomende eis wanneer je identifiers, tijdstempels of andere metadata direct in een visuele code wilt opnemen. Deze tutorial laat zien hoe je een Macro PDF417‑barcode maakt die aangepaste tekst en een volledige set metadata bevat, met behulp van de **Aspose.BarCode**‑bibliotheek voor .NET.

Je leert hoe je de generator configureert, aangepaste tekst toepast, Macro PDF417‑specifieke velden instelt en het resultaat opslaat als een PNG‑afbeelding. Er zijn geen externe tools nodig—alleen het Aspose.BarCode‑NuGet‑pakket en een .NET‑ontwikkelomgeving.

## Vereisten

Zorg ervoor dat je het volgende hebt voordat je begint:

* .NET 6.0 SDK of later geïnstalleerd  
* Visual Studio 2022 (of een andere IDE die .NET ondersteunt)  
* **Aspose.BarCode for .NET** NuGet‑pakket (`Install-Package Aspose.BarCode`)  

Deze vereisten zorgen ervoor dat de code compileert en draait zonder extra configuratie.

## Stap 1: Installeer het Aspose.BarCode‑pakket

Open een terminal in je projectmap en voer uit:

```bash
dotnet add package Aspose.BarCode
```

Het commando voegt de nieuwste stabiele versie van Aspose.BarCode toe aan je project, zodat je toegang krijgt tot de `BarcodeGenerator`‑klasse en alle gerelateerde parameters.

## Stap 2: Maak een nieuwe console‑applicatie

Maak een minimale console‑app die de barcode‑generatielogica host:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The full barcode generation flow is encapsulated in a separate method
            GenerateMacroPdf417Barcode();
        }

        /// <summary>
        /// Generates a Macro PDF417 barcode with custom text and metadata, then saves it as PNG.
        /// </summary>
        private static void GenerateMacroPdf417Barcode()
        {
            // Step 1: Instantiate the generator with the desired encode type and data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the visual appearance of the barcode
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // Size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;            // Number of columns in the symbol

                // Step 3: Populate Macro PDF417 specific metadata fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example value
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the barcode image to disk
                string outputPath = @"ExtPDF417Meta.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

### Waarom elke regel belangrijk is

* **EncodeTypes.MacroPdf417** – selecteert de Macro PDF417‑symbologie, die gesegmenteerde data en metadata ondersteunt.  
* **XDimension.Pixels** – bepaalt de grootte van elk module; een waarde van 2 pixels levert een duidelijke, scanbare afbeelding op.  
* **Pdf417.Columns** – verkleint de totale breedte, waardoor de barcode compacter wordt voor afgedrukte labels.  
* **MacroPdf417*‑eigenschappen** – embedden bestands‑niveau informatie (ID, segment‑aantal, tijdstempels, enz.) direct in de barcode. Deze mogelijkheid is uniek voor Macro PDF417 en wordt vaak gebruikt in logistiek of documentbeheersystemen.  
* **Save(..., BarCodeImageFormat.Png)** – schrijft een lossless PNG‑bestand, waardoor de scherpe randen van de barcode behouden blijven voor betrouwbare scanning.

## Stap 3: Voer het programma uit en controleer de output

Bouw en voer de console‑app uit:

```bash
dotnet run
```

Het programma maakt `ExtPDF417Meta.png` aan in de werkmap van het project. Het openen van het bestand toont een Macro PDF417‑barcode die de tekst **“Åspóse.Barcóde©”** codeert samen met de metadata die je hebt opgegeven.

**Verwachte output** – een PNG‑afbeelding vergelijkbaar met de onderstaande:

![voorbeeldoutput PNG‑afbeelding van hoe een barcode te genereren, toont een Macro PDF417 barcode](ExtPDF417Meta.png)

*De alt‑tekst van de afbeelding (“voorbeeldoutput PNG‑afbeelding van hoe een barcode te genereren”) versterkt het primaire zoekwoord voor toegankelijkheid en SEO.*

## Veelvoorkomende variaties en randgevallen

### Een ander barcode‑type gebruiken

Als je **barcode met aangepaste tekst** wilt genereren voor een QR‑code in plaats van Macro PDF417, vervang je `EncodeTypes.MacroPdf417` door `EncodeTypes.QR`. De rest van de parameterstructuur blijft gelijk, maar QR‑codes ondersteunen geen Macro‑metadata‑velden.

### Unicode‑tekens verwerken

Het voorbeeld bevat al Unicode‑tekens (`Å`, `ó`, `©`). Aspose.BarCode verwerkt UTF‑8‑invoer out‑of‑the‑box, maar zorg ervoor dat het bronbestand is opgeslagen met UTF‑8‑codering om compile‑time waarschuwingen te voorkomen.

### Opslaan in andere afbeeldingsformaten

Aspose.BarCode ondersteunt BMP, JPEG, TIFF en SVG naast PNG. Pas de `BarCodeImageFormat`‑enumwaarde dienovereenkomstig aan:

```csharp
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

### Grote datasets

Macro PDF417 kan data over meerdere segmenten verdelen. Wanneer de tekst de capaciteit van één segment overschrijdt, verhoog je `MacroPdf417SegmentID` en houd je `MacroPdf417SegmentsCount` consistent over alle gegenereerde delen. Deze aanpak is essentieel voor **create barcode aspose**‑scenario's waarbij de payload groter is dan één barcode kan bevatten.

### Foutafhandeling

Omloop de generatielogica met een try‑catch‑blok om runtime‑problemen zoals ongeldige bestands‑paden of niet‑ondersteunde tekens zichtbaar te maken:

```csharp
try
{
    GenerateMacroPdf417Barcode();
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Barcode generation failed: {ex.Message}");
}
```

## Pro‑tips voor betrouwbare barcode‑generatie

* **Valideer de barcode** na creatie met `BarCodeReader`. Deze extra stap bevestigt dat de gecodeerde data overeenkomt met je verwachtingen.

  ```csharp
  using (BarCodeReader reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
  {
      if (reader.Read())
          Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
  }
  ```

* **Houd de X‑dimensie tussen 2 – 4 pixels** voor de meeste scanners. Lagere waarden kunnen onleesbare afbeeldingen opleveren op apparaten met lage resolutie.

* **Vermijd zeer lange bestandsnamen** in `MacroPdf417FileName`. De specificatie beperkt dit veld tot 32 tekens.

* **Gebruik consistente tijdstempels** (UTC) bij het genereren van meerdere segmenten om downstream‑verwerking te vereenvoudigen.

## Conclusie

Je weet nu **hoe je een barcode met aangepaste tekst** kunt genereren met Aspose.BarCode voor .NET, hoe je Macro PDF417‑metadata configureert en hoe je het resultaat opslaat als een PNG‑afbeelding. Het volledige, uitvoerbare voorbeeld toont elke vereiste stap—van het installeren van het NuGet‑pakket tot het verwerken van Unicode‑tekens en het opslaan van de output.

Vanaf hier kun je:

* **Barcode met aangepaste tekst** genereren voor andere symbologieën (QR, DataMatrix, enz.)  
* **Barcode Aspose**‑workflows opzetten die duizenden afbeeldingen batch‑verwerken  
* De barcode‑generatiecode integreren in ASP.NET Core‑services, Windows‑services of Azure Functions  

Experimenteer met verschillende parameters, verken extra metadata‑velden en integreer de barcode in je document‑automatiseringspijplijnen. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe een PDF417‑barcode te maken met Aspose – Complete stap‑voor‑stap‑gids](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Barcode genereren vanuit tekst met Aspose.BarCode – C#‑gids](/barcode/english/net/one-dimensional-barcode-types/generate-barcode-from-text-using-aspose-barcode-c-guide/)
- [Hoe Aspose.BarCode te gebruiken om DataMatrix‑code‑tekst te maken in .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}