---
category: general
date: 2026-09-26
description: Lär dig hur du avkodar PDF417 i C# med ett steg‑för‑steg-exempel på streckkodsläsare.
  Denna guide visar hur du läser streckkodsbild i C# med Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcode image c#
- c# barcode reader example
language: sv
lastmod: 2026-09-26
og_description: Hur man avkodar PDF417 i C# snabbt. Följ detta exempel på streckkodsläsare
  för att läsa streckkodsbilder i C# med Aspose.BarCode och extrahera makrodetaljer.
og_image_alt: Screenshot showing how to decode PDF417 in C# using Aspose.BarCode
og_title: Hur man avkodar PDF417 i C# – komplett guide för streckkodsläsare
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to decode PDF417 in C# with a step‑by‑step barcode reader
    example. This guide shows you how to read barcode image C# using Aspose.BarCode.
  headline: How to decode PDF417 in C# – barcode reader example
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Hur man avkodar PDF417 i C# – exempel på streckkodsläsare
url: /sv/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man avkodar PDF417 i C# – exempel på streckkodsläsare

Om du behöver **hur man avkodar PDF417** i en .NET‑applikation, ger den här handledningen en komplett, färdig‑att‑köra lösning. Du får se hur du läser en streckkodsbild i C# med Aspose.BarCode‑biblioteket, hämtar den utökade PDF417‑makroinformationen och visar varje relevant fält.

Avkodning av PDF417 är inte begränsad till vanlig text; formatet kan bära data om filsegmentering, tidsstämplar och kontrollsummor. Denna guide går igenom varje steg, förklarar varför koden är strukturerad som den är och lyfter fram vanliga fallgropar du kan stöta på när du implementerar ett C#‑exempel på streckkodsläsare.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 (eller senare) SDK installerad  
* Visual Studio 2022 (eller någon C#‑kompatibel IDE)  
* **Aspose.BarCode for .NET** NuGet‑paket (`Aspose.BarCode`)  
* En exempel‑Macro PDF417‑bild (t.ex. `ExtPDF417Meta.png`)

Dessa krav säkerställer att koden kompileras och körs utan ytterligare konfiguration.

## Steg 1: Installera Aspose.BarCode NuGet‑paketet

Det första steget i alla **read barcode image C#**‑projekt är att lägga till streckkodsbiblioteket. Öppna terminalen i din lösningsmapp och kör:

```bash
dotnet add package Aspose.BarCode
```

Paketet tillhandahåller `BarCodeReader`, `DecodeType` och egenskapen `Extended` som används för att komma åt makrodatan. Att installera det en gång gör klasserna tillgängliga i hela ditt projekt.

## Steg 2: Skapa en streckkodsläsare för en Macro PDF417‑bild

Nu kan du instansiera `BarCodeReader` med sökvägen till bilden och ange `DecodeType.MacroPdf417`. Detta talar om för biblioteket att leta efter det utökade PDF417‑formatet som innehåller makroinformation.

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Path to the Macro PDF417 image
string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

// Initialize the reader for Macro PDF417 decoding
using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is ready – next we will extract barcodes.
}
```

**Varför detta är viktigt:**  
`DecodeType.MacroPdf417` aktiverar den makro‑specifika parsern. Om du utelämnar den returnerar läsaren bara den rena textpayloaden och ignorerar de makrofält du sannolikt behöver för filrekonstruktion.

## Steg 3: Läs alla streckkoder som finns i bilden

En enda bild kan innehålla flera PDF417‑symboler, särskilt när data är uppdelad i segment. Att loopa genom `ReadBarCodes()` garanterar att du fångar varje segment.

```csharp
// Step 3: Iterate over each detected barcode
foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
{
    // Inside the loop we will access both basic and macro data.
}
```

**Varför loopa:**  
PDF417‑makrodatan visas ofta i flera segment. Genom att bearbeta varje `BarCodeResult` samlar du in hela uppsättningen makrofält, såsom `MacroPdf417FileID` och `MacroPdf417SegmentsCount`.

## Steg 4: Hämta och visa grundläggande streckkodsdata

`BarCodeResult`‑objektet innehåller typen och den avkodade texten. Att visa dessa värden hjälper dig verifiera att läsaren korrekt identifierade symbolen innan du dyker djupare in i makrodetaljer.

```csharp
Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
Console.WriteLine($"CodeText: {barcodeResult.CodeText}");
```

**Tips:** Om `CodeText` är tom kan bilden vara korrupt eller så är avkodningsläget felaktigt. Dubbelkolla `DecodeType` som användes vid initieringen.

## Steg 5: Extrahera den utökade PDF417‑makroinformationen

Makrodatan finns under `barcodeResult.Extended.Pdf417`. Varje egenskap motsvarar ett fält som definieras i PDF417‑specifikationen.

```csharp
// Step 5: Access macro-specific fields
var macroInfo = barcodeResult.Extended.Pdf417;

Console.WriteLine($"Pdf417MacroFileID: {macroInfo.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {macroInfo.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount: {macroInfo.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName: {macroInfo.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum: {macroInfo.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize: {macroInfo.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp: {macroInfo.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee: {macroInfo.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender: {macroInfo.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator: {macroInfo.MacroPdf417Terminator}");
```

**Vad varje fält betyder**

| Egenskap | Beskrivning |
|----------|-------------|
| `MacroPdf417FileID` | Identifierare som grupperar alla segment som tillhör samma logiska fil. |
| `MacroPdf417SegmentID` | Index för det aktuella segmentet (börjar på 1). |
| `MacroPdf417SegmentsCount` | Totalt antal segment som krävs för att rekonstruera originalfilen. |
| `MacroPdf417FileName` | Valfritt filnamn inbäddat i makrot. |
| `MacroPdf417Checksum` | CRC‑16‑kontrollsumma för integritetsverifiering. |
| `MacroPdf417FileSize` | Förväntad storlek på den rekonstruerade filen (i byte). |
| `MacroPdf417TimeStamp` | Datum‑tid då makrot genererades. |
| `MacroPdf417Addressee` | Valfri mottagaridentifierare. |
| `MacroPdf417Sender` | Valfri avsändaridentifierare. |
| `MacroPdf417Terminator` | Terminator‑flagga; bör vara `true` i sista segmentet. |

Att förstå dessa fält låter dig återuppbygga originalfilen, validera dataintegritet och implementera anpassad affärslogik (t.ex. avvisa föråldrade dokument).

## Steg 6: Hantera flera segment och återuppbygg originalfilen (avancerat)

När `MacroPdf417SegmentsCount` är större än 1 måste du samla varje segment, sortera dem efter `MacroPdf417SegmentID` och konkatenera `CodeText`‑värdena. Nedan är en koncis implementation:

```csharp
// Collect segments in a dictionary keyed by SegmentID
var segments = new SortedDictionary<int, string>();

foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
{
    var macro = result.Extended.Pdf417;
    segments[macro.MacroPdf417SegmentID] = result.CodeText;
}

// Verify that we received all expected segments
int expectedCount = segments.First().Value != null
    ? barcodeReader.ReadBarCodes().First().Extended.Pdf417.MacroPdf417SegmentsCount
    : 0;

if (segments.Count == expectedCount)
{
    // Reconstruct the full payload
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine($"Reconstructed payload ({fullPayload.Length} chars):");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Warning: Expected {expectedCount} segments but received {segments.Count}.");
}
```

**Varför detta är viktigt:**  
Utan sortering och konkatenering blir den avkodade datan ofullständig eller förvrängd. Kodsnutten visar också defensiv programmering genom att kontrollera segmentantalet.

## Steg 7: Avsluta med felhantering och bästa praxis

Ett produktionsklart **c# barcode reader example** bör förutse IO‑fel, ej‑stödda format och korrupta bilder.

```csharp
try
{
    // Existing barcode reading code goes here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image file not found: {ex.Message}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode processing error: {ex.Message}");
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Unexpected error: {ex.Message}");
}
```

**Checklista för bästa praxis**

* Validera bildsökvägen innan du skapar `BarCodeReader`.  
* Använd `using`‑satser för att garantera att oönskade resurser frigörs.  
* Logga makrofält för revisionsspår – särskilt `MacroPdf417Checksum` och `MacroPdf417TimeStamp`.  
* Vid hantering av stora filer, överväg att strömma den konkatenerade payloaden till disk istället för att hålla hela i minnet.

## Förväntad utdata

Att köra hela programmet mot en giltig `ExtPDF417Meta.png` ger en utdata liknande:

```
CodeType: MacroPdf417
CodeText: <base64‑encoded segment data>
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254312
Pdf417MacroTimeStamp: 2024-03-15T10:23:45Z
Pdf417MacroAddressee: Acme Corp
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: False
...
```

Om alla tre segment är närvarande skriver återuppbyggnadsblocket ut hela payloaden efter verifieringsmeddelandet.

## Slutsats

Du vet nu **hur man avkodar PDF417** i C# med ett robust exempel på streckkodsläsare. Handledningen täckte installation av Aspose.BarCode, initiering av en `BarCodeReader` för Macro PDF417, iteration över flera streckkoder, extraktion av makrofält, återuppbyggnad av segmenterad data och implementering av felhantering.  

Härifrån kan du:

* Integrera läsaren i ett web‑API som tar emot uppladdade bilder.  
* Lagra makrometadata i en databas för revisionsändamål.  
* Utöka lösningen till andra 2‑D‑symbologier genom att byta `DecodeType` (e

## Vad bör du lära dig härnäst?

De följande handledningarna täcker närbesläktade ämnen som bygger vidare på teknikerna i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationssätt i dina egna projekt.

- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Read PDF417 barcode in C# – barcode reader example](/barcode/english/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}