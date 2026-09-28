---
category: general
date: 2026-09-28
description: Läs PDF417-streckkod c# snabbt med Aspose.BarCode. Avkoda flera streckkoder
  från en bild, extrahera Macro‑PDF417-fält och hantera rotation eller batchbearbetning.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read pdf417 barcode c#
- read multiple barcodes
- pdf417 c# decoding
- Aspose.BarCode PDF417
- barcode image c#
lastmod: 2026-09-28
og_description: Läs PDF417-streckkod c# snabbt med Aspose.BarCode. Denna guide visar
  hur du avkodar flera streckkoder från en enda bild, extraherar alla Macro‑PDF417-egenskaper
  och hanterar roterade eller batchbilder.
og_image_alt: Screenshot of C# console output displaying PDF417 barcode details
og_title: Läs PDF417-streckkod c# – komplett kodexempel & guide
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Read PDF417 barcode c# and read multiple barcodes from an image. Learn
    to read barcode image C# with detailed code and tips.
  headline: Read PDF417 barcode c# – complete step‑by‑step guide
  type: TechArticle
- description: Read PDF417 barcode c# and read multiple barcodes from an image. Learn
    to read barcode image C# with detailed code and tips.
  name: Read PDF417 barcode c# – complete step‑by‑step guide
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
title: Hur man läser PDF417-streckkod c# – komplett steg‑för‑steg‑guide
url: /sv/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så läser du PDF417-streckkod c# – komplett steg‑för‑steg‑guide

Har du någonsin undrat **hur man läser PDF417** från en bild med C#? Du är inte ensam. De flesta utvecklare stöter på problem när de måste extrahera de utökade Macro‑PDF417‑fälten från ett skannat dokument. Den goda nyheten? Med bara några rader kod kan du **läsa PDF417-streckkod c#**, avkoda flera streckkoder i samma bild och hämta varje dold egenskap som specifikationen erbjuder.

## Snabba svar
- **Kan Aspose.BarCode avkoda Macro‑PDF417?** Ja – aktivera bara `DecodeType.MacroPdf417` så returnerar biblioteket alla utökade fält.  
- **Hur många streckkoder kan läsas från en bild?** Obegränsat; API:et returnerar en samling av `BarCodeResult`‑objekt.  
- **Behöver jag en licens för produktion?** En kommersiell licens krävs för produktionsanvändning; en gratis provversion fungerar för utvärdering.  
- **Kommer roterade streckkoder att upptäckas?** Inbyggd rotationskompensation fungerar för streckkoder som täcker minst 30 % av bildens bredd.  
- **Stöds batch‑behandling?** Absolut – omslut läsaren i en `foreach`‑loop och frigör varje instans med `using`.

## Vad är read PDF417 barcode c#?
`read pdf417 barcode c#` avser processen att använda ett .NET‑bibliotek för att avkoda PDF417‑symboler (inklusive Macro‑PDF417) från bildfiler direkt i C#‑kod. Aspose.BarCode SDK erbjuder ett en‑anrop‑API som hanterar bildladdning, streckkoddetektering och extraktion av alla ISO‑definierade fält.

## Varför använda Aspose.BarCode för PDF417‑avkodning?
Aspose.BarCode stödjer **30+ streckkodssymboler** och kan bearbeta bilder upp till **5000 × 5000 px** på under **0,1 s** på vanlig serverhårdvara. Det erbjuder dessutom inbyggd rotation, förvrängning och hantering av inverterade streckkoder, vilket eliminerar behovet av anpassad bild‑förbehandling. Biblioteket innehåller också inbyggt stöd för att läsa Macro‑PDF417‑utökade fält, vilket gör det till en komplett lösning för komplexa skanningsscenarier.

## Förutsättningar

* .NET 6.0 SDK eller senare (koden fungerar även med .NET Core och .NET Framework).  
* Visual Studio 2022 (eller någon annan editor du föredrar).  
* **Aspose.BarCode for .NET** NuGet‑paketet – detta är biblioteket som faktiskt parsar PDF417.  
* En exempelbild som innehåller en Macro‑PDF417‑streckkod (t.ex. `ExtPDF417Meta.png`).  

Ingen extra konfiguration krävs; biblioteket levereras med alla avkodare du behöver.

## Så läser du PDF417-streckkod c#?

Läs in bilden med `BarCodeReader`, ange `DecodeType.MacroPdf417` och iterera över den returnerade `BarCodeResult`‑samlingen – det är den kompletta lösningen på under tio kodrader. Läsaren extraherar automatiskt både vanliga PDF417‑symboler och Macro‑PDF417‑utökad data, så du får filidentifierare, segmentnummer, tidsstämplar och kontrollsummor utan extra parsning.

### Steg 1: installera Aspose.BarCode

Öppna din projektmapp i en terminal och kör:

```bash
dotnet add package Aspose.BarCode
```

Det kommandot hämtar den senaste stabila versionen (i juli 2026 är den 23.12). Om du föredrar Package Manager Console i Visual Studio, använd:

```powershell
Install-Package Aspose.BarCode
```

> **Proffstips:** lås versionen (`23.12.0`) i din `.csproj` för att undvika oavsiktliga brytande förändringar senare.

### Steg 2: skapa ett konsolapp‑skelett

Skapa ett nytt konsolprojekt om du inte redan har ett:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Ersätt den automatiskt genererade `Program.cs` med koden nedan. Vi kommer att förklara varje block i nästa avsnitt.

### Steg 3: skriv den kompletta “how to read PDF417”-koden

`BarCodeReader` är kärnklassen som strömmar bilden, upptäcker streckkoder och returnerar en samling av `BarCodeResult`‑objekt.

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

* `BarCodeReader` — den primära klassen som ansvarar för att läsa och avkoda streckkoder från bilder.  
* `DecodeType.MacroPdf417` — en flagga som instruerar SDK:n att behandla Macro‑PDF417 särskilt samtidigt som vanliga PDF417‑symboler returneras.  
* `Extended.Pdf417.MacroPdf417` — objektet som innehåller alla valfria fält definierade av ISO/IEC 15438, såsom `FileID`, `SegmentID` och `Checksum`.

`using`‑blocket garanterar att de inhemska resurserna frigörs, vilket förhindrar minnesläckor i långvariga tjänster.

### Steg 4: kör applikationen och verifiera utskriften

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

Om bilden innehåller mer än en streckkod skriver loopen ut en avgränsningsrad (`----------------------------------------`) och fortsätter med nästa resultat – exakt så **read multiple barcodes** ser ut i praktiken.

## Vanliga frågor och specialfall

### Vad händer om bilden har både Macro‑PDF417 och vanliga PDF417‑symboler?

Samma `BarCodeReader`‑anrop returnerar båda. Du kan skilja dem åt genom att kontrollera `result.CodeType` (`MacroPdf417` vs `Pdf417`). De utökade egenskaperna blir `null` för en vanlig PDF417, så skyddet `if (macro != null)` förhindrar ett `NullReferenceException`.

### Min streckkod är roterad eller skev – fungerar läsaren fortfarande?

Aspose.BarCode innehåller inbyggd rotations- och förvrängningskompensation. Så länge streckkoden täcker minst 30 % av bildens bredd lyckas avkodaren vanligtvis. För extrema fall kan du aktivera `reader.Options.AllowInvertedBarcodes = true;` innan du anropar `ReadBarCodes()`.

### Hur hanterar jag stora bildbatchar?

Omslut läslogiken i en `foreach (var file in Directory.GetFiles(folder, "*.png"))`‑loop. `using`‑mönstret säkerställer att varje bilds inhemska resurser frigörs innan nästa iteration, vilket håller minnesanvändningen låg.

## Fullständig källkod (redo att kopiera och klistra in)

Nedan är hela programmet i ett block för snabb kopiering och inklistring. Inga dolda beroenden – bara Aspose.BarCode‑NuGet‑paketet.

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

## Sammanfattning – vad vi gick igenom

* **Hur man läser PDF417-streckkod c#** med Aspose.BarCode.  
* De exakta stegen för att **läsa flera streckkoder** från en enda bild.  
* Hur man **läser streckkod bild c#** och extraherar varje Macro‑PDF417‑fält.  
* Tips för rotation, batch‑behandling och hantering av saknad utökad data.

## Nästa steg och relaterade ämnen

* **Encode PDF417** – generera dina egna Macro‑PDF417‑streckkoder med `BarCodeBuilder`.  
* **Läs andra 2‑D‑symbologier** – QR, DataMatrix, Aztec – med samma `BarCodeReader`‑klass.  
* **Integrera med ASP.NET Core** – exponera en webb‑endpoint som tar emot en uppladdad bild och returnerar JSON med de avkodade fälten.  

### Ytterligare användbara länkar
- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)  
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)  
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

Känn dig fri att experimentera: ändra bildsökvägen, släng en vanlig PDF417 i samma mapp eller justera `DecodeType`‑flaggorna för att se hur biblioteket beter sig. Ju mer du leker, desto bekvämare blir du med **read barcode image c#**‑scenarier.

Har du en knepig bild som vägrar att avkodas? Lämna en kommentar nedan eller öppna ett ärende i GitHub‑repot för exempelprojektet. Lycka till med kodningen!

## Vanliga frågor

**Q: Kan jag använda detta i en kommersiell applikation?**  
A: Ja, du kan använda Aspose.BarCode i kommersiella projekt så länge du har en giltig licens; en gratis provversion finns för utvärdering.

**Q: Stöder läsaren lösenordsskyddade bilder?**  
A: SDK:n fungerar med alla standardbildformat; lösenordsskydd är inte tillämpligt på rasterbilder, bara på PDF‑filer, som hanteras av en separat Aspose.PDF‑komponent.

**Q: Vilka .NET‑versioner stöds?**  
A: .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ och .NET 6+ stöds alla fullt ut av den nuvarande Aspose.BarCode‑utgåvan.

**Q: Hur kan jag förbättra prestandan för mycket stora bildbatchar?**  
A: Aktivera `reader.Options.Quality = QualityMode.HighPerformance` och bearbeta bilder parallellt med `Parallel.ForEach` samtidigt som varje `BarCodeReader` omsluts av ett `using`‑block.

**Q: Finns det ett sätt att få endast Macro‑PDF417‑fälten utan att iterera alla resultat?**  
A: Ja – efter att ha anropat `ReadBarCodes()` filtrerar du samlingen med `result => result.CodeType == DecodeType.MacroPdf417` och får sedan åtkomst till egenskapen `Extended.Pdf417.MacroPdf417`.

---

**Last updated:** 2026-09-28  
**Tested with:** Aspose.BarCode 23.12 for .NET  
**Author:** Aspose

## Relaterade handledningar

- [How To Generate Pdf417 Barcode Image In C With Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Create Pdf417 Barcode With Aspose Barcode Step By Step Guide](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-barcode-step-by-step-guide/)
- [Read Multiple Barcodes C Complete Guide With Pdf417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}