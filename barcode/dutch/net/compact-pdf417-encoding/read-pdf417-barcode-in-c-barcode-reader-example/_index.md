---
category: general
date: 2026-08-03
description: Lees PDF417-barcode van een afbeelding met C# BarCodeReader – een compleet
  barcode-leesvoorbeeld dat ook laat zien hoe meerdere barcodes gelezen kunnen worden.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read PDF417 barcode
- barcode reader example
- read multiple barcodes
- read barcodes image
language: nl
lastmod: 2026-08-03
og_description: Lees PDF417‑barcode snel met een C# BarCodeReader‑voorbeeld. Volg
  deze stap‑voor‑stap‑gids om macro PDF417 te decoderen en meerdere barcodes uit een
  afbeelding te lezen.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: PDF417‑barcode lezen in C# – compleet voorbeeld van een barcodelezer
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  headline: Read PDF417 barcode in C# – barcode reader example
  type: TechArticle
- description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  name: Read PDF417 barcode in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
title: PDF417‑barcode lezen in C# – voorbeeld van barcodelezer
url: /nl/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PDF417 barcode lezen in C# – barcode lezer voorbeeld

Als je PDF417 barcode‑gegevens uit een afbeelding moet lezen, laat deze gids zien hoe je dat doet met de **BarCodeReader**‑klasse in C#. Je leert een barcode‑lezer‑voorbeeld dat ook macro PDF417 afhandelt en meerdere barcodes in één afbeelding kan lezen.

Werken met barcodes betekent vaak omgaan met verschillende afbeeldingsbronnen, wisselende lichtomstandigheden en soms samengestelde gegevens zoals macro PDF417‑segmenten. Deze tutorial behandelt alles wat je nodig hebt om een PDF417‑barcode te decoderen, de uitgebreide velden te extraheren en meerdere barcodes uit dezelfde afbeelding te verwerken. Aan het einde heb je een uitvoerbaar console‑programma dat barcodes uit een afbeeldingsbestand leest en gedetailleerde informatie naar de console print.

## Wat je nodig hebt

Voordat je begint, zorg dat je het volgende hebt:

* .NET 6.0 SDK of later geïnstalleerd  
* Een recente versie van het **Aspose.BarCode for .NET** NuGet‑pakket (of een compatibele bibliotheek die `BarCodeReader` en `DecodeType.MacroPdf417` biedt)  
* Een afbeeldingsbestand dat een PDF417‑ of macro PDF417‑barcode bevat (het voorbeeld gebruikt `ExtPDF417Meta.png`)  
* Een code‑editor of IDE zoals Visual Studio 2022  

Er zijn geen extra services of externe API’s vereist.

## Het project instellen voor barcode‑lezen

1. **Maak een nieuw console‑project**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Voeg de barcode‑bibliotheek toe**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Kopieer de barcode‑afbeelding**  

   Plaats `ExtPDF417Meta.png` (of elke afbeelding die een PDF417‑barcode bevat) in de projectmap.  
   Voor deze tutorial gaan we ervan uit dat het bestand zich bevindt op `YOUR_DIRECTORY/ExtPDF417Meta.png`.

Het project is nu klaar om te compileren en het barcode‑lezer‑voorbeeld uit te voeren.

## Hoe PDF417 barcode lezen met BarCodeReader

De kern van de oplossing is een `using`‑blok dat een `BarCodeReader`‑instantie maakt, `DecodeType.MacroPdf417` specificeert en over elke gedetecteerde barcode iterereert. De volgende code is een compleet, zelfstandig programma dat je kunt plakken in `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Waarom dit werkt**:  

* `DecodeType.MacroPdf417` vertelt de lezer om te zoeken naar de macro‑extensie van PDF417, die extra metadata bevat zoals bestand‑ID, segment‑aantal en tijdstempels.  
* De `using`‑statement zorgt ervoor dat onbeheerste resources (bestandshandles, native decode‑buffers) direct worden vrijgegeven.  
* De `foreach`‑lus verwerkt automatisch **alle** barcodes die in de afbeelding aanwezig zijn, waardoor wordt voldaan aan de *meerdere barcodes lezen*‑vereiste.  

Wanneer je het programma uitvoert (`dotnet run`), zie je output die lijkt op het volgende:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

Bevat de afbeelding meer dan één PDF417‑barcode, dan print de lus een apart blok voor elke barcode, waarmee wordt aangetoond hoe je **meerdere barcodes** uit één afbeelding kunt **lezen**.

## Meerdere barcodes uit een afbeelding lezen

Dezelfde `BarCodeReader`‑instantie kan meerdere barcode‑typen tegelijk decoderen. Om de scope uit te breiden van alleen macro PDF417 naar elke PDF417 (of zelfs QR, Code128, enz.), pas je de `DecodeType`‑vlag aan:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* is een bitmasker, zodat je een willekeurig aantal ondersteunde formaten kunt combineren. Deze flexibiliteit maakt de snippet een **barcode lezer voorbeeld** dat werkt voor een breed scala aan use‑cases, zoals het scannen van productlabels, tickets of ID‑kaarten.

## Macro PDF417‑velden veilig benaderen

Macro PDF417 voegt een rijke set uitgebreide eigenschappen toe. Niet elke barcode bevat echter elk veld. Het benaderen van een ontbrekende eigenschap kan een `NullReferenceException` veroorzaken. De veiligste aanpak is om elke eigenschap te verifiëren voordat je deze afdrukt:

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Waarom dit belangrijk is*: In real‑world implementaties kun je gewone PDF417‑barcodes ontvangen die geen macro‑data bevatten. De defensieve controle zorgt ervoor dat je applicatie blijft draaien zonder te crashen.

## Veelvoorkomende valkuilen en best practices

| Probleem | Waarom het gebeurt | Aanbevolen oplossing |
|----------|--------------------|----------------------|
| Pad naar afbeelding is onjuist | `BarCodeReader` gooit een file‑not‑found‑exception voordat er gedecodeerd wordt | Gebruik `Path.Combine` en controleer of het bestand bestaat met `File.Exists` |
| Lage resolutie afbeelding | De decoder kan de barcode‑randen niet vinden, wat leidt tot nul detecties | Zorg voor een minimale resolutie van 300 dpi voor betrouwbare resultaten |
| Barcode gedraaid > 45° | Veel bibliotheken gaan uit van een rechtopstaande oriëntatie | Schakel `reader.RecognitionOptions.RotateImage = true` in als de afbeelding gedraaid kan zijn |

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Read Barcode from Image – Mastering Barcode Region Extraction in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}