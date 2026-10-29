---
category: general
date: 2026-10-28
description: Hur man avkodar PDF417‑streckkoder i C# snabbt. Lär dig läsa streckkodsbilder
  i C# med Aspose.BarCode med ett komplett, körbart exempel.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcode image c#
- PDF417 decoding C#
- barcode reader C#
- Aspose.BarCode example
language: sv
lastmod: 2026-10-28
og_description: Hur man avkodar PDF417‑streckkoder i C# med Aspose.BarCode. Denna
  guide visar dig hur du läser streckkodsbilder i C# steg för steg, komplett med kod.
og_image_alt: Screenshot of C# code that decodes a PDF417 barcode from an image
og_title: Hur man avkodar PDF417‑streckkoder i C# – läs streckkodsbild C#‑handledning
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to decode PDF417 barcodes in C# quickly. Learn to read barcode
    image C# using Aspose.BarCode with a complete, runnable example.
  headline: How to decode PDF417 barcodes in C# and read barcode image C#
  type: TechArticle
- description: How to decode PDF417 barcodes in C# quickly. Learn to read barcode
    image C# using Aspose.BarCode with a complete, runnable example.
  name: How to decode PDF417 barcodes in C# and read barcode image C#
  steps:
  - name: What each line does
    text: '| Line | Explanation | |------|-------------| | `result.CodeTypeName` |
      Human‑readable name of the detected barcode type (e.g., “MacroPdf417”). | |
      `result.CodeText` | The raw data encoded in the barcode. | | `result.Extended.Pdf417.MacroPdf417FileID`
      | Identifier that ties all segments of a macro P'
  - name: Handling common edge cases
    text: '| Situation | Recommended handling | |-----------|----------------------|
      | **No barcode found** | Check `reader.ReadBarCodes().Any()` before the loop
      and display a friendly message. | | **Corrupted image** | Wrap the `BarCodeReader`
      creation in a `try/catch` block for `BarCodeException`. | | **Mult'
  - name: Next steps
    text: '* Explore other barcode formats by changing `DecodeType` (e.g., `DecodeType.QR`,
      `DecodeType.Code128`). * Combine multiple decoded segments to reconstruct the
      original document. * Use the `BarCodeGenerator` class to create test PDF417
      barcodes on the fly.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Hur man avkodar PDF417‑streckkoder i C# och läser streckkodsbilder i C#
url: /sv/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-and-read-barcode-image-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så avkodar du PDF417-streckkoder i C# och läser streckkodsbilder i C#

Om du behöver **how to decode pdf417** i en .NET‑applikation, ger den här guiden dig en färdig‑att‑köra‑lösning. Du kommer att se exakt hur du **read barcode image c#** med Aspose.BarCode‑biblioteket, extraherar macro‑PDF417‑fält och visar dem i konsolen.

Avkodning av PDF417-streckkoder förekommer ofta i logistik, biljettförsäljning och identitetsverifieringssystem. I slutet av den här handledningen kommer du att kunna läsa in vilken bild som helst som innehåller en Macro PDF417‑streckkod, avkoda den och komma åt fil‑ID, segment‑ID och segmentantal‑värdena som är nödvändiga för att sammanställa flerdelade dokument.

## Förutsättningar

* .NET 6.0 SDK eller senare installerat  
* Visual Studio 2022 (eller någon C#‑IDE)  
* Ett Aspose.BarCode för .NET NuGet‑paket (`Aspose.BarCode`)  
* En bildfil som innehåller en Macro PDF417‑streckkod (exemplet använder `ExtPDF417Meta.png`)

```bash
dotnet add package Aspose.BarCode
```

## Steg 1: Skapa projektet och importera namnrymder

Skapa ett nytt konsolprojekt och importera de nödvändiga namnrymderna. `using`‑direktiven ger dig åtkomst till `BarCodeReader`, `DecodeType` och result‑extensions‑objekten.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

> **Varför detta steg är viktigt** – Att importera rätt namnrymder förhindrar kompileringsfel och gör API‑ytan tillgänglig för den efterföljande avkodningslogiken.

## Steg 2: Ange bildens sökväg

Definiera den fullständiga eller relativa sökvägen till streckkodsbilden. Att hålla sökvägen i en variabel gör koden återanvändbar för olika bilder.

```csharp
// Step 2: Specify the path to the image that contains a Macro PDF417 barcode
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

> **Tips:** Använd `Path.Combine` om du bygger sökvägen av flera delar; den hanterar katalogseparatorer på olika operativsystem.

## Steg 3: Skapa en `BarCodeReader` konfigurerad för Macro PDF417‑avkodning

Instansiera `BarCodeReader` med bildens sökväg och flaggan `DecodeType.MacroPdf417`. Detta instruerar biblioteket att specifikt leta efter Macro PDF417‑symboler.

```csharp
// Step 3: Create a BarCodeReader configured for MacroPdf417 decoding
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
```

> **Varför detta steg är viktigt** – Att välja rätt `DecodeType` förbättrar prestandan eftersom motorn hoppar över orelaterade streckkodformat.

## Steg 4: Läs alla streckkoder och visa makroinformation

Loopa igenom varje `BarCodeResult` som returneras av `reader.ReadBarCodes()`. Resultatobjektet innehåller både generiska fält (`CodeTypeName`, `CodeText`) och Macro PDF417‑specifika tillägg (`MacroPdf417FileID`, `MacroPdf417SegmentID`, `MacroPdf417SegmentsCount`).

```csharp
    // Step 4: Read all barcodes in the image and display the most relevant macro information
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Code Type : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // Macro PDF417 specific fields
        Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment ID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Segments  : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
    }
}
```

### Vad varje rad gör

| Line | Explanation |
|------|-------------|
| `result.CodeTypeName` | Mänskligt läsbart namn på den upptäckta streckkodstypen (t.ex. “MacroPdf417”). |
| `result.CodeText` | Den råa data som är kodad i streckkoden. |
| `result.Extended.Pdf417.MacroPdf417FileID` | Identifierare som binder ihop alla segment av ett macro PDF417‑dokument. |
| `result.Extended.Pdf417.MacroPdf417SegmentID` | Index för det aktuella segmentet i hela dokumentet. |
| `result.Extended.Pdf417.MacroPdf417SegmentsCount` | Totalt antal segment som förväntas för dokumentet. |

> **Proffstips:** Spara makrofälten i en databas om du senare behöver återmontera hela dokumentet. `File ID` låter dig gruppera segment som tillhör samma källa.

## Steg 5: Kör programmet och verifiera utskriften

Bygg och kör konsolapplikationen:

```bash
dotnet run
```

Typisk konsolutskrift ser ut så här:

```
Code Type : MacroPdf417
Code Text : 0123456789ABCD
File ID   : 101
Segment ID: 1
Segments  : 3
```

Om bilden innehåller flera Macro PDF417‑symboler skriver loopen ut varje symbol i sekvens.

### Hantera vanliga kantfall

| Situation | Recommended handling |
|-----------|----------------------|
| **Ingen streckkod hittades** | Check `reader.ReadBarCodes().Any()` before the loop and display a friendly message. |
| **Skadad bild** | Wrap the `BarCodeReader` creation in a `try/catch` block for `BarCodeException`. |
| **Flera streckkodformat** | Use `DecodeType.AllSupported` and filter results by `result.CodeTypeName == "MacroPdf417"`. |
| **Stora bilder** | Downscale the image before decoding to improve performance; the library accepts a `Bitmap` object. |

## Fullständig källkod

Nedan är det kompletta, fristående programmet. Kopiera det till `Program.cs` i ett nytt konsolprojekt och ersätt `YOUR_DIRECTORY/ExtPDF417Meta.png` med den faktiska sökvägen till din bild.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417Decoder
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Specify the path to the image that contains a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Step 3: Create a BarCodeReader configured for MacroPdf417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Step 4: Read all barcodes in the image and display the most relevant macro information
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // Macro PDF417 specific fields
                    Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments  : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                }
            }
        }
    }
}
```

## Slutsats

Du vet nu **how to decode pdf417** streckkoder i C# och hur du **read barcode image c#** med Aspose.BarCode. Handledningen guidade dig genom projektuppsättning, bildladdning, läsarkonfiguration, resultatextraktion och hantering av kantfall. Med detta grundlag kan du integrera PDF417‑avkodning i lagersystem, biljettvaliderare eller vilket arbetsflöde som helst som förlitar sig på makro‑kodad data.

### Nästa steg

* Utforska andra streckkodformat genom att ändra `DecodeType` (t.ex. `DecodeType.QR`, `DecodeType.Code128`).  
* Kombinera flera avkodade segment för att återskapa originaldokumentet.  
* Använd klassen `BarCodeGenerator` för att skapa test‑PDF417‑streckkoder i farten.  

Känn dig fri att experimentera med olika bildkällor, justera konsolutskriften eller bädda in avkodningslogiken i ett webb‑API för realtidsbehandling. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man avkodar PDF417 i C# med ett streckkodsläsare‑exempel](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [Hur man genererar PDF417‑streckkoder i C# med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [Hur man läser streckkod från bild c# med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}