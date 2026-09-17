---
category: general
date: 2026-08-06
description: Hur man ställer in kolumner för en Databar Expanded Stacked‑streckkod
  och lär sig hur man genererar streckkodsbilder, ställer in rader och sparar streckkodsfilen
  i C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set columns
- how to generate barcode
- how to set rows
- barcode save file
language: sv
lastmod: 2026-08-06
og_description: Hur man ställer in kolumner för en Databar Expanded Stacked‑streckkod
  och snabbt lär sig hur man genererar streckkodsbilder, ställer in rader och sparar
  streckkodsfilen med Aspose.Barcode.
og_image_alt: Screenshot showing how to set columns for a Databar Expanded Stacked
  barcode in C#
og_title: Hur man ställer in kolumner för en Databar Expanded Stacked‑streckkod –
  steg‑för‑steg C#‑guide
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: How to set columns for a Databar Expanded Stacked barcode and learn
    how to generate barcode images, set rows, and save the barcode file in C#.
  headline: How to set columns for a Databar Expanded Stacked barcode – complete C#
    guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: Hur man ställer in kolumner för en Databar Expanded Stacked‑streckkod – komplett
  C#‑guide
url: /sv/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så ställer du in kolumner för en Databar Expanded Stacked streckkod – komplett C#-guide

Om du behöver **how to set columns** för en Databar Expanded Stacked streckkod, visar den här handledningen exakt hur du går tillväga. Oavsett om du bygger ett detaljhandels‑etiketteringssystem eller en logistikapplikation, låter kontroll av kolumner och rader dig finjustera streckkodens storlek och skanningspålitlighet. Dessutom kommer du att se **how to generate barcode** bilder, justera antalet rader och korrekt **barcode save file** till disk.

Denna guide går igenom:

* Installera Aspose.Barcode för .NET-biblioteket.  
* Skapa en streckkodsgenerator för Databar Expanded Stacked‑typen.  
* Ställa in antalet kolumner, antalet rader och bildformat.  
* Spara de resulterande PNG‑filerna till en vald katalog.  

Ingen tidigare erfarenhet av Aspose.Barcode krävs – bara en grundläggande C#‑utvecklingsmiljö.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare installerat.  
* Visual Studio 2022 (eller någon IDE som stödjer .NET).  
* En NuGet‑referens till **Aspose.Barcode** (`dotnet add package Aspose.Barcode`).  

Alla kodsnuttar kompileras med standardkonsolprojekt‑mallen.

## Steg 1: Skapa en streckkodsgenerator för Databar Expanded Stacked

Den första operationen är att instansiera `BarcodeGenerator` med `EncodeTypes.DatabarExpandedStacked`‑enum. Detta ställer in standardlayouten (stacked) och förbereder objektet för vidare konfiguration.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a generator for the Databar Expanded Stacked type.
        // The text "Databar Expanded Stacked long" is the data encoded in the barcode.
        BarcodeGenerator barcodeGeneratorCols = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

**Varför detta är viktigt:** Generatorn innehåller alla renderingsparametrar. Genom att välja `DatabarExpandedStacked` talar du om för biblioteket att använda den staplade layouten, som är den enda layouten som stödjer justering av kolumner och rader.

## Så ställer du in kolumner för en Databar Expanded Stacked streckkod

Nu när generatorn finns kan du kontrollera antalet kolumner. `DataBar.Columns`‑egenskapen accepterar ett heltal mellan 1 och 4. Att sätta den till **4** skapar den bredaste möjliga streckkoden samtidigt som den fortfarande passar den staplade layouten.

```csharp
        // Step 2: Configure the generator to use 4 columns.
        barcodeGeneratorCols.Parameters.Barcode.DataBar.Columns = 4;
```

**Praktiskt tips:** Använd det maximala antalet kolumner endast när du har tillräckligt med vitt utrymme på etiketten. För många kolumner på en liten etikett kan orsaka skanningsproblem.

## Så genererar du streckkodsbilder och sparar dem

Efter att ha konfigurerat kolumnerna måste du rendera streckkoden och skriva bilden till disk. `Save`‑metoden tar en filsökväg och en bildformat‑enum.

```csharp
        // Step 3: Save the barcode image as PNG.
        barcodeGeneratorCols.Save("output/DatabarCols4.png", BarCodeImageFormat.Png);
```

Mappen `output` måste finnas, annars kastas ett undantag. Du kan skapa den programatiskt med `Directory.CreateDirectory("output");` om du föredrar.

## Så ställer du in rader för en Databar Expanded Stacked streckkod

Rader fungerar på liknande sätt som kolumner, men de påverkar den vertikala staplingen av streckkodens moduler. `DataBar.Rows`‑egenskapen accepterar värden från 1 till 5. I detta exempel använder vi **3** rader.

```csharp
        // Step 4: Create a second generator for the same barcode type.
        BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 5: Configure the generator to use 3 rows.
        barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

        // Step 6: Save the row‑adjusted barcode.
        barcodeGeneratorRows.Save("output/DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Varför rader är viktiga:** Att lägga till rader ökar streckkodens höjd, vilket kan vara användbart för högdensitetsetiketter där du behöver fler datamoduler utan att bredda streckkoden.

## Alternativ för att spara streckkodsfiler och bästa praxis

`Save`‑metoden stödjer flera bildformat (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`). PNG är förlustfri och fungerar bra för de flesta skanningsenheter. Om du behöver en mindre filstorlek och kan tolerera små komprimeringsartefakter, välj JPEG:

```csharp
barcodeGeneratorCols.Save("output/DatabarCols4.jpg", BarCodeImageFormat.Jpeg);
```

**Särskilt fall:** När du sparar som JPEG, se till att kvalitetsparametern är korrekt inställd (standard är 90). Låg kvalitet kan sudda ut de små modulerna, vilket gör streckkoden oläslig.

## Komplett, körbart exempel

När allt sätts ihop, här är en enda fil som du kan kopiera in i ett nytt konsolprojekt och köra omedelbart:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Ensure the output directory exists.
        Directory.CreateDirectory("output");

        // ------------------------------
        // How to set columns (4 columns)
        // ------------------------------
        BarcodeGenerator colsGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
        colsGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colsGenerator.Save("output/DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to output/DatabarCols4.png");

        // ------------------------------
        // How to set rows (3 rows)
        // ------------------------------
        BarcodeGenerator rowsGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
        rowsGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowsGenerator.Save("output/DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to output/DatabarRows3.png");

        // ------------------------------
        // How to generate barcode (additional format)
        // ------------------------------
        rowsGenerator.Save("output/DatabarRows3.jpg", BarCodeImageFormat.Jpeg);
        Console.WriteLine("Saved JPEG version to output/DatabarRows3.jpg");
    }
}
```

**Förväntad output:** Efter att programmet har körts innehåller mappen `output` tre filer:

* `DatabarCols4.png` – streckkod med 4 kolumner (bred).  
* `DatabarRows3.png` – streckkod med 3 rader (tall).  
* `DatabarRows3.jpg` – JPEG‑version av 3‑raders streckkoden.

Öppna någon av PNG‑filerna i en bildvisare; du bör se en tydlig Databar Expanded Stacked streckkod redo för skanning.

## Vanliga frågor och felsökning

| Question | Answer |
|----------|--------|
| *Vad händer om bilden är suddig?* | Verifiera att du använder PNG för förlustfri output. Om du behöver JPEG, öka kvalitetsinställningen (`new JpegOptions { Quality = 95 }`). |
| *Kan jag ändra streckkodstexten?* | Ja – ersätt det andra argumentet i `new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Your Text")`. |
| *Fungerar kolumner och rader tillsammans?* | De kan kombineras; sätt bara både `DataBar.Columns` och `DataBar.Rows` innan du anropar `Save`. |
| *Finns det en gräns för katalogdjup?* | Sökvägen måste vara giltig för operativsystemet. Använd `Path.Combine` för plattformsoberoende säkerhet. |

## Slutsats

Du vet nu **how to set columns** för en Databar Expanded Stacked streckkod, **how to set rows**, och **how to generate barcode** bilder som du kan **barcode save file** i PNG‑ eller JPEG‑format. Det kompletta exemplet demonstrerar varje nödvändigt steg, från bibliotekets installation till slutlig filverifiering.

Nästa, överväg att utforska:

* **how to generate barcode** med felkorrigeringsnivåer för QR‑koder.  
* **barcode save file** alternativ för vektorformat som SVG eller PDF.  
* Integrera de genererade streckkoderna i ASP.NET Core MVC‑vyer för dynamisk etikettutskrift.

Känn dig fri att experimentera med olika kolumn-/radkombinationer, bildformat och streckkodsinnehåll för att matcha ditt projekts specifikationer. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Hur man genererar streckkod – endimensionella streckkodstyper](/barcode/english/net/one-dimensional-barcode-types/)
- [Hur man genererar streckkod – Code 39‑konfiguration med Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Hur man genererar Aztec‑streckkod med anpassat bildförhållande med Aspose.BarCode för .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}