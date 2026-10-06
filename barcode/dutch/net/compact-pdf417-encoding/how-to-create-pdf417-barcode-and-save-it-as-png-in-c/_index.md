---
category: general
date: 2026-10-05
description: Leer hoe je een PDF417‑barcode maakt in C# en een barcode‑PNG genereert
  met stapsgewijze code en best‑practice‑tips.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- generate barcode PNG
- how to generate PDF417
language: nl
lastmod: 2026-10-05
og_description: Maak PDF417‑barcode in C# en genereer direct een PNG‑barcode. Volg
  deze volledige tutorial voor een productieklare oplossing.
og_image_alt: Example of a compact PDF417 barcode created with C#
og_title: PDF417-barcode maken in C# – volledige gids om PNG te genereren
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  headline: How to create PDF417 barcode and save it as PNG in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  name: How to create PDF417 barcode and save it as PNG in C#
  steps:
  - name: Expected output
    text: When you open `CompactPdf417.png`, you should see a vertical, high‑density
      barcode that encodes the string *Åspóse.Barcóde©*. Scanning the image with any
      PDF417 reader returns the original text.
  - name: Generating other image formats
    text: 'If you prefer JPEG or BMP, change the `BarCodeImageFormat` enum:'
  - name: Adjusting error correction
    text: 'For harsh environments (e.g., outdoor signage), increase the error‑correction
      level:'
  - name: Encoding binary data
    text: 'PDF417 can encode binary payloads. Pass a `byte[]` instead of a string:'
  - name: Handling very long strings
    text: 'When the data exceeds the default capacity, the generator automatically
      creates additional rows. You can limit the row count to avoid oversized images:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- image generation
title: Hoe maak je een PDF417‑barcode en sla je deze op als PNG in C#
url: /nl/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417-barcode maken en opslaan als PNG in C#

Als je een **PDF417-barcode moet maken** in een .NET‑applicatie, laat deze gids je precies zien hoe je dat doet. Je krijgt een kant‑klaar C#‑fragment dat een hoogwaardige **barcode‑PNG**‑bestand genereert, en je begrijpt elke instelling die de output beïnvloedt.

Barcodes genereren is een veelvoorkomende eis voor ticketsystemen, voorraadtracking en veilige documentcodering. Aan het einde van deze tutorial kun je de vraag “**hoe PDF417 te genereren**” beantwoorden met een compleet, uitvoerbaar voorbeeld.

## Vereisten

* .NET 6.0 SDK of later geïnstalleerd  
* Een ontwikkelomgeving zoals Visual Studio 2022 of VS Code  
* Het **Aspose.BarCode for .NET** NuGet‑pakket (of een andere compatibele bibliotheek die PDF417 ondersteunt)  

Je kunt het pakket toevoegen met het volgende commando:

```bash
dotnet add package Aspose.BarCode
```

De onderstaande code gebruikt de Aspose‑API omdat deze gedetailleerde controle over PDF417‑parameters biedt en PNG‑export direct ondersteunt.

## Stap 1: Het project opzetten en namespaces importeren

Maak een nieuw console‑project aan en importeer de vereiste namespaces:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

De namespace `Aspose.BarCode.Generation` bevat de klasse `BarcodeGenerator`, die het startpunt is voor **het maken van PDF417‑barcode**‑afbeeldingen.

## Stap 2: PDF417‑barcode maken met de gewenste tekst

Instantieer de generator met de `EncodeTypes.Pdf417`‑enum en de gegevens die je wilt coderen. Het voorbeeld gebruikt een string met speciale tekens om Unicode‑verwerking te demonstreren:

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

De generator bevat nu een barcode‑object dat je kunt configureren voordat je het rendert.

## Stap 3: Visuele parameters configureren

Het fijn afstellen van de barcode verbetert de leesbaarheid en verkleint de afbeeldingsgrootte. De meest vaak aangepaste instellingen zijn **X‑dimension**, **columns** en **compact mode**.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 4: Define the number of columns for the PDF417 code
generator.Parameters.Barcode.Pdf417.Columns = 3;

// Step 5: Enable compact (truncated) mode to reduce the barcode size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

* **X‑dimension** bepaalt de breedte van elke module; een waarde van `2` pixels levert een compacte maar leesbare barcode op.  
* **Columns** bepalen hoeveel datakolommen de code gebruikt. Minder kolommen maken de barcode smaller maar hoger.  
* **Truncate** activeert de “compact”‑modus zoals gedefinieerd in de PDF417‑specificatie, die onnodige opvulrijen verwijdert.

Je kunt experimenteren met `Rows` en `ErrorCorrectionLevel` als jouw scenario een hogere weerstand tegen schade vereist.

## Stap 4: De barcode opslaan als PNG‑afbeelding

Exporteer tenslotte de barcode naar een PNG‑bestand. PNG behoudt scherpe randen en ondersteunt transparantie, waardoor het ideaal is voor web‑ en printscenario's.

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Het uitvoeren van het programma maakt `CompactPdf417.png` aan in de opgegeven map. De afbeelding ziet er als volgt uit:

![Compact PDF417 barcode created with C#](compact-pdf417.png "Example of a compact PDF417 barcode created with C#")

*De alt‑tekst hierboven bevat het primaire zoekwoord, wat zowel aan SEO‑ als toegankelijkheidsvereisten voldoet.*

## Volledig, uitvoerbaar voorbeeld

Alle onderdelen samengevoegd, hier is een zelfstandige programma‑code die je kunt kopiëren, plakken en uitvoeren:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1. Initialize the generator with PDF417 type and sample data
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

        // 2. Configure size and compactness
        generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
        generator.Parameters.Barcode.Pdf417.Columns = 3;           // number of columns
        generator.Parameters.Barcode.Pdf417.Truncate = true;       // enable compact mode

        // 3. Optional: increase error correction for damaged prints
        // generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;

        // 4. Export to PNG
        string outputPath = @"C:\Barcodes\CompactPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

### Verwachte output

Wanneer je `CompactPdf417.png` opent, zou je een verticale, hoge‑dichtheid barcode moeten zien die de string *Åspóse.Barcóde©* codeert. Het scannen van de afbeelding met een PDF417‑lezer geeft de oorspronkelijke tekst terug.

## Waarom deze instellingen belangrijk zijn

* **X‑dimension** beïnvloedt zowel de fysieke grootte als de scansnelheid. Kleinere modules verhogen de datadichtheid maar kunnen een scanner met hogere resolutie vereisen.  
* **Columns** beïnvloeden de beeldverhouding. Voor mobiele bonnen houdt een laag aantal kolommen de barcode smal genoeg om op smal papier te passen.  
* **Truncate** vermindert het aantal rijen, bespaart inkt en ruimte zonder de gegevensintegriteit te schaden, omdat PDF417 al fout‑correctie‑codewoorden bevat.

Het begrijpen van deze parameters stelt je in staat de barcode af te stemmen op de beperkingen van je doelmedium — of het nu een labelprinter, een webpagina of een mobiele app is.

## Veelvoorkomende variaties en randgevallen

### Andere afbeeldingsformaten genereren

Als je JPEG of BMP verkiest, wijzig dan de `BarCodeImageFormat`‑enum:

```csharp
generator.Save(@"C:\Barcodes\Pdf417.jpg", BarCodeImageFormat.Jpeg);
```

JPEG comprimeert de afbeelding maar kan artefacten introduceren die het scannen op kleine formaten beïnvloeden.

### Foutcorrectie aanpassen

Voor ruwe omgevingen (bijv. buitenreclame) verhoog je het fout‑correctieniveau:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 8; // max is 8
```

Hogere niveaus voegen meer redundantie toe, waardoor de barcode groter maar robuuster wordt.

### Binaire gegevens coderen

PDF417 kan binaire payloads coderen. Geef een `byte[]` door in plaats van een string:

```csharp
byte[] binaryData = new byte[] { 0x01, 0xFF, 0xA5 };
generator = new BarcodeGenerator(EncodeTypes.Pdf417, binaryData);
```

De bibliotheek schakelt automatisch over naar binaire modus.

### Zeer lange strings verwerken

Wanneer de gegevens de standaardcapaciteit overschrijden, maakt de generator automatisch extra rijen aan. Je kunt het aantal rijen beperken om te grote afbeeldingen te voorkomen:

```csharp
generator.Parameters.Barcode.Pdf417.Rows = 30; // max rows
```

Als de inhoud nog steeds niet past, overweeg dan om het over meerdere barcodes te verdelen.

## Pro‑tips

* **Cache de generator** als je veel barcodes met dezelfde instellingen moet maken. Het hergebruiken van het object voorkomt herhaalde toewijzing van interne bronnen.  
* **Stel `Resolution` in** op de `ImageOptions` als je een specifieke DPI voor afdrukken nodig hebt:

  ```csharp
  generator.Parameters.ImageResolution = 300; // DPI
  ```

* **Valideer de output** programmatisch met `BarCodeReader` om te verzekeren dat de gegenereerde PNG kan worden gedecodeerd voordat je deze aan gebruikers levert.

## Conclusie

Je weet nu hoe je **PDF417‑barcode kunt maken** in C# en **barcode‑PNG‑bestanden kunt genereren** met volledige controle over grootte, kolommen en compacte modus. Het volledige voorbeeld toont de standaardaanpak, legt uit waarom elke instelling belangrijk is, en behandelt variaties zoals foutcorrectie, alternatieve formaten en binaire gegevens. Gebruik de bovenstaande tips om de oplossing aan te passen aan jouw specifieke workflow, of je nu een ticketsysteem, een logistiek labelgenerator of een veilige documentencoder bouwt.

---

**Volgende stappen**

* [Hoe PDF417-barcode te maken in C# – stapsgewijze gids](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
* [Hoe micro‑PDF417-barcode te genereren in C# – stapsgewijze gids](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
* [Hoe PDF417-barcode te maken in C# met compacte modus](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}