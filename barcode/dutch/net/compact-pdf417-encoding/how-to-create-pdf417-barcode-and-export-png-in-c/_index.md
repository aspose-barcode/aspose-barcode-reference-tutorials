---
category: general
date: 2026-09-19
description: Maak een PDF417-barcode in C# en leer hoe je een barcode‑afbeelding genereert,
  de afmetingen van de barcode instelt en opslaat als PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode image
- how to set barcode dimensions
- how to create barcode png
language: nl
lastmod: 2026-09-19
og_description: Maak een PDF417-barcode in C# en ontdek hoe je een barcode‑afbeelding
  genereert, de afmetingen van de barcode instelt en deze opslaat als een PNG‑bestand.
og_image_alt: Sample PDF417 barcode generated with C# showing custom dimensions saved
  as PNG
og_title: PDF417‑barcode maken en PNG exporteren in C# – stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Create PDF417 barcode in C# and learn how to generate barcode image,
    set barcode dimensions, and save as PNG.
  headline: How to create PDF417 barcode and export PNG in C#
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- image generation
title: Hoe PDF417-barcode te maken en PNG te exporteren in C#
url: /nl/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417-barcode te maken en PNG te exporteren in C#

Als je een **PDF417-barcode** moet **maken** in een .NET‑applicatie, laat deze gids je zien hoe je een barcode‑afbeelding genereert, de afmetingen aanpast en opslaat als een PNG‑bestand. Je ziet een volledig, uitvoerbaar voorbeeld dat de Aspose.BarCode‑bibliotheek gebruikt, zodat je de code direct in je eigen project kunt kopiëren.

Het genereren van een barcode‑afbeelding is een veelvoorkomende eis voor ticketsystemen, voorraadtracking en mobiele instapkaarten. Aan het einde van deze tutorial begrijp je **hoe je een barcode‑afbeelding genereert**, **hoe je barcode‑afmetingen instelt**, en **hoe je barcode‑PNG‑bestanden maakt** die voldoen aan je visuele kwaliteitsnormen.

## Vereisten

* .NET 6.0 SDK of later (de code werkt ook met .NET Framework 4.7+).
* Een ontwikkelomgeving zoals Visual Studio 2022 of VS Code.
* Een geldige licentie voor de **Aspose.BarCode for .NET**‑bibliotheek (de gratis proefversie werkt voor dit voorbeeld).
* Basiskennis van C#‑syntaxis.

Installeer het NuGet‑pakket met de volgende opdracht:

```bash
dotnet add package Aspose.BarCode
```

## Stap 1: Het project opzetten en namespaces importeren

Maak een nieuwe console‑applicatie of voeg de code toe aan een bestaand project. Importeer de benodigde namespaces bovenaan het bestand:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Deze namespaces geven je toegang tot de `BarcodeGenerator`‑klasse en de `EncodeTypes`‑enumeratie.

## Stap 2: Hoe een PDF417‑barcode te maken – basisgeneratorconfiguratie

De eerste stap is het aanmaken van een `BarcodeGenerator` met het `Pdf417`‑encodeertype en de tekst die je wilt coderen. Dit object vertegenwoordigt de barcode die je later rendert.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");
```

*Waarom dit belangrijk is*: `EncodeTypes.Pdf417` vertelt de bibliotheek om de PDF417‑symbologie te gebruiken, een gestapelde lineaire barcode die grote hoeveelheden data kan opslaan. Het tweede argument (“Sample”) is de payload die verschijnt wanneer de barcode wordt gescand.

## Stap 3: Hoe barcode‑afmetingen in te stellen – fijn afstellen van dichtheid en lay‑out

Een PDF417‑barcode bestaat uit rijen en kolommen van modules. Het aanpassen van de X‑dimensie (modulebreedte) en het aantal rijen/kolommen stelt je in staat de visuele dichtheid en de totale grootte van de afbeelding te regelen.

```csharp
// Step 3: Set the module (X) dimension in pixels – controls the barcode's density
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Define the barcode layout – number of columns and rows
generator.Parameters.Barcode.Pdf417.Columns = 4;   // up to 30 columns
generator.Parameters.Barcode.Pdf417.Rows    = 9;   // up to 90 rows
```

*Waarom dit belangrijk is*:  
* **X‑dimension** bepaalt hoe breed elk klein vierkant (module) is. Een kleinere waarde levert een compactere barcode op, maar kan moeilijker leesbaar zijn voor scanners met lage resolutie.  
* **Columns** en **Rows** beïnvloeden de gegevenscapaciteit en de fysieke vorm. Meer kolommen maken de barcode breder; meer rijen maken hem hoger. Je kunt experimenteren met waarden tot de limieten die in de opmerkingen staan.

**Pro tip**: Als de barcode te dicht lijkt op een scherm met hoge DPI, verhoog dan `XDimension.Pixels` naar 3 of 4. Omgekeerd, voor een klein label kun je deze op 1 pixel zetten en het aantal kolommen verminderen.

## Stap 4: Hoe een barcode‑afbeelding te genereren – renderen naar een bitmap in het geheugen

Na het configureren van de generator kun je de barcode renderen naar een afbeeldingobject. Deze stap is optioneel als je het bestand direct wilt opslaan, maar het blootleggen van de bitmap stelt je in staat verdere bewerkingen uit te voeren (bijv. een logo toevoegen of een rand tekenen).

```csharp
// Step 4: Render the barcode to a bitmap (optional but useful for further manipulation)
using var barcodeImage = generator.GenerateBarCodeImage();
```

`GenerateBarCodeImage()` retourneert een `System.Drawing.Image` die je, indien gewenst, met GDI+ kunt manipuleren.

## Stap 5: Hoe een barcode‑PNG te maken – het uiteindelijke afbeeldingsbestand opslaan

Schrijf tenslotte de afbeelding naar schijf in PNG‑formaat. PNG behoudt verliesvrije kwaliteit, wat ideaal is voor scan‑toepassingen.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY\Pdf417Custom.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

*Waarom dit belangrijk is*: De `Save`‑methode verzorgt de codering en bestands‑I/O voor je. Het gebruik van `BarCodeImageFormat.Png` zorgt ervoor dat de output een draagbare, verliesvrije afbeelding is die werkt in browsers en op mobiele apparaten.

### Volledig uitvoerbaar voorbeeld

Hieronder staat het volledige programma dat je kunt plakken in `Program.cs` en uitvoeren. Vervang `YOUR_DIRECTORY` door een bestaande map op je computer.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Create the generator with PDF417 symbology
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");

        // 2. Adjust dimensions for desired visual density
        generator.Parameters.Barcode.XDimension.Pixels = 2;
        generator.Parameters.Barcode.Pdf417.Columns = 4; // up to 30
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // up to 90

        // 3. (Optional) Render to a bitmap if you need further processing
        // using var image = generator.GenerateBarCodeImage();

        // 4. Save as PNG
        string outputPath = @"YOUR_DIRECTORY\Pdf417Custom.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode created and saved to: {outputPath}");
    }
}
```

Het uitvoeren van het programma genereert een PNG‑bestand dat er als volgt uitziet:

![Generated PDF417 barcode example](https://example.com/placeholder-image.png "PDF417 barcode generated with custom dimensions saved as PNG")

*Alt‑tekst*: **Voorbeeld PDF417‑barcode gegenereerd met C# met aangepaste afmetingen opgeslagen als PNG** – dit voldoet aan de **create PDF417 barcode**‑vereiste voor beeldtoegankelijkheid.

## Veelvoorkomende variaties en randgevallen

| Situatie | Aanbevolen aanpassing |
|-----------|------------------------|
| **Zeer klein label** (bijv. 1 cm × 2 cm) | Stel `XDimension.Pixels = 1` in en verminder `Columns` tot 2‑3. Controleer de leesbaarheid met de scanner. |
| **Hoge‑resolutie afdruk** (300 dpi of meer) | Verhoog `XDimension.Pixels` naar 3‑4 en verhoog eventueel `Rows` voor meer gegevenscapaciteit. |
| **Andere afbeeldingformaat nodig** (JPEG, BMP) | Verander `BarCodeImageFormat.Png` naar `BarCodeImageFormat.Jpeg` of `BarCodeImageFormat.Bmp`. |
| **Inbedden in een PDF** | Gebruik `generator.Save("output.pdf", BarCodeImageFormat.Pdf)` in plaats van PNG. |
| **Dynamische data** (gebruikerinvoer) | Vervang de statische `"Sample"`‑string door een variabele, bv. `userInput`. Zorg dat de tekstlengte de PDF417‑limieten niet overschrijdt (≈ 1 800 karakters). |

## Probleemoplossingschecklist

* **Lege afbeelding** – Controleer of de uitvoermap bestaat en of de applicatie schrijfrechten heeft.  
* **Barcode niet scanbaar** – Verhoog `XDimension.Pixels` of voeg meer kolommen/rijen toe; achtergronden met weinig contrast kunnen ook falen.  
* **Onverwachte grootte** – Controleer de waarden van `Columns` en `Rows`; de bibliotheek houdt zich aan de maximale limieten die in de opmerkingen staan.

## Volgende stappen

Nu je **PDF417‑barcode kunt maken**, overweeg dan deze gerelateerde onderwerpen te verkennen:

* **Hoe een barcode‑afbeelding te genereren** in andere formaten zoals SVG voor web‑schaalbare graphics.  
* **Hoe barcode‑afmetingen in te stellen** voor QR‑codes en DataMatrix‑symbologieën.  
* **Hoe een barcode‑PNG te maken** met aangepaste kleuren of ingebedde logo's met `System.Drawing`.  

Deze uitbreidingen stellen je in staat een volledig uitgeruste barcode‑generatieservice te bouwen die mobiele apps, webportalen en desktop‑hulpmiddelen kan bedienen.

---

*Je hebt geleerd hoe je een PDF417‑barcode maakt, de afmetingen aanpast, een barcode‑afbeelding rendert en deze opslaat als een PNG‑bestand met C#. Pas de hier getoonde patronen toe op andere barcode‑typen en afbeeldingsformaten om je automatiseringsmogelijkheden uit te breiden.*

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PDF417‑barcode‑afbeelding te genereren in C# met Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Hoe PDF417‑barcode te maken met Aspose – Complete stapsgewijze gids](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Hoe barcode op te slaan in C# – PDF417‑barcodes genereren](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}