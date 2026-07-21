---
category: general
date: 2026-07-21
description: Generera streckkod i C# snabbt med Aspose.BarCode. Lär dig att skapa
  DataBar‑streckkod, anpassa streckkodens storlek och exportera streckkodsbilden på
  bara några steg.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode c#
- create databar barcode
- customize barcode size
- change barcode dimensions
- export barcode image
language: sv
lastmod: 2026-07-21
og_description: Generera streckkod i C# med Aspose.BarCode. Skapa DataBar-streckkod,
  anpassa dess storlek och exportera bilden omedelbart.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode saved as PNG
og_title: Generera streckkod C# – Skapa DataBar-streckkoder med anpassad storlek
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Generate barcode C# quickly with Aspose.BarCode. Learn to create DataBar
    barcode, customize barcode size, and export barcode image in just a few steps.
  headline: Generate barcode C# – Create DataBar barcode
  type: TechArticle
- questions:
  - answer: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, `Gif`, or `Svg`.
      The API handles the conversion automatically.
    question: What if I need a different image format?
  - answer: Technically you can set both, but Aspose will prioritize the last property
      you modify. It's safer to set *one* dimension and let the library compute the
      other for a valid DataBar.
    question: Can I change both rows and columns simultaneously?
  - answer: 'Use `barcodeGen.Parameters.Barcode.ForegroundColor` and `BackgroundColor`.
      Example:'
    question: How do I apply a foreground/background color?
  - answer: DataBar Expanded Stacked supports up to 74 numeric characters (or 30 alphanumeric).
      Exceeding that throws an exception.
    question: Is there a size limit for the encoded data?
  type: FAQPage
tags:
- barcode
- csharp
- databar
- image-export
- aspnet
title: Generera streckkod C# – Skapa DataBar‑streckkod
url: /sv/python-java/general/generate-barcode-c-create-databar-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera streckkod C# – Skapa DataBar streckkod

Letar du efter **generate barcode C#** utan att gå igenom oändliga dokument? Du är på rätt plats. I den här guiden går vi igenom hur du skapar en **DataBar barcode**, justerar dess dimensioner och slutligen **exporterar streckkodsbilden**—allt med några få rader C#.

Föreställ dig att du behöver en kompakt produktetikett som får plats på en liten hylltagg. En DataBar Expanded Stacked-symbolik löser det, och med Aspose.BarCode kan du exakt kontrollera hur många kolumner eller rader den använder. Är du redo? Låt oss dyka ner.

## Vad du kommer att uppnå

- **Create a DataBar barcode** (den “expanded stacked” varianten) från grunden.  
- **Customize barcode size** genom att direkt ange kolumner eller rader.  
- **Change barcode dimensions** i farten utan att bygga om generatorn.  
- **Export barcode image** till PNG (eller vilket format Aspose stödjer).  

Inga externa tjänster, inga röriga konfigurationer—bara ren, körbar C#-kod.

## Förutsättningar

- .NET 6.0 eller senare (koden fungerar också på .NET Framework 4.7+).  
- En giltig Aspose.BarCode för .NET-licens (eller så kan du köra i provläge).  
- En IDE du föredrar—Visual Studio, Rider eller VS Code räcker.  

Om du ännu inte har installerat NuGet-paketet, kör:

```bash
dotnet add package Aspose.BarCode
```

Det är allt—inga andra beroenden.

## Steg 1: Ställ in streckkodsgeneratorn (Hur man **generate barcode C#**)

Först behöver vi en `BarcodeGenerator`-instans som pekar på **DataBar Expanded Stacked**-symboliken. Detta objekt är motorn som senare skapar bilden.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Initialize the generator with the desired symbology and data
BarcodeGenerator barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // Symbology
    "Databar Expanded Stacked long");    // Human‑readable text (optional)
```

*Varför detta är viktigt*: `EncodeTypes.DatabarExpandedStacked`‑enumet talar om för Aspose att vi vill ha den staplade versionen, vilket är idealiskt för smala utrymmen. Texten vi skickar blir det kodade värdet; du kan ersätta den med vilken numerisk sträng din applikation än kräver.

## Steg 2: **Customize barcode size** – ange kolumner

DataBar-streckkoder låter dig påverka den visuella densiteten genom att ange antingen antalet **columns** *eller* **rows**. Låt oss börja med kolumner. Radräkningen beräknas automatiskt för att hålla streckkoden giltig.

```csharp
// Set the number of columns; rows are computed automatically
barcodeGen.Parameters.Barcode.DataBar.Columns = 4;
```

*Proffstips*: Kolumner påverkar streckkodens bredd. Fler kolumner → bredare streckkod, vilket kan förbättra skanningspålitligheten på lågrelösningsskrivare.

## Steg 3: **Export barcode image** med kolumninställningen

Nu skriver vi bilden till disk. Du kan välja PNG, JPEG, BMP eller till och med SVG. Här är PNG för skarp, förlustfri output.

```csharp
// Save the barcode image using the current column configuration
barcodeGen.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

> **Förväntat resultat** – Öppna `DatabarCols4.png` så bör du se en prydligt staplad DataBar med fyra kolumner. Den ser ut som en tät stapel av vertikala staplar, perfekt för en liten etikett.

## Steg 4: **Change barcode dimensions** – ange rader istället

Ibland behöver du en högre streckkod snarare än en bredare. Byt till radkontroll; Aspose kommer att beräkna kolumnerna automatiskt.

```csharp
// Switch to row control – columns will be derived automatically
barcodeGen.Parameters.Barcode.DataBar.Rows = 3;
```

*Varför byta?* Rader påverkar streckkodens höjd. Fler rader gör symbolen högre, vilket kan vara praktiskt när du har vertikalt utrymme men begränsad bredd.

## Steg 5: **Export barcode image** med radinställningen

Spara den andra varianten. Lägg märke till att filnamnet återspeglar förändringen; du kan också behålla båda bilderna för jämförelse.

```csharp
// Save the barcode image using the new row configuration
barcodeGen.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

> **Resultat** – `DatabarRows3.png` visar nu en högre version av samma data, fortfarande perfekt skannbar.

## Fullt fungerande exempel

När vi sätter ihop allt, här är en fristående konsolapp som du kan kopiera‑klistra in och köra omedelbart:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator for DataBar Expanded Stacked
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Customize size – set columns (width)
        barcodeGen.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Export image with column setting
        string colPath = @"C:\Barcodes\DatabarCols4.png";
        barcodeGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column‑based barcode to {colPath}");

        // 4️⃣ Change dimensions – set rows (height)
        barcodeGen.Parameters.Barcode.DataBar.Rows = 3;

        // 5️⃣ Export image with row setting
        string rowPath = @"C:\Barcodes\DatabarRows3.png";
        barcodeGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row‑based barcode to {rowPath}");
    }
}
```

Kör programmet, öppna sedan de två PNG-filerna. Du har nu **generated barcode C#**, **customized barcode size**, **changed barcode dimensions**, och **exported the barcode image**—allt på under en minut.

## Vanliga frågor & kantfall

- **What if I need a different image format?**  
  Ersätt `BarCodeImageFormat.Png` med `Jpeg`, `Bmp`, `Gif` eller `Svg`. API:et hanterar konverteringen automatiskt.

- **Can I change both rows and columns simultaneously?**  
  Tekniskt sett kan du sätta båda, men Aspose prioriterar den sista egenskapen du ändrar. Det är säkrare att sätta *en* dimension och låta biblioteket beräkna den andra för en giltig DataBar.

- **How do I apply a foreground/background color?**  
  Använd `barcodeGen.Parameters.Barcode.ForegroundColor` och `BackgroundColor`. Exempel:  
  ```csharp
  barcodeGen.Parameters.Barcode.ForegroundColor = Color.DarkBlue;
  barcodeGen.Parameters.Barcode.BackgroundColor = Color.White;
  ```

- **Is there a size limit for the encoded data?**  
  DataBar Expanded Stacked stödjer upp till 74 numeriska tecken (eller 30 alfanumeriska). Att överskrida detta kastar ett undantag.

## Nästa steg

Nu när du behärskar grunderna i **create databar barcode**, överväg:

- Lägga till **text annotations** under streckkoden (`barcodeGen.Parameters.CaptionAbove.Text`).
- Bädda in PNG direkt i en PDF med Aspose.PDF.
- Generera streckkoder i bulk genom att loopa över en CSV med produkt‑ID:n.

Varje av dessa ämnen bygger på samma `BarcodeGenerator`‑objekt, så du behöver inte börja från början.

---

**Slutsats**: du vet nu hur du **generate barcode C#**, **customize barcode size**, **change barcode dimensions**, och **export barcode image** med Aspose.BarCode. Experimentera med kolumn‑/radvärdena, byt bildformat och integrera koden i ditt lager‑ eller POS‑system. Lycka till med kodningen!

## Vad du bör lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}