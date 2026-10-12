---
category: general
date: 2026-10-12
description: Lär dig hur du skapar ett Aspose‑streckkodsexempel i C# som genererar
  en MacroPdf417‑streckkod med full metadata och läser tillbaka den med BarCodeReader.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- macroPdf417 barcode
- barcode metadata
- c# barcode generation
- BarCodeReader
language: sv
lastmod: 2026-10-12
og_description: Aspose streckkodsexempel i C# som visar hur man genererar en MacroPdf417‑streckkod
  med inbäddad metadata och läser tillbaka den med BarCodeReader.
og_image_alt: Screenshot of an Aspose barcode example displaying a MacroPdf417 barcode
  with metadata
og_title: Skapa ett Aspose‑streckkodsexempel med MacroPdf417 i C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn how to create an Aspose barcode example in C# that generates
    a MacroPdf417 barcode with full metadata and reads it back using BarCodeReader.
  headline: How to build an Aspose barcode example with MacroPdf417 in C#
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Barcode
title: Hur man bygger ett Aspose‑streckkodsexempel med MacroPdf417 i C#
url: /sv/net/compact-pdf417-encoding/how-to-build-an-aspose-barcode-example-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man bygger ett Aspose‑streckkodsexempel med MacroPdf417 i C#

Om du behöver ett **aspose barcode example** som skapar en MacroPdf417‑streckkod och läser dess inbäddade metadata, visar den här guiden hela arbetsflödet. Du kommer att se hur du konfigurerar generatorn, bäddar in fil‑nivåinformation, sparar bilden och sedan avkodar samma data med `BarCodeReader`.

Handledningen täcker allt du behöver veta för **C# barcode generation** med Aspose.BarCode, inklusive vanliga fallgropar och tips för att hantera stora fil‑ID:n eller anpassade tidsstämplar.

## Vad du behöver

* .NET 6.0 SDK eller senare (koden fungerar med .NET Core och .NET Framework)
* Visual Studio 2022 eller någon IDE som stödjer C#
* En aktiv Aspose.BarCode‑licens (gratis provversion fungerar för utveckling)
* NuGet‑paketet `Aspose.BarCode` installerat i ditt projekt

Dessa förutsättningar garanterar att exemplet körs utan ytterligare konfiguration.

## Steg 1: Ställ in Aspose‑streckkodsexempelprojektet

Skapa en ny konsolapplikation och lägg till Aspose.BarCode‑biblioteket:

```bash
dotnet new console -n AsposeMacroPdf417Demo
cd AsposeMacroPdf417Demo
dotnet add package Aspose.BarCode
```

`Aspose.BarCode`‑paketet tillhandahåller `BarcodeGenerator`, `BarCodeReader` och alla typer som krävs för MacroPdf417‑hantering.

### Varför detta steg är viktigt
Att lägga till NuGet‑paketet löser upp `EncodeTypes`, `DecodeType` och `BarCodeImageFormat`‑enum‑värden som används senare. Utan paketet skulle kompilatorn inte känna igen dessa symboler, och exemplet skulle misslyckas vid byggtid.

## Steg 2: Skapa MacroPdf417‑streckkodsgeneratorn

Öppna **Program.cs** och ersätt mallkoden med följande block. Detta block skapar en `BarcodeGenerator` konfigurerad för MacroPdf417‑symboliken och ställer in grundläggande utseendeparametrar.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Enums;
using System;

class Program
{
    static void Main()
    {
        // Step 2.1: Initialize the generator with source text.
        using (BarcodeGenerator barcodeGenerator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
        {
            // Adjust the module size – 2 pixels per X‑dimension.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Reduce the number of columns to keep the barcode compact.
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Step 2.2: Embed MacroPdf417 metadata.
            // ---------------------------------------------------------
            // The following properties are optional but illustrate
            // how a full‑featured barcode can carry file‑level data.
            // ---------------------------------------------------------
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp =
                new DateTime(2024, 9, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator =
                Pdf417MacroTerminator.Set;

            // Step 2.3: Save the barcode image.
            const string outPath = "ExtPDF417Meta.png";
            barcodeGenerator.Save(outPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outPath}");
        }
```

#### Förklaring av nyckelegenskaper

| Egenskap | Syfte | Typiskt intervall / anteckningar |
|----------|-------|-----------------------------------|
| `MacroPdf417FileID` | Unik identifierare för hela filen | Måste vara ≤ 2³¹‑1 |
| `MacroPdf417SegmentID` | Index för det aktuella segmentet | Startar vid 0 |
| `MacroPdf417SegmentsCount` | Totalt antal segment i filen | Måste vara ≥ SegmentID |
| `MacroPdf417FileName` | Mänskligt läsbart namn för filen | Upp till 255 tecken |
| `MacroPdf417Checksum` | CCITT‑16‑kontrollsumma för originalfilen | Beräknas av externt verktyg om behövs |
| `MacroPdf417FileSize` | Storlek på originalfilen i byte | Användbart för validering |
| `MacroPdf417TimeStamp` | Datum/tid då filen skapades | Använd UTC för konsistens |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Valfri routningsinformation | Godtycklig sträng upp till 255 tecken |
| `MacroPdf417Terminator` | Markerar det sista segmentet | Använd `Set` för det sista segmentet |

Dessa fält utgör **barcode metadata** som läsaren kan extrahera senare.

## Steg 3: Avkoda streckkoden och visa metadata

Efter att bilden sparats fortsätter samma program genom att öppna filen med `BarCodeReader`. Lägg till följande kod i `Main`‑metoden, efter föregående `using`‑block:

```csharp
        // Step 3: Open the saved image with a MacroPdf417 reader.
        using (BarCodeReader barcodeReader =
               new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
        {
            // Step 3.1: Iterate through all decoded results.
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                // The Extended property holds the MacroPdf417 specific fields.
                var meta = result.Extended.Pdf417;
                Console.WriteLine($"FileID: {meta.MacroPdf417FileID}");
                Console.WriteLine($"SegmentID: {meta.MacroPdf417SegmentID}");
                Console.WriteLine($"SegmentsCount: {meta.MacroPdf417SegmentsCount}");
                Console.WriteLine($"FileName: {meta.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {meta.MacroPdf417Checksum}");
                Console.WriteLine($"FileSize: {meta.MacroPdf417FileSize}");
                Console.WriteLine($"Timestamp: {meta.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {meta.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {meta.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {meta.MacroPdf417Terminator}");
            }
        }
    }
}
```

### Varför återläsning är viktigt
`BarCodeReader` validerar att den metadata du bäddat in är korrekt kodad. Om någon egenskap saknas eller ligger utanför intervallet returnerar läsaren `null` för det fältet, vilket gör att du kan hantera fel på ett smidigt sätt.

## Steg 4: Kör och verifiera resultatet

Kör programmet:

```bash
dotnet run
```

Du bör se konsolutdata liknande:

```
Barcode saved to ExtPDF417Meta.png
FileID: 12345678
SegmentID: 12
SegmentsCount: 20
FileName: file01
Checksum: 1234
FileSize: 400000
Timestamp: 9/1/2024 12:00:00 AM
Addressee: street
Sender: aspose
Terminator: Set
```

Om värdena matchar de du satte i Steg 2, fungerar **aspose barcode example** som förväntat.

## Kantfall och bästa‑praxis‑tips

| Situation | Vad att hålla utkik efter | Rekommenderad hantering |
|-----------|---------------------------|--------------------------|
| **FileID överskrider 32‑bit‑intervall** | Aspose throws `ArgumentOutOfRangeException`. | Behåll ID:n ≤ 2 147 483 647 eller dela filen i flera MacroPdf417‑block. |
| **Tidsstämpel i lokal tid** | Läsare i en annan tidszon kan misstolka värdet. | Spara tidsstämplar i UTC (`DateTime.UtcNow`) och konvertera vid visning om behövs. |
| **Stor filstorlek** | `MacroPdf417FileSize` är en `int`; värden > 2 GB överflödar. | Använd ett anpassat fält eller dela filen i mindre segment. |
| **Saknat segment** | Om `SegmentID` inte är sekventiell misslyckas återuppbyggnad. | Validera segmentordning innan kodning eller använd felkorrigeringsinställningar. |
| **Ej stödd bildformat** | Att spara som BMP kan öka storleken dramatiskt. | PNG är ett bra standardval; JPEG kan användas om du accepterar förlustkomprimering. |

**Pro tip:** När du genererar många streckkoder i en batch, återanvänd en enda `BarcodeGenerator`‑instans och ändra bara `EncodeTypes` och källtexten. Detta minskar minnesallokeringar och snabbar upp bearbetningen.

## Relaterade ämnen du kan utforska härnäst

* **Other macro symbologies** – Aspose stödjer också MacroPdf417 med felkorrigeringsnivåer.
* **Embedding barcodes in PDFs** – Kombinera `Aspose.PDF` med streckkodsgeneratorn för att producera utskrivbara dokument.
* **ASP.NET Core integration** – Servera genererade streckkoder direkt från ett web‑API.
* **Scanning via mobile devices** – Använd `Aspose.BarCode.Cloud`‑SDK för plattformsoberoende avkodning.

Dessa uppföljande ämnen utökar naturligt **aspose barcode example** och fördjupar din expertis inom **C# barcode generation**.

## Slutsats

Du har nu ett fullt funktionellt **aspose barcode example** som skapar en MacroPdf417‑streckkod, bäddar in rik **barcode metadata**, sparar bilden och läser tillbaka data med `BarCodeReader`. Genom att följa stegen ovan kan du anpassa koden till olika fil‑ID:n, tidsstämplar eller till och med andra streckkodstyper som stöds av Aspose.

Känn dig fri att experimentera med ytterligare metadatafält, ändra bildformatet eller integrera generatorn i en större applikation. Lycka till med kodningen!

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}