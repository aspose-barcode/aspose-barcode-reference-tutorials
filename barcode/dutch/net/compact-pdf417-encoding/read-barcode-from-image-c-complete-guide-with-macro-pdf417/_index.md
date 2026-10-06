---
category: general
date: 2026-10-05
description: Barcode lezen van afbeelding in C# met Aspose.BarCode. Leer stapsgewijs
  C# barcode‑scanning, decodeer Macro PDF417 en verwerk uitgebreide eigenschappen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image c#
- C# barcode scanning
- Macro PDF417 decoding
- Aspose.BarCode for .NET
- decode barcode image C#
language: nl
lastmod: 2026-10-05
og_description: Barcode lezen van afbeelding C# met Aspose.BarCode. Deze tutorial
  laat zien hoe je een Macro PDF417-barcode scant, uitgebreide velden ophaalt en meerdere
  codes verwerkt.
og_image_alt: Screenshot of C# console output showing barcode type and Macro PDF417
  properties
og_title: Barcode lezen van afbeelding C# – volledige stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Read barcode from image C# using Aspose.BarCode. Learn step‑by‑step
    C# barcode scanning, decode Macro PDF417 and handle extended properties.
  headline: Read barcode from image C# – complete guide with Macro PDF417
  type: TechArticle
tags:
- barcode
- C#
- image-processing
title: Barcode lezen uit afbeelding C# – volledige gids met Macro PDF417
url: /nl/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lees barcode van afbeelding C# – volledige gids met Macro PDF417

Als je een **barcode van afbeelding C#** moet lezen, laat deze tutorial je een kant‑klaar werkende oplossing zien. Met behulp van de Aspose.BarCode for .NET bibliotheek decodeer je een Macro PDF417 barcode, haal je de basisgegevens eruit, en haal je elke uitgebreide eigenschap op die het formaat biedt.

Barcodes lezen van afbeeldingen is een veelvoorkomende eis—of je nu een ticket‑validatiesysteem bouwt, verzendlabels verwerkt, of metadata uit gescande documenten haalt. In de onderstaande stappen zie je waarom de `BarCodeReader`‑klasse de aanbevolen aanpak is, hoe je deze configureert voor Macro PDF417, en wat je met de resultaten doet.

---

## Wat je zult leren

* Installeer en verwijs naar **Aspose.BarCode for .NET** (de bibliotheek die het voorbeeld aandrijft).  
* Maak een `BarCodeReader` geconfigureerd voor **Macro PDF417 decodering**.  
* Loop over alle barcodes in een afbeelding en geef zowel standaard- als uitgebreide velden weer.  
* Verwerk meerdere barcodes, beheer resources correct, en los veelvoorkomende valkuilen op.

**Voorvereisten**

* .NET 6.0 SDK of later (de code werkt ook met .NET Framework 4.6+).  
* Basiskennis van C# console‑applicaties.  
* Een afbeeldingsbestand dat een Macro PDF417 barcode bevat (bijv. `ExtPDF417Meta.png`).  

---

## Stap 1: Voeg Aspose.BarCode toe aan je project (C# barcode scanning)

1. Open een terminal in je solution‑map.  
2. Voer het NuGet‑commando uit:

```bash
dotnet add package Aspose.BarCode
```

Het pakket bevat de `BarCodeReader`‑klasse, de `DecodeType`‑enumeratie, en het `BarCodeResult`‑object dat door de hele tutorial wordt gebruikt.

> **Pro tip:** Als je .NET Framework target, gebruik dan de Package Manager Console in Visual Studio:  
> `Install-Package Aspose.BarCode`

---

## Stap 2: Stel het console‑programma in (decode barcode image C#)

Maak een nieuw console‑project aan (of voeg de code toe aan een bestaand project):

```csharp
using System;
using Aspose.BarCode;               // Core namespace
using Aspose.BarCode.BarCodeRecognition; // For DecodeType and BarCodeReader

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image that contains a Macro PDF417 barcode.
            const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Step 2.1: Initialise the BarCodeReader for Macro PDF417.
            using (BarCodeReader barcodeReader = new BarCodeReader(
                       imagePath, DecodeType.MacroPdf417))
            {
                // Step 2.2: Read every barcode present in the image.
                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    // Step 2.3: Output basic information.
                    Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
                    Console.WriteLine($"CodeText: {barcodeResult.CodeText}");

                    // Step 2.4: Output Macro PDF417 extended properties.
                    PrintMacroPdf417Properties(barcodeResult);
                }
            }

            // Keep console window open for inspection.
            Console.WriteLine("\nPress any key to exit...");
            Console.ReadKey();
        }

        /// <summary>
        /// Writes all Macro PDF417 extended fields to the console.
        /// </summary>
        /// <param name="result">Result object returned by BarCodeReader.</param>
        private static void PrintMacroPdf417Properties(BarCodeResult result)
        {
            // The Extended property is null if the barcode type does not support it.
            if (result?.Extended?.Pdf417 == null)
            {
                Console.WriteLine("No Macro PDF417 extended data available.");
                return;
            }

            var macro = result.Extended.Pdf417;
            Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
            Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
            Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
            Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
            Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
            Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
            Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
            Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
            Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
            Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
        }
    }
}
```

### Waarom deze structuur?

* **`using` statement** – garandeert dat de `BarCodeReader` native resources vrijgeeft (belangrijk voor grote afbeeldingen).  
* **`DecodeType.MacroPdf417`** – vertelt de bibliotheek specifiek naar Macro PDF417 te zoeken; andere types (bijv. QR, Code128) zouden de uitgebreide velden negeren.  
* **`ReadBarCodes()`** – retourneert een enumerable, waardoor je **meerdere barcodes** in dezelfde afbeelding kunt verwerken zonder extra code.  
* **Aparte `PrintMacroPdf417Properties`‑methode** – isoleert de logica voor uitgebreide velden, waardoor de hoofdloop makkelijker te lezen is en toekomstig onderhoud wordt vereenvoudigd.

---

## Stap 3: Voer het programma uit en controleer de output (Macro PDF417 decodering)

Open een opdrachtprompt, navigeer naar de projectmap, en voer uit:

```bash
dotnet run
```

Je zou een output moeten zien die lijkt op het volgende (waarden zullen verschillen afhankelijk van de daadwerkelijke barcode):

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 3
Pdf417MacroSegmentsCount: 5
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B3C4D
Pdf417MacroFileSize: 1048576
Pdf417MacroTimeStamp: 2023-08-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True

Press any key to exit...
```

Als de afbeelding geen Macro PDF417 barcode bevat, zal de console **“No Macro PDF417 extended data available.”** weergeven. Deze nette afhandeling voorkomt null‑reference‑exceptions.

---

## Stap 4: Veelvoorkomende variaties en randgevallen (C# barcode scanning tips)

| Situatie | Aanbevolen aanpassing |
|-----------|------------------------|
| **Meerdere barcode‑types in één afbeelding** | Initialiseer de reader met `DecodeType.AllSupported` en inspecteer `barcodeResult.CodeTypeName` om de logica te vertakken. |
| **Grote afbeeldingen (≥10 MP)** | Verhoog `barcodeReader.Options.MaxBarCodeCount` of gebruik `barcodeReader.SetResolution(300)` om de detectiesnelheid te verbeteren. |
| **Ontbrekende uitgebreide velden** | Sommige scanners verwijderen Macro‑data; controleer met een barcode‑inspectietool of de bronafbeelding de velden bevat voordat je codeert. |
| **Uitvoeren op Linux/macOS** | Zorg ervoor dat de native binaries voor Aspose.BarCode aanwezig zijn (`Aspose.BarCode.Native` NuGet‑pakket) of stel `Environment.SetEnvironmentVariable("DOTNET_SYSTEM_GLOBALIZATION_INVARIANT", "1")` in als je alleen ASCII‑data nodig hebt. |
| **Prestatie‑kritieke loops** | Cache de `BarCodeReader`‑instantie en hergebruik deze voor een batch afbeeldingen; dispose pas na het voltooien van de batch. |

---

## Stap 5: Samenvatting en volgende stappen (read barcode from image C#)

Je hebt nu een **volledige, zelfstandige oplossing** om een Macro PDF417 barcode van een afbeelding te lezen in C#. Het voorbeeld toont:

* Correcte **installatie** van de Aspose.BarCode‑bibliotheek.  
* Aanmaak van een **`BarCodeReader`** geconfigureerd voor **Macro PDF417**.  
* Iteratie over **alle barcodes** in de meegeleverde afbeelding.  
* Extractie van **standaard** (`CodeTypeName`, `CodeText`) **en uitgebreide** Macro PDF417‑metadata.  

### Wat kun je hierna verkennen?

* **Decodeer andere formaten** – vervang `DecodeType.MacroPdf417` door `DecodeType.QR`, `DecodeType.Code128`, enz.  
* **Integreer met ASP.NET Core** – exposeer een Web API‑endpoint die afbeeldingsuploads accepteert en JSON met barcode‑data teruggeeft.  
* **Bewaar resultaten** – sla de geëxtraheerde metadata op in een database voor latere analyses.  
* **Combineer met OCR** – gebruik Aspose.OCR om tekst te lezen die niet als barcode is gecodeerd.

Voel je vrij om te experimenteren met de voorbeeldafbeelding, het bestandspad aan te passen, of de logica in een grotere applicatie te integreren. De **`BarCodeReader`**‑klasse biedt een robuuste basis voor elk **C# barcode scanning**‑scenario.

--- 

*Veel plezier met coderen! Als je problemen tegenkomt, controleer dan dubbel of de afbeelding echt een Macro PDF417 barcode bevat en of de Aspose.BarCode‑versie overeenkomt met je .NET‑runtime.*

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Barcode lezen van afbeelding in C# – BarCodeReader tutorial](/barcode/english/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/)
- [Hoe PDF417 barcode afbeelding te genereren in C# met Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}