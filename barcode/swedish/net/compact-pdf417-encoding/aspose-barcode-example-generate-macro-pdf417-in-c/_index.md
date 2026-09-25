---
category: general
date: 2026-08-09
description: Aspose streckkodsexempel som visar hur man använder en streckkodsgenerator
  i C# för att skapa en Macro PDF417 med fullt metadata‑stöd.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- barcode generator c#
language: sv
lastmod: 2026-08-09
og_description: Aspose barcode-exempel visar hur man använder en streckkodgenerator
  i C# för att skapa en Macro PDF417-streckkod som innehåller fil‑ID, segmentdata,
  tidsstämpel och annan metadata.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Aspose streckkodsexempel – skapa Macro PDF417 med C#
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Macro PDF417
title: 'Aspose streckkodsexempel: generera Macro PDF417 i C#'
url: /sv/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose streckkodsexempel: generera Macro PDF417 i C#

Om du behöver ett **aspose barcode example** som skapar en Macro PDF417‑streckkod, visar den här guiden hur du gör det med en **barcode generator C#**. Du kommer att se alla nödvändiga inställningar, från grundläggande dimensioner till hela uppsättningen av Macro PDF417‑metadatafält, och du får en PNG‑bild klar för nedströmsbehandling.

Tutorialen täcker hela arbetsflödet, förklarar varför varje parameter är viktig, och ger ett färdigt kodexempel som kan köras direkt. Inga externa referenser krävs; du kan kopiera koden, justera värdena och köra den omedelbart.

## Förutsättningar

Innan du börjar, se till att du har:

- .NET 6.0 (eller senare) installerat  
- Visual Studio 2022 eller någon C#‑kompatibel IDE  
- En giltig licens för **Aspose.BarCode for .NET** (gratis provversion fungerar för detta exempel)  

Lägg till Aspose.BarCode NuGet‑paketet i ditt projekt:

```bash
dotnet add package Aspose.BarCode
```

## Steg 1: Skapa barcode‑generator‑instansen i C#

Det första steget är att instansiera `BarcodeGenerator` med enum‑värdet `EncodeTypes.MacroPdf417` och den text du vill koda. Texten kan innehålla Unicode‑tecken, vilket biblioteket hanterar automatiskt.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Varför detta är viktigt*: `EncodeTypes.MacroPdf417` talar om för motorn att producera en Macro PDF417‑symbol, som stödjer segmenterad data och extra fil‑nivå‑metadata. `using`‑satsen garanterar att ohanterade resurser frigörs efter att bilden har sparats.

## Steg 2: Definiera grundläggande streckkodens utseende

En Macro PDF417‑streckkod består av fyrkantiga moduler. Att kontrollera modulstorlek och kolumnantal påverkar både läsbarhet och filstorlek.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Varför detta är viktigt*: `XDimension.Pixels` bestämmer den visuella densiteten; ett värde på 2 pixlar fungerar bra för skärmvisning samtidigt som bilden hålls liten. Justera kolumnantalet för att passa dina layoutbegränsningar—fler kolumner ger en bredare, kortare streckkod.

## Steg 3: Ange Macro PDF417‑specifik metadata

Macro PDF417 utökar standard‑PDF417‑formatet med fält som möjliggör återuppbyggnad av stora filer från flera streckkodsegment. Varje fält är valfritt, men att ange dem demonstrerar API:ets fulla kapacitet.

```csharp
    // Unique identifier for the entire file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (zero‑based)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the file
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Logical name of the source file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // 16‑bit CCITT checksum for error detection
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate size of the original file in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;

    // Timestamp when the file was generated
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields for routing information
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the last segment
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Varför detta är viktigt*:  
- `MacroPdf417FileID` länkar alla segment som tillhör samma logiska fil.  
- `MacroPdf417SegmentID` och `MacroPdf417SegmentsCount` gör att avkodaren kan sortera fragmenten korrekt.  
- `MacroPdf417Checksum` ger en snabb integritetskontroll utan att avkoda hela nyttolasten.  
- `MacroPdf417FileSize` och `MacroPdf417TimeStamp` låter nedströmsystem verifiera att den återuppbyggda filen matchar originalet.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` är användbara i logistik‑ eller dokumentutbytesscenario.  
- Att sätta `MacroPdf417Terminator` till `Set` markerar denna streckkod som det sista segmentet, vilket förenklar återuppbyggnadsalgoritmen.

## Steg 4: Spara den genererade streckkodsbilden

Till sist skriver du streckkoden till en PNG‑fil. Du kan välja vilket som helst av de stödjade formaten (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Varför detta är viktigt*: PNG bevarar förlustfri pixeldata, vilket säkerställer att skannrar läser exakt det modulmönster du konfigurerat. Att byta format kan påverka den visuella kvaliteten och filstorleken.

### Förväntat resultat

När programmet körs skapas en fil med namnet **ExtPDF417Meta.png**. När du öppnar bilden visas en rektangulär Macro PDF417‑streckkod med texten “Åspóse.Barcóde©” kodad, och den visuella densiteten matchar den 2‑pixel X‑dimension du angav. Att skanna bilden med en PDF417‑kompatibel läsare returnerar alla metadatafält som definierades i Steg 3.

## Fullt fungerande exempel

Kopiera koden nedan till ett nytt konsolprojekt (`dotnet new console`) och ersätt `YOUR_DIRECTORY` med en absolut eller relativ sökväg som finns på din maskin.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with the desired text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the basic barcode appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // pixel size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol

                // Step 3: Set Macro PDF417 specific metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode image
                generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

Kör programmet (`dotnet run`). Efter körning, verifiera att PNG‑filen finns på den plats du angav. Använd någon streckkodsläsare som stödjer Macro PDF417 för att bekräfta att metadata är korrekt inbäddad.

## Vanliga variationer och kantfall

- **Olika bildformat**: Byt `BarCodeImageFormat.Png` mot `Jpeg`, `Bmp` eller `Tiff` om ditt nedströmsystem föredrar ett annat format.  
- **Ändra modulstorlek**: Större `XDimension.Pixels`‑värden förbättrar skanningspålitlighet på lågupplösta skannrar men ökar bildstorleken.  
- **Flera segment**: För att producera en fler‑segment‑fil, generera en serie streckkoder, öka `MacroPdf417SegmentID` för varje och håll `MacroPdf417FileID` konstant. Endast det sista segmentet ska ha `MacroPdf417Terminator` satt.  
- **Unicode‑stöd**: Generatorn kodar automatiskt Unicode‑tecken; säkerställ att din källsträng använder UTF‑8‑kodning om du läser den från en extern fil.  
- **Felhantering**: Omge `using`‑blocket med en try‑catch för att fånga `BarCodeException` vid ogiltiga parametrar (t.ex. kolumnantal utanför intervall).

## Pro‑tips

- **Prestanda**: Återanvänd en enda `BarcodeGenerator`‑instans när du skapar många streckkoder med samma inställningar; ändra bara `CodeText`‑egenskapen mellan sparningar.  
- **Filstorleksestimering**: `MacroPdf417FileSize`‑fältet bör matcha byte‑antalet av den ursprungliga nyttolasten; avvikelser kan orsaka valideringsfel i nedströmsystem.  
- **Testning**: Validera genererade streckkoder med både Asposes inbyggda avkodare (`BarCodeReader`) och en tredjeparts‑skanner för att säkerställa interoperabilitet.

## Slutsats

Detta **aspose barcode example

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstreras i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar streckkod – Compact PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hur man skapar tyst zon för Code 16K med Aspose.BarCode för .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Hur man skapar tyst zon för ITF-14 med Aspose.BarCode för .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}