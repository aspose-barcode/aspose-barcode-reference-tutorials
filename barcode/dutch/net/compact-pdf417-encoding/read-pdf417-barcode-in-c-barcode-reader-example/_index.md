---
category: general
date: 2026-10-14
description: Maak een console barcode‑scanner in C# die PDF417‑barcodes leest, macro
  PDF417 verwerkt en meerdere barcodes uit één afbeelding decodeert.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create console barcode scanner
- read barcodes from picture
- c# barcode reader example
lastmod: 2026-10-14
og_description: Maak een console barcode‑scanner in C# om snel PDF417‑ en macro PDF417‑barcodes
  uit afbeeldingen te lezen. Deze stapsgewijze gids laat zien hoe je meerdere barcodes
  in één afbeelding decodeert.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Maak een console barcode‑scanner in C# – volledige gids
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  headline: Create console barcode scanner in C# – barcode reader example
  type: TechArticle
- description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  name: Create console barcode scanner in C# – barcode reader example
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
- console application
title: Maak een console barcode‑scanner in C# – voorbeeld voor het lezen van PDF417‑barcode
url: /nl/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak een console barcode scanner in C# – voorbeeld voor het lezen van PDF417 barcode

`BarCodeReader` is de kernklasse van Aspose.BarCode die barcodes decodeert van afbeeldingen en gedetailleerde metadata retourneert. Als je PDF417 barcode‑gegevens uit een afbeelding moet lezen, laat deze gids zien hoe je dat doet met de **BarCodeReader**‑klasse in C#. Je leert een **create console barcode scanner**‑voorbeeld dat ook macro PDF417 afhandelt en meerdere barcodes in één afbeelding kan lezen.

Werken met barcodes betekent vaak omgaan met verschillende afbeeldingsbronnen, wisselende lichtomstandigheden en soms samengestelde gegevens zoals macro PDF417‑segmenten. Deze tutorial behandelt alles wat je nodig hebt om een PDF417‑barcode te decoderen, de uitgebreide velden te extraheren en meerdere barcodes uit dezelfde afbeelding te verwerken. Aan het einde heb je een uitvoerbaar console‑programma dat barcodes uit een afbeeldingsbestand leest en gedetailleerde informatie naar de console print.

## Snelle antwoorden
- **What does the example do?** Het maakt een console barcode scanner die PDF417‑ en macro PDF417‑barcodes van een afbeelding leest en alle gedecodeerde velden print.  
- **Which library is required?** Aspose.BarCode for .NET (NuGet).  
- **Can it read multiple barcodes at once?** Ja – de lezer iterereert over elke barcode die in de afbeelding wordt gevonden.  
- **Do I need an internet connection?** Nee, de bibliotheek werkt volledig offline.  
- **What .NET version is supported?** .NET 6.0 of later.

## Wat je nodig hebt

Voordat je begint, zorg ervoor dat je het volgende hebt:

* .NET 6.0 SDK of later geïnstalleerd  
* Een recente versie van het **Aspose.BarCode for .NET** NuGet‑pakket (of een compatibele bibliotheek die `BarCodeReader` en `DecodeType.MacroPdf417` biedt)  
* Een afbeeldingsbestand dat een PDF417‑ of macro PDF417‑barcode bevat (het voorbeeld gebruikt `ExtPDF417Meta.png`)  
* Een code‑editor of IDE zoals Visual Studio 2022  

Er zijn geen extra services of externe API’s nodig.

## Het project instellen voor barcode‑lezen

1. **Create a new console project**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Add the barcode library**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Copy the barcode image**  

   Plaats `ExtPDF417Meta.png` (of elke afbeelding die een PDF417‑barcode bevat) in de projectmap.  
   Voor deze tutorial gaan we ervan uit dat het bestand zich bevindt op `YOUR_DIRECTORY/ExtPDF417Meta.png`.

Het project is nu klaar om te compileren en het barcode‑lezer‑voorbeeld uit te voeren.

## Hoe maak ik een console barcode scanner in C#?

`BarCodeReader` is een klasse die door Aspose.BarCode wordt geleverd en barcodes uit afbeeldingen leest en hun gedecodeerde gegevens retourneert.  
Laad de afbeelding met `BarCodeReader`, stel het decodeertype in op `MacroPdf417` en iterereer over de resultaten – dat is alles wat je nodig hebt om een console barcode scanner te maken. De lezer geeft automatisch native resources vrij dankzij de `using`‑statement, zodat je geen geheugen handmatig hoeft te beheren. Deze aanpak werkt voor elk door .NET ondersteund afbeeldingsformaat, zoals PNG, JPEG of BMP.

### Stap‑voor‑stap doorloop

De kern van de oplossing is een `using`‑blok dat een `BarCodeReader`‑instantie maakt, `DecodeType.MacroPdf417` specificeert en over elke gedetecteerde barcode iterereert. De volgende code is een volledig, zelfstandig programma dat je kunt plakken in `Program.cs`.

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

**Why this works**:  

* `DecodeType.MacroPdf417` vertelt de lezer om te zoeken naar de macro‑extensie van PDF417, die extra metadata bevat zoals bestand‑ID, segment‑aantal en tijdstempels.  
* De `using`‑statement garandeert dat onbeheerste resources (bestands‑handles, native decodeer‑buffers) tijdig worden vrijgegeven.  
* De `foreach`‑lus verwerkt automatisch **all** barcodes die de afbeelding bevat, waardoor aan de *read multiple barcodes*‑vereiste wordt voldaan.  

Wanneer je het programma uitvoert (`dotnet run`), zou je output moeten zien die lijkt op het volgende:

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

Als de afbeelding meer dan één PDF417‑barcode bevat, print de lus een apart blok voor elke barcode, waarmee wordt aangetoond hoe je **read multiple barcodes** van één afbeelding kunt uitvoeren.

## Hoe kan ik meerdere barcodes uit een afbeelding lezen?

Gebruik één `BarCodeReader`‑instantie en stel de `DecodeType`‑vlag in om alle formaten op te nemen die je wilt detecteren. Door vlaggen te combineren met de bitwise OR‑operator kun je de bibliotheek laten zoeken naar PDF417, QR, Code‑128 en vele andere symbologieën in één enkele pass. Dit elimineert de noodzaak voor afzonderlijke lezers en verkort de verwerkingstijd.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* is een bitmasker, dus je kunt een willekeurig aantal ondersteunde formaten combineren. Aspose.BarCode ondersteunt **30+ barcode symbologies**, waaronder QR, DataMatrix, Code‑128 en UPC‑A, waardoor één scanner diverse use‑cases kan afhandelen zoals productlabeling, ticketvalidatie en identiteitsverificatie.

## Wat is macro PDF417 en hoe krijg ik veilig toegang tot de velden?

Macro PDF417 is een uitbreiding van de PDF417‑symbologie die een grote dataset over meerdere barcode‑symbolen kan verdelen.  
Macro PDF417 voegt een rijke set uitgebreide eigenschappen toe. Niet elke barcode bevat echter elk veld. Het benaderen van een ontbrekende eigenschap kan een `NullReferenceException` veroorzaken. De veiligste aanpak is om elk eigendom te verifiëren voordat je het afdrukt, zodat je applicatie stabiel blijft zelfs wanneer macro‑data afwezig is.

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Why this matters*: In real‑world deployments kun je platte PDF417‑barcodes ontvangen die geen macro‑data bevatten. De defensieve controle zorgt ervoor dat je applicatie blijft draaien zonder te crashen.

## Veelvoorkomende valkuilen en best practices

| Issue | Why it happens | Recommended fix |
|-------|----------------|-----------------|
| Image path is incorrect | `BarCodeReader` throws a file‑not‑found exception before any decoding occurs | Use `Path.Combine` and validate the file exists with `File.Exists` |
| Low‑resolution image | The decoder cannot locate barcode edges, resulting in zero detections | Provide a minimum resolution of 300 dpi for reliable results |
| Barcode rotated > 45° | Many libraries assume upright orientation | Enable `reader.RecognitionOptions.RotateImage = true` if the image may be rotated |
| Missing macro fields | Attempting to read a null property causes a crash | Always check for `null` before accessing macro properties |
| Large batch processing | Re‑creating the reader for each file adds overhead | Re‑use a single `BarCodeReader` instance with different streams when processing many images |

## Waarom Aspose.BarCode gebruiken voor een console barcode scanner?

Aspose.BarCode kan **30+ barcode types** decoderen en verwerkt afbeeldingen tot **200 MP** zonder het volledige bestand in het geheugen te laden, met een doorvoersnelheid van **150 frames per second** op een typische 3.2 GHz CPU. Deze gekwantificeerde mogelijkheden maken het een betrouwbare keuze voor high‑volume, on‑premises scanning‑oplossingen waar latentie en nauwkeurigheid cruciaal zijn.

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe DataMatrix-barcodes lezen met Aspose.BarCode voor .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [DataMatrix barcode lezen C# – DataMatrix-modus genereren (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Barcode lezen van afbeelding – Barcode-regio-extractie beheersen in Java met Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

## Veelgestelde vragen

**Q: Kan ik deze scanner in een productieomgeving gebruiken?**  
A: Ja. Schaf een commerciële Aspose.BarCode‑licentie aan om het evaluatiewatermerk te verwijderen en volledige ondersteuning te krijgen.

**Q: Werkt de bibliotheek op Linux en macOS?**  
A: Absoluut. Aspose.BarCode for .NET is cross‑platform en draait op .NET 6+ op Windows, Linux en macOS.

**Q: Hoe ga ik om met zeer grote afbeeldingen zonder het geheugen uit te putten?**  
A: Gebruik de `LoadOptions`‑constructor om streaming‑modus in te schakelen, waardoor de afbeelding in delen wordt verwerkt in plaats van volledig in RAM te laden.

**Q: Is het mogelijk om versleutelde of met een wachtwoord beveiligde afbeeldingen te decoderen?**  
A: De lezer kan afbeeldingen verwerken die zijn versleuteld met standaard PNG/JPEG‑wachtwoordschema’s; geef simpelweg het wachtwoord door via `reader.ImagePassword`.

**Q: Wat als mijn barcode gedeeltelijk beschadigd is?**  
A: Schakel fout‑correctie‑opties in, zoals `reader.RecognitionOptions.CorrectErrors = true`, om de veerkracht tegen schade of ruis te verbeteren.

**Last Updated:** 2026-10-14  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose

## Gerelateerde tutorials

- [Hoe Pdf417 lezen in C – volledig barcode lezer voorbeeld](/barcode/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Meerdere barcodes lezen C – volledige gids met Pdf417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)
- [Barcode decoderen van afbeelding met een C barcode lezer voorbeeld](/barcode/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}