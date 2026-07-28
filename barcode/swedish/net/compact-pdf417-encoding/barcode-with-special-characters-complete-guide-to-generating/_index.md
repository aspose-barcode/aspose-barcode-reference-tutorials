---
category: general
date: 2026-07-27
description: Barcode med specialtecken‑handledning visar hur man genererar PDF417‑streckkoder
  med Aspose. Lär dig steg‑för‑steg‑skapande och hantering av Unicode‑data.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode with special characters
- how to generate pdf417
- create barcode with aspose
- Aspose PDF417 macro
- Unicode barcode generation
language: sv
lastmod: 2026-07-27
og_description: Barcode med specialtecken‑handledning förklarar hur man genererar
  PDF417‑streckkoder med Aspose, och täcker Unicode‑hantering samt makrometadata.
og_image_alt: Screenshot of a PDF417 barcode containing special characters generated
  with Aspose
og_title: Streckkod med specialtecken – Generera PDF417 med Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Barcode with special characters tutorial shows how to generate PDF417
    barcodes with Aspose. Learn step‑by‑step creation and handling of Unicode data.
  headline: Barcode with Special Characters – Complete Guide to Generating PDF417
    Using Aspose
  type: TechArticle
- description: Barcode with special characters tutorial shows how to generate PDF417
    barcodes with Aspose. Learn step‑by‑step creation and handling of Unicode data.
  name: Barcode with Special Characters – Complete Guide to Generating PDF417 Using
    Aspose
  steps:
  - name: Expected Output
    text: If you open the PNG, you’ll see a rectangular barcode with a series of black
      and white bars. Scanning it with a PDF417‑compatible scanner (or a mobile app
      like “Barcode Scanner”) will return the exact text `"Åspóse.Barcóde©"` along
      with the macro metadata we set. In other words, the barcode faithful
  - name: What if my text contains emojis or non‑BMP characters?
    text: Aspose.BarCode supports full UTF‑16, so emojis work as long as the target
      scanner can decode them. Just pass the string directly; the library handles
      the encoding internally.
  - name: Do I need to set a specific character set?
    text: No. Unlike older barcode SDKs that required `CodePage` settings, Aspose
      automatically detects Unicode. However, if you target a legacy device that only
      understands ASCII, you’ll need to strip or replace special characters before
      generation.
  - name: How does this differ from a regular PDF417 barcode?
    text: The `MacroPdf417` variant adds extra fields (file ID, segment count, etc.)
      that help split large payloads across multiple barcodes. If you don’t need those,
      you can switch `EncodeTypes.Pdf417` and drop the macro‑specific properties.
  - name: Can I generate the barcode as a vector (SVG) instead of PNG?
    text: 'Absolutely. Change the `BarCodeImageFormat` to `Svg`:'
  type: HowTo
tags:
- barcode
- Aspose
- PDF417
- .NET
title: Streckkod med specialtecken – Komplett guide för att generera PDF417 med Aspose
url: /sv/net/compact-pdf417-encoding/barcode-with-special-characters-complete-guide-to-generating/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Streckkod med specialtecken – Komplett guide för att generera PDF417 med Aspose

Har du någonsin undrat hur man skapar en **streckkod med specialtecken** som innehåller accenter, symboler eller till och med upphovsrättstecken? Du är inte ensam. Många utvecklare stöter på problem när deras data innehåller tecken som “Å”, “é” eller “©”, och standardexempel visar sällan hur man hanterar dem. I den här handledningen går vi igenom ett konkret exempel som inte bara löser det problemet utan också demonstrerar **hur man genererar PDF417** streckkoder med Aspose.BarCode‑biblioteket.

Vi börjar med att sätta upp en enkel .NET‑konsolapp, och sedan dyker vi ner i koden som genererar en PDF417‑streckkod som innehåller strängen `"Åspóse.Barcóde©"`. På vägen kommer du att se varför varje inställning är viktig, hur man konfigurerar macro‑PDF417‑metadata, och vad man ska vara uppmärksam på när man hanterar Unicode. I slutet är du redo att **skapa streckkod med Aspose** i alla dina projekt, oavsett om det är för lagerhantering, biljettsystem eller säker dokumentspårning.

## Förutsättningar

- .NET 6.0 SDK eller senare (koden fungerar även med .NET Framework 4.7+)
- Visual Studio 2022 (eller någon IDE du föredrar)
- En giltig Aspose.BarCode för .NET‑licens (du kan börja med en gratis provversion)
- Grundläggande kunskap om C#‑syntax

Om något av detta låter obekant, panik inte—installera bara .NET‑SDK:n och hämta NuGet‑paketet `Aspose.BarCode` så är du redo att köra.

## Steg 1: Installera Aspose.BarCode och konfigurera projektet

För att generera en **streckkod med specialtecken** är det första du behöver Aspose.BarCode‑biblioteket. Öppna en terminal i din projektmapp och kör:

```bash
dotnet add package Aspose.BarCode
```

Det här hämtar den senaste versionen (från juli 2026, version 23.12) som stödjer full Unicode‑hantering direkt. Efter att paketet har återställts, skapa en ny C#‑fil som heter `Program.cs` och lägg till de vanliga `using`‑direktiven:

```csharp
using System;
using Aspose.BarCode.Generation;
```

Varför `using Aspose.BarCode.Generation`? Det ger oss åtkomst till `BarcodeGenerator`‑klassen, hjärtat i **hur man genererar PDF417** streckkoder med Aspose.

## Steg 2: Initiera Barcode Generator med Unicode‑text

Nu kommer delen som faktiskt skapar en **streckkod med specialtecken**. Observera att strängen vi skickar till konstruktorn innehåller ett “Å”, ett “ó” och ett “©”. Aspose upptäcker automatiskt Unicode‑området, så du behöver inga extra kodningssteg—ange bara den vanliga .NET‑strängen:

```csharp
// Step 2: Create a barcode generator for Macro PDF417 with Unicode text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

`EncodeTypes.MacroPdf417` talar om för Aspose att vi vill ha en PDF417‑streckkod som kan bära makroinformation (användbart för att dela upp stora datamängder). Generatorn innehåller nu en **streckkod med specialtecken** som är klar för vidare justering.

## Steg 3: Finjustera utseende och makro‑metadata

En enkel streckkod fungerar, men de flesta verkliga scenarier kräver kontroll över storlek, kolumnantal och makrofält. Nedan justerar vi X‑dimensionen, antalet kolumner och sätter sedan ett antal macro‑PDF417‑egenskaper. Varje rad är kommenterad så att du kan se *varför* den är viktig.

```csharp
    // Adjust basic barcode appearance
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel size of a module
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns (affects width)

    // Define macro PDF417 metadata (file ID, segment info, etc.)
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

Ett snabbt tips: om du någonsin ser att den genererade streckkoden blir för bred, sänk `Columns`‑värdet eller öka `XDimension`. Båda påverkar den slutliga bildstorleken, vilket är avgörande när du bäddar in streckkoden i PDF‑filer eller tryckta etiketter.

## Steg 4: Spara streckkoden som en bild

Till sist sparar vi streckkoden till en PNG‑fil. `Save`‑metoden renderar automatiskt **streckkoden med specialtecken** till ett rasterformat som du kan visa på en webbplats, bädda in i en rapport eller skicka till en skrivare.

```csharp
    // Save the generated barcode as a PNG image
    barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

Byt ut `YOUR_DIRECTORY` mot en absolut eller relativ sökväg som finns på din maskin. När programmet är klart bör du se `ExtPDF417Meta.png` som innehåller en skarp PDF417‑streckkod som kodar Unicode‑strängen.

### Förväntat resultat

Om du öppnar PNG‑filen ser du en rektangulär streckkod med en serie svarta och vita staplar. Att skanna den med en PDF417‑kompatibel scanner (eller en mobilapp som “Barcode Scanner”) returnerar exakt texten `"Åspóse.Barcóde©"` tillsammans med de makro‑metadata vi satte. Med andra ord bevarar streckkoden specialtecknen exakt—ingen dataförlust.

## Vanliga frågor & kantfall

### Vad händer om min text innehåller emojis eller icke‑BMP‑tecken?

Aspose.BarCode stödjer full UTF‑16, så emojis fungerar så länge målscannern kan avkoda dem. Skicka bara strängen direkt; biblioteket hanterar kodningen internt.

### Behöver jag ange en specifik teckenuppsättning?

Nej. Till skillnad från äldre barcode‑SDK:er som krävde `CodePage`‑inställningar upptäcker Aspose automatiskt Unicode. Men om du riktar dig mot en äldre enhet som bara förstår ASCII måste du ta bort eller ersätta specialtecken innan generering.

### Hur skiljer sig detta från en vanlig PDF417‑streckkod?

`MacroPdf417`‑varianten lägger till extra fält (fil‑ID, segmentantal osv.) som hjälper till att dela upp stora datamängder över flera streckkoder. Om du inte behöver dem kan du byta till `EncodeTypes.Pdf417` och ta bort de makro‑specifika egenskaperna.

### Kan jag generera streckkoden som en vektor (SVG) istället för PNG?

Absolut. Ändra `BarCodeImageFormat` till `Svg`:

```csharp
barcodeGenerator.Save("ExtPDF417Meta.svg", BarCodeImageFormat.Svg);
```

## Fullt fungerande exempel

Nedan är det kompletta, färdiga programmet. Kopiera‑klistra in det i `Program.cs`, justera utsökvägen och tryck **F5**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeSpecialCharsDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Adjust basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel size of a module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns

                // Step 3: Define macro PDF417 metadata (file ID, segment info, etc.)
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode as a PNG image
                barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Barcode with special characters generated successfully!");
        }
    }
}
```

När du kör programmet skrivs en bekräftelserad ut och `ExtPDF417Meta.png` placeras i programmets mapp. Öppna filen, skanna den och verifiera att specialtecknen överlever hela processen.

## Pro‑tips för produktionsanvändning

- **Cachea generatorn** om du skapar många streckkoder i en loop; återanvändning av samma `BarcodeGenerator`‑instans minskar minnesbelastning.
- **Ställ in `Resolution`** (`barcodeGenerator.Parameters.ImageResolution`) när du behöver högre DPI för utskriftsklara tillgångar.
- **Validera indata**: ta bort kontrolltecken som kan bryta makrofälten. Ett enkelt regex som `^[\u0020-\u007E\u00A0-\u00FF]+$` fungerar för de flesta Latin‑1‑fall.
- **Trådsäkerhet**: varje tråd bör ha sin egen `BarcodeGenerator`. Klassen är inte trådsäker.

## Slutsats

Du har nu ett robust, helhetsrecept för att skapa en **streckkod med specialtecken** med Aspose, och du har också sett **hur man genererar PDF417** streckkoder som bär makro‑metadata. Exemplet täckte allt från att installera NuGet‑paketet till att spara den slutgiltiga PNG‑filen, och det belyste vanliga fallgropar som Unicode‑hantering och bildstorlek.

Redo för nästa steg? Prova att byta bildformat till SVG, experimentera med större datamängder

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Hur man skapar streckkod – Compact PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Känna igen PDF417‑streckkod med kinesiska tecken i Java](/barcode/english/java/multilingual-support/recognizing-pdf417-chinese-characters/)
- [Känna igen PDF417‑streckkod med turkiska tecken i Java](/barcode/english/java/multilingual-support/recognizing-pdf417-turkish-characters/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}