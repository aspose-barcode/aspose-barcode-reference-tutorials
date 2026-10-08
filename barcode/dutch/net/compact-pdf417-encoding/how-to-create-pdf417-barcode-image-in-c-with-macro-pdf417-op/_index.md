---
category: general
date: 2026-09-13
description: Leer hoe je een PDF417‑barcodeafbeelding maakt in C# met BarcodeGenerator
  en Macro PDF417‑opties. Stapsgewijze code, tips en volledig voorbeeld.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode image
- macro PDF417 options
- BarcodeGenerator class
- C# barcode generation
- barcode image format
language: nl
lastmod: 2026-09-13
og_description: Maak een PDF417‑barcode‑afbeelding in C# met BarcodeGenerator. Volg
  deze gedetailleerde tutorial om de Macro PDF417‑opties te configureren en een PNG‑barcode
  op te slaan.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Maak PDF417-barcode afbeelding in C# – volledige gids
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  headline: How to create PDF417 barcode image in C# with Macro PDF417 options
  type: TechArticle
- description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  name: How to create PDF417 barcode image in C# with Macro PDF417 options
  steps:
  - name: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
    text: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
  - name: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
    text: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
  - name: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
    text: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
  - name: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
    text: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
  - name: Create a new .NET 6 (or later) console project.
    text: Create a new .NET 6 (or later) console project.
  - name: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
    text: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
  - name: Replace the generated `Program.cs` with the code above.
    text: Replace the generated `Program.cs` with the code above.
  - name: Adjust `outputPath` to a folder you have write access to.
    text: Adjust `outputPath` to a folder you have write access to.
  - name: Build and run – the console will confirm the image location.
    text: Build and run – the console will confirm the image location.
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: Hoe maak je een PDF417‑barcodeafbeelding in C# met Macro PDF417‑opties
url: /nl/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417-barcodeafbeelding te maken in C# met Macro PDF417-opties

Als je een **PDF417 barcode afbeelding** moet maken in C#, laat deze gids je precies zien hoe je dat doet met behulp van de **BarcodeGenerator class**. Of je nu een document‑volgsysteem bouwt of grote bestanden codeert, de stap‑voor‑stap instructies hieronder behandelen alles, van het instellen van Macro PDF417‑opties tot het opslaan van de uiteindelijke PNG.

Het genereren van een barcode is eenvoudig zodra je de belangrijkste parameters begrijpt. In deze tutorial leer je hoe je:

* Een `BarcodeGenerator` initialiseert voor **Macro PDF417**.
* De barcode-modulgrootte (`XDimension`) aanpast.
* Segment‑specifieke instellingen configureert, zoals bestands‑ID, segment‑ID en checksum.
* Het resultaat opslaat als een **barcode‑afbeeldingsformaat** (PNG) dat in elke UI kan worden weergegeven.

Het enige vereiste is een .NET‑ontwikkelomgeving (Visual Studio 2022 of later) en het Aspose.BarCode for .NET NuGet‑pakket, dat de `BarcodeGenerator`‑API levert die in de voorbeelden wordt gebruikt.

---

## Hoe PDF417 barcode afbeelding te maken in C# – overzicht

Het maken van een PDF417 barcode afbeelding bestaat uit vier logische stappen:

1. **Maak de generator** – instantiate `BarcodeGenerator` met `EncodeTypes.MacroPdf417` en de gegevens die je wilt coderen.  
2. **Definieer de modulegrootte** – stel `XDimension.Pixels` in om de fysieke breedte van elk barcode‑element te regelen.  
3. **Configureer Macro PDF417‑opties** – specificeer kolommen, bestands‑identifiers, segment‑nummers en optionele checksum.  
4. **Sla de barcode op** – schrijf de gegenereerde afbeelding naar schijf met een ondersteund **barcode‑afbeeldingsformaat** zoals PNG.

Elke stap wordt hieronder in detail uitgelegd, met volledige, uitvoerbare C#‑code.

---

## Stap 1: Initialiseert de BarcodeGenerator voor Macro PDF417

De eerste regel maakt een `BarcodeGenerator`‑object dat weet dat het een **Macro PDF417** barcode moet produceren. De constructor neemt twee argumenten: het coderings‑type en de ruwe gegevens‑string.

```csharp
using Aspose.BarCode.Generation;   // NuGet: Aspose.BarCode
using System.Drawing.Imaging;      // For ImageFormat if you prefer System.Drawing

// Step 1 – create a barcode generator for Macro PDF417
using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
{
    // Subsequent configuration goes here
}
```

**Waarom dit belangrijk is:**  
`EncodeTypes.MacroPdf417` vertelt de bibliotheek om de barcode te behandelen als een multi‑segment container, wat essentieel is wanneer je een groot bestand in meerdere symbolen moet opsplitsen. De `BarcodeGenerator`‑instantie is disposable, dus het `using`‑blok garandeert dat alle unmanaged resources worden vrijgegeven nadat de afbeelding is opgeslagen.

---

## Stap 2: Stel de barcode-modulgrootte in (XDimension)

`XDimension` regelt de pixelbreedte van een enkele barcode‑module (de kleinste zwarte of witte balk). Een waarde van **2 pixels** levert een compacte maar leesbare afbeelding op.

```csharp
    // Step 2 – define the size of each barcode module (pixel width)
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Praktische tip:**  
Als je doelprinter een lage DPI heeft, verhoog dan het aantal pixels (bijv. `3` of `4`) om vegen te voorkomen. Omgekeerd kun je voor weergave op het scherm de waarde laag houden om de bestandsgrootte te verkleinen.

---

## Stap 3: Configureer Macro PDF417‑specifieke opties

Macro PDF417 voegt metadata toe die een scanner in staat stelt het oorspronkelijke bestand te reconstrueren uit meerdere barcode‑segmenten. De meest voorkomende opties zijn:

| Eigenschap | Betekenis |
|------------|----------|
| `Columns` | Aantal kolommen in elk symbool (beïnvloedt de breedte). |
| `MacroPdf417FileID` | Unieke identifier voor het volledige bestand. |
| `MacroPdf417SegmentID` | Index van het huidige segment (begint bij 1). |
| `MacroPdf417SegmentsCount` | Totaal aantal segmenten waaruit het bestand bestaat. |
| `MacroPdf417FileName` | Originele bestandsnaam (optioneel, voor weergave). |
| `MacroPdf417Checksum` | Optionele 16‑bit checksum voor integriteitsverificatie. |

```csharp
    // Step 3 – configure Macro PDF417 specific options
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns in the symbol
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf"; // Original file name
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;    // Optional checksum
```

**Waarom deze instellingen belangrijk zijn:**  
- **Columns** beïnvloeden de leesbaarheid en de totale afbeeldingsafmetingen.  
- **FileID** moet in alle segmenten gelijk zijn zodat de decoder weet dat ze bij elkaar horen.  
- **SegmentID** en **SegmentsCount** laten de scanner de stukken correct ordenen.  
- **FileName** en **Checksum** zijn optioneel maar verbeteren de gebruikerservaring en de gegevensintegriteit.

**Randgeval:** Als je meer dan 999 segmenten genereert, overflowt het `SegmentID`‑veld; splits de gegevens in plaats daarvan in meerdere bestanden.

---

## Stap 4: Sla de gegenereerde barcode op als een PNG‑afbeelding

De laatste stap schrijft de barcode naar schijf. `BarCodeImageFormat.Png` produceert een verliesvrije afbeelding die werkt op web-, desktop- en mobiele platformen.

```csharp
    // Step 4 – save the generated barcode as a PNG image
    barcodeGenerator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

**Alternatieve formaten:**  
Je kunt `BarCodeImageFormat.Png` vervangen door `Jpeg`, `Bmp` of `Gif` als je downstream‑systeem een specifiek formaat vereist. Houd er rekening mee dat JPEG compressie‑artefacten introduceert die de scan‑betrouwbaarheid kunnen verminderen.

**Verwachte output:**  
Het bestand `MacroPdf417.png` zal een hoog‑contrast, multi‑segment PDF417 barcode bevatten. Bij openen zou het er vergelijkbaar uit moeten zien als de illustratie hieronder.

![Voorbeeld van PDF417 barcode afbeelding](image.png){: .align-center alt="Voorbeeld van PDF417 barcode afbeelding gegenereerd door C# code"}

---

## Volledige broncode – klaar om te kopiëren en uit te voeren

Hieronder staat het volledige, zelfstandige programma. Het bevat de benodigde `using`‑directieven, de `Main`‑methode en commentaren die elke niet‑voor de hand liggende regel uitleggen.

```csharp
using System;
using Aspose.BarCode.Generation;   // Install-Package Aspose.BarCode
// No other external dependencies are required.

namespace Pdf417BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – can be any UTF‑8 string up to 1,800 characters.
            const string dataToEncode = "Sample data";

            // Output directory – change this to a valid path on your machine.
            const string outputPath = @"C:\Barcodes\MacroPdf417.png";

            // Create a BarcodeGenerator for Macro PDF417.
            using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, dataToEncode))
            {
                // 1️⃣ Define module size (pixel width of each bar).
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // 2️⃣ Configure Macro PDF417 options.
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;

                // 3️⃣ Save the barcode as a PNG image.
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            }

            Console.WriteLine($"PDF417 barcode image created at: {outputPath}");
        }
    }
}
```

**Het programma uitvoeren:**  

1. Maak een nieuw .NET 6 (of later) console‑project.  
2. Voeg het Aspose.BarCode NuGet‑pakket toe (`dotnet add package Aspose.BarCode`).  
3. Vervang het gegenereerde `Program.cs` door de bovenstaande code.  
4. Pas `outputPath` aan naar een map waar je schrijfrechten voor hebt.  
5. Build en voer uit – de console bevestigt de locatie van de afbeelding.

---

## Veelgestelde vragen & probleemoplossing

| Vraag | Antwoord |
|-------|----------|
| *Wat als de barcode te breed is voor mijn label?* | Verlaag `Columns` of verhoog `XDimension.Pixels` om breedte en leesbaarheid in balans te brengen. |
| *Moet ik een checksum instellen?* | De checksum is optioneel |

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [PDF417-barcode maken in C# – Complete stap‑voor‑stap gids](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [PDF417-barcode metadata maken in C# – Complete stap‑voor‑stap gids](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [Barcode genereren met tekst – Volledige PDF417 Macro gids](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}