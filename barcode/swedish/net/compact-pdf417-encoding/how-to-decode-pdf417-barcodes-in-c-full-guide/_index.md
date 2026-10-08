---
category: general
date: 2026-09-13
description: Lär dig hur du avkodar PDF417 i C# med steg‑för‑steg‑kod som läser flera
  streckkoder och visar streckkoddata för alla applikationer.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read multiple barcodes
- c# barcode decoding
- display barcode data
language: sv
lastmod: 2026-09-13
og_description: Hur avkodar man PDF417 i C#? Följ den här guiden för att läsa flera
  streckkoder och visa streckkoddata med Aspose.BarCode.
og_image_alt: Console window showing decoded PDF417 barcode information
og_title: Hur man avkodar PDF417‑streckkoder i C# – snabb, komplett handledning
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to decode PDF417 in C# with step‑by‑step code that reads
    multiple barcodes and displays barcode data for any application.
  headline: How to decode PDF417 barcodes in C# – full guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
- aspnet
title: Hur man avkodar PDF417‑streckkoder i C# – fullständig guide
url: /sv/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man avkodar PDF417‑streckkoder i C# – fullständig guide

Om du behöver **how to decode pdf417** i ett .NET‑projekt, visar den här handledningen de exakta stegen. Du kommer att se hur du läser flera streckkoder från en enda bild och visar streckkoddata i en tydlig konsolutskrift. I slutet har du ett färdigt C#‑program som hanterar Macro PDF417‑avkodning utan några saknade delar.

Att avkoda PDF417 är inte begränsat till en enda skanning; många verkliga scenarier—såsom fraktetiketter eller boardingkort—inbäddar flera Macro PDF417‑segment i en bild. Denna guide täcker hela arbetsflödet, från installation av biblioteket till utskrift av varje fält du kan behöva, så att du kan integrera streckkodsläsning i vilken C#‑applikation som helst redan idag.

## Vad du behöver

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare (koden fungerar också med .NET Framework 4.7+)
* Visual Studio 2022 (eller någon IDE som stödjer C#)
* **Aspose.BarCode for .NET** NuGet‑paketet – det tillhandahåller `BarCodeReader` och `DecodeType.MacroPdf417`
* En PNG/JPEG‑bild som innehåller en eller flera Macro PDF417‑symboler (t.ex. `MacroPdf417.png`)

> **Proffstips:** Om du inte har en exempelbild kan du generera en med den kostnadsfria Aspose.BarCode‑demo‑sajten eller använda någon scanner som sparar en PDF417‑kodad bild.

## Steg 1: Installera streckkodsbiblioteket

Öppna en terminal i din projektmapp och kör:

```bash
dotnet add package Aspose.BarCode
```

NuGet‑kommandot lägger till den senaste stabila versionen av **Aspose.BarCode for .NET** i ditt projekt och återställer alla nödvändiga beroenden.

## Steg 2: Skapa ett konsolprojekt (om du inte redan har ett)

```bash
dotnet new console -n Pdf417Decoder
cd Pdf417Decoder
```

Den genererade `Program.cs`‑filen kommer att innehålla avkodningslogiken som vi diskuterar härnäst.

## Steg 3: Skriv avkodningskoden – läs flera streckkoder

Byt ut innehållet i `Program.cs` mot det kompletta exemplet nedan. Varje rad förklaras, så att du förstår **c# barcode decoding** inifrån och ut.

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
            // Path to the image that contains one or more Macro PDF417 symbols
            const string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            // 1️⃣ Initialize the BarCodeReader for Macro PDF417 decoding.
            //    The DecodeType.MacroPdf417 flag tells the library to expect
            //    Macro PDF417 symbols, which contain extra fields like FileID.
            using (var barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Read all barcodes present in the image.
                //    The ReadBarCodes() method returns an IEnumerable<BarCodeResult>,
                //    allowing us to iterate over each detected barcode.
                foreach (var barcodeResult in barcodeReader.ReadBarCodes())
                {
                    // 3️⃣ Display the raw text of the barcode.
                    Console.WriteLine($"Decoded Text : {barcodeResult.CodeText}");

                    // 4️⃣ Access Macro PDF417‑specific extended information.
                    //    These properties are only populated when DecodeType.MacroPdf417 is used.
                    var macroInfo = barcodeResult.Extended?.Pdf417?.MacroPdf417;
                    if (macroInfo != null)
                    {
                        Console.WriteLine($"FileID      : {macroInfo.FileID}");
                        Console.WriteLine($"SegmentID   : {macroInfo.SegmentID}");
                        Console.WriteLine($"FileName    : {macroInfo.FileName}");
                        Console.WriteLine($"FileSize    : {macroInfo.FileSize}");
                        Console.WriteLine($"Checksum    : {macroInfo.Checksum}");
                        // Add any other fields you need here.
                    }
                    else
                    {
                        Console.WriteLine("No Macro PDF417 extended data found.");
                    }

                    Console.WriteLine(new string('-', 40)); // visual separator
                }
            }

            // Keep the console window open when debugging locally.
            Console.WriteLine("Decoding finished. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Varför varje del är viktig

* **`using (var barcodeReader = new BarCodeReader(...))`** – Säkerställer att ohanterade resurser frigörs omedelbart, vilket förhindrar minnesläckor i långlivade tjänster.
* **`DecodeType.MacroPdf417`** – Instruerar motorn att leta efter de utökade Macro PDF417‑fälten; utan detta får du bara den rena textpayloaden.
* **`ReadBarCodes()`** – Returnerar *alla* streckkoder i bilden, vilket uppfyller kravet **read multiple barcodes**. Även om bilden bara innehåller en symbol returnerar metoden en samling, vilket håller koden enhetlig.
* **`barcodeResult.Extended.Pdf417.MacroPdf417`** – Ger åtkomst till extra metadata (FileID, SegmentID, osv.) som skiljer Macro PDF417 från en vanlig PDF417. Detta är kärnan i **display barcode data** på ett meningsfullt sätt.
* **Konsolutskrift** – Genom att skriva ut varje fält kan du verifiera att avkodaren fungerar korrekt och du kan senare skicka data till en databas, en fil eller ett API.

## Steg 4: Bygg och kör programmet

```bash
dotnet build
dotnet run
```

Förutsatt att `MacroPdf417.png` finns och innehåller två Macro PDF417‑symboler, kommer konsolen att visa något liknande:

```
Decoded Text : https://example.com/page1
FileID      : 12
SegmentID   : 1
FileName    : document_part1.pdf
FileSize    : 1048576
Checksum    : 0x1A2B3C4D
----------------------------------------
Decoded Text : https://example.com/page2
FileID      : 12
SegmentID   : 2
FileName    : document_part2.pdf
FileSize    : 1048576
Checksum    : 0x5E6F7A8B
----------------------------------------
Decoding finished. Press any key to exit.
```

Om bilden bara innehåller ett enda PDF417‑segment körs loopen fortfarande en gång, vilket uppfyller logiken **read multiple barcodes** utan några kodändringar.

## Steg 5: Vanliga variationer och kantfall

| Situation | Vad som ska ändras |
|-----------|--------------------|
| **Non‑Macro PDF417** (vanlig PDF417) | Använd `DecodeType.Pdf417` istället för `MacroPdf417`. `Extended`‑egenskapen blir `null`, så skydda mot detta enligt exemplet. |
| **Flera bildformat** | `BarCodeReader`‑konstruktorn accepterar alla bildformat som stöds av .NET (`.png`, `.jpg`, `.tif`). Ange bara rätt sökväg. |
| **Stora bildbatcher** | Omslut läslogiken i en `foreach (var file in Directory.GetFiles(folder, "*.png"))`‑loop och återanvänd en enda `BarCodeReader`‑instans per fil för att förbättra genomströmningen. |
| **Prestandaoptimering** | Sätt `barcodeReader.Options.Pdf417.Pdf417CompactionMode = Pdf417CompactionMode.Auto` så att motorn väljer det snabbaste avkodningsläget för varje streckkod. |
| **Felhantering** | Fånga `BarCodeException` runt anropet till `ReadBarCodes()` för att hantera korrupta bilder på ett smidigt sätt. |

## Steg 6: Bästa praxis för C#‑streckkodsavkodning

* **Disposera objekt** – Använd alltid `using`‑satser för `BarCodeReader` och andra disposable‑klasser.
* **Validera resultat** – Kontrollera `barcodeResult.CodeText` för `null` eller tomma strängar innan du bearbetar dem.
* **Logga utökad data** – Spara fält som `FileID` och `SegmentID` i ett strukturerat format (JSON, databas) snarare än att bara skriva ut dem.
* **Enhetstest** – Skapa ett testprojekt som laddar kända streckkodsbilder och verifierar att varje utökat fält matchar förväntade värden. Detta fångar regressioner när du uppgraderar Aspose‑biblioteket.

## Slutsats

Du vet nu **how to decode pdf417** streckkoder i C# med Aspose.BarCode, hur du **read multiple barcodes** från en enda bild, och hur du **display barcode data** såsom FileID, SegmentID och FileName. Det kompletta, körbara exemplet demonstrerar varje steg—from installation av NuGet‑paketet till hantering av kantfall—så att du kan klistra in koden i vilken .NET‑applikation som helst och börja bearbeta PDF417‑symboler omedelbart.

**Nästa steg**

* Utforska **c# barcode decoding**‑alternativen för andra symbologier (QR, Code128, DataMatrix) genom att ändra `DecodeType`.
* Integrera de avkodade fälten i ett webb‑API som returnerar JSON för front‑end‑konsumtion.
* Kombinera denna avkodare med en fil‑watcher‑tjänst för att automatiskt bearbeta inkommande skanningar i realtid.

Lycka till med kodningen, och njut av att förvandla råa streckkoder till handlingsbar data!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Hur man läser PDF417 i C# – komplett streckkodsexempel](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [Hur man genererar PDF417‑streckkod med Aspose – komplett guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Hur man ställer in felnivå i PDF417‑streckkod – komplett guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}