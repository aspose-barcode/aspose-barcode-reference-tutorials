---
category: general
date: 2026-10-15
description: Maak een barcode‑PNG in C# met een compact PDF417‑voorbeeld – leer hoe
  je kolommen instelt, afmetingen aanpast en de afbeelding genereert.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to create barcode
- how to set columns
- c# barcode example
language: nl
lastmod: 2026-10-15
og_description: Maak barcode PNG in C# met een compact PDF417‑voorbeeld. Deze gids
  laat zien hoe je kolommen instelt, afmetingen aanpast en de afbeelding opslaat.
og_image_alt: Screenshot showing a generated barcode PNG created with C#
og_title: Maak barcode PNG in C# – volledige programmeertutorial
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  headline: How to create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  name: How to create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: Initialise the barcode generator with the desired text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the module (X) dimension in pixels
    text: '```csharp // Set the width of the smallest bar (module) to 2 pixels generator.Parameters.Barcode.XDimension.Pixels
      = 2; ```'
  - name: Define the number of columns for the PDF417 barcode
    text: '```csharp // Specify that the barcode should use 3 columns generator.Parameters.Barcode.Pdf417.Columns
      = 3; ```'
  - name: Enable the compact layout by truncating the barcode
    text: '```csharp // Truncate removes unnecessary empty rows, making the barcode
      shorter generator.Parameters.Barcode.Pdf417.Truncate = true; ```'
  - name: Save the barcode image as PNG
    text: '```csharp // Choose the output folder and file name string outputPath =
      Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");'
  - name: Full, runnable example
    text: 'Putting everything together, here is a self‑contained program you can copy,
      paste, and run:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Hoe maak je een barcode PNG in C# – stapsgewijze handleiding
url: /nl/net/compact-pdf417-encoding/how-to-create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe barcode PNG maken in C# – stapsgewijze gids

Als je **barcode PNG** bestanden wilt maken vanuit C#-code, laat deze tutorial je een complete oplossing zien in slechts een paar regels. Je ziet hoe je kolommen instelt, de modulegrootte aanpast en een compacte PDF417-barcode opslaat als een PNG-afbeelding — allemaal met één eenvoudig leesbaar voorbeeld.

Barcodes programmatisch genereren verwijdert de handmatige stap van het gebruik van een grafische editor, en stelt je in staat barcodes direct in facturen, tickets of voorraadlabels te embedden. In de volgende secties behandelen we alles wat je moet weten om **hoe een barcode te maken** afbeeldingen, waarom elke configuratie belangrijk is, en hoe je de code aanpast voor verschillende use‑cases.

## Vereisten

* .NET 6.0 of later (de code werkt ook met .NET Framework 4.7+)
* Een referentie naar een barcode‑bibliotheek die PDF417 ondersteunt, zoals **Aspose.BarCode for .NET** of **IronBarcode**. Het voorbeeld gebruikt Aspose.BarCode, die je kunt installeren via NuGet:

```bash
dotnet add package Aspose.BarCode
```

* Basiskennis van C#‑syntaxis en Visual Studio (of een IDE naar keuze).

> **Pro tip:** Als je een gratis alternatief verkiest, ondersteunt de open‑source **ZXing.Net**‑bibliotheek ook PDF417, maar de eigenschapsnamen verschillen iets. De hier getoonde concepten blijven hetzelfde.

## Hoe barcode PNG maken in C# (primaire stap)

De kern van de oplossing is een `BarcodeGenerator`‑object geconfigureerd voor PDF417‑codering. De volgende secties splitsen elke regel code uit, leggen **hoe kolommen in te stellen**, en laten zien waarom de instellingen de uiteindelijke PNG‑grootte beïnvloeden.

### Stap 1: Initialise de barcode‑generator met de gewenste tekst

```csharp
using Aspose.BarCode.Generation;

// The text you want to encode in the barcode
string barcodeText = "Compact example";

// Create a generator for PDF417 barcodes
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
{
    // Subsequent configuration goes here
}
```

*Waarom dit belangrijk is*: De `EncodeTypes.Pdf417`‑enum vertelt de bibliotheek een 2‑dimensionale gestapelde barcode te produceren. De constructor accepteert ook de gegevens die je wilt coderen, zodat je geen aparte `SetData`‑aanroep nodig hebt.

### Stap 2: Stel de module (X) dimensie in pixels in

```csharp
// Set the width of the smallest bar (module) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

De **X‑dimensie** bepaalt de visuele dichtheid van de barcode. Een kleinere waarde levert een compactere afbeelding op, wat handig is wanneer je een compacte PNG nodig hebt voor mobieltjeschermen of beperkte afdrukruimte.

### Stap 3: Definieer het aantal kolommen voor de PDF417‑barcode

```csharp
// Specify that the barcode should use 3 columns
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

Deze regel toont **hoe kolommen in te stellen**. PDF417 kan automatisch het optimale aantal kolommen kiezen, maar expliciet instellen geeft je een voorspelbare breedte, vooral wanneer je de PNG in een vaste lay-out embedt.

### Stap 4: Schakel de compacte lay-out in door de barcode te trunceren

```csharp
// Truncate removes unnecessary empty rows, making the barcode shorter
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

Wanneer `Truncate` true is, verwijdert de bibliotheek achterste rijen die geen gegevens bevatten, waardoor de totale hoogte van de afbeelding wordt verminderd zonder informatie te verliezen.

### Stap 5: Sla de barcode‑afbeelding op als PNG

```csharp
// Choose the output folder and file name
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");

// Save the generated barcode as a PNG file
generator.Save(outputPath, BarCodeImageFormat.Png);
```

De `Save`‑methode schrijft de barcode naar schijf in het formaat dat je opgeeft. PNG is verliesvrij, waardoor het ideaal is voor scan‑toepassingen die nauwkeurige randdetectie vereisen.

### Volledig, uitvoerbaar voorbeeld

Alles samenvoegend, hier is een zelfstandige programma dat je kunt kopiëren, plakken en uitvoeren:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise the generator with the data to encode
        string barcodeText = "Compact example";

        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
        {
            // 2️⃣ Set module width to 2 pixels for a tighter image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Explicitly set the number of columns (how to set columns)
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Enable compact layout by truncating empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define the output path and save as PNG (create barcode PNG)
            string outputPath = Path.Combine(Directory.GetCurrentDirectory(), "CompactPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode PNG saved to: {outputPath}");
        }
    }
}
```

**Verwachte output** – Na het uitvoeren van het programma vind je `CompactPdf417.png` in de uitvoermap. De afbeelding bevat een drie‑koloms PDF417‑barcode die compact genoeg is om op een standaard 2 × 2 cm‑label te passen en toch volledig scanbaar blijft.

![Voorbeeld van barcode PNG maken](placeholder.png){alt="Barcode PNG maken met C#"}

## Hoe kolommen in te stellen voor verschillende gegevensgroottes (secundaire zoekterm)

Het aantal kolommen beïnvloedt zowel de breedte als de leesbaarheid van de barcode:

| Kolommen | Geschatte breedte (px) | Typisch gebruik |
|----------|------------------------|-----------------|
| 1‑2      | Smal, hoog             | Kleine tags, RFID‑achtige afdrukken |
| 3‑5      | Gebalanceerd           | Algemene labels |
| 6‑9      | Breed, kort            | Grote posters of verpakkingen |

Als je gegevensreeks groeit, kan de bibliotheek automatisch het aantal rijen verhogen om de barcode binnen de kolomlimiet te houden. Het forceren van een te laag kolomaantal kan echter leiden tot een buitensporig hoge barcode, die mogelijk niet op een bonprinter past. Pas het kolomaantal aan op basis van de fysieke beperkingen van je uitvoermedium.

## Hoe barcode‑afbeeldingen in andere formaten te maken (secundaire zoekterm)

Hoewel PNG het meest voorkomende formaat is voor web en mobiel, heb je mogelijk **hoe een barcode te maken** afbeeldingen nodig in JPEG, BMP of SVG voor gespecialiseerde workflows:

```csharp
// Save as JPEG with 90 % quality
generator.Save("CompactPdf417.jpg", BarCodeImageFormat.Jpeg, 90);

// Save as SVG (vector, infinite scaling)
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

Het kiezen van het juiste formaat hangt af van de downstream‑gebruiker:

* **PNG** – verliesloos, ideaal voor scanners.
* **JPEG** – kleinere bestandsgrootte, acceptabel wanneer lichte compressie‑artefacten acceptabel zijn.
* **SVG** – perfect voor hoge‑resolutie afdrukken of UI‑schaling.

## C# barcode‑voorbeeld: fouten en randgevallen afhandelen

Een robuust **c# barcode voorbeeld** moet runtime‑problemen anticiperen:

```csharp
try
{
    // All configuration steps as shown earlier
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode parameter: {ex.Message}");
}
catch (IOException ex)
{
    Console.Error.WriteLine($"Failed to write file: {ex.Message}");
}
```

*Waarom wikkelen in `try/catch`?* Ongeldige tekens in de tekst, niet‑ondersteunde dimensies, of schrijfrechten‑problemen zullen uitzonderingen veroorzaken. Ze op een nette manier afhandelen voorkomt dat je applicatie crasht tijdens batchverwerking.

## Voorbeeld uitbreiden: een logo of achtergrond toevoegen

Veel real‑world scenario's vereisen een logo‑overlay of een gekleurde achtergrond. De Aspose.BarCode API laat je de barcode combineren met een bitmap:

```csharp
// Load a logo image
using (Bitmap logo = (Bitmap)Image.FromFile("logo.png"))
{
    generator.Parameters.Barcode.ImageFormat = BarCodeImageFormat.Png;
    generator.Parameters.Barcode.Pdf417.EnablePdf417CodewordCount = true; // optional

    // Merge the logo with the barcode (centered)
    generator.Save("BarcodeWithLogo.png", BarCodeImageFormat.Png, logo);
}
```

Deze techniek houdt de **barcode PNG maken** workflow intact terwijl het de visuele branding van de uiteindelijke afbeelding verrijkt.

## Samenvatting

In deze gids hebben we laten zien hoe je **barcode PNG** bestanden maakt in C# met een compacte PDF417‑configuratie. Je leerde:

* De exacte code die nodig is om een `BarcodeGenerator` te initialiseren.
* **Hoe kolommen in te stellen** en waarom het aantal kolommen belangrijk is voor grootte en leesbaarheid.
* Hoe de X‑dimensie aan te passen en truncatie in te schakelen voor een compactere PNG.
* Manieren om de afbeelding op te slaan in PNG, JPEG of SVG.
* Foutafhandelingspatronen voor een productie‑klaar **c# barcode voorbeeld**.
* Optionele uitbreidingen zoals logo‑overlay en achtergrond‑aanpassing.

Je hebt nu een kant‑klaar fragment dat je kunt integreren in factuur‑generatoren, ticketsystemen of voorraadbeheertools. Experimenteer met verschillende kolomwaarden, modulegroottes of barcode‑typen (bijv. QR, Code128) om te zien hoe de afbeelding verandert.

## Volgende stappen

* Verken andere coderings‑typen (`EncodeTypes.QR`, `EncodeTypes.Code128`) om meer use‑cases te dekken.
* Combineer barcode‑generatie met PDF‑creatiebibliotheken (bijv. **iTextSharp**) om de PNG direct in documenten te embedden.
* Onderzoek dynamische sizing: bereken het optimale aantal kolommen op basis van de lengte van de invoerstring en de doel‑labelafmetingen.

Veel plezier met coderen, en geniet van de eenvoud van het programmatisch genereren van scherpe barcode‑PNGs in C#!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids zijn gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PDF417‑barcode te maken en op te slaan als PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)
- [Hoe PDF417‑barcode te maken en de grootte in te stellen in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/)
- [Hoe PDF417‑barcode te maken in C# met compacte modus](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}