---
category: general
date: 2026-09-22
description: Leer hoe je een PDF417‑barcode maakt in C#, de barcodegrootte instelt
  en barcode‑afbeeldingsbestanden genereert met duidelijke stapsgewijze codevoorbeelden.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to create PDF417
- set barcode size
- create barcode image c#
language: nl
lastmod: 2026-09-22
og_description: Maak snel een PDF417‑barcode in C#. Deze tutorial laat zien hoe je
  de barcodegrootte instelt, compacte modus inschakelt en PNG‑afbeeldingen genereert
  voor elk .NET‑project.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: PDF417-barcode maken in C# – stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to create PDF417 barcode in C#, set barcode size, and generate
    barcode image files with clear step‑by‑step code examples.
  headline: How to create PDF417 barcode and set its size in C#
  type: TechArticle
tags:
- PDF417
- C#
- Barcode
- Imaging
title: Hoe maak je een PDF417-barcode en stel je de grootte in C#
url: /nl/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417‑barcode te maken en de grootte in C# in te stellen

Als je een **PDF417‑barcode** wilt **maken** in C#, laat deze gids je zien hoe je de barcode genereert, de afmetingen regelt en het resultaat opslaat als een afbeeldingsbestand. Of je nu een ticketsysteem, een logistiek label of een beveiligde legitimatie bouwt, het beheersen van het PDF417‑formaat stelt je in staat grote hoeveelheden data compact visueel te coderen.

In deze tutorial leer je:

* **PDF417‑barcode maken** met de Aspose.BarCode (of een compatibele) bibliotheek.  
* **Barcode‑grootte instellen** door de X‑dimensie en het aantal kolommen aan te passen.  
* Een **barcode‑afbeelding genereren in C#** voor PNG, JPEG of BMP.

Het voorbeeld maakt gebruik van de gratis community‑editie van Aspose.BarCode voor .NET, maar dezelfde concepten gelden voor andere bibliotheken die soortgelijke eigenschappen blootleggen.

## Vereisten

Zorg ervoor dat je het volgende hebt:

* .NET 6.0 SDK of later geïnstalleerd.  
* Een C#‑IDE (Visual Studio, Visual Studio Code, Rider, etc.).  
* Het `Aspose.BarCode` NuGet‑pakket (`dotnet add package Aspose.BarCode`).  

Er is geen extra configuratie nodig; de bibliotheek werkt op Windows, Linux en macOS.

## Stap 1: Een basis‑PDF417‑barcode maken en de grootte instellen

De eerste stap is het aanmaken van een `BarcodeGenerator` met de `EncodeTypes.Pdf417`‑enum en de tekst die je wilt coderen. Pas vervolgens de **X‑dimensie** (module‑breedte) en het aantal **kolommen** aan om de totale grootte te regelen.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Define the text that the barcode will represent.
string data = "Sample text for PDF417 barcode";

// Create a basic PDF417 barcode generator.
var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Set the module width to 2 pixels (controls bar thickness).
basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Set the column count; 3 columns yields a compact visual but still readable.
basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image.
string basicPath = Path.Combine("YOUR_DIRECTORY", "Pdf417Basic.png");
basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
```

**Waarom deze instellingen belangrijk zijn**

* `XDimension.Pixels` bepaalt de smalste balkbreedte. Kleinere waarden geven een compactere barcode, terwijl grotere waarden de leesbaarheid op scanners met lage resolutie verbeteren.  
* `Pdf417.Columns` beïnvloedt de beeldverhouding van de barcode. Minder kolommen maken de barcode hoger; meer kolommen maken hem platter. Het aanpassen van kolommen is de primaire manier om de **barcode‑grootte** te bepalen zonder de gecodeerde data te wijzigen.

Na het uitvoeren van de code vind je `Pdf417Basic.png` in de opgegeven map. De afbeelding ziet er ongeveer zo uit als de screenshot hieronder:

<img src="images/pdf417-basic.png" alt="create PDF417 barcode example showing basic barcode layout">

## Stap 2: Een compacte PDF417‑barcode (truncate‑modus) met dezelfde grootte maken

Soms heb je een kortere barcode nodig voor beperkte ruimte. PDF417 biedt een *truncate* (compact) modus die het stop‑patroon verwijdert en de totale hoogte vermindert. De eigenschap `Truncate` schakelt dit gedrag in.

```csharp
// Reuse the same data string.
var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Keep the same module width and column count for a fair size comparison.
compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Enable compact (truncate) mode – this removes the stop pattern.
compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version.
string compactPath = Path.Combine("YOUR_DIRECTORY", "CompactPdf417.png");
compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
```

**Wat verandert er bij `Truncate = true`?**

* De barcode wordt ongeveer 15‑20 % korter in de verticale richting, wat nuttig is voor kleine labels of mobiele schermen.  
* De data blijft volledig herstelbaar; de meeste moderne scanners begrijpen de truncate‑modus automatisch.

De resulterende `CompactPdf417.png` verschijnt als een slankere versie van de basis‑barcode.

## Stap 3: Een Micro PDF417‑barcode maken, kolommen aanpassen en opslaan

Micro PDF417 is een nieuwere, hoge‑dichtheid variant ontworpen voor zeer kleine ruimtes (bijv. ID‑kaarten). Het ondersteunt alleen 1‑4 kolommen, en de bibliotheek biedt dezelfde `XDimension`‑eigenschap voor grootte‑regeling.

```csharp
// Create a Micro PDF417 generator.
var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);

// Set module width – 2 pixels works well for most printers.
microPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Micro PDF417 allows only 1 to 4 columns; choose 4 for a more square shape.
microPdf417.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode.
string microPath = Path.Combine("YOUR_DIRECTORY", "MicroPdf417.png");
microPdf417.Save(microPath, BarCodeImageFormat.Png);
```

**Belangrijke punten voor Micro PDF417**

* De `EncodeTypes.MicroPdf417`‑enum selecteert automatisch de micro‑variant.  
* Omdat het symbool dichter is, heb je mogelijk een printer met hogere DPI (300 dpi of meer) nodig om de barcode leesbaar te houden.  
* Het aanpassen van het aantal kolommen is de enige beschikbare grootte‑knop; de bibliotheek respecteert nog steeds `XDimension`.

## Hoe barcode‑grootte in te stellen voor verschillende uitvoerformaten

De voorbeelden hierboven gebruiken PNG, maar dezelfde `Save`‑methode werkt met JPEG, BMP of TIFF. Als je een specifieke afbeeldingsgrootte nodig hebt (bijv. 300 × 150 px), combineer je `XDimension` met `ResolutionX`/`ResolutionY`:

```csharp
basicPdf417.Parameters.ImageResolution = 300; // DPI
basicPdf417.Parameters.Barcode.XDimension.Pixels = 3; // larger modules for higher DPI
basicPdf417.Save("Pdf417HighRes.jpg", BarCodeImageFormat.Jpeg);
```

Het verhogen van `ImageResolution` terwijl je `XDimension` schaalt, behoudt de visuele kwaliteit bij afdrukken met hoge resolutie.

## Veelvoorkomende valkuilen en pro‑tips

| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| Barcode ziet er wazig uit op het scherm | Lage DPI gecombineerd met kleine `XDimension` | Verhoog `ImageResolution` en/of `XDimension.Pixels` |
| Scanner kan truncate‑modus niet lezen | Oudere scanner‑firmware ondersteunt het niet | Gebruik de volledige (niet‑getruncate) modus voor legacy‑hardware |
| Micro PDF417 is onleesbaar | Afgedrukt onder < 300 dpi of met onvoldoende contrast | Druk af op mat papier met 300 dpi of hoger, zorg voor donkere voorgrond |
| Uitvoerbestand is corrupt | Geen schrijfrechten voor de doelmap | Controleer of `YOUR_DIRECTORY` bestaat en schrijfbaar is |

**Pro‑tip:** Genereer de barcode altijd als PNG wanneer je verliesvrije kwaliteit nodig hebt voor verdere verwerking (bijv. inbedden in PDF’s). PNG behoudt exacte pixelwaarden, terwijl JPEG compressie‑artefacten introduceert die de leesbaarheid van de barcode kunnen beïnvloeden.

## Volledig, uitvoerbaar voorbeeld

Hieronder vind je een complete console‑applicatie die alle drie de barcode‑typen in één run demonstreert. Kopieer de code naar een nieuw .NET‑console‑project en voer het uit.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // The text to encode – change this to whatever data you need.
        const string data = "Sample text for PDF417 barcode";

        // Directory where images will be saved.
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // ---------- Basic PDF417 ----------
        var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        string basicPath = Path.Combine(outputDir, "Pdf417Basic.png");
        basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Basic PDF417 saved to {basicPath}");

        // ---------- Compact (Truncate) PDF417 ----------
        var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;
        string compactPath = Path.Combine(outputDir, "CompactPdf417.png");
        compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Compact PDF417 saved to {compactPath}");

        // ---------- Micro PDF417 ----------
        var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);
        microPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        microPdf417.Parameters.Barcode.Pdf417.Columns = 4; // 1‑4 allowed
        string microPath = Path.Combine(outputDir, "MicroPdf417.png");
        microPdf417.Save(microPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Micro PDF417 saved to {microPath}");
    }
}
```

**Verwachte output**

Het uitvoeren van het programma maakt drie PNG‑bestanden aan in een `Barcodes`‑map:

* `Pdf417Basic.png` – een standaard PDF417‑barcode met drie kolommen.  
* `CompactPdf417.png` – dezelfde data in truncate (compact) modus, iets korter.  
* `MicroPdf417.png` – een hoge‑dichtheid Micro PDF417‑variant met vier kolommen.

Open een van de afbeeldingen met een beeldviewer; je zult de karakteristieke gestapelde structuur zien.


## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids zijn gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Create PDF417 Barcode Metadata in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}