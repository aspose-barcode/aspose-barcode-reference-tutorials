---
category: general
date: 2026-10-21
description: Genereer pdf417‑barcode snel in C#. Leer hoe je een pdf417‑barcode kunt
  genereren met aangepaste lay‑out, kolommen, rijen en PNG‑output.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- pdf417 barcode layout
- barcode generator C#
- save barcode as PNG
language: nl
lastmod: 2026-10-21
og_description: Genereer pdf417-barcode in C#. Volg deze tutorial om te leren hoe
  je een pdf417-barcode kunt genereren met aangepaste kolommen, rijen en PNG-uitvoer.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: Genereer pdf417‑barcode in C# – volledige stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  headline: Generate pdf417 barcode in C# with custom columns and rows
  type: TechArticle
- description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  name: Generate pdf417 barcode in C# with custom columns and rows
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
    text: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
  - name: Confirm that the decoded text matches the original input.
    text: Confirm that the decoded text matches the original input.
  type: HowTo
tags:
- barcode
- pdf417
- C#
- image generation
title: Genereer pdf417-barcode in C# met aangepaste kolommen en rijen
url: /nl/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-with-custom-columns-and-rows/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Genereer pdf417 barcode in C# – volledige programmeergids

Als je een **pdf417 barcode genereren** moet in een .NET‑applicatie, laat deze gids je zien hoe je dat doet met een paar regels code. Je ziet een praktisch voorbeeld dat het aantal kolommen en rijen configureert, en vervolgens het resultaat opslaat als een PNG‑afbeelding. Dezelfde aanpak werkt voor elke tekst die je wilt coderen, zodat je het kunt aanpassen voor facturen, tickets of ID‑kaarten.

Het genereren van een **pdf417 barcode** voelt vaak als een aparte taak ten opzichte van de rest van je codebase. Aan het einde van deze tutorial begrijp je waarom lay‑outparameters belangrijk zijn, hoe je de beeldkwaliteit kunt regelen, en welke bibliotheek‑aanroepen nodig zijn om **pdf417 barcode** betrouwbaar te **genereren**.

## Wat je nodig hebt

* .NET 6.0 SDK of later geïnstalleerd  
* Een C#‑compatibele IDE (Visual Studio, VS Code, Rider, enz.)  
* Het **Aspose.BarCode for .NET** NuGet‑pakket (of een andere compatibele barcode‑bibliotheek)  

Je kunt de bibliotheek toevoegen met het volgende commando:

```bash
dotnet add package Aspose.BarCode
```

De bibliotheek levert de `BarcodeGenerator`‑klasse die door de hele tutorial wordt gebruikt.

## Stap 1: Maak een barcode‑generator‑instance

De eerste regel maakt een object dat weet hoe een **pdf417 barcode** te **genereren**. Je moet het coderings‑type (`EncodeTypes.Pdf417`) en de tekst die je wilt coderen opgeven.

```csharp
using Aspose.BarCode.Generation;

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample Text");
```

*Waarom deze stap belangrijk is* – De `BarcodeGenerator` omvat alle instellingen voor de barcode. Het instantieren met de juiste `EncodeTypes` vertelt de engine om de PDF417‑symbologie te gebruiken in plaats van QR, Code128 of andere formaten.

## Stap 2: Configureer de PDF417‑lay-out

PDF417 stelt je in staat het aantal kolommen en rijen te regelen, wat direct de grootte en dichtheid van de barcode beïnvloedt. Het aanpassen van deze waarden is de kern van **hoe je een pdf417 barcode kunt genereren** met een aangepaste lay-out.

```csharp
// Set the number of data columns (valid range: 2‑30)
generator.Parameters.Barcode.Pdf417.Columns = 4;

// Set the number of rows (up to 90 rows)
generator.Parameters.Barcode.Pdf417.Rows = 9;
```

*Waarom je deze waarden zou kunnen wijzigen* – Meer kolommen verkleinen de hoogte van de barcode, terwijl meer rijen de breedte vergroten. Kies waarden die passen bij het doel‑scanapparaat en het beschikbare afdrukgebied.

> **Pro tip:** Als je rijen weglaat, berekent de bibliotheek automatisch het optimale aantal op basis van de gegevenslengte. Het expliciet instellen van rijen is nuttig wanneer je een vaste afbeeldingsgrootte voor UI‑lay-outs nodig hebt.

## Stap 3: Kies een afbeeldingsformaat en sla het bestand op

Na het configureren van de lay-out kun je de barcode renderen naar een afbeelding. Het voorbeeld hieronder slaat de barcode op als een PNG‑bestand, maar je kunt ook JPEG, BMP of TIFF selecteren.

```csharp
using Aspose.BarCode;
using System.IO;

// Define the output path – replace with your actual directory
string outputPath = Path.Combine("C:\\Barcodes", "CustomLayout.png");

// Save the barcode image as PNG
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Wanneer de code wordt uitgevoerd, zal `CustomLayout.png` een duidelijke **pdf417 barcode** bevatten die overeenkomt met de kolom‑/rij‑instellingen die je hebt opgegeven.

### Verwachte output

Het openen van `CustomLayout.png` toont een rechthoekige barcode met vier datakolommen en negen rijen. Het scannen van de afbeelding met een willekeurige PDF417‑lezer geeft de oorspronkelijke tekst **“Sample Text”** terug.

![Generated PDF417 barcode example](generated-pdf417.png){: .center-image alt="Gegenereerde pdf417 barcode opgeslagen als een PNG‑bestand"}

## Stap 4: Volledig, uitvoerbaar voorbeeld

Hieronder staat een zelfstandige console‑applicatie die alle onderdelen samenvoegt. Kopieer de code naar een nieuw `.csproj`‑project en voer het uit — er zijn geen extra bestanden nodig.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample Text for PDF417 barcode");

            // 2️⃣ Configure layout – custom columns and rows
            generator.Parameters.Barcode.Pdf417.Columns = 4; // 2‑30
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // up to 90

            // Optional: increase image resolution for sharper output
            generator.Parameters.ImageResolution = 300; // DPI

            // 3️⃣ Define the output location
            string folder = Path.Combine(Environment.CurrentDirectory, "output");
            Directory.CreateDirectory(folder);
            string filePath = Path.Combine(folder, "CustomLayout.png");

            // 4️⃣ Save as PNG
            generator.Save(filePath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode generated at: {filePath}");
        }
    }
}
```

Het uitvoeren van het programma print een bevestigingsregel en maakt het PNG‑bestand aan in een `output`‑submap. De afbeelding kan worden ingebed in rapporten, afgedrukt op labels, of verzonden naar een mobiel apparaat voor scanning.

## Veelvoorkomende variaties en randgevallen

| Scenario | Wat te wijzigen | Waarom het belangrijk is |
|----------|----------------|--------------------------|
| **Encode a long string** | Verhoog `Rows` of laat de bibliotheek automatisch berekenen door de `Rows`‑toewijzing weg te laten | PDF417 kan tot 1.850 tekens bevatten; onvoldoende rijen veroorzaken afkapping |
| **Higher visual quality** | Stel `generator.Parameters.ImageResolution` in op 600 DPI | Handig voor afdrukken op hoge‑resolutieprinters |
| **Different image format** | Vervang `BarCodeImageFormat.Png` door `Jpeg` of `Tiff` | JPEG verkleint de bestandsgrootte; TIFF behoudt verliesvrije data voor archivering |
| **Add a quiet zone** | `generator.Parameters.Barcode.XDimension = 2;` (of pas `Margins` aan) | Quiet zones verbeteren de scannerbetrouwbaarheid in lawaaierige omgevingen |
| **Dynamic text from user input** | Vervang de hard‑coded string door `Console.ReadLine()` | Maakt runtime‑generatie mogelijk op basis van gebruikersdata |

### Hoe een pdf417 barcode te genereren in een web‑API

Als je barcode‑generatie wilt blootstellen via een ASP.NET Core‑endpoint, retourneer je de afbeelding als een byte‑array:

```csharp
[HttpGet("api/barcode/pdf417")]
public IActionResult GetPdf417([FromQuery] string data)
{
    var generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
    generator.Parameters.Barcode.Pdf417.Columns = 5;
    generator.Parameters.Barcode.Pdf417.Rows = 10;

    using var ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return File(ms.ToArray(), "image/png");
}
```

Dit fragment beantwoordt **hoe je een pdf417 barcode kunt genereren** on‑the‑fly zonder naar schijf te schrijven, wat ideaal is voor microservices of mobiele back‑ends.

## De gegenereerde barcode testen

1. Open het PNG‑bestand in een willekeurige afbeeldingsviewer.  
2. Gebruik een gratis PDF417‑scanner‑app (bijv. ZXing, PDF417 Decoder) om de afbeelding te scannen.  
3. Bevestig dat de gedecodeerde tekst overeenkomt met de oorspronkelijke invoer.

Als de scanner fouten meldt, controleer dan de kolom‑/rij‑waarden opnieuw en zorg ervoor dat de beeldresolutie hoog genoeg is voor je apparaat.

## Conclusie

Je weet nu hoe je een **pdf417 barcode** in C# kunt **genereren** met volledige controle over kolommen, rijen en uitvoerformaat. Het volledige voorbeeld toont de volledige workflow — van het maken van de `BarcodeGenerator` tot het opslaan van een PNG‑bestand — zodat je barcode‑creatie kunt integreren in elk .NET‑project.

Vervolgens kun je gerelateerde onderwerpen verkennen, zoals optimalisatie van **pdf417 barcode lay-out**, het insluiten van barcodes in PDF‑rapporten, of het decoderen van barcodes op mobiele apparaten. Het aanpassen van fout‑correctieniveaus en experimenteren met verschillende beeldresoluties helpt je de oplossing af te stemmen op jouw specifieke gebruikssituatie. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PDF417 barcode te genereren in C# – stapsgewijze gids](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Hoe barcode op te slaan in C# – PDF417 barcodes genereren](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Hoe PDF417 barcode te genereren – volledige programmeergids](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}