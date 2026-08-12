---
category: general
date: 2026-08-12
description: Generera streckkod Aspose med Aspose.BarCode och lär dig hur du genererar
  PDF417 med anpassad text på några enkla steg.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode aspose
- how to generate pdf417
- create barcode custom text
- Aspose.BarCode macro pdf417
- barcode metadata Aspose
language: sv
lastmod: 2026-08-12
og_description: Generera streckkod med Aspose.BarCode. Denna handledning visar hur
  man genererar PDF417 med anpassad text, makrometadata och sparar resultatet som
  PNG.
og_image_alt: Screenshot of a MacroPdf417 barcode generated with Aspose.BarCode in
  C#
og_title: Generera streckkod med Aspose – steg‑för‑steg guide
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Generate barcode aspose with Aspose.BarCode and learn how to generate
    pdf417 with custom text in a few easy steps.
  headline: Generate barcode aspose – complete C# guide
  type: TechArticle
tags:
- Aspose
- barcode
- pdf417
title: Generera streckkod aspose – komplett C#‑guide
url: /sv/net/compact-pdf417-encoding/generate-barcode-aspose-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera streckkod aspose – komplett C#-guide

Om du behöver **generera streckkod aspose** för en MacroPdf417-symbol, guidar den här handledningen dig genom hela processen. Du kommer att se hur du konfigurerar macro‑specifika alternativ, bäddar in anpassad text och sparar streckkoden som en PNG-bild.

Att generera en streckkod med Aspose.BarCode eliminerar manuella beräkningar och garanterar efterlevnad av PDF417-specifikationen. I stegen nedan kommer du också att lära dig **how to generate pdf417** med anpassad metadata såsom fil-ID, segmentantal och tidsstämplar. I slutet av guiden har du ett färdigt kodexempel som du kan klistra in i vilket .NET‑projekt som helst.

## Förutsättningar

* .NET 6.0 eller senare (koden fungerar också med .NET Framework 4.7+)
* En giltig Aspose.BarCode för .NET-licens (den fria utvärderingen fungerar för testning)
* Visual Studio 2022 eller någon C#‑IDE du föredrar
* Grundläggande kunskap om C#‑syntax och objekt‑orienterade koncept

Inga ytterligare NuGet‑paket krävs utöver **Aspose.BarCode**.

## Steg 1: Installera Aspose.BarCode NuGet‑paketet

Öppna ditt projekt i Visual Studio och kör sedan följande kommando i Package Manager Console:

```powershell
Install-Package Aspose.BarCode
```

Paketet lägger till namnutrymmet `Aspose.BarCode`, som innehåller klassen `BarcodeGenerator` som används genom hela handledningen.

## Steg 2: Skapa en streckkodsgenerator för MacroPdf417

Den första raden skapar en `BarcodeGenerator`‑instans som riktar sig mot **MacroPdf417**‑symbologin och bäddar in den anpassade text du vill koda.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

// Step 2: Initialize the generator with custom text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

*Varför detta är viktigt*: Enum‑värdet `EncodeTypes.MacroPdf417` talar om för Aspose att behandla streckkoden som en macro‑aktiverad PDF417‑symbol, vilket möjliggör uppdelning av stora data i flera segment. Strängen `"Åspóse.Barcóde©"` visar att generatorn korrekt hanterar Unicode‑tecken.

## Steg 3: Definiera grundläggande modulstorlek

Modulstorleken styr den visuella densiteten i streckkoden. Ett pixelvärde på `2` ger en skarp bild som skrivs ut bra på vanliga etikettprinterar.

```csharp
    // Step 3: Set the X‑dimension (module width) in pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Att öka värdet gör streckkoden större, medan en minskning kan leda till skanningsproblem på lågupplösta enheter.

## Steg 4: Konfigurera PDF417 macro‑specifika layoutalternativ

MacroPdf417 kräver flera ytterligare parametrar. Dessa inställningar gör det möjligt att dela upp data i flera filer, identifiera varje segment och verifiera integriteten.

```csharp
    // Step 4: Macro‑specific layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

*Varför detta är viktigt*: Egenskapen `Columns` påverkar streckkodens bredd, medan macro‑fälten (`FileID`, `SegmentID`, `SegmentsCount`, `FileName`) låter efterföljande system återmontera den ursprungliga datan korrekt.

## Steg 5: Lägg till ytterligare macro‑metadata

Aspose.BarCode låter dig bädda in valfria macro‑fält såsom kontrollsumma, filstorlek, tidsstämpel och avsändar/mottagarinformation. Dessa fält är användbara för revisionsspår och felupptäckt.

```csharp
    // Step 5: Optional macro metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                 // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // Approximate size in bytes
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                       // Creation date
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                       // Marks the last segment
```

*Varför detta är viktigt*: Kontrollsumman skyddar mot överföringsfel, medan tidsstämpeln och avsändarfälten ger kontext för efterföljande bearbetning. Att sätta `MacroPdf417Terminator` till `Set` signalerar att detta är det sista segmentet i macro‑serien.

## Steg 6: Spara streckkoden som en PNG‑bild

Slutligen skriver du den genererade streckkoden till disk. PNG bevarar förlustfri kvalitet, vilket är idealiskt för skanning.

```csharp
    // Step 6: Export the barcode
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

När koden är klar innehåller filen `ExtPDF417Meta.png` en högupplöst MacroPdf417‑streckkod som kodar den anpassade texten och all macro‑metadata.

### Förväntat resultat

När du öppnar `ExtPDF417Meta.png` visas en vertikalt orienterad streckkod med tydligt definierade rader och kolumner. Skannar du bilden med någon PDF417‑läsare får du tillbaka den ursprungliga strängen **Åspóse.Barcóde©** samt de macro‑fält du konfigurerade (fil‑ID, segment‑ID, kontrollsumma osv.).

## Hur man genererar pdf417 utan macro‑alternativ (alternativt scenario)

Om du bara behöver en standard‑PDF417‑streckkod, utelämna macro‑egenskaperna och behåll den grundläggande konfigurationen:

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(
           EncodeTypes.Pdf417, "Standard PDF417 data"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 3;
    generator.Parameters.Barcode.Pdf417.Columns = 6;
    generator.Save("StandardPdf417.png", BarCodeImageFormat.Png);
}
```

Detta kodsnutt demonstrerar **how to generate pdf417** snabbt när macro‑funktionalitet inte krävs.

## Vanliga fallgropar och pro‑tips

| Problem | Varför det händer | Lösning |
|-------|----------------|-----|
| Streckkoden är för liten för att skannas | X‑dimensionen är satt till 1 pixel eller kolumnerna är för många | Använd minst `2` pixlar för `XDimension` och håll kolumner mellan `3` och `9` för vanliga etikettstorlekar |
| Unicode‑tecken visas som � | Kodningsfel i projektfilen | Se till att projektfilen sparas som UTF‑8 och att källfilen innehåller korrekt BOM |
| Macro‑fält ignoreras av skannern | `MacroPdf417Terminator` är inte satt för sista segmentet | Sätt `MacroPdf417Terminator = Pdf417MacroTerminator.Set` på det sista segmentet |
| Bildfilen är korrupt | Utdatastreamen stängs inte korrekt | Använd `using`‑satsen (som visas) för att garantera att generatorn tas bort |

## Fullt, körbart exempel

Kopiera följande kod till en ny konsolapplikation och kör den. Programmet skapar streckkoden, sparar den och skriver ut sökvägen till konsolen.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace AsposeBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with custom Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Basic size
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // Macro layout
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Optional macro metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputFile = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
                barcodeGenerator.Save(outputFile, BarCodeImageFormat.Png);

                Console.WriteLine($"Barcode saved to: {outputFile}");
            }
        }
    }
}
```

När programmet körs skrivs en rad liknande följande ut:

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Öppna filen för att verifiera den visuella utskriften.

## Slutsats

Du vet nu hur du **generate barcode aspose** för MacroPdf417‑symbologin, bäddar in anpassad Unicode‑text, konfigurerar macro‑metadata och exporterar resultatet som en PNG‑bild. Samma mönster låter dig **how to generate pdf417** utan macro‑alternativ, och du kan anpassa koden till andra streckkodformat som stöds av Aspose.BarCode.

Nästa steg är att utforska relaterade ämnen såsom **create barcode custom text** för QR‑koder, lägga till färgfilter med `Color`‑parametrar, eller bädda in streckkoder direkt i PDF‑dokument med Aspose.PDF. Experimentera med olika `XDimension`‑värden och kolumnantal för att finjustera streckkoden för din specifika skrivare eller skanner.

Lycka till med kodandet, och njut av den pålitlighet som Aspose.BarCode ger dina .NET‑streckkodslösningar!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to generate DataMatrix barcode with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Generate Barcode Java - Set Code Text using Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}