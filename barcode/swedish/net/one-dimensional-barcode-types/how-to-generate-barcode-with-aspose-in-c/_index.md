---
category: general
date: 2026-09-19
description: Hur man genererar streckkod med Aspose i C# – en steg‑för‑steg‑guide
  för att snabbt och pålitligt skapa streckkod med Aspose.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
language: sv
lastmod: 2026-09-19
og_description: Hur man genererar streckkod med Aspose i C#. Följ den här guiden för
  att skapa streckkod med Aspose, konfigurera MacroPdf417 och spara som PNG.
og_image_alt: Screenshot showing a MacroPdf417 barcode generated with Aspose in C#
og_title: Hur man genererar streckkod med Aspose – komplett C#‑guide
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  headline: How to generate barcode with Aspose in C#
  type: TechArticle
- description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  name: How to generate barcode with Aspose in C#
  steps:
  - name: What if I need a different image format?
    text: Aspose supports `BarCodeImageFormat.Jpeg`, `Bmp`, `Tiff`, `Svg`, and `Pdf`.
      Just replace `BarCodeImageFormat.Png` with the desired enum value.
  - name: How do I generate multiple segments automatically?
    text: You can place the code above inside a loop, incrementing `MacroPdf417SegmentID`
      on each iteration and updating the data string. Remember to keep `MacroPdf417SegmentsCount`
      constant across all segments.
  - name: What if the data exceeds the capacity of a single MacroPdf417 symbol?
    text: MacroPdf417 is designed for large payloads, but every barcode has a theoretical
      maximum (≈ 1.1 KB per segment). Split the source file into chunks that fit this
      limit, then encode each chunk as a separate segment.
  - name: Does the checksum need to be calculated manually?
    text: Aspose can generate the CCITT‑16 checksum automatically if you set `MacroPdf417Checksum`
      to `0`. In the example we supplied a hard‑coded value for illustration; in production
      code you’d typically let the library compute it.
  - name: How can I change the barcode’s foreground/background colors?
    text: 'Use the `BarColor` and `BackColor` properties:'
  type: HowTo
tags:
- barcode
- Aspose
- C#
- .NET
title: Hur man genererar streckkod med Aspose i C#
url: /sv/net/one-dimensional-barcode-types/how-to-generate-barcode-with-aspose-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så genererar du streckkod med Aspose i C#

Att generera streckkod i C# är enkelt när du använder Aspose.BarCode‑biblioteket. Denna handledning visar dig hur du **skapar streckkod med Aspose** steg för steg, med fokus på formatet MacroPdf417, vanliga utseendeinställningar och hur du sparar resultatet som en PNG‑bild.

Du kommer att lära dig att:

* Installera och referera Aspose.BarCode för .NET  
* Konfigurera MacroPdf417‑specifika egenskaper såsom file‑ID, segment‑ID och kontrollsumma  
* Justera visuella alternativ som X‑dimension och kolumnantal  
* Exportera streckkoden till en bildfil  

Ingen förkunskap om Aspose krävs – bara en grundläggande förståelse för C# och Visual Studio.

## Förutsättningar

Innan du börjar, se till att du har:

| Krav | Detalj |
|------|--------|
| .NET‑runtime | .NET 6.0 eller senare (koden fungerar också med .NET Framework 4.7+) |
| IDE | Visual Studio 2022, Rider eller någon editor som stödjer C# |
| Aspose.BarCode | NuGet‑paket `Aspose.BarCode` (gratis provversion eller licensierad version) |
| Grundläggande C#‑kunskaper | Bekantskap med `using`‑satser och objektinitialisering |

Du kan lägga till Aspose.BarCode i ditt projekt via NuGet Package Manager:

```bash
dotnet add package Aspose.BarCode
```

## Så genererar du streckkod i C# – övergripande arbetsflöde

Processen består av fyra logiska steg:

1. **Skapa en `BarcodeGenerator`‑instans** med önskad kodningstyp (MacroPdf417) och den text du vill koda.  
2. **Ställ in vanliga utseendealternativ** såsom X‑dimension och kolumnantal.  
3. **Konfigurera MacroPdf417‑specifika egenskaper** som file‑ID, segment‑ID och tidsstämpel.  
4. **Spara streckkoden** till ett filformat du väljer (PNG i detta exempel).

Varje steg förklaras i detalj nedan.

## Steg 1: Skapa en barcode‑generator för MacroPdf417

Klassen `BarcodeGenerator` är startpunkten för alla streckkodsskapande‑uppgifter. När du instansierar den skickar du två argument:

* `EncodeTypes.MacroPdf417` – talar om för Aspose att använda MacroPdf417‑symboliken.  
* Datatsträngen – den text som ska kodas i streckkoden.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – instantiate the generator with MacroPdf417 and sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Subsequent steps go here
            }
        }
    }
}
```

> **Varför detta är viktigt:** MacroPdf417 är en tvådimensionell streckkod som kan bära stora mängder data och stödjer makro‑funktioner såsom filsegmentering, vilket är användbart för att överföra stora filer i delar.

## Steg 2: Ställ in vanliga utseendealternativ för streckkoden

Även om MacroPdf417 har många specialiserade inställningar vill du ändå kunna kontrollera den visuella tätheten och layouten. De vanligaste parametrarna är:

* **X‑dimension** – bredden på den minsta modulen (pixel). Mindre värden ger en tätare bild.  
* **Columns** – antalet datakolumner per rad; fler kolumner minskar streckkodens höjd.

```csharp
// Step 2 – adjust appearance
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2‑pixel modules
generator.Parameters.Barcode.Pdf417.Columns = 5;    // 5 columns per row
```

> **Tips:** Håll `XDimension` mellan 2 och 4 pixlar för de flesta skärm‑display‑scenarier. Större värden förbättrar läsbarheten på lågupplösta skrivare men ökar den totala bildstorleken.

## Steg 3: Konfigurera MacroPdf417‑specifika egenskaper

MacroPdf417 lägger till ett antal metadatafält som låter dig dela upp en stor fil i flera streckkodsegment. Följande egenskaper är vanligt förekommande:

| Egenskap | Syfte |
|----------|-------|
| `MacroPdf417FileID` | Unikt identifierare för hela filen (max 8 siffror). |
| `MacroPdf417SegmentID` | Index för det aktuella segmentet (börjar på 0). |
| `MacroPdf417SegmentsCount` | Totalt antal segment i filen. |
| `MacroPdf417FileName` | Läsbart namn på den ursprungliga filen. |
| `MacroPdf417Checksum` | Valfri CCITT‑16‑kontrollsumma för felupptäckt. |
| `MacroPdf417FileSize` | Storlek på den ursprungliga filen i byte. |
| `MacroPdf417TimeStamp` | Tidsstämpel när filen genererades. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Valfria strängar för att identifiera mottagare/avsändare. |
| `MacroPdf417Terminator` | Anger om streckkoden är sista segmentet (`Set`) eller ett mellansteg (`Unset`). |

```csharp
// Step 3 – set macro‑specific data
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // in bytes
generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

> **Varför dessa fält är användbara:**  
> *När du behöver skicka ett stort dokument över en låg‑bandbreddskanal kan du dela dokumentet i flera MacroPdf417‑streckkoder. Mottagaren rekonstruerar den ursprungliga filen genom att läsa varje segments metadata.*

## Steg 4: Spara den genererade streckkoden som en bild

Aspose stödjer många utdataformat: PNG, JPEG, BMP, TIFF, SVG och PDF. PNG är ett förlustfritt format som är idealiskt för webb eller UI‑visning.

```csharp
// Step 4 – export the barcode
string outputPath = @"C:\Barcodes\MacroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

När du kör programmet hittar du en PNG‑fil som liknar illustrationen nedan.

![MacroPdf417 barcode generated with Aspose in C#](placeholder-image.png){.img-fluid alt="hur man genererar streckkod med Aspose i C#"}

> **Förväntat resultat:** En 300 × 150 pixel PNG som visar en MacroPdf417‑streckkod som kodar texten “Sample” tillsammans med de makro‑metadata du angav.

## Fullt, körbart exempel

Sammanställt får du hela programmet som du kan kopiera, klistra in och köra:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for MacroPdf417
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Appearance settings
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // MacroPdf417 specific data
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputPath = @"C:\Barcodes\MacroPdf417.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

Kör programmet med `dotnet run` (eller tryck **F5** i Visual Studio). Efter körning, verifiera att PNG‑filen finns och kan öppnas utan fel.

## Vanliga frågor och hantering av kantfall

### Vad gör jag om jag behöver ett annat bildformat?
Aspose stödjer `BarCodeImageFormat.Jpeg`, `Bmp`, `Tiff`, `Svg` och `Pdf`. Byt bara ut `BarCodeImageFormat.Png` mot önskat enum‑värde.

### Hur genererar jag flera segment automatiskt?
Placera koden ovan i en loop, öka `MacroPdf417SegmentID` för varje iteration och uppdatera datatsträngen. Kom ihåg att hålla `MacroPdf417SegmentsCount` konstant för alla segment.

### Vad händer om datan överskrider kapaciteten för en enda MacroPdf417‑symbol?
MacroPdf417 är avsedd för stora nyttolaster, men varje streckkod har en teoretisk maxgräns (≈ 1,1 KB per segment). Dela upp källfilen i bitar som ryms inom denna gräns och koda varje bit som ett separat segment.

### Måste kontrollsumman beräknas manuellt?
Aspose kan generera CCITT‑16‑kontrollen automatiskt om du sätter `MacroPdf417Checksum` till `0`. I exemplet har vi angett ett hårdkodat värde för illustration; i produktionskod låter du vanligtvis biblioteket beräkna den.

### Hur ändrar jag streckkodens förgrunds‑/bakgrundsfärger?
Använd egenskaperna `BarColor` och `BackColor`:

```csharp
generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

## Slutsats

Du vet nu **hur du genererar streckkod** i C# med Aspose.BarCode och, specifikt, hur du **skapar streckkod med Aspose** för MacroPdf417‑symboliken. Handledningen täckte installation, konfiguration av utseende och makro‑specifika fält.

## Vad bör du lära dig härnäst?

Följande handledningar behandlar närliggande ämnen som bygger vidare på teknikerna i den här guiden. Varje resurs innehåller kompletta kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationssätt i egna projekt.

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}