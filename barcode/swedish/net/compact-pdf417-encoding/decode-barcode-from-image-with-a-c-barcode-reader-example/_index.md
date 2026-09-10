---
category: general
date: 2026-09-10
description: Lär dig hur du avkodar streckkod från en bild med ett koncist C#-exempel
  på streckkodsläsare som läser Macro PDF417‑koder på bara några rader.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- decode barcode from image
- c# barcode reader example
- read barcode C#
- barcode decoding tutorial
- Macro PDF417 C#
language: sv
lastmod: 2026-09-10
og_description: Avkoda streckkod från bild med ett kort C#‑exempel på streckkodsläsare.
  Följ den steg‑för‑steg‑guiden för att läsa Macro PDF417‑data omedelbart.
og_image_alt: Screenshot of console output showing decoded Macro PDF417 barcode information
og_title: Avkoda streckkod från en bild med ett C#‑streckkodsläsareexempel
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to decode barcode from image using a concise C# barcode reader
    example that reads Macro PDF417 codes in just a few lines.
  headline: Decode barcode from image with a C# barcode reader example
  type: TechArticle
- description: Learn how to decode barcode from image using a concise C# barcode reader
    example that reads Macro PDF417 codes in just a few lines.
  name: Decode barcode from image with a C# barcode reader example
  steps:
  - name: '**Initialize** a `BarCodeReader` for the target image.'
    text: '**Initialize** a `BarCodeReader` for the target image.'
  - name: '**Iterate** over every detected barcode.'
    text: '**Iterate** over every detected barcode.'
  - name: '**Print** the standard and extended Macro PDF417 data.'
    text: '**Print** the standard and extended Macro PDF417 data.'
  type: HowTo
tags:
- barcode
- C#
- image processing
title: Avkoda streckkod från bild med ett C#‑streckkodsläsareexempel
url: /sv/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Avkoda streckkod från bild med ett C#-streckkodsläsarexempel

Om du behöver **avkoda streckkod från bild**, visar den här guiden exakt hur du gör det i C#. Med ett kompakt **C# barcode reader example** läser du Macro PDF417-data med bara några rader kod.

Du kommer att se ett komplett, körbart program, förstå varför varje del är viktig, och lära dig tips som förhindrar vanliga fallgropar. Ingen extern dokumentation krävs—allt du behöver finns här.

## Vad du kommer att lära dig

- Installera det erforderliga NuGet‑paketet för streckkodavkodning.  
- Skriv ett **C# barcode reader example** som öppnar en bildfil och extraherar varje streckkod.  
- Få åtkomst till utökade Macro PDF417‑fält såsom fil‑ID.  
- Verifiera utskriften och anpassa koden för andra streckkodstyper.

### Förutsättningar

- .NET 6.0 SDK eller senare (koden fungerar också med .NET Core 3.1 och .NET Framework 4.7+).  
- Grundläggande kunskap om C#‑konsolapplikationer.  
- En bildfil som innehåller en Macro PDF417‑streckkod (t.ex. `MacroPdf417.png`).  

## Steg 1: Installera streckkodsbiblioteket

Exemplet använder **Aspose.BarCode for .NET**, ett allmänt använt bibliotek som stödjer avkodning av Macro PDF417.

```bash
dotnet add package Aspose.BarCode
```

> **Varför detta bibliotek?**  
> Det tillhandahåller en enda `BarCodeReader`-klass som hanterar många format, erbjuder hög noggrannhet och returnerar utökad information för Macro PDF417‑koder—allt utan extra konfiguration.

## Steg 2: Skapa ett C# barcode reader example

Skapa ett nytt konsolprojekt och ersätt den genererade `Program.cs` med koden nedan. Exemplet följer tre tydliga steg:

1. **Initialize** en `BarCodeReader` för målbilden.  
2. **Iterate** över varje upptäckt streckkod.  
3. **Print** den standard‑ och utökade Macro PDF417‑datat.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Path to the image that contains the Macro PDF417 barcode
            const string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            // 1️⃣ Create a BarCodeReader configured for Macro PDF417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Read all barcodes found in the image
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Display basic information
                    Console.WriteLine($"Code Type: {result.CodeTypeName}");
                    Console.WriteLine($"Code Text: {result.CodeText}");

                    // 3️⃣ Display Macro PDF417 extended fields (if available)
                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

### Förklaring av varje avsnitt

- **`BarCodeReader`‑konstruktorn** – Det första argumentet är bildens sökväg; det andra talar om för biblioteket att specifikt leta efter Macro PDF417‑koder. Denna fokuserade avkodning förbättrar prestanda jämfört med att skanna varje möjligt format.  
- **`ReadBarCodes()`** – Returnerar en enumerabel av alla streckkoder som upptäckts i bilden, vilket låter dig hantera flera koder i en enda fil.  
- **`result.Extended.Pdf417.MacroPdf417FileID`** – Macro PDF417 lagrar ytterligare metadata (fil‑ID, segmentantal, etc.). Exemplet kontrollerar om värdet är null för att undvika ett `NullReferenceException` när bilden innehåller en icke‑Macro‑streckkod.  

## Steg 3: Kör programmet och verifiera utskriften

Bygg och kör konsolapplikationen:

```bash
dotnet run
```

Du bör se en utskrift liknande:

```
Code Type: MacroPdf417
Code Text: 1234567890ABCDEF
Macro PDF417 File ID: 42
----------------------------------------
```

Om bilden inte innehåller en Macro PDF417‑streckkod kommer programmet fortfarande lista andra upptäckta format, men det utökade fältet kommer att utelämnas.

## Proffstips: Avkoda andra streckkodstyper utan att ändra mycket kod

För att **avkoda streckkod från bild** för ett annat format, ändra `DecodeType`‑enum‑värdet:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.QR))
```

Du kan också skicka `DecodeType.AllSupportedTypes` så att biblioteket upptäcker alla streckkoder det känner till.

## Vanliga fallgropar och hur du undviker dem

| Symptom | Orsak | Lösning |
|---------|-------|-----|
| Ingen utskrift alls | Fel bildsökväg eller filformat som inte stöds | Verifiera sökvägen, säkerställ att filen är en stödd bild (PNG, JPEG, BMP) |
| `result.Extended` är null för Macro PDF417 | Streckkoden är inte en Macro PDF417‑variant | Bekräfta att källbilden faktiskt innehåller en Macro PDF417‑kod |
| Undantag `System.IO.FileNotFoundException` | Saknat NuGet‑paket vid körning | Kör `dotnet restore` och säkerställ att `Aspose.BarCode.dll` kopieras till utdata‑mappen |

## Fullständig källkod för snabb kopiering

Nedan är hela programmet, redo att kopieras in i `Program.cs`. Inga ytterligare filer krävs.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            const string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type: {result.CodeTypeName}");
                    Console.WriteLine($"Code Text: {result.CodeText}");

                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

## Nästa steg

- **Utforska andra utökade fält** såsom `MacroPdf417SegmentID` eller `MacroPdf417FileSize` för att bygga arbetsflöden för fullständig dokumentrekonstruktion.  
- **Integrera läsaren i ett webb‑API** så att klienter kan ladda upp bilder och omedelbart få avkodad data.  
- **Benchmarka prestanda** genom att avkoda stora bildbatcher; `BarCodeReader` stödjer asynkron bearbetning i nyare Aspose‑versioner.

---

Genom att följa detta **C# barcode reader example** har du nu ett pålitligt sätt att **avkoda streckkod från bild** och extrahera rik Macro PDF417‑information. Experimentera med olika `DecodeType`‑värden, kombinera denna logik med fil‑watchers, eller bädda in den i mobila back‑ends—dina streckkodshanteringsmöjligheter är redo att skalas.

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man läser PDF417 i C# – Komplett streckkodsläsarexempel](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Generera streckkod med text – Fullständig PDF417 Macro‑guide](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)
- [Hur man skapar PDF417‑streckkod med Aspose – Komplett steg‑för‑steg‑guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}