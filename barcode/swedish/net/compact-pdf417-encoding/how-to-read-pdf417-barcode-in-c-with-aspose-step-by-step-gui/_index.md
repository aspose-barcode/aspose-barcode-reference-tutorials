---
category: general
date: 2026-10-24
description: Lär dig hur du läser PDF417‑streckkod i C# med Aspose.BarCode. Denna
  handledning täcker läsning av en streckkodsbild, extrahering av Macro PDF417‑fält
  och hantering av vanliga scenarier.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode image c#
- read barcode with aspose
language: sv
lastmod: 2026-10-24
og_description: Hur man läser PDF417-streckkod i C# med Aspose.BarCode. Följ den här
  kompletta handledningen för att avkoda bilder, hämta Macro PDF417-metadata och undvika
  vanliga fallgropar.
og_image_alt: Screenshot showing how to read PDF417 barcode results in a C# console
  application
og_title: Hur man läser PDF417‑streckkod i C# med Aspose – komplett guide
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  headline: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  name: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  steps:
  - name: Why use `DecodeType.MacroPdf417`?
    text: '* **Macro PDF417** stores additional fields (file ID, segment count, timestamps,
      etc.) that are not present in standard PDF417. * The `Extended` property of
      `BarCodeResult` is populated only when you request the macro type, saving you
      a separate parsing step.'
  - name: What each property means
    text: '| Property | Description | |----------|-------------| | **MacroPdf417FileID**
      | Unique identifier for the whole multi‑segment document. | | **MacroPdf417SegmentID**
      | Index of the current segment (starting at 0). | | **MacroPdf417SegmentsCount**
      | Total number of segments that belong to the file. | '
  - name: Missing macro fields
    text: 'Sometimes a PDF417 barcode is generated without the optional macro fields.
      Accessing a missing property returns `null` or `0`. Guard against this if you
      plan to store the values:'
  - name: Corrupted or low‑quality images
    text: 'If the image is blurry, you can improve detection by enabling the `BarCodeReader`
      quality options:'
  - name: Multiple barcode formats in one image
    text: 'If you suspect other barcode types might be present, use `DecodeType.AllSupported`
      and filter results:'
  type: HowTo
- questions:
  - answer: Yes. Change `DecodeType.MacroPdf417` to `DecodeType.Pdf417`. The `Extended`
      property will be empty, but `CodeText` and `CodeTypeName` remain available.
    question: Can I read a standard PDF417 (non‑macro) with the same code?
  - answer: Absolutely. Use the overload `new BarCodeReader(Stream, DecodeType)` and
      pass a `FileStream` or `MemoryStream`. This is useful when the image comes from
      a web API.
    question: Does Aspose.BarCode support reading from a stream instead of a file
      path?
  - answer: 'The `MacroPdf417Checksum` field contains the raw CRC‑16 value. You can
      recompute the checksum on the reconstructed file and compare it to ensure data
      integrity. ## Next steps and related topics * **Write PDF417 barcodes** – explore
      `BarCodeGenerator` to create macro barcodes for testing. * **Combine'
    question: How do I validate the checksum?
  type: FAQPage
tags:
- barcode
- Aspose.BarCode
- C#
title: Hur man läser PDF417-streckkod i C# med Aspose – steg‑för‑steg‑guide
url: /sv/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-with-aspose-step-by-step-gui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man läser PDF417‑streckkod i C# med Aspose – steg‑för‑steg‑guide

Om du behöver **läsa PDF417‑streckkod** i en .NET‑applikation, visar den här guiden exakt hur du läser PDF417‑streckkod i C# med hjälp av Aspose.BarCode‑biblioteket. Oavsett om du bearbetar skannade dokument, mobila fångster eller batch‑importerade bilder, dekodar koden nedan streckkoden och extraherar varje Macro PDF417‑egenskap du kan behöva.

Att läsa en streckkodsbild i C# kan kännas överväldigande, särskilt när streckkoden innehåller utökad metadata. Den här handledningen eliminerar gissningsarbetet genom att erbjuda ett komplett, körbart exempel, förklara varje rad och täcka kantfall som saknade makrosegment eller korrupta bilder. I slutet kommer du kunna integrera PDF417‑avkodning i vilket C#‑projekt som helst med självförtroende.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare installerat  
* Visual Studio 2022 (eller någon IDE som stödjer .NET)  
* En licens eller gratis utvärdering av **Aspose.BarCode for .NET** – du kan få en tillfällig nyckel från Aspose‑webbplatsen  
* En bildfil som innehåller en Macro PDF417‑streckkod (t.ex. `ExtPDF417Meta.png`)

> **Proffstips:** Om du bara behöver experimentera erbjuder Aspose en 30‑dagars provperiod som inkluderar full funktionalitet för streckkodsläsning.

## Steg 1: Installera Aspose.BarCode‑paketet via NuGet

Öppna din projektmapp i en terminal och kör:

```bash
dotnet add package Aspose.BarCode
```

Paketet lägger till namnutrymmet `Aspose.BarCode.ReadRecognition`, som innehåller klassen `BarCodeReader` som används för att avkoda bilder.

## Steg 2: Skapa en BarCodeReader för en PDF417‑bild

`BarCodeReader`‑konstruktorn tar två argument: sökvägen till bildfilen och den `DecodeType` du vill rikta in dig på. Att ange `DecodeType.MacroPdf417` talar om för Aspose att leta efter Macro PDF417‑symboler och att automatiskt fylla i de utökade egenskaperna.

```csharp
using Aspose.BarCode.ReadRecognition;

// Replace with the actual path to your barcode image
string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image
```

### Varför använda `DecodeType.MacroPdf417`?

* **Macro PDF417** lagrar ytterligare fält (fil‑ID, segmentantal, tidsstämplar osv.) som inte finns i standard‑PDF417.  
* `Extended`‑egenskapen i `BarCodeResult` fylls endast i när du begär makro‑typen, vilket sparar ett separat parsningsteg.

## Steg 3: Iterera genom alla upptäckta streckkoder

En enda bild kan innehålla flera PDF417‑symboler (t.ex. när ett dokument är uppdelat över flera sidor). Metoden `ReadBarCodes()` returnerar ett `IEnumerable<BarCodeResult>` som du kan loopa igenom.

```csharp
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Basic information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

Om bilden inte innehåller någon streckkod körs loopen helt enkelt aldrig, och programmet avslutas smidigt. Detta beteende gör koden säker för batch‑bearbetning där vissa filer kan vara utan streckkod.

## Steg 4: Skriva ut Macro PDF417‑utökade egenskaper

`Extended.Pdf417`‑egenskapen grupperar alla makro‑specifika fält. Varje fält motsvarar direkt PDF417‑specifikationen, så du kan lagra dem i en databas, logga dem eller använda dem för vidare validering.

```csharp
        // Macro PDF417 extended properties
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
    }
}
```

### Vad varje egenskap betyder

| Egenskap | Beskrivning |
|----------|-------------|
| **MacroPdf417FileID** | Unik identifierare för hela det flersegmenterade dokumentet. |
| **MacroPdf417SegmentID** | Index för det aktuella segmentet (börjar på 0). |
| **MacroPdf417SegmentsCount** | Totalt antal segment som tillhör filen. |
| **MacroPdf417FileName** | Valfritt filnamn inbäddat i streckkoden. |
| **MacroPdf417Checksum** | CRC‑16‑kontrollsumma för makro‑datablocket. |
| **MacroPdf417FileSize** | Ursprunglig filstorlek i byte. |
| **MacroPdf417TimeStamp** | Tidsstämpel när makro‑streckkoden genererades. |
| **MacroPdf417Addressee** | Avsedd mottagare av dokumentet. |
| **MacroPdf417Sender** | Ursprunglig avsändare av dokumentet. |
| **MacroPdf417Terminator** | Termineringflagga som indikerar slutet på makrosekvensen. |

Dessa fält är särskilt användbara när du rekonstruerar en stor PDF eller bild som delats upp i flera PDF417‑symboler för utskrift på lågupplöst media.

## Steg 5: Hantera vanliga kantfall

### Saknade makrofält

Ibland genereras en PDF417‑streckkod utan de valfria makrofälten. Att komma åt ett saknat egenskap returnerar `null` eller `0`. Skydda mot detta om du planerar att lagra värdena:

```csharp
string fileName = result.Extended.Pdf417.MacroPdf417FileName ?? "Unnamed";
long fileSize = result.Extended.Pdf417.MacroPdf417FileSize;
```

### Korrupta eller lågkvalitativa bilder

Om bilden är suddig kan du förbättra detektering genom att aktivera `BarCodeReader`‑kvalitetsalternativen:

```csharp
reader.BarcodeSettings.ImageQuality = 90; // value between 0‑100
reader.BarcodeSettings.PureBarcode = false; // allow detection in noisy backgrounds
```

Dessa inställningar är valfria men kan dramatiskt öka framgångsfrekvensen för skannade dokument.

### Flera streckkodformat i en bild

Om du misstänker att andra streckkodstyper kan finnas, använd `DecodeType.AllSupported` och filtrera resultaten:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        if (result.CodeType == DecodeType.MacroPdf417)
        {
            // Process macro PDF417 as shown above
        }
    }
}
```

## Komplett körbart exempel

Kopiera följande program till ett nytt konsolprojekt (`dotnet new console`) och kör det. Ersätt variabeln `imagePath` med platsen för din egen Macro PDF417‑bild.

```csharp
using System;
using Aspose.BarCode.ReadRecognition;

class Program
{
    static void Main()
    {
        // Path to the barcode image
        string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Optional: improve detection on low‑quality scans
            reader.BarcodeSettings.ImageQuality = 90;
            reader.BarcodeSettings.PureBarcode = false;

            // Iterate through every barcode found in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Output extended Macro PDF417 fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender ?? \"N/A\"}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Förväntad output** (värdena kommer att skilja sig beroende på din bild):

```
CodeType: MacroPdf417
CodeText: 1234567890ABCDEFGHIJ
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: Invoice_2026_10.pdf
Pdf417MacroChecksum: 32768
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2026-10-24T14:32:10Z
Pdf417MacroAddressee: AccountingDept
Pdf417MacroSender: SalesTeam
MacroPdf417Terminator: True
----------------------------------------
```

Om bilden inte innehåller några Macro PDF417‑symboler skriver programmet inget och avslutas tyst – perfekt för batch‑jobb som bearbetar många filer.

## Vanliga frågor

**Q: Kan jag läsa en standard PDF417 (icke‑makro) med samma kod?**  
A: Ja. Ändra `DecodeType.MacroPdf417` till `DecodeType.Pdf417`. `Extended`‑egenskapen blir tom, men `CodeText` och `CodeTypeName` förblir tillgängliga.

**Q: Stöder Aspose.BarCode att läsa från en ström istället för en filsökväg?**  
A: Absolut. Använd överlagringen `new BarCodeReader(Stream, DecodeType)` och skicka en `FileStream` eller `MemoryStream`. Detta är användbart när bilden kommer från ett web‑API.

**Q: Hur validerar jag kontrollsumman?**  
A: `MacroPdf417Checksum`‑fältet innehåller det råa CRC‑16‑värdet. Du kan beräkna om kontrollsumman på den rekonstruerade filen och jämföra den för att säkerställa dataintegritet.

## Nästa steg och relaterade ämnen

* **Write PDF417 barcodes** – utforska `BarCodeGenerator` för att skapa makro‑streckkoder för testning.  
* **Combine multiple segments** – efter att ha läst alla segment, sortera dem efter `MacroPdf417SegmentID` och slå ihop `CodeText` för att rekonstruera den ursprungliga nyttolasten.  
* **Performance tuning** – för scenarier med hög genomströmning, återanvänd en enda `BarCodeReader`‑instans över många bilder och

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Hur man läser PDF417 i C# – komplett streckkodsexempel](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [Hur man skapar macro PDF417‑streckkod i C# med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Läs streckkod från bild C# – komplett guide med Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}