---
category: general
date: 2026-09-29
description: Maak een GS1‑barcode in C# en genereer barcode‑PNG‑afbeeldingen met BarcodeGenerator.
  Volg een stapsgewijze handleiding om de barcode‑afbeelding efficiënt te exporteren.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode gs1
- generate barcode png
- barcode generator c#
- how to generate barcode
- export barcode image
language: nl
lastmod: 2026-09-29
og_description: Maak een GS1-barcode in C# en genereer barcode‑PNG‑bestanden met BarcodeGenerator.
  Volg deze volledige gids om snel een barcode‑afbeelding te exporteren.
og_image_alt: Generated GS1 MicroPDF417 barcode saved as a PNG file
og_title: Maak GS1-barcode in C# – exporteer als PNG in enkele minuten
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create barcode GS1 in C# and generate barcode PNG images using BarcodeGenerator.
    Follow a step‑by‑step guide to export barcode image efficiently.
  headline: Create barcode GS1 in C# and export it as PNG
  type: TechArticle
tags:
- barcode
- C#
- GS1
- PNG
- Aspose
title: Maak een GS1-barcode in C# en exporteer deze als PNG
url: /nl/net/gs1-barcode-encoding/create-barcode-gs1-in-c-and-export-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode GS1 maken in C# en exporteren als PNG

Als je **barcode GS1** moet maken in een .NET‑applicatie, laat deze gids je precies zien hoe je dat doet. Je ziet een beknopte oplossing die een barcode‑PNG‑afbeelding genereert en de barcode‑afbeelding naar schijf exporteert, allemaal met de Aspose.BarCode `BarcodeGenerator`‑klasse.

Het genereren van een GS1‑barcode is een veelvoorkomende eis voor voorraad‑, verzend‑ en kassasystemen. Aan het einde van deze tutorial kun je een klein C#‑programma schrijven dat een GS1‑conforme MicroPDF417‑barcode maakt en opslaat als een PNG‑bestand van hoge kwaliteit.

## Vereisten

* **.NET 6** (of een latere .NET‑versie) geïnstalleerd.
* **Visual Studio 2022** of een IDE die C# ondersteunt.
* Het **Aspose.BarCode for .NET** NuGet‑pakket (`Aspose.BarCode`) – het levert de `BarcodeGenerator`‑API die in de voorbeelden wordt gebruikt.
* Basiskennis van C#‑syntaxis.

> **Pro tip:** Gebruik de gratis community‑editie van Aspose.BarCode bij experimenten; de volledige versie verwijdert eventuele evaluatiewatermerken.

## Stap 1 – Barcode GS1 maken met BarcodeGenerator

Het eerste wat je moet doen is de `BarcodeGenerator` voor het *MicroPDF417*‑formaat instantiëren en er een GS1‑datastring aan voeren. De GS1‑Application Identifiers (AIs) worden tussen haakjes geplaatst, bv. `(01)` voor GTIN‑14 en `(21)` voor een serienummer.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// GS1 data: (01) – GTIN‑14, (21) – serial number
string gs1Data = "(01)12345678901234(21)ABC123";

// Initialise the generator for MicroPDF417 (GS1 compatible)
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);
```

**Waarom dit belangrijk is:**  
`EncodeTypes.MicroPdf417` behandelt de invoer automatisch als GS1‑data wanneer de string geldige AIs bevat. Dit zorgt ervoor dat de gegenereerde barcode voldoet aan de GS1‑specificatie zonder extra configuratie.

## Stap 2 – Barcode‑dimensies instellen voor optimale grootte

De visuele grootte van een barcode wordt bepaald door de **X‑dimension** (de breedte van één module). Het aanpassen van `XDimension.Pixels` stelt je in staat de uiteindelijke afbeeldingsgrootte nauwkeurig af te stemmen terwijl de leesbaarheid behouden blijft.

```csharp
// Set the module width to 2 pixels – a good balance for screen and print
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Hoe een barcode‑PNG te genereren** – De X‑dimension beïnvloedt niet de gecodeerde data; het verandert alleen de fysieke afmetingen van de gegenereerde afbeelding. Als je een grotere barcode nodig hebt voor hoge‑resolutie‑afdrukken, verhoog dan deze waarde (bijv. `3` of `4`).

## Stap 3 – Barcode‑PNG genereren en barcode‑afbeelding exporteren

Nu kun je de barcode renderen en naar een PNG‑bestand schrijven. De `Save`‑methode neemt het doelpad en het gewenste afbeeldingsformaat.

```csharp
// Define the output folder (ensure it exists)
string outputFolder = Path.Combine(Environment.CurrentDirectory, "output");
Directory.CreateDirectory(outputFolder);

// Export the barcode image as PNG
string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
generator.Save(pngPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode image saved to: {pngPath}");
```

**Wat er achter de schermen gebeurt:**  
`BarcodeGenerator.Save` rastert de barcode naar een bitmap, past de eerder ingestelde X‑dimension toe, en codeert de bitmap als een PNG‑bestand. Het resulterende bestand kan direct in webpagina’s worden gebruikt, op etiketten worden afgedrukt, of in PDF’s worden ingebed.

## Volledig broncode‑voorbeeld

Hieronder staat een volledige, zelfstandige console‑applicatie die je kunt kopiëren, plakken en uitvoeren. Het demonstreert **hoe barcode‑PNG‑bestanden te genereren**, **barcode‑afbeelding te exporteren**, en bevat basis‑foutafhandeling.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the barcode generator for GS1 MicroPDF417
                string gs1Data = "(01)12345678901234(21)ABC123";
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417, gs1Data);

                // 2️⃣ Adjust X‑dimension to control the visual size
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Prepare output folder
                string outputFolder = Path.Combine(
                    Environment.CurrentDirectory, "output");
                Directory.CreateDirectory(outputFolder);

                // 4️⃣ Save the barcode as PNG (export barcode image)
                string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
                generator.Save(pngPath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode created and saved as PNG:");
                Console.WriteLine(pngPath);
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error: {ex.Message}");
            }
        }
    }
}
```

### Verwachte output

Wanneer je het programma uitvoert, zou je moeten zien:

```
✅ Barcode created and saved as PNG:
C:\Path\To\Your\App\output\GS1MicroPdf417.png
```

Het openen van het PNG‑bestand toont een duidelijke **GS1 MicroPDF417**‑barcode die de GTIN‑14 `12345678901234` en het serienummer `ABC123` codeert. Het scannen met een willekeurige GS1‑compatibele scanner zal de oorspronkelijke datastring teruggeven.

## Veelvoorkomende valkuilen en best practices

| Probleem | Waarom het gebeurt | Hoe te voorkomen |
|----------|--------------------|-------------------|
| **Onjuiste AI‑opmaak** | Ontbrekende haakjes of verkeerde volgorde maakt de barcode niet‑GS1. | Zet elke AI altijd tussen haakjes, bv. `(01)`. |
| **Te kleine X‑dimension** | De barcode wordt onleesbaar op apparaten met lage resolutie. | Houd `XDimension.Pixels` ≥ 2 voor de meeste printers; verhoog voor high‑DPI‑output. |
| **Uitvoermap bestaat niet** | `Save` geeft een `DirectoryNotFoundException`. | Gebruik `Directory.CreateDirectory` voordat je `Save` aanroept. |
| **Verkeerd EncodeType gebruiken** | Sommige types (bijv. `Code128`) ondersteunen GS1‑data niet direct. | Kies `EncodeTypes.MicroPdf417` of een ander GS1‑compatibel type. |
| **Ontbrekende NuGet‑referentie** | Compile‑time fouten zoals `The type or namespace name 'Aspose' could not be found`. | Installeer het `Aspose.BarCode`‑pakket via NuGet. |

## Voorbeeld uitbreiden

* **Verschillende afbeeldingsformaten** – Vervang `BarCodeImageFormat.Png` door `Jpeg`, `Gif` of `Bmp` als je een ander formaat nodig hebt.
* **Hogere resolutie‑output** – Stel `generator.Parameters.ImageResolution.DpiX` en `DpiY` in vóór het opslaan.
* **Inbedden in PDF** – Gebruik `Aspose.Pdf` om de PNG in een PDF‑factuur of -etiket te plaatsen.

## Conclusie

Je weet nu hoe je **barcode GS1** kunt maken in C# met de Aspose.BarCode `BarcodeGenerator`, **barcode‑PNG kunt genereren**, en **barcode‑afbeelding kunt exporteren** naar het bestandssysteem. De gids behandelde elke stap — van het initialiseren van de generator met GS1‑data, het aanpassen van de X‑dimension, tot het opslaan van het uiteindelijke PNG‑bestand — en ging in op veelvoorkomende fouten en bood uitbreidingsideeën.

Voel je vrij om te experimenteren met andere GS1‑Application Identifiers, verschillende barcode‑symbologieën, of afbeeldingen met hogere resolutie. Zodra je deze basis beheerst, wordt het genereren van conforme barcodes voor voorraad, verzending of detailhandel een routineonderdeel van je .NET‑gereedschapskist.

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [GS1‑barcode‑afbeeldingen maken in C# – Hoe barcode C# snel te genereren](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [Barcode PNG maken in C# – stapsgewijze gids](/barcode/english/python-java/general/create-barcode-png-in-c-step-by-step-guide/)
- [Barcode‑afbeelding maken in C# – volledige programmeergids](/barcode/english/python-java/general/create-barcode-image-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}