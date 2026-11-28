---
category: general
date: 2026-11-27
description: hoe je een pdf417‑barcode in C# van een afbeelding leest met Aspose.BarCode
  – stapsgewijze handleiding met volledig codevoorbeeld en tips voor probleemoplossing
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode from image c#
- C# barcode decoding
- BarCodeReader class
- DecodeType.MacroPdf417
- BarCodeResult properties
language: nl
lastmod: 2026-11-27
og_description: hoe pdf417-barcode snel lezen in C#. Leer PDF417-barcodes decoderen
  uit afbeeldingen met Aspose.BarCode, volledige code en best practices.
og_image_alt: Console output showing how to read PDF417 barcode in C#
og_title: Hoe PDF417‑barcode lezen in C# – stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: how to read pdf417 barcode in C# from an image using Aspose.BarCode
    – step‑by‑step guide with full code example and troubleshooting tips.
  headline: How to read PDF417 barcode in C# – complete programming guide
  type: TechArticle
- description: how to read pdf417 barcode in C# from an image using Aspose.BarCode
    – step‑by‑step guide with full code example and troubleshooting tips.
  name: How to read PDF417 barcode in C# – complete programming guide
  steps:
  - name: Create a new console project
    text: 'Open a terminal (or PowerShell) and run:'
  - name: Install the Aspose.BarCode NuGet package
    text: 'Aspose.BarCode provides the `BarCodeReader` class used in the example.
      Install it with:'
  - name: Add the code shown above
    text: Replace the content of `Program.cs` with the full snippet from the previous
      section. The code demonstrates **C# barcode decoding** and shows how to access
      **BarCodeResult properties** such as `CodeTypeName`, `CodeText`, and the macro‑specific
      `MacroPdf417FileID`.
  - name: Run the application
    text: '```bash dotnet run ```'
  - name: Handle multiple barcodes and error cases
    text: 'Real‑world images may hold more than one barcode or none at all. Wrap the
      reading logic in a `try`/`catch` block to surface parsing errors, and check
      `reader.HasBarcodes` before iterating:'
  - name: Optional – Decode other barcode types from the same image
    text: 'If you later need to **read barcode from image c#** for other symbologies,
      simply change the `DecodeType` argument:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Hoe PDF417-barcode te lezen in C# – volledige programmeergids
url: /nl/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417-barcode lezen in C# – volledige programmeergids

Als je **hoe je een pdf417-barcode** van een afbeelding moet lezen, toont deze gids je de exacte stappen. Met Aspose.BarCode voor .NET kun je een PDF417-barcode decoderen met één methodeaanroep, en de gids leidt je door elke benodigde regel code.

Het lezen van een barcode van een afbeelding is een veelvoorkomende taak bij het bouwen van voorraadscanners, ticketvalidatiesystemen of documentverwerkingspijplijnen. In deze tutorial leer je hoe je de omgeving instelt, het benodigde pakket installeert en een robuust C#‑programma schrijft dat een PDF417‑barcode leest en de uitgebreide gegevensvelden extraheert. Er zijn geen externe services nodig; alles draait lokaal.

> **Prerequisites**  
> • .NET 6.0 SDK of later geïnstalleerd  
> • Basiskennis van C# en console‑applicaties  
> • Toegang tot een afbeeldingsbestand dat een PDF417 (of Macro PDF417) barcode bevat  

We behandelen ook **read barcode from image c#**‑alternatieven, leggen de meest bruikbare eigenschappen van het `BarCodeResult`‑object uit, en geven je tips voor het verwerken van meerdere barcodes in één afbeelding.

---

## Hoe PDF417-barcode lezen van een afbeelding in C#

De eerste belangrijke stap is het maken van een `BarCodeReader` die naar het afbeeldingsbestand wijst en de bibliotheek vertelt naar welk barcode‑type gezocht moet worden. Door `DecodeType.MacroPdf417` op te geven, beperk je de scan tot PDF417‑varianten, wat snelheid en nauwkeurigheid verbetert.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image that contains the PDF417 barcode
            string imagePath = @"C:\Barcodes\Pdf417Sample.png";

            // Initialize the reader for Macro PDF417 barcodes
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate through all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // Macro PDF417 specific extended information
                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID : {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    // Show confidence and symbology details
                    Console.WriteLine($"Code Confidence : {result.CodeTextConfidence}");
                    Console.WriteLine($"Is Mirror Image : {result.IsMirrored}");
                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

**Why this works** – De `BarCodeReader`‑constructor ontvangt het pad naar de afbeelding en een `DecodeType`. `MacroPdf417` vertelt de engine om naar de PDF417‑familie te zoeken, inclusief de macro‑extensie die extra metadata draagt, zoals de bestands‑ID. De `ReadBarCodes()`‑methode retourneert een enumerable van `BarCodeResult`‑objecten, elk een gedetecteerde barcode representerend.

### Stap 1: Maak een nieuw console‑project

Open een terminal (of PowerShell) en voer uit:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Het aanmaken van een nieuw project isoleert de demo en garandeert dat het `csproj`‑bestand alleen de afhankelijkheden bevat die je vervolgens toevoegt.

### Stap 2: Installeer het Aspose.BarCode NuGet‑pakket

Aspose.BarCode levert de `BarCodeReader`‑klasse die in het voorbeeld wordt gebruikt. Installeer het met:

```bash
dotnet add package Aspose.BarCode --version 23.12
```

Het pakket bevat ondersteuning voor alle 1D‑ en 2D‑symbologieën, inclusief PDF417 en de macro‑variant.

### Stap 3: Voeg de hierboven getoonde code toe

Vervang de inhoud van `Program.cs` door de volledige snippet uit de vorige sectie. De code demonstreert **C# barcode decoding** en toont hoe je **BarCodeResult‑eigenschappen** zoals `CodeTypeName`, `CodeText` en de macro‑specifieke `MacroPdf417FileID` kunt benaderen.

### Stap 4: Voer de applicatie uit

```bash
dotnet run
```

Bevat de afbeelding een leesbare PDF417‑barcode, dan geeft de console iets vergelijkbaars weer:

```
Code Type : PDF417
Code Text : https://example.com/invoice/12345
Macro PDF417 File ID : 7
Code Confidence : 98.7
Is Mirror Image : False
----------------------------------------
```

Bevat de afbeelding geen PDF417‑barcode, dan eindigt de lus simpelweg zonder iets af te drukken.

### Stap 5: Meerdere barcodes en foutgevallen afhandelen

Afbeeldingen uit de praktijk kunnen meer dan één barcode bevatten of helemaal geen. Plaats de leeslogica in een `try`/`catch`‑blok om parse‑fouten zichtbaar te maken, en controleer `reader.HasBarcodes` voordat je iterereert:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    if (!reader.HasBarcodes)
    {
        Console.WriteLine("No PDF417 barcodes detected.");
        return;
    }

    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // existing processing code...
    }
}
```

**Pro tip:** Pas de `Resolution`‑eigenschap van de `BarCodeReader` aan (bijv. `reader.Resolution = 300;`) bij lage‑resolutie‑scans. Een hogere resolutie verbetert de detectie, maar kan het CPU‑gebruik verhogen.

### Stap 6: Optioneel – Andere barcode‑types uit dezelfde afbeelding decoderen

Moet je later **read barcode from image c#** voor andere symbologieën gebruiken, wijzig dan simpelweg het `DecodeType`‑argument:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupportedTypes))
{
    // This will detect QR, Code128, DataMatrix, etc.
}
```

Dezelfde `BarCodeResult`‑klasse werkt voor elk type, zodat je de verwerkingslus zonder wijziging kunt hergebruiken.

---

## Inzicht in de belangrijkste klassen

| Klasse | Doel | Meest bruikbare leden |
|--------|------|------------------------|
| `BarCodeReader` | Opent een afbeelding en scant op barcodes | `ReadBarCodes()`, `HasBarcodes`, `Resolution` |
| `BarCodeResult` | Bevat informatie over een enkele gedetecteerde barcode | `CodeTypeName`, `CodeText`, `CodeTextConfidence`, `Extended` |
| `Extended.Pdf417` | Biedt macro‑specifieke gegevens voor PDF417 | `MacroPdf417FileID`, `MacroPdf417SegmentCount`, `MacroPdf417SegmentIndex` |

Kennis van deze leden stelt je in staat niet alleen de mens‑leesbare tekst, maar ook de gestructureerde metadata die Macro PDF417 embedt, te extraheren – vaak vereist voor batch‑verwerking van meer‑pagina‑documenten.

---

## Veelvoorkomende valkuilen en hoe ze te vermijden

* **Incorrect `DecodeType`** – Het gebruik van `DecodeType.Pdf417` in plaats van `MacroPdf417` mist macro‑extensies. Kies het exacte type dat overeenkomt met jouw barcode.  
* **Niet‑ondersteund afbeeldingsformaat** – Aspose.BarCode leest PNG, JPEG, BMP, TIFF en GIF. Heb je een RAW‑afbeelding, converteer die dan eerst.  
* **Lage beeldcontrast** – Pre‑process de afbeelding (verhoog contrast of binariseer) voordat je deze aan `BarCodeReader` doorgeeft. De bibliotheek biedt ook `reader.ImageProcessingOptions`.  
* **Grote bestanden** – Voor zeer hoge resolutie‑scans, stel `reader.MaxBarcodesPerPage` in om het geheugenverbruik te beperken.

---

## Conclusie

Je weet nu **hoe je een pdf417-barcode** in C# kunt lezen met Aspose.BarCode, van project‑setup tot het afhandelen van macro‑specifieke velden. Het volledige, uitvoerbare voorbeeld demonstreert **C# barcode decoding**, laat zien hoe je **BarCodeResult‑eigenschappen** benadert, en geeft je praktische tips voor robuuste scanning.  

Vervolgens kun je gerelateerde onderwerpen verkennen, zoals **read barcode from image c#** voor QR‑codes, barcode‑lezen integreren in ASP.NET Core‑API’s, of experimenteren met batch‑verwerking van meerdere afbeeldingen. Dezelfde `BarCodeReader`‑klasse werkt voor alle ondersteunde symbologieën, zodat je deze oplossing kunt uitbreiden naar elke barcode die je applicatie tegenkomt.

Happy coding, en voel je vrij om het voorbeeld aan te passen aan je eigen workflow!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe macro PDF417-barcode lezen in C# met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-macro-pdf417-barcode-in-c-with-aspose-barcode/)
- [Hoe PDF417-barcode lezen in C# – volledige barcode‑lezer gids](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-full-barcode-reader-guide/)
- [Hoe PDF417-barcode maken met Aspose – Complete stapsgewijze gids](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}