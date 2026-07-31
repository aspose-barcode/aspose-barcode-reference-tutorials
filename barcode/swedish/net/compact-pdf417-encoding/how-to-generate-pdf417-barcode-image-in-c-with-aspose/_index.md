---
category: general
date: 2026-07-30
description: Hur man genererar PDF417‑streckkodbild i C# med Aspose. Lär dig steg
  för steg hur du skapar streckkod med Aspose, sätter MacroPDF417‑metadata och sparar
  som PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- generate barcode image c#
- create barcode with aspose
- Aspose.BarCode PDF417
- MacroPdf417 metadata
language: sv
lastmod: 2026-07-30
og_description: Hur man genererar PDF417-streckkodsbild i C# med Aspose. Följ den
  här kompletta guiden för att skapa en streckkod med Aspose, konfigurera MacroPDF417-metadata
  och exportera en PNG-fil.
og_image_alt: Screenshot showing a generated PDF417 barcode image created with Aspose
  in C#
og_title: Hur man genererar PDF417‑streckkodsbild i C# med Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: How to generate PDF417 barcode image in C# with Aspose. Learn step‑by‑step
    how to create barcode with Aspose, set MacroPDF417 metadata, and save as PNG.
  headline: How to Generate PDF417 Barcode Image in C# with Aspose
  type: TechArticle
tags:
- Aspose
- C#
- Barcode
title: Hur man genererar PDF417-streckkodbild i C# med Aspose
url: /sv/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så här genererar du PDF417 streckkodsbild i C# med Aspose

Att generera PDF417 streckkodsbild i C# med Aspose är ett vanligt hinder för alla som arbetar med högdensitetsdatakodning. I den här guiden går vi igenom varje steg – från att konfigurera generatorn, justera MacroPDF417‑metadata, till att slutligen spara en skarp PNG‑fil.

Om du någonsin har försökt **generate barcode image c#** och slutat med en tom canvas eller en oläslig skanning, är du inte ensam. Den goda nyheten är att Aspose.BarCode gör hela processen nästan smärtfri, och i slutet av den här artikeln kommer du kunna **create barcode with Aspose** för vilket företagsarbetsflöde som helst.

## Vad du kommer att lära dig

- Installera och referera Aspose.BarCode‑biblioteket för .NET.  
- Initiera en PDF417‑generator med en anpassad payload.  
- Tillämpa MacroPDF417‑specifika fält såsom file ID, segment ID och timestamp.  
- Exportera resultatet till en PNG‑bild som du kan bädda in i rapporter eller mobilappar.  
- Tips för felsökning av vanliga fallgropar (t.ex. fel modulbredd, saknade segment).

Ingen förkunskap om MacroPDF417 krävs; en grundläggande förståelse för C# och Visual Studio räcker.

## Förutsättningar

| Requirement | Reason |
|-------------|--------|
| .NET 6.0 eller senare | Aktuell LTS‑version, fullt stöd av Aspose |
| Visual Studio 2022 (eller någon IDE) | För att kompilera och köra exemplet |
| Aspose.BarCode for .NET (NuGet) | Tillhandahåller `BarcodeGenerator` och PDF417‑stöd |

Du kan lägga till biblioteket via NuGet:

```bash
dotnet add package Aspose.BarCode
```

Nu när grunden är lagd, låt oss dyka ner i koden.

## Så här genererar du PDF417 streckkodsbild i C# – Inställning

Det första vi gör är att skapa en `BarcodeGenerator`‑instans för kodningstypen **MacroPdf417**. Detta objekt innehåller alla konfigurationsalternativ, från modulstorlek till den rika metadata som MacroPDF417 förväntar sig.

```csharp
using Aspose.BarCode.Generation;
using System;

// Step 1: Create the barcode generator with the desired payload.
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Payload"))
{
    // The rest of the configuration goes here.
}
```

> **Varför detta är viktigt:** `EncodeTypes.MacroPdf417` talar om för Aspose att producera en PDF417‑streckkod som kan delas upp i flera segment – ett måste för stora filer eller batch‑bearbetning.

## Konfigurera grundläggande utseende

En läsbar streckkod börjar med rätt visuella inställningar. `XDimension` styr bredden på varje modul (de små svarta/vita rutorna), medan `Columns` bestämmer hur många kolumner streckkoden sträcker sig över.

```csharp
// Step 2: Define basic barcode appearance.
generator.Parameters.Barcode.XDimension.Pixels = 2;   // Module width in pixels.
generator.Parameters.Barcode.Pdf417.Columns = 5;    // Number of columns (adjust for size).
```

- **Tips:** Om streckkoden ser för tät ut på en kvittoskrivare, öka `XDimension` till `3` eller `4`.  
- **Fallgrop:** Att sätta `Columns` för lågt kan leda till att streckkoden överskrider bildens gränser, vilket resulterar i en oläslig skanning.

## Ange MacroPDF417‑specifik metadata

MacroPDF417 låter dig bädda in fil‑nivåinformation direkt i streckkoden. Detta är perfekt för att spåra stora dokumentleveranser eller dela en fil över flera skanningar.

```csharp
// Step 3: Set MacroPDF417 specific metadata.
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 CRC
generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // bytes
generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**Vad varje fält gör:**

| Property | Description |
|----------|-------------|
| `MacroPdf417FileID` | Unik identifierare för hela filen. |
| `MacroPdf417SegmentID` | Index för det aktuella segmentet (börjar på 0). |
| `MacroPdf417SegmentsCount` | Totalt antal segment som filen är delad i. |
| `MacroPdf417FileName` | Läsbart namn, användbart för audit‑loggar. |
| `MacroPdf417Checksum` | 16‑bit CRC för verifiering av dataintegritet. |
| `MacroPdf417FileSize` | Ursprunglig filstorlek i byte, hjälper mottagare att allokera buffertar. |
| `MacroPdf417TimeStamp` | Datum/tid då filen genererades. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Valfria strängar för att identifiera mottagare/avsändare. |
| `MacroPdf417Terminator` | Markerar sista segmentet; krävs för korrekt avkodning. |

> **Varför bry sig?** Utan dessa fält kan en scanner bara läsa rådata, inte sammanhanget. Genom att lägga till metadata kan mottagarsystemet automatiskt sätta ihop den ursprungliga filen igen.

## Spara streckkoden som PNG

När generatorn är fullt konfigurerad är det bara en rad för att spara bilden:

```csharp
// Step 4: Save the generated barcode image.
generator.Save("YOUR_DIRECTORY/MacroPdf417Meta.png", BarCodeImageFormat.Png);
```

- **Filformat:** PNG är förlustfritt, vilket säkerställer att varje modul förblir skarp för scanners.  
- **Alternativ:** Använd `BarCodeImageFormat.Jpeg` om du behöver en mindre filstorlek, men förvänta dig en liten försämring i läsbarhet.

### Förväntad utdata

Efter att ha kört kodsnutten hittar du `MacroPdf417Meta.png` i den angivna mappen. Den bör se ut ungefär som illustrationen nedan:

![PDF417 barcode generated with Aspose](path/to/your/image.png){alt="Hur man genererar PDF417 streckkodsbild i C#"}

Bilden innehåller ett tätt rutnät av svarta och vita fyrkanter, med den kodade payloaden och MacroPDF417‑metadata inbäddade.

## Fullt fungerande exempel

Nedan är det kompletta, kopiera‑och‑klistra‑klara programmet. Det kompileras med vilket .NET 6+‑projekt som helst och kräver bara Aspose.BarCode‑NuGet‑paketet.



## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationssätt i dina egna projekt.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}