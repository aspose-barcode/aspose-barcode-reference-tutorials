---
category: general
date: 2026-10-24
description: Leer hoe je een PDF417‑barcode genereert met Aspose.BarCode in C# met
  compacte instellingen en controle over de X‑dimensie van de barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode
- compact PDF417
- barcode XDimension
- PDF417 columns
language: nl
lastmod: 2026-10-24
og_description: Genereer PDF417-barcode in C# met Aspose.BarCode. Volg deze volledige
  gids om compacte PDF417-afbeeldingen te maken, XDimension te regelen en kolommen
  in te stellen.
og_image_alt: Screenshot of generated PDF417 barcode using Aspose.BarCode
og_title: Genereer PDF417-barcode met Aspose.BarCode – C# stap‑voor‑stap
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  headline: How to generate PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  name: How to generate PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: 1. Changing the image format
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 2. Encoding large amounts of data
    text: 'PDF417 can store up to ~1.1 KB of text. When the payload exceeds the capacity
      of three columns, the library automatically adds rows. To keep the barcode compact,
      you can:'
  - name: 3. Using a license to remove the trial watermark
    text: '```csharp Aspose.BarCode.License license = new Aspose.BarCode.License();
      license.SetLicense("Aspose.BarCode.lic"); ```'
  - name: 4. Handling exceptions
    text: '```csharp try { generator.Save(outputPath, BarCodeImageFormat.Png); } catch
      (Exception ex) { Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
      } ```'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- PDF417
- C#
title: Hoe PDF417-barcode te genereren met Aspose.BarCode in C#
url: /nl/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417-barcode te genereren met Aspose.BarCode in C#

Als je een **PDF417-barcode** moet **genereren** in een .NET‑applicatie, toont deze gids je een complete, kant‑klaar oplossing. Je ziet hoe Aspose.BarCode het proces eenvoudig maakt en je fijne controle geeft over **compact PDF417**, **barcode XDimension**, en **PDF417 columns**.

Het maken van een barcode is een veelvoorkomende eis voor voorraadsystemen, ticketplatforms en documentworkflows. Aan het einde van deze tutorial heb je een zelfstandige C#‑programmaat die een scherpe PNG‑afbeelding van een PDF417‑barcode produceert, klaar om in elke UI te worden ingebed of op een label te worden afgedrukt.

## Wat je nodig hebt

- .NET 6.0 SDK of later (de code werkt ook met .NET Framework 4.6+)
- Visual Studio 2022 of een C#‑editor naar keuze
- Een geldige Aspose.BarCode for .NET‑licentie (de gratis proefversie werkt voor ontwikkeling)
- Basiskennis van C#‑syntaxis

> **Pro tip:** Als je Aspose.BarCode evalueert, download dan de proefversie van de officiële site en voeg het NuGet‑pakket `Aspose.BarCode` toe aan je project. De proefversie voegt een klein watermerk toe aan de gegenereerde afbeelding, dat verdwijnt zodra je een licentie toepast.

## Stap 1: Installeer het Aspose.BarCode NuGet‑pakket

Open een terminal in je solution‑map en voer uit:

```bash
dotnet add package Aspose.BarCode
```

Het commando haalt de nieuwste stabiele versie op (vanaf oktober 2026, versie 23.12). Het toevoegen van het pakket herstelt de `Aspose.BarCode.Generation`‑namespace die je zult gebruiken om **PDF417‑barcode**‑afbeeldingen te **genereren**.

## Stap 2: Maak een basis C#‑consoleproject

Als je nog geen project hebt, maak er dan één:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Open `Program.cs`. Het skelet bevat al een `Main`‑methode waar we de barcode‑generatiecode zullen plaatsen.

## Stap 3: Initialiseert de barcode‑generator

Importeer eerst de vereiste namespace:

```csharp
using Aspose.BarCode.Generation;
```

Instantieer vervolgens, binnen `Main`, `BarcodeGenerator` met de PDF417‑symbologie en de gegevens die je wilt coderen:

```csharp
// Step 3: Initialize the generator for a PDF417 barcode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

De string bevat Unicode‑tekens om te laten zien dat Aspose.BarCode niet‑ASCII‑invoer correct verwerkt. Als je alleen ASCII nodig hebt, vervang dan de tekst door een gewone string.

## Stap 4: Pas de barcode XDimension (module‑grootte) aan

De **barcode XDimension** bepaalt de breedte van de kleinste balk (de module). Het instellen in pixels geeft je pixel‑perfecte controle over de uiteindelijke afbeeldingsgrootte:

```csharp
// Step 4: Set the module size – XDimension in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Een waarde van `2` pixels levert een compacte afbeelding op zonder de scan‑betrouwbaarheid te verminderen. Verhoog de waarde voor grotere barcodes of verlaag deze voor zeer dichte lay-outs.

## Stap 5: Configureer compacte PDF417‑opties

Twee PDF417‑specifieke instellingen beïnvloeden de visuele voetafdruk drastisch:

| Instelling | Betekenis | Typische waarde voor compacte output |
|------------|-----------|--------------------------------------|
| `Columns` | Aantal datakolommen | `3` |
| `Truncate` (compact mode) | Laat de rechter‑quiet‑zone weg en vermindert het aantal rijen | `true` |

Pas ze als volgt toe:

```csharp
// Step 5: Use a small number of columns and enable compact mode
generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417
```

Het gebruik van **PDF417 columns** ingesteld op `3` samen met `Truncate = true` creëert een *compacte PDF417* barcode die mooi op een standaard label past en toch leesbaar blijft voor de meeste scanners.

## Stap 6: Sla de barcode‑afbeelding op

Schrijf tenslotte de barcode naar schijf. Het voorbeeld slaat een PNG op, maar Aspose.BarCode ondersteunt ook BMP, JPEG, GIF, TIFF en SVG:

```csharp
// Step 6: Save the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

De constante `BarCodeImageFormat.Png` vertelt de bibliotheek om een verliesvrije PNG te produceren, wat ideaal is voor verdere verwerking of afdrukken.

## Volledige, uitvoerbare broncode

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator for PDF417 with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size – barcode XDimension in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Configure compact PDF417 options
        generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
        generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417

        // 4️⃣ Save as PNG
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "CompactPdf417.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

Het uitvoeren van het programma genereert `CompactPdf417.png` in de hoofdmap van het project. Open het bestand met een willekeurige afbeeldingsviewer; je ziet een compact PDF417‑barcode die de string *Åspóse.Barcóde©* codeert.

![Schermafbeelding van gegenereerde PDF417-barcode met Aspose.BarCode](placeholder-image.png "Gegenereerde PDF417 barcode")

*Afbeeldings‑alt‑tekst: Schermafbeelding van gegenereerde PDF417‑barcode met Aspose.BarCode* – deze alt‑tekst bevat het primaire zoekwoord voor toegankelijkheid en SEO.

## Het resultaat verifiëren

1. Open het PNG‑bestand. De barcode moet bestaan uit drie verticale datakolommen met een compacte lay-out (geen extra quiet zones aan de rechterkant).
2. Scan de afbeelding met een smartphone‑barcode‑scanner die PDF417 ondersteunt. De gedecodeerde tekst moet overeenkomen met de oorspronkelijke invoerstring.
3. Als de scanner faalt, probeer dan `XDimension.Pixels` te verhogen naar `3` of `4`. Grotere modules verbeteren de leesbaarheid op apparaten met lage resolutie.

## Veelvoorkomende variaties en randgevallen

### 1. Het wijzigen van het afbeeldingsformaat

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

SVG is vector‑gebaseerd, waardoor de barcode scherp blijft op elk zoomniveau — handig voor webpagina's.

### 2. Het coderen van grote hoeveelheden data

PDF417 kan tot ongeveer 1,1 KB tekst opslaan. Wanneer de payload de capaciteit van drie kolommen overschrijdt, voegt de bibliotheek automatisch rijen toe. Om de barcode compact te houden, kun je:

- Verminder de datalengte (bijv. gebruik een identifier in plaats van een volledige boodschap)
- Verhoog het aantal **PDF417 columns** (bijv. `generator.Parameters.Barcode.Pdf417.Columns = 5;`)

### 3. Een licentie gebruiken om het proef‑watermerk te verwijderen

```csharp
Aspose.BarCode.License license = new Aspose.BarCode.License();
license.SetLicense("Aspose.BarCode.lic");
```

Plaats het licentiebestand naast het uitvoerbare bestand. Na licentiëren bevat de gegenereerde afbeelding geen watermerk.

### 4. Het afhandelen van uitzonderingen

```csharp
try
{
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

Typische fouten omvatten onvoldoende schrijfrechten of een niet‑ondersteund afbeeldingsformaat.

## Waarom de instellingen belangrijk zijn

- **barcode XDimension** – Regelt het visuele gewicht van elke balk. Te klein maakt de barcode onleesbaar; te groot verspilt ruimte.
- **PDF417 columns** – Minder kolommen geven een smallere barcode, maar verhogen het aantal rijen


## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PDF417-barcode te genereren met Aspose – Complete gids](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [PDF417-barcode genereren met compacte instellingen in C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-with-compact-settings-in-c/)
- [Hoe barcode op te slaan en PDF417 te genereren met Aspose in C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}