---
category: general
date: 2026-11-23
description: Leer hoe je BarCodeReader in C# kunt gebruiken om barcodes van een afbeelding
  te lezen, inclusief Macro PDF417‑decodering, met een volledig codevoorbeeld en duidelijke
  uitleg.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use barcodereader
- read barcodes from image c#
language: nl
lastmod: 2026-11-23
og_description: Hoe je BarCodeReader in C# gebruikt om barcodes van een afbeelding
  te lezen. Volg deze stapsgewijze handleiding om Macro PDF417 en andere formaten
  te decoderen met kant‑klaar code.
og_image_alt: Screenshot of BarCodeReader console output showing decoded Macro PDF417
  data
og_title: Hoe BarCodeReader in C# te gebruiken – lees barcodes snel uit afbeeldingen
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  headline: How to use BarCodeReader in C# to read barcodes from images
  type: TechArticle
- description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  name: How to use BarCodeReader in C# to read barcodes from images
  steps:
  - name: 1. Decoding multiple barcode formats
    text: 'If you need to detect more than one format, pass a combined `DecodeType`
      flag:'
  - name: 2. Managing large images
    text: 'Large images can cause high memory usage. Downscale the image before passing
      it to the reader:'
  - name: 3. Error handling
    text: 'Wrap the reading logic in a try‑catch block to surface decoding failures:'
  type: HowTo
tags:
- barcode
- C#
- image-processing
title: Hoe BarCodeReader in C# te gebruiken om barcodes uit afbeeldingen te lezen
url: /nl/net/compact-pdf417-encoding/how-to-use-barcodereader-in-c-to-read-barcodes-from-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe BarCodeReader in C# te gebruiken om barcodes uit afbeeldingen te lezen

Als je **how to use BarCodeReader** nodig hebt voor een snelle barcodescan, laat deze gids je precies dat zien. Of je nu een point‑of‑sale‑systeem bouwt of documentinvoer automatiseert, je leert hoe je barcodes uit afbeeldingen in C#‑projecten kunt lezen met slechts een paar regels code.

In deze tutorial zie je een volledig, uitvoerbaar voorbeeld dat een Macro PDF417‑barcode decodeert, de uitgebreide eigenschappen ervan extraheert en nuttige informatie naar de console print. Er is geen externe documentatie nodig – alles wat je nodig hebt staat hier.

## Vereisten

* .NET 6.0 (of later) geïnstalleerd – de code richt zich op de nieuwste LTS‑versie.
* Een referentie naar het **Aspose.BarCode** (of een compatibel) NuGet‑pakket dat `BarCodeReader` levert.
* Een afbeeldingsbestand dat een Macro PDF417‑barcode bevat (het voorbeeld gebruikt `ExtPDF417Meta.png`).

> **Pro tip:** Als je Visual Studio gebruikt, voeg je het pakket toe via `dotnet add package Aspose.BarCode` of de NuGet Package Manager UI.

## Stap 1: Maak een BarCodeReader‑instantie

Het eerste wat je doet bij het werken met een barcode‑bibliotheek is een lezer instantieren die naar de bronafbeelding wijst en de API vertelt naar welk(e) barcode‑type(s) gezocht moet worden.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Step 1: Initialise BarCodeReader for a Macro PDF417 image
using (BarCodeReader barcodeReader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png",
           DecodeType.MacroPdf417))
{
    // The using block guarantees proper disposal of native resources.
```

*Waarom deze stap belangrijk is:*  
`BarCodeReader` opent de afbeelding, reserveert native geheugen en bereidt decodeeralgoritmen voor het opgegeven `DecodeType` voor. Door het type te beperken tot `MacroPdf417`, verminder je de CPU‑belasting en verbeter je de detectienauwkeurigheid.

## Stap 2: Lees alle barcodes die in de afbeelding zijn gevonden

Een enkele afbeelding kan meerdere barcodes bevatten, vooral bij macro‑gecodeerde data. De `ReadBarCodes`‑methode retourneert een enumerable van `BarCodeResult`‑objecten, elk een gedetecteerde code representerend.

```csharp
    // Step 2: Iterate over every barcode found
    foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
    {
```

*Waarom deze stap belangrijk is:*  
Itereren over de collectie zorgt ervoor dat je elke instantie vastlegt, wat essentieel is voor batch‑verwerkingsscenario's of wanneer een document meerdere codes bevat.

## Stap 3: Toegang tot de uitgebreide Macro PDF417‑eigenschappen

Macro PDF417 slaat extra metadata op zoals bestandsidentifiers, segmentnummers en het totale aantal segmenten. Deze waarden worden blootgesteld via de `Extended.Pdf417`‑eigenschap van `BarCodeResult`.

```csharp
        // Step 3: Pull extended Macro PDF417 information
        var macroInfo = barcodeResult.Extended.Pdf417;
```

*Waarom deze stap belangrijk is:*  
De uitgebreide velden stellen je in staat om multi‑segment‑documenten te reconstrueren of te valideren dat alle delen tot dezelfde bron behoren. Als je deze stap overslaat, krijg je alleen de ruwe tekst, waardoor waardevolle context verloren gaat.

## Stap 4: Output de meest bruikbare informatie

Schrijf tenslotte de gegevens naar de console (of een logger) zodat je de leesoperatie kunt verifiëren. Het voorbeeld print het code‑type, de gedecodeerde tekst en verschillende macro‑velden.

```csharp
        // Step 4: Display key details
        Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
        Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
        Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
        // Additional macro fields are available:
        // macroInfo.MacroPdf417SegmentID
        // macroInfo.MacroPdf417SegmentsCount
    }
}
```

**Verwachte console‑output**

```
Code Type: MacroPdf417
Code Text: 1234567890
Macro PDF417 File ID: 42
```

> **Opmerking:** Als de afbeelding geen Macro PDF417‑barcode bevat, retourneert `ReadBarCodes()` een lege collectie en wordt de luslichaam nooit uitgevoerd. Controleer altijd op een leeg resultaat in productiecodel.

## Barcodes lezen uit afbeelding in C# – veelvoorkomende scenario's afhandelen

### 1. Meerdere barcode‑formaten decoderen

Als je meer dan één formaat moet detecteren, geef je een gecombineerde `DecodeType`‑vlag door:

```csharp
using (BarCodeReader reader = new BarCodeReader(
           "sample.png",
           DecodeType.Pdf417 | DecodeType.QR | DecodeType.DataMatrix))
{
    // Same iteration logic as before
}
```

### 2. Grote afbeeldingen beheren

Grote afbeeldingen kunnen veel geheugen verbruiken. Schaal de afbeelding naar beneden voordat je deze aan de lezer doorgeeft:

```csharp
using (Bitmap original = new Bitmap("large.png"))
using (Bitmap resized = new Bitmap(original, new Size(1024, 768)))
{
    // Save resized image to a temporary stream and feed it to BarCodeReader
}
```

### 3. Foutafhandeling

Omhul de leeslogica in een try‑catch‑blok om decodeerfouten zichtbaar te maken:

```csharp
try
{
    // reading code from previous steps
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Volledig werkend voorbeeld

Hieronder staat het volledige programma dat je kunt kopiëren, plakken en uitvoeren. Het bevat alle stappen, benodigde `using`‑directieven en een eenvoudige foutafhandelingsstructuur.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(
                       imagePath,
                       DecodeType.MacroPdf417))
            {
                bool anyFound = false;

                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    anyFound = true;
                    var macroInfo = barcodeResult.Extended.Pdf417;

                    Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
                    Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
                    Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {macroInfo.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments Count: {macroInfo.MacroPdf417SegmentsCount}");
                    Console.WriteLine(new string('-', 40));
                }

                if (!anyFound)
                {
                    Console.WriteLine("No barcodes were detected in the image.");
                }
            }
        }
        catch (BarCodeException ex)
        {
            Console.Error.WriteLine($"Error reading barcode: {ex.Message}");
        }
    }
}
```

**Het uitvoeren van het programma** print elke gedetecteerde Macro PDF417‑barcode en de bijbehorende uitgebreide velden, of informeert je dat er geen barcodes zijn gevonden.

## Conclusie

Je weet nu **how to use BarCodeReader** om barcodes uit afbeelding‑C#‑applicaties te lezen, inclusief het extraheren van Macro PDF417‑metadata. De oplossing behandelt initialisatie, iteratie, toegang tot uitgebreide eigenschappen en praktische tips voor het afhandelen van meerdere formaten, grote afbeeldingen en fouten.

Vervolgens kun je verkennen:

* **QR‑codes lezen** – vervang `DecodeType.MacroPdf417` door `DecodeType.QR`.
* **Gedecodeerde data opslaan** in een database of JSON‑bestand voor downstream verwerking.
* **Integreren met ASP.NET Core** om geüploade afbeeldingen via een web‑API te accepteren.

Voel je vrij om te experimenteren met verschillende barcode‑types en afbeeldingsbronnen. Veel plezier met coderen!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [c# barcode lezer tutorial – Macro PDF417 barcodes stap voor stap lezen met GroupDocs.Barcode](/barcode/english/net/compact-pdf417-encoding/c-barcode-reader-tutorial-read-macro-pdf417-barcodes-step-by/)
- [Hoe een barcode generator C# te gebruiken voor Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/)
- [Barcode lezen uit afbeelding C# – volledige gids met Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}