---
category: general
date: 2026-11-23
description: Leer hoe u een barcode‑afbeelding genereert met Aspose.BarCode voor .NET
  met MacroPdf417‑metadata in C#. Volg de volledige stap‑voor‑stap‑handleiding.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode image
- MacroPdf417 barcode
- Aspose.BarCode for .NET
- set barcode metadata
- barcode image format
- C# barcode generation
language: nl
lastmod: 2026-11-23
og_description: Hoe een barcode‑afbeelding te genereren met Aspose.BarCode voor .NET.
  Deze tutorial toont de configuratie van MacroPdf417‑metadata en C#‑barcodegeneratie.
og_image_alt: Barcode image generated with MacroPdf417 using C#
og_title: Hoe een barcode‑afbeelding te genereren met MacroPdf417 in C#
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  headline: How to generate barcode image with MacroPdf417 in C#
  type: TechArticle
- description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  name: How to generate barcode image with MacroPdf417 in C#
  steps:
  - name: Open a terminal or the Package Manager Console in Visual Studio.
    text: Open a terminal or the Package Manager Console in Visual Studio.
  - name: 'Run the following command:'
    text: 'Run the following command:'
  - name: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
    text: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
  - name: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
    text: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- PDF417
title: Hoe een barcode‑afbeelding genereren met MacroPdf417 in C#
url: /nl/net/compact-pdf417-encoding/how-to-generate-barcode-image-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een barcode‑afbeelding te genereren met MacroPdf417 in C#

Als je een **barcode‑afbeelding** moet **genereren** in een .NET‑applicatie, laat deze gids je precies zien hoe je dat doet met **Aspose.BarCode for .NET**. We lopen stap voor stap door het maken van een **MacroPdf417‑barcode**, het configureren van de metadata en het opslaan van het resultaat als een PNG‑bestand.

Deze tutorial behandelt alles, van het installeren van de bibliotheek tot het schrijven van een compleet, uitvoerbaar console‑programma. Aan het einde heb je een kant‑klaar code‑voorbeeld dat een hoogwaardige barcode‑afbeelding produceert, en begrijp je hoe je **barcode‑metadata instelt**, een **barcode‑afbeeldingsformaat kiest** en veelvoorkomende valkuilen oplost. Er is geen eerdere ervaring met Aspose vereist—alleen een basiskennis van C#.

## Installeer Aspose.BarCode for .NET

Voordat je **barcode‑afbeelding kunt genereren**, heb je het Aspose.BarCode‑NuGet‑pakket nodig.

1. Open een terminal of de Package Manager Console in Visual Studio.  
2. Voer het volgende commando uit:

```bash
dotnet add package Aspose.BarCode
```

Het pakket voegt de `Aspose.BarCode.Generation`‑namespace toe, die de `BarcodeGenerator`‑klasse bevat die wordt gebruikt voor **C# barcode‑generatie**.

> **Pro tip:** Gebruik de nieuwste stabiele versie (vanaf november 2026 is de huidige versie 24.11) om de nieuwste functies en bug‑fixes te krijgen.

## Maak de BarcodeGenerator‑instantie

De eerste code‑stap maakt een `BarcodeGenerator` aan die is geconfigureerd voor het **MacroPdf417‑barcode**‑type en de gegevensreeks levert die je wilt coderen.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a BarcodeGenerator for MacroPdf417 with the desired text
            using (BarcodeGenerator barcodeGenerator =
                   new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Subsequent configuration goes here...
```

Het `using`‑blok zorgt ervoor dat de generator correct wordt vrijgegeven, waardoor eventuele unmanaged resources worden vrijgelaten.

## Configureer basis­uiterlijk

Een leesbare barcode begint met verstandige afmetingen. Hier stellen we de pixelbreedte van elke module (`XDimension`) en het aantal kolommen voor de PDF417‑matrix in.

```csharp
                // Step 2: Set basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel width of a module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

*Waarom deze waarden?*  
- **XDimension** bepaalt hoe dik elke balk verschijnt; 2 pixels werkt goed voor weergave op schermen en de meeste printers.  
- **Columns** beïnvloeden de totale breedte; een klein aantal kolommen houdt de barcode compact terwijl de fout‑correctiecapaciteit behouden blijft.

## Stel barcode‑metadata in (MacroPdf417‑specifiek)

MacroPdf417 maakt het mogelijk om bestands‑niveau‑informatie direct in de barcode te embedden. Hier stel je **barcode‑metadata** in, zoals bestand‑ID, segment‑ID en tijdstempels.

```csharp
                // Step 3: Configure MacroPdf417 specific metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### Wat elke eigenschap betekent

| Eigenschap | Doel |
|------------|------|
| **MacroPdf417FileID** | Unieke identifier voor het logische bestand waartoe de barcode behoort. |
| **MacroPdf417SegmentID** | Index van het huidige segment (0‑gebaseerd). |
| **MacroPdf417SegmentsCount** | Totaal aantal segmenten waaruit het volledige bestand bestaat. |
| **MacroPdf417FileName** | Menselijk leesbare naam van het bronbestand. |
| **MacroPdf417Checksum** | Optionele CCITT‑16‑checksum voor verificatie van gegevensintegriteit. |
| **MacroPdf417FileSize** | Verwachte grootte van het originele bestand in bytes. |
| **MacroPdf417TimeStamp** | Datum en tijd waarop de barcode werd gegenereerd – nuttig voor versie‑tracking. |
| **MacroPdf417Addressee / Sender** | Aangepaste strings die routing‑informatie kunnen bevatten. |
| **MacroPdf417Terminator** | Geeft aan of dit segment het laatste is (`Set`) of niet (`Unset`). |

> **Randgeval:** Als je een groot document in veel segmenten wilt opsplitsen, houd dan de `SegmentsCount` consistent in alle gegenereerde barcodes. Niet‑overeenkomende aantallen veroorzaken decodeer‑fouten.

## Kies het barcode‑afbeeldingsformaat en sla op

Aspose ondersteunt veel **barcode‑afbeeldingsformaten** (PNG, JPEG, BMP, TIFF, enz.). PNG is verlies­vrij en werkt goed voor de meeste web‑ en printscenario’s.

```csharp
                // Step 4: Save the generated barcode image
                string outputPath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode image saved to: {outputPath}");
            } // end using
        }
    }
}
```

Vervang `YOUR_DIRECTORY` door een absolute of relatieve map waarin de applicatie schrijfrechten heeft.

Wanneer het programma wordt uitgevoerd, zie je een console‑bericht dat de bestandslocatie bevestigt. Open het PNG‑bestand met een willekeurige afbeeldingsviewer—je ziet een scherpe **MacroPdf417‑barcode** die de opgegeven tekst en de metadata die je hebt gedefinieerd, codeert.

### Verwachte output

```
Barcode image saved to: C:\Projects\BarcodeDemo\ExtPDF417Meta.png
```

De bestandsgrootte van de afbeelding zal ongeveer 30‑40 KB bedragen, afhankelijk van de gekozen `XDimension` en het aantal kolommen.

## Controleer de barcode en los problemen op

1. **Visuele inspectie** – De barcode moet een reeks gestapelde kolommen tonen met een stille zone (witte marge) eromheen.  
2. **Decodeertest** – Gebruik een barcode‑scanner‑app of de Aspose.BarCode `BarCodeReader`‑klasse om de afbeelding terug te lezen en te bevestigen dat alle metadata‑velden correct zijn ingebed.  



## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Generate PDF417 barcode image with Aspose.BarCode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-barcode-image-with-pdf417-in-c-step-by-step-gu/)
- [How to generate barcode with custom text using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/)
- [How to read barcodes from image using C# with Aspose.BarCode – step‑by‑step guide](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}