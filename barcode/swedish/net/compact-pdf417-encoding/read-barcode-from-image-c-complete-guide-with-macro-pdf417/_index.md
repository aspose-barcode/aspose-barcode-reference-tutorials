---
category: general
date: 2026-10-05
description: Läs streckkod från bild i C# med Aspose.BarCode. Lär dig steg‑för‑steg
  C# streckkodsskanning, avkoda Macro PDF417 och hantera utökade egenskaper.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image c#
- C# barcode scanning
- Macro PDF417 decoding
- Aspose.BarCode for .NET
- decode barcode image C#
language: sv
lastmod: 2026-10-05
og_description: Läs streckkod från bild C# med Aspose.BarCode. Denna handledning visar
  hur man skannar en Macro PDF417‑streckkod, hämtar utökade fält och hanterar flera
  koder.
og_image_alt: Screenshot of C# console output showing barcode type and Macro PDF417
  properties
og_title: Läs streckkod från bild i C# – fullständig steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Read barcode from image C# using Aspose.BarCode. Learn step‑by‑step
    C# barcode scanning, decode Macro PDF417 and handle extended properties.
  headline: Read barcode from image C# – complete guide with Macro PDF417
  type: TechArticle
tags:
- barcode
- C#
- image-processing
title: Läs streckkod från bild C# – komplett guide med Macro PDF417
url: /sv/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Läs streckkod från bild C# – komplett guide med Macro PDF417

Om du behöver **läsa streckkod från bild C#**, visar den här handledningen en färdig‑till‑körning‑lösning. Med Aspose.BarCode for .NET‑biblioteket kommer du att avkoda en Macro PDF417‑streckkod, extrahera dess grundläggande data och hämta varje utökad egenskap som formatet tillhandahåller.

Att läsa streckkoder från bilder är ett vanligt krav—oavsett om du bygger ett biljettvalideringssystem, bearbetar fraktetiketter eller extraherar metadata från skannade dokument. I stegen nedan kommer du att se varför `BarCodeReader`‑klassen är den rekommenderade metoden, hur du konfigurerar den för Macro PDF417, och vad du ska göra med resultaten.

---

## Vad du kommer att lära dig

* Installera och referera **Aspose.BarCode for .NET** (biblioteket som driver exemplet).  
* Skapa en `BarCodeReader` konfigurerad för **Macro PDF417‑avkodning**.  
* Iterera över alla streckkoder i en bild och skriv ut både standard- och utökade fält.  
* Hantera flera streckkoder, hantera resurser korrekt och felsök vanliga fallgropar.

**Förutsättningar**

* .NET 6.0 SDK eller senare (koden fungerar också med .NET Framework 4.6+).  
* Grundläggande kunskap om C#‑konsolapplikationer.  
* En bildfil som innehåller en Macro PDF417‑streckkod (t.ex. `ExtPDF417Meta.png`).  

---

## Steg 1: Lägg till Aspose.BarCode i ditt projekt (C# streckkodsskanning)

1. Öppna en terminal i din lösningsmapp.  
2. Kör NuGet‑kommandot:

```bash
dotnet add package Aspose.BarCode
```

Paketet innehåller `BarCodeReader`‑klassen, `DecodeType`‑enumerationen och `BarCodeResult`‑objektet som används genom hela handledningen.

> **Proffstips:** Om du riktar dig mot .NET Framework, använd Package Manager Console i Visual Studio:  
> `Install-Package Aspose.BarCode`

---

## Steg 2: Ställ in konsolprogrammet (avkoda streckkod från bild C#)

Skapa ett nytt konsolprojekt (eller lägg till koden i ett befintligt):

```csharp
using System;
using Aspose.BarCode;               // Core namespace
using Aspose.BarCode.BarCodeRecognition; // For DecodeType and BarCodeReader

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image that contains a Macro PDF417 barcode.
            const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Step 2.1: Initialise the BarCodeReader for Macro PDF417.
            using (BarCodeReader barcodeReader = new BarCodeReader(
                       imagePath, DecodeType.MacroPdf417))
            {
                // Step 2.2: Read every barcode present in the image.
                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    // Step 2.3: Output basic information.
                    Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
                    Console.WriteLine($"CodeText: {barcodeResult.CodeText}");

                    // Step 2.4: Output Macro PDF417 extended properties.
                    PrintMacroPdf417Properties(barcodeResult);
                }
            }

            // Keep console window open for inspection.
            Console.WriteLine("\nPress any key to exit...");
            Console.ReadKey();
        }

        /// <summary>
        /// Writes all Macro PDF417 extended fields to the console.
        /// </summary>
        /// <param name="result">Result object returned by BarCodeReader.</param>
        private static void PrintMacroPdf417Properties(BarCodeResult result)
        {
            // The Extended property is null if the barcode type does not support it.
            if (result?.Extended?.Pdf417 == null)
            {
                Console.WriteLine("No Macro PDF417 extended data available.");
                return;
            }

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
        }
    }
}
```

### Varför denna struktur?

* **`using`‑sats** – garanterar att `BarCodeReader` frigör inhemska resurser (viktigt för stora bilder).  
* **`DecodeType.MacroPdf417`** – talar om för biblioteket att specifikt leta efter Macro PDF417; andra typer (t.ex. QR, Code128) skulle ignorera de utökade fälten.  
* **`ReadBarCodes()`** – returnerar en enumerable, vilket låter dig hantera **flera streckkoder** i samma bild utan extra kod.  
* **Separat `PrintMacroPdf417Properties`‑metod** – isolerar logiken för de utökade fälten, gör huvudloopen lättare att läsa och förenklar framtida underhåll.

---

## Steg 3: Kör programmet och verifiera utskriften (Macro PDF417‑avkodning)

Öppna en kommandotolk, navigera till projektmappen och kör:

```bash
dotnet run
```

Du bör se en utskrift liknande följande (värdena kommer att skilja sig beroende på den faktiska streckkoden):

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 3
Pdf417MacroSegmentsCount: 5
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B3C4D
Pdf417MacroFileSize: 1048576
Pdf417MacroTimeStamp: 2023-08-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True

Press any key to exit...
```

Om bilden inte innehåller en Macro PDF417‑streckkod kommer konsolen att visa **“No Macro PDF417 extended data available.”** Denna eleganta hantering förhindrar null‑referens‑undantag.

---

## Steg 4: Vanliga variationer och kantfall (C# streckkodsskanningstips)

| Situation | Rekommenderad justering |
|-----------|------------------------|
| **Flera streckkodstyper i en bild** | Initiera läsaren med `DecodeType.AllSupported` och inspektera `barcodeResult.CodeTypeName` för att välja logik. |
| **Stora bilder (≥10 MP)** | Öka `barcodeReader.Options.MaxBarCodeCount` eller använd `barcodeReader.SetResolution(300)` för att förbättra detekteringshastigheten. |
| **Saknade utökade fält** | Vissa skannrar tar bort Macro‑data; verifiera att källbilden innehåller fälten med ett streckkodsinspektionsverktyg innan du kodar. |
| **Kör på Linux/macOS** | Säkerställ att de inhemska binärerna för Aspose.BarCode finns (`Aspose.BarCode.Native` NuGet‑paket) eller sätt `Environment.SetEnvironmentVariable("DOTNET_SYSTEM_GLOBALIZATION_INVARIANT", "1")` om du bara behöver ASCII‑data. |
| **Prestandakritiska loopar** | Cacha `BarCodeReader`‑instansen och återanvänd den för en batch av bilder; disponera först när batchen är klar. |

---

## Steg 5: Sammanfattning och nästa steg (läsa streckkod från bild C#)

Du har nu en **fullständig, självständig lösning** för att läsa en Macro PDF417‑streckkod från en bild i C#. Exemplet visar:

* Korrekt **installation** av Aspose.BarCode‑biblioteket.  
* Skapande av en **`BarCodeReader`** konfigurerad för **Macro PDF417**.  
* Iteration över **alla streckkoder** i den medföljande bilden.  
* Extraktion av **standard** (`CodeTypeName`, `CodeText`) **och utökad** Macro PDF417‑metadata.  

### Vad du kan utforska härnäst?

* **Avkoda andra format** – ersätt `DecodeType.MacroPdf417` med `DecodeType.QR`, `DecodeType.Code128` osv.  
* **Integrera med ASP.NET Core** – exponera en Web API‑endpoint som accepterar bilduppladdningar och returnerar JSON med streckkodsdata.  
* **Spara resultat** – lagra extraherad metadata i en databas för senare analys.  
* **Kombinera med OCR** – använd Aspose.OCR för att läsa text som inte är kodad som en streckkod.

Känn dig fri att experimentera med exempelbilden, justera filvägen eller bädda in logiken i en större applikation. Klassen **`BarCodeReader`** ger en robust grund för alla **C# streckkodsskannings**‑scenarier.

--- 

*Lycklig kodning! Om du stöter på problem, dubbelkolla att bilden verkligen innehåller en Macro PDF417‑streckkod och att Aspose.BarCode‑versionen matchar din .NET‑runtime.*

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Läs streckkod från bild i C# – BarCodeReader‑handledning](/barcode/english/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/)
- [Hur man genererar PDF417‑streckkodbild i C# med Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}