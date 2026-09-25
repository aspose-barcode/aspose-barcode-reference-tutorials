---
category: general
date: 2026-08-22
description: Hur man läser PDF417‑streckkoder i C# med en steg‑för‑steg‑guide, som
  täcker hur man läser flera streckkoder från en bild och extraherar MacroPdf417‑detaljer.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcodes image c#
language: sv
lastmod: 2026-08-22
og_description: Hur man läser PDF417‑streckkoder i C# snabbt. Denna handledning visar
  hur du läser flera streckkoder från en bild och hämtar utökad information från MacroPdf417.
og_image_alt: Developer console displaying MacroPdf417 barcode details extracted by
  C# code
og_title: Hur man läser PDF417‑streckkoder i C# – fullständig programmeringsgenomgång
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to read PDF417 barcodes in C# with a step‑by‑step guide, covering
    how to read multiple barcodes from an image and extract MacroPdf417 details.
  headline: How to read PDF417 barcodes in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Hur man läser PDF417‑streckkoder i C# – komplett guide
url: /sv/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man läser PDF417‑streckkoder i C# – komplett guide

Om du behöver **hur man läser PDF417** staplar i en .NET‑applikation, ger den här handledningen dig en färdig‑till‑körning‑lösning. Du kommer att lära dig hur du läser flera streckkoder från en enda bild, extraherar hela MacroPdf417‑datamängden och visar den i konsolen. Tillvägagångssättet fungerar med Aspose.BarCode för .NET‑biblioteket och kräver bara några få rader kod.

Att läsa streckkoder från en bild är en vanlig uppgift i lagerhanteringssystem, biljettvalidering och dokumenthantering. I slutet av den här guiden kommer du att kunna avkoda vilken PDF417‑ eller MacroPdf417‑streckkod som helst, hantera flera koder i en bild och förstå de utökade fält som MacroPdf417 tillhandahåller.

## Förutsättningar

- .NET 6.0 SDK eller senare (koden kompileras också med .NET Framework 4.7+)
- Visual Studio 2022 eller någon C#‑redigerare du föredrar
- Aspose.BarCode for .NET NuGet‑paket (`Install-Package Aspose.BarCode`)
- En exempelbild som innehåller en MacroPdf417‑streckkod (t.ex. `MacroPdf417.png`)

Ingen ytterligare konfiguration krävs; biblioteket hanterar bildladdning och avkodning internt.

## Så läser du PDF417‑streckkoder från en bild i C#

Kärnan i lösningen är klassen `BarCodeReader`. Den öppnar bilden, upptäcker alla streckkoder av den angivna typen och returnerar en samling av `BarCodeResult`‑objekt. Följande kod visar ett komplett konsolprogram.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            // Path to the image that contains one or more MacroPdf417 barcodes
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // 1️⃣ Initialize the reader for MacroPdf417 barcodes.
            // DecodeType.MacroPdf417 tells the engine to look for the extended PDF417 format.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Iterate over every barcode found in the image.
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Print basic information.
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // 4️⃣ Access MacroPdf417 extended fields.
                    // The Extended property contains format‑specific data; for PDF417 it is .Pdf417.
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

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Varför varje rad är viktig

| Steg | Syfte |
|------|-------|
| **1️⃣ Initialize** | Skapar en `BarCodeReader` bunden till bildfilen och begränsar detektering till MacroPdf417‑symbologi, vilket snabbar upp bearbetningen. |
| **2️⃣ Iterate** | `ReadBarCodes()` returnerar **alla** streckkoder som matchar den begärda typen, vilket gör att du kan **läsa flera streckkoder** utan extra loopar. |
| **3️⃣ Basic output** | Visar det generiska `CodeTypeName` och den mänskligt läsbara `CodeText`. Detta är användbart för loggning eller snabb validering. |
| **4️⃣ Extended data** | MacroPdf417 bär med sig ytterligare metadata (fil‑ID, segmentantal, tidsstämplar osv.). `Extended.Pdf417`‑objektet exponerar varje fält direkt, så du kan lagra eller verifiera hela datapaketet. |

Att köra programmet mot en giltig MacroPdf417‑bild ger konsolutdata som liknar följande:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345678
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x9A3F
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2024-07-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

Utdata bekräftar att biblioteket framgångsrikt läste streckkoden, extraherade texten och levererade varje MacroPdf417‑fält.

## Läsa flera streckkoder från en enda bild

Många verkliga scenarier placerar flera PDF417‑symboler på en etikett – tänk på ett fraktmanifest som innehåller en transportörskod, ett spårningsnummer och en tulldeklaration. Samma kodblock ovan **läser redan flera streckkoder** eftersom `ReadBarCodes()` returnerar en enumerabel av alla matchningar. Ingen extra konfiguration behövs; du behöver bara loopa igenom resultaten, som demonstrerat.

Om du vill begränsa läsaren till standard‑PDF417 (icke‑macro) men ändå hantera flera koder, ersätt `DecodeType.MacroPdf417` med `DecodeType.Pdf417`. Resten av logiken förblir oförändrad.

## Förstå MacroPdf417 utökade data

MacroPdf417 är en utökning av den vanliga PDF417‑specifikationen. Den delar stora nyttolaster i flera segment och lägger till ett litet huvud som beskriver hela filen. De mest relevanta fälten är:

- **MacroPdf417FileID** – ett unikt identifierare som delas av alla segment av samma fil.
- **MacroPdf417SegmentID** – sekvensnumret för det aktuella segmentet.
- **MacroPdf417SegmentsCount** – totalt förväntat antal segment.
- **MacroPdf417FileName** – valfritt filnamn som överförs med streckkoden.
- **MacroPdf417Checksum** – felkontrollvärde för hela filen.
- **MacroPdf417FileSize** – storlek på den ursprungliga binära nyttolasten.
- **MacroPdf417TimeStamp** – ISO‑8601‑tidsstämpel när streckkoden genererades.
- **MacroPdf417Addressee / Sender** – valfria textfält för routing.
- **MacroPdf417Terminator** – indikerar om detta segment är det sista.

När du har mottagit alla segment kan du rekonstruera den ursprungliga filen genom att sortera dem efter `MacroPdf417SegmentID` och concatenera `CodeText`‑värdena. Denna logik är enkel att implementera när du har fälten tillgängliga.

## Vanliga fallgropar och pro‑tips

- **Image quality matters** – lågupplösta eller kraftigt komprimerade PNG/JPEG‑filer kan leda till missade detekteringar. Använd minst 300 dpi för tryckta streckkoder.
- **Mixed symbologies** – om bilden innehåller både MacroPdf417 och vanlig PDF417, skapa två läsare (en för varje `DecodeType`) eller använd `DecodeType.AllSupported` och filtrera resultat efter `result.CodeTypeName`.
- **Memory usage** – `using`‑satsen disponerar `BarCodeReader` omedelbart, vilket förhindrar att stora bildbuffertar ligger kvar i minnet.
- **Thread safety** – `BarCodeReader` är inte trådsäker. Skapa en separat instans per tråd om du avkodar bilder parallellt.
- **Error handling** – omslut anropet till `ReadBarCodes()` med ett try/catch‑block för att fånga `BarCodeException` vid korrupta bilder.

## Fullständig fungerande exempel‑sammanfattning

Nedan är det kompletta programmet som du kan kopiera in i ett nytt konsolprojekt. Det inkluderar alla `using`‑direktiv, en konstant för bildsökvägen och disposeringsmönstret.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

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
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

Kompilera med `dotnet build` och kör med `dotnet run`. Konsolen skriver ut varje streckkods grunddata samt hela MacroPdf417‑payloaden.

## Nästa steg

- **Reconstruct multipart files** – collect all segments, sort by `MacroPdf417SegmentID`, and concatenate `CodeText` to

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar PDF417‑streckkod – kompakt PDF417‑kodning](/barcode/english/net/compact-pdf417-encoding/)
- [Hur man läser PDF417‑streckkoder med turkiska tecken i Java](/barcode/english/java/multilingual-support/recognizing-pdf417-turkish-characters/)
- [Hur man använder Aspose för PDF417‑streckkod (kinesiska) i Java](/barcode/english/java/multilingual-support/recognizing-pdf417-chinese-characters/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}