---
category: general
date: 2026-07-15
description: Hur man läser PDF417‑streckkod i C# och läser flera streckkoder från
  en bild. Lär dig att läsa streckkodsbilder i C# med detaljerad kod och tips.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcode image c#
- Aspose.BarCode PDF417
- C# barcode decoding
language: sv
lastmod: 2026-07-15
og_description: Hur man läser PDF417‑streckkod i C# snabbt. Den här guiden visar hur
  du läser flera streckkoder från en enda bild och avkodar varje egenskap.
og_image_alt: Screenshot of C# console output displaying PDF417 barcode details
og_title: Hur man läser PDF417 i C# – Fullt kodexempel och förklaring
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  headline: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  name: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  steps:
  - name: Why This Code Works
    text: '* **`BarCodeReader`** is the core class that streams the image, detects
      barcodes, and returns a collection of `BarCodeResult` objects. * Passing **`DecodeType.MacroPdf417`**
      tells the library to treat Macro‑PDF417 specially; it still returns plain PDF417
      symbols, which satisfies the **read multiple '
  - name: What if the image has both Macro‑PDF417 and regular PDF417 symbols?
    text: The same `BarCodeReader` call will return both. You can differentiate them
      by checking `result.CodeType` (`MacroPdf417` vs `Pdf417`). The extended properties
      will be `null` for a plain PDF417, so the `if (macro != null)` guard prevents
      a `NullReferenceException`.
  - name: My barcode is rotated or skewed—will the reader still work?
    text: Aspose.BarCode includes built‑in rotation and distortion compensation. As
      long as the barcode is at least 30 % of the image width, the decoder will usually
      succeed. For extreme cases you can enable `reader.Options.AllowInvertedBarcodes
      = true;` before calling `ReadBarCodes()`.
  - name: How do I handle large batches of images?
    text: Wrap the reading logic in a `foreach (var file in Directory.GetFiles(folder,
      "*.png"))` loop. The `using` pattern ensures each image’s native resources are
      freed before the next iteration, keeping memory usage low.
  type: HowTo
tags:
- C#
- barcode
- PDF417
- Aspose
title: Hur man läser PDF417 i C# – Komplett steg‑för‑steg‑guide
url: /sv/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man läser PDF417 i C# – Komplett steg‑för‑steg‑guide

Har du någonsin undrat **hur man läser PDF417** från en bild med C#? Du är inte ensam. De flesta utvecklare stöter på problem när de måste hämta de utökade Macro‑PDF417-fälten från ett skannat dokument. Den goda nyheten? Med bara några rader kod kan du avkoda en PDF417, läsa flera streckkoder i samma bild och hämta varje dold egenskap som specifikationen erbjuder.

I den här handledningen går vi igenom ett verkligt exempel som visar **hur man läser PDF417**, hur man **läser flera streckkoder** från en enda fil, och varför **read barcode image C#**‑kod ser ut som den gör. I slutet har du en färdigkörbar konsolapp som skriver ut varje bit information du kan behöva—fil‑ID, segment‑ID, kontrollsumma, tidsstämplar, du namnger det.

## Förutsättningar

* .NET 6.0 SDK eller senare (koden fungerar även med .NET Core och .NET Framework).  
* Visual Studio 2022 (eller någon annan editor du föredrar).  
* NuGet‑paketet **Aspose.BarCode for .NET** – detta är biblioteket som faktiskt parsar PDF417.  
* En exempelbild som innehåller en Macro‑PDF417‑streckkod (t.ex. `ExtPDF417Meta.png`).  

Ingen extra konfiguration krävs; biblioteket levereras med alla dekodrar du behöver.

## Steg 1: Installera Aspose.BarCode

Öppna din projektmapp i en terminal och kör:

```bash
dotnet add package Aspose.BarCode
```

Det kommandot hämtar den senaste stabila versionen (i juli 2026 är den 23.12). Om du föredrar Package Manager Console i Visual Studio, använd:

```powershell
Install-Package Aspose.BarCode
```

> **Proffstips:** lås versionen (`23.12.0`) i din `.csproj` för att undvika oavsiktliga brytande förändringar senare.

## Steg 2: Skapa ett konsolapp‑skelett

Skapa ett nytt konsolprojekt om du inte redan har ett:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Ersätt den automatiskt genererade `Program.cs` med koden nedan. Vi kommer att förklara varje block i nästa avsnitt.

## Steg 3: Skriv den kompletta “How to Read PDF417”-koden

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
            // -----------------------------------------------------------------
            // 1️⃣  Set the path to the image that contains one or more PDF417 codes
            // -----------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarCodeReader for MacroPdf417 decoding
            // -----------------------------------------------------------------
            // The DecodeType flag tells Aspose to look specifically for Macro‑PDF417,
            // but it will also pick up plain PDF417 symbols that happen to be in the
            // same image – perfect for the “read multiple barcodes” scenario.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // -----------------------------------------------------------------
                // 3️⃣  Iterate over every barcode found in the image
                // -----------------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -------------------------------------------------------------
                    // 4️⃣  Basic barcode information – works for any barcode type
                    // -------------------------------------------------------------
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // -------------------------------------------------------------
                    // 5️⃣  Macro‑PDF417 extended properties (the real reason you’re here)
                    // -------------------------------------------------------------
                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40)); // visual separator
                }
            }

            // -----------------------------------------------------------------
            // 6️⃣  Keep the console window open when running from VS
            // -----------------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

### Varför den här koden fungerar

* **`BarCodeReader`** är kärnklassen som strömmar bilden, upptäcker streckkoder och returnerar en samling av `BarCodeResult`‑objekt.  
* Att skicka **`DecodeType.MacroPdf417`** talar om för biblioteket att behandla Macro‑PDF417 speciellt; det returnerar fortfarande vanliga PDF417‑symboler, vilket uppfyller kravet på **read multiple barcodes**.  
* Objektet **`Extended.Pdf417.MacroPdf417`** innehåller alla valfria fält som definieras av ISO/IEC 15438‑standarden – där får du `FileID`, `SegmentID`, `Checksum` osv.  
* `using`‑blocket garanterar att de inhemska resurserna frigörs, vilket förhindrar minnesläckor i långkörande tjänster.

## Steg 4: Kör applikationen och verifiera utskrift

Från terminalen:

```bash
dotnet run
```

Du bör se något liknande:

```
Code Type : MacroPdf417
Code Text : 1234567890...
File ID          : 12
Segment ID       : 1
Segments Count   : 3
File Name        : invoice2024.pdf
Checksum         : 9A3F
File Size        : 245760
Time Stamp       : 2024-11-02T14:23:00Z
Addressee        : Acme Corp
Sender           : Logistics Dept
Terminator       : 1
----------------------------------------
Done. Press any key to exit...
```

Om bilden innehåller mer än en streckkod kommer loopen att skriva ut en avgränsningslinje (`----------------------------------------`) och fortsätta med nästa resultat—precis vad **read multiple barcodes** ser ut som i praktiken.

## Vanliga frågor & specialfall

### Vad händer om bilden har både Macro‑PDF417 och vanliga PDF417‑symboler?

Samma `BarCodeReader`‑anrop returnerar båda. Du kan skilja dem åt genom att kontrollera `result.CodeType` (`MacroPdf417` vs `Pdf417`). De utökade egenskaperna blir `null` för en vanlig PDF417, så skyddet `if (macro != null)` förhindrar ett `NullReferenceException`.

### Min streckkod är roterad eller skev—kommer läsaren fortfarande fungera?

Aspose.BarCode innehåller inbyggd kompensation för rotation och förvrängning. Så länge streckkoden täcker minst 30 % av bildens bredd lyckas dekodern oftast. För extrema fall kan du aktivera `reader.Options.AllowInvertedBarcodes = true;` innan du anropar `ReadBarCodes()`.

### Hur hanterar jag stora bildbatcher?

Omslut läslogiken i en `foreach (var file in Directory.GetFiles(folder, "*.png"))`‑loop. `using`‑mönstret säkerställer att varje bilds inhemska resurser frigörs innan nästa iteration, vilket håller minnesanvändningen låg.

## Fullständig källkodslista (klar för kopiering och inklistring)

Nedan är hela programmet i ett block för snabb kopiering och inklistring. Inga dolda beroenden—bara Aspose.BarCode‑NuGet‑paketet.

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
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

## Sammanfattning – Vad vi gick igenom

* **How to read PDF417** using Aspose.BarCode in C#.  
* De exakta stegen för att **read multiple barcodes** från en enda bild.  
* Hur man **read barcode image C#** och extraherar varje Macro‑PDF417‑fält.  
* Tips för rotation, batch‑bearbetning och hantering av saknade utökade data.

## Nästa steg & relaterade ämnen

* **Encode PDF417** – generera dina egna Macro‑PDF417‑streckkoder med `BarCodeBuilder`.  
* **Read other 2‑D symbologies** – QR, DataMatrix, Aztec – med samma `BarCodeReader`‑klass.  
* **Integrate with ASP.NET Core** – exponera en web‑endpoint som tar emot en uppladdad bild och returnerar JSON med de avkodade fälten.  

Känn dig fri att experimentera: ändra bildsökvägen, släng in en vanlig PDF417 i samma mapp, eller justera `DecodeType`‑flaggorna för att se hur biblioteket beter sig. Ju mer du leker, desto bekvämare blir du med **read barcode image C#**‑scenarier.

Har du en knepig bild som vägrar att avkodas? Lämna en kommentar nedan eller öppna ett ärende i GitHub‑repot för exempelprojektet. Lycka till med kodandet!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man läser DataMatrix‑streckkoder med Aspose.BarCode för .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Hur man skapar streckkod – Compact PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Läs DataMatrix‑streckkod C# – Generera DataMatrix‑läge (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}