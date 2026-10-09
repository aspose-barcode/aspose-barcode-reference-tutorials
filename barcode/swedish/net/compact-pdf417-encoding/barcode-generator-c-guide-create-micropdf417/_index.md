---
category: general
date: 2026-09-29
description: Barcode‑generatorn C#‑guide visar hur man genererar en MicroPdf417‑streckkod,
  ändrar dimensioner, ställer in kolumner och anpassar streckkodens storlek på bara
  några rader.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to generate barcode
- how to change dimensions
- how to set columns
- customize barcode size
language: sv
lastmod: 2026-09-29
og_description: Barcode‑generator C#‑guide visar hur man genererar en MicroPdf417‑streckkod,
  ändrar dimensioner, ställer in kolumner och anpassar streckkodens storlek på bara
  några rader.
og_image_alt: Screenshot of a MicroPdf417 barcode generated with a C# barcode generator
og_title: Barcodegenerator C#‑guide – skapa och anpassa MicroPdf417
schemas:
- author: GroupDocs
  dateModified: '2026-09-29'
  description: Barcode generator C# guide shows how to generate a MicroPdf417 barcode,
    change dimensions, set columns, and customize barcode size in just a few lines.
  headline: 'Barcode generator C# guide: create MicroPdf417'
  type: TechArticle
tags:
- barcode
- C#
- MicroPdf417
- barcode generation
title: 'Barcodegenerator C#‑guide: skapa MicroPdf417'
url: /sv/net/compact-pdf417-encoding/barcode-generator-c-guide-create-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator C# guide: skapa MicroPdf417

Om du behöver en **barcode generator C#** för ditt .NET‑projekt, guidar den här handledningen dig genom att skapa en MicroPdf417‑streckkod från grunden. Du kommer att lära dig **hur man genererar streckkod**, ändra dimensioner, ange kolumner och **anpassa streckkodens storlek** utan ansträngning.

MicroPdf417 är en kompakt 2‑D‑symbologi som fungerar bra för märkning av små delar, biljetter eller lageretiketter. I slutet av den här guiden har du en komplett, körbar konsolapplikation som sparar en PNG‑bild av streckkoden, och du förstår hur varje parameter påverkar den slutliga storleken.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare (koden fungerar också med .NET Framework 4.7+)
* En C#‑kompatibel IDE (Visual Studio, VS Code, Rider, etc.)
* **GroupDocs.Barcode**‑paketet från NuGet – installera det med  

  ```bash
  dotnet add package GroupDocs.Barcode
  ```

Inga ytterligare externa verktyg krävs; biblioteket hanterar kodning, rendering och filsparning.

## Barcode generator C#: initiera generatorn

Det första steget är att skapa en instans av `BarcodeGenerator` och ange symbologin (`EncodeTypes.MicroPdf417`) tillsammans med den data du vill koda.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // Subsequent configuration steps go here...

            // Save the final image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

**Varför detta är viktigt:**  
`BarcodeGenerator` är ingångspunkten för alla streckkodoperationer. Konstruktorn binder den valda **EncodeTypes** (MicroPdf417) till den råa datasträngen. Biblioteket hanterar automatiskt Unicode‑tecken som “Å” och “©”, så du behöver ingen extra kodningslogik.

## Hur du ändrar streckkodens dimensioner

En streckkods läsbarhet beror starkt på modulbredden (X‑dimensionen). Att sätta den till ett högre pixelantal gör staplarna bredare och bilden lättare att skanna, särskilt på lågupplösta skärmar.

```csharp
// Step 2 – adjust the X‑dimension (module width) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Förklaring:**  
`XDimension.Pixels` styr bredden på en enskild streckkodmodul. Standardvärdet är 1 pixel, vilket kan se tunt ut på hög‑DPI‑monitorer. Att höja det till 2 pixel fördubblar den totala bredden utan att påverka den kodade datan.

**Tips:** Om du planerar att skriva ut streckkoden i 300 dpi, ger ett värde på 3 eller 4 pixel ofta den bästa balansen mellan storlek och skanningspålitlighet.

## Hur du anger kolumner för storlekskontroll

MicroPdf417 låter dig specificera antalet kolumner (upp till 4). Färre kolumner ger en högre streckkod; fler kolumner gör den bredare men kortare. Att justera detta värde är det primära sättet att **anpassa streckkodens storlek**.

```csharp
// Step 3 – set the maximum number of columns (4 is the limit for MicroPdf417)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Varför detta fungerar:**  
`Pdf417.Columns`‑egenskapen delas av alla PDF417‑baserade symbologier, inklusive MicroPdf417. Att sätta den till maxvärdet (4) sprider datan över den bredaste möjliga layouten, vilket minskar den totala höjden. Om du behöver en mer kompakt höjd, sänk kolumnantalet till 2 eller 3.

**Edge case:** När datasträngen är lång kan biblioteket automatiskt öka antalet rader för att rymma innehållet, oavsett kolumnantal. Håll payloaden under 50 tecken för förutsägbar storlek.

## Anpassa streckkodens storlek för olika utdata

Utöver X‑dimension och kolumner kan du påverka den slutliga bildstorleken genom att välja ett lämpligt bildformat och DPI. PNG är förlustfritt, perfekt för webbvisning, medan BMP eller TIFF kan vara att föredra för högkvalitativ utskrift.

```csharp
// Step 4 – save as PNG (lossless) with default 96 dpi
generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
```

Om du behöver en högre DPI kan du ange den explicit:

```csharp
generator.Parameters.Image.DpiX = 300;
generator.Parameters.Image.DpiY = 300;
generator.Save("MicroPdf417_300dpi.png", BarCodeImageFormat.Png);
```

**Resultat:** Den sparade PNG‑filen innehåller en skarp MicroPdf417‑streckkod som respekterar de dimensioner du konfigurerat. Öppna filen i någon bildvisare för att verifiera den visuella storleken.

### Förväntad output

När programmet körs skapas en fil med namnet **MicroPdf417.png** (eller **MicroPdf417_300dpi.png** om du har satt DPI). Streckkoden kommer att se ut ungefär som illustrationen nedan:

![Barcode generator C# output showing a MicroPdf417 PNG](barcode-micro-pdf417.png)

*Alt text:* *Barcode generator C# output som visar en MicroPdf417 PNG*

Att skanna bilden med en standard 2‑D‑streckkodsläsare returnerar den ursprungliga strängen `Åspóse.Barcóde©`.

## Fullständig källkod för snabb kopiering

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // 2️⃣ Change dimensions – make modules 2 pixels wide
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set columns – use the maximum of 4 for a wider, shorter barcode
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // (Optional) Increase DPI for high‑resolution output
            // generator.Parameters.Image.DpiX = 300;
            // generator.Parameters.Image.DpiY = 300;

            // 4️⃣ Save the barcode as a PNG image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

Kopiera koden till ett nytt konsolprojekt, återställ NuGet‑paket och kör `dotnet run`. Konsolen bekräftar bildens plats, och du ser den genererade streckkoden i projektmappen.

## Vanliga frågor och felsökning

| Fråga | Svar |
|----------|--------|
| **Vad händer om streckkoden ser suddig ut?** | Öka `XDimension.Pixels` eller DPI (`Parameters.Image.DpiX/Y`). Båda förstorar modulerna och förbättrar den visuella kvaliteten. |
| **Kan jag använda ett annat bildformat?** | Ja. Byt `BarCodeImageFormat.Png` mot `Jpeg`, `Bmp` eller `Tiff`. PNG är fortfarande det säkraste valet för förlustfri kvalitet. |
| **Min data innehåller emojis—kommer de att kodas?** | MicroPdf417 stödjer UTF‑8, så de flesta emojis kodas korrekt. Om du får fel, kontrollera att strängen är korrekt normaliserad (`System.Text.Encoding.UTF8`). |
| **Hur genererar jag andra symbologier?** | Ändra `EncodeTypes.MicroPdf417` till något annat värde från `EncodeTypes` (

## Vad bör du lära dig härnäst?

De följande handledningarna täcker närliggande ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to Generate Barcode Image in C# – MicroPdf417 Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)
- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}