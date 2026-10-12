---
category: general
date: 2026-10-02
description: Lär dig hur du läser en streckkod från en bild i C# med ett komplett
  exempel som visar hur du avkodar PDF417‑streckkod med Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image c#
- how to decode pdf417 barcode
language: sv
lastmod: 2026-10-02
og_description: Läs streckkod från bild i C# med Aspose.BarCode. Den här handledningen
  förklarar hur man avkodar PDF417-streckkod och extraherar utökad metadata.
og_image_alt: Screenshot showing how to read barcode from image c# in Visual Studio
og_title: Läs av streckkod från bild i C# – steg‑för‑steg guide
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to read barcode from image c# with a complete example that
    shows how to decode PDF417 barcode using Aspose.BarCode.
  headline: How to read barcode from image c# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image c# with a complete example that
    shows how to decode PDF417 barcode using Aspose.BarCode.
  name: How to read barcode from image c# using Aspose.BarCode
  steps:
  - name: Create a `BarCodeReader` for a PDF417 image
    text: '```csharp using System; using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Iterate over all detected barcodes
    text: '```csharp // Step 2: Read every barcode found in the image foreach (BarCodeResult
      barcodeResult in barcodeReader.ReadBarCodes()) { // At this point you have successfully
      read barcode from image c#. ```'
  - name: Access the extended PDF417 macro metadata
    text: '```csharp // Step 3: Grab the macro‑PDF417 extended information var macro
      = barcodeResult.Extended.Pdf417;'
  - name: Output the barcode text and macro details
    text: '```csharp // Step 4: Print the basic barcode information Console.WriteLine($"Type:
      {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");'
  - name: Handle errors and clean up resources
    text: 'The `using` statement automatically disposes the `BarCodeReader`. However,
      you should still catch exceptions that may arise from missing files or unsupported
      formats:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Hur man läser streckkod från bild i C# med Aspose.BarCode
url: /sv/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så läser du streckkod från bild c# med Aspose.BarCode

Om du behöver **läsa streckkod från bild c#**, så guidar den här guiden dig genom en komplett, körbar lösning. Du kommer att lära dig hur du avkodar en PDF417-streckkod, får åtkomst till dess utökade makrodata och skriver ut resultaten till konsolen.

Att läsa streckkoder från bilder är ett vanligt krav för lagersystem, biljettvalidering och dokumentbehandling. Denna handledning täcker allt du behöver: nödvändiga paket, kodförklaring, hantering av kantfall och förväntad output. Ingen extern dokumentation krävs; exemplet fungerar direkt med Aspose.BarCode .NET.

## Förutsättningar

* .NET 6.0 SDK eller senare installerat  
* Visual Studio 2022 (eller någon C#-IDE)  
* En NuGet-referens till **Aspose.BarCode** (version 23.10 eller nyare)  
* En bildfil som innehåller en PDF417-streckkod – till exempel `ExtPDF417Meta.png`

Om någon av dessa komponenter saknas, installera .NET SDK, lägg till NuGet-paketet med `dotnet add package Aspose.BarCode` och placera bilden i en mapp som du kan referera till från ditt projekt.

## Så läser du streckkod från bild c# – steg för steg

Följande avsnitt delar upp implementeringen i logiska steg. Varje steg innehåller ett kodexempel, en förklaring av **varför** steget är viktigt, samt ett tips du kan använda i verkliga projekt.

### Steg 1: Skapa en `BarCodeReader` för en PDF417-bild

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Initialise the reader for a Macro PDF417 image
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // The DecodeType enum tells the library which symbology to look for.
        // Using DecodeType.MacroPdf417 restricts the scan to PDF417 macro symbols.
        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // The reader is now ready to read barcode from image c# efficiently.
```

**Varför detta är viktigt** – `BarCodeReader`‑konstruktorn accepterar bildens sökväg och den förväntade streckkodstypen. Genom att ange `MacroPdf417` begränsar du sökningen, vilket förbättrar prestanda och minskar falska positiva när bilden innehåller flera symboltyper.

**Proffstips:** Om du är osäker på streckkodstypen, använd `DecodeType.AllSupportedTypes` och filtrera resultaten senare.

### Steg 2: Iterera över alla upptäckta streckkoder

```csharp
            // Step 2: Read every barcode found in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // At this point you have successfully read barcode from image c#.
```

**Varför detta är viktigt** – En PDF417-makrobild kan innehålla flera segment. Metoden `ReadBarCodes()` returnerar en samling, vilket låter dig bearbeta varje segment individuellt.

**Kantfall:** Om bilden inte innehåller några PDF417‑symboler är samlingen tom och loopens kropp körs aldrig. Överväg att lägga till en kontroll efter loopen för att informera användaren.

### Steg 3: Åtkomst till den utökade PDF417-makro‑metadata

```csharp
                // Step 3: Grab the macro‑PDF417 extended information
                var macro = barcodeResult.Extended.Pdf417;

                // The macro object holds file‑level data that PDF417 uses for
                // multi‑segment documents such as shipping manifests.
```

**Varför detta är viktigt** – Egenskapen `Extended.Pdf417` visar fält definierade av PDF417‑specifikationen, såsom fil‑ID, segment‑ID och filnamn. Denna data är avgörande när du behöver återskapa ett flersidigt dokument från separata streckkodsskanningar.

**Proffstips:** Verifiera alltid att `barcodeResult.Extended` inte är null innan du får åtkomst till `Pdf417`. Biblioteket returnerar `null` för symboltyper som inte stödjer utökad data.

### Steg 4: Skriv ut streckkodstexten och makro‑detaljerna

```csharp
                // Step 4: Print the basic barcode information
                Console.WriteLine($"Type: {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");

                // Print macro‑specific fields
                Console.WriteLine($"Macro File ID: {macro.MacroPdf417FileID}, Segment ID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {macro.MacroPdf417SegmentsCount}, File Name: {macro.MacroPdf417FileName}");
            }
        }
    }
}
```

**Varför detta är viktigt** – Konsolutskriften ger dig omedelbar insyn i både den avkodade texten och makro‑metadata. Detta är användbart för felsökning och för efterföljande bearbetning, såsom att lagra informationen i en databas.

**Förväntad output** (förutsatt att exempelbilden innehåller ett makrosegment):

```
Type: MacroPdf417, Text: https://example.com/document.pdf
Macro File ID: 12, Segment ID: 1
Segments Count: 3, File Name: shipment_manifest.pdf
```

Om bilden innehåller tre segment skriver loopen ut tre block, var och en med ett annat `Segment ID`.

### Steg 5: Hantera fel och rensa resurser

`using`‑satsen disponerar automatiskt `BarCodeReader`. Du bör dock fortfarande fånga undantag som kan uppstå på grund av saknade filer eller format som inte stöds:

```csharp
        try
        {
            // Place the entire reader block here (Steps 1‑4)
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"Error while trying to read barcode from image c#: {ex.Message}");
        }
```

**Varför detta är viktigt** – Robustapplikationer kraschar aldrig för att en fil saknas eller bilden är korrupt. Att tillhandahålla ett tydligt felmeddelande hjälper dig eller ditt supportteam att snabbt diagnostisera problemet.

## Så avkodar du PDF417-streckkod med Aspose.BarCode

Det sekundära nyckelordet **how to decode pdf417 barcode** förekommer naturligt i detta avsnitt. Att avkoda en PDF417‑streckkod följer samma mönster som visas ovan, men du kan utelämna `MacroPdf417`‑flaggan om du bara behöver ren text:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Decoded text: {result.CodeText}");
    }
}
```

**Varför du kan välja denna variant** – När streckkoden inte innehåller makroinformation minskar användning av `DecodeType.Pdf417` bearbetningsbördan och förenklar hanteringen av resultatet.

**Vanlig fråga:** *Vad händer om streckkoden är roterad?*  
Aspose.BarCode upptäcker automatiskt rotation och korrigerar den, så du behöver ingen extra bild‑förbehandlingskod.

## Fullständigt, körbart exempel

Kopiera hela programmet nedan till ett nytt konsolprojekt (`dotnet new console`) och ersätt `YOUR_DIRECTORY/ExtPDF417Meta.png` med den faktiska sökvägen till din bild.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    var macro = barcodeResult.Extended?.Pdf417;

                    Console.WriteLine($"Type: {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");

                    if (macro != null)
                    {
                        Console.WriteLine($"Macro File ID: {macro.MacroPdf417FileID}, Segment ID: {macro.MacroPdf417SegmentID}");
                        Console.WriteLine($"Segments Count: {macro.MacroPdf417SegmentsCount}, File Name: {macro.MacroPdf417FileName}");
                    }
                    else
                    {
                        Console.WriteLine("No macro PDF417 metadata available.");
                    }
                }
            }
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"Error while trying to read barcode from image c#: {ex.Message}");
        }
    }
}
```

När du kör programmet skrivs streckkodstypen, avkodad text och eventuell makro‑metadata ut. Om bilden inte innehåller en PDF417‑makro informerar programmet dig på ett smidigt sätt.

## Slutsats

Du vet nu hur du **läser streckkod från bild c#** med Aspose.BarCode, hur du **avkodar PDF417-streckkod**, och hur du extraherar de utökade makro‑PDF417‑fälten. Lösningen täcker initiering, iteration, åtkomst till metadata, felhantering och en variant för ren PDF417‑avkodning.

Från och med nu kan du:

* Spara den extraherade datan i en SQL-databas för senare hämtning.  
* Kombinera flera segment för att återuppbygga originaldokumentet.  
* Utforska andra symboltyper som stöds av Aspose.BarCode, such

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man läser PDF417 i C# – Komplett streckkodsexempel](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [Hur man läser PDF417 i C# – Komplett streckkodsläsarexempel](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Hur man genererar PDF417-streckkodbild i C# med Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}