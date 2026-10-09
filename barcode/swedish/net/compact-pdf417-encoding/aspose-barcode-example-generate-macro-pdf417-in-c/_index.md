---
category: general
date: 2026-10-09
description: Lär dig hur du skapar PDF417-streckkod i C# med Aspose.BarCode – generera
  en Macro PDF417 med fullt metadata-stöd.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode c#
- macro pdf417 c#
- aspose barcode c#
- barcode generator c#
lastmod: 2026-10-09
og_description: Lär dig hur du skapar PDF417-streckkod i C# med Aspose.BarCode – generera
  en Macro PDF417 med fullt metadata-stöd, inklusive fil-ID, segmentdata, tidsstämpel
  och mer.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Hur man skapar PDF417-streckkod i C# med Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- aspose barcode
- pdf417 barcode
- c# barcode generation
- macro pdf417
title: Hur man skapar PDF417-streckkod i C# med Aspose.BarCode
url: /sv/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar PDF417-streckkod i C# med Aspose.BarCode

Om du snabbt och pålitligt behöver **create PDF417 barcode C#**, går den här handledningen igenom hela processen med Aspose.BarCode. Du kommer att se alla nödvändiga inställningar, från grundläggande dimensioner till hela uppsättningen av Macro PDF417-metadatafält, och du avslutar med en PNG-bild som är klar för vidare bearbetning.

## Snabba svar
- **Vilket bibliotek genererar PDF417-streckkoder?** Aspose.BarCode for .NET.
- **Vilket format ger exemplet som output?** En förlustfri PNG-bild.
- **Behöver jag en licens?** En gratis provversion fungerar för exemplet; en kommersiell licens krävs för produktion.
- **Vilken .NET-version stöds?** .NET 6.0 eller senare.
- **Kan jag lägga till metadata till streckkoden?** Ja – Macro PDF417 stöder fil‑ID, segmentantal, tidsstämplar och mer.

## Vad är en PDF417-streckkod?
En PDF417-streckkod är en staplad linjär symbologi som kan koda upp till cirka 1 KB data per symbol och stöder valfri makro‑metadata för fler‑segment‑filer. Den består av flera rader av staplade linjära mönster, vilket ger hög datakapacitet samtidigt som den förblir läsbar av vanliga 2‑D‑skannrar. Formatet inkluderar även felkorrigeringsnivåer för att förbättra tillförlitligheten, och den valfria makro‑funktionen möjliggör uppdelning av stora filer över flera streckkoder med metadata som hjälper till att återmontera dem.

## Varför använda Aspose.BarCode för PDF417?
Aspose.BarCode stöder **över 50 streckkodssymbologier** och kan generera Macro PDF417‑streckkoder med upp till **2 000 kolumner**, vilket hanterar filer större än **10 MB** utan att ladda hela nyttolasten i minnet. Denna kvantifierade förmåga säkerställer att hög‑genomströmning i företagsmiljöer fungerar smidigt, och den erbjuder omfattande anpassningsalternativ.

## Förutsättningar

Innan du börjar, se till att du har:

- .NET 6.0 (eller senare) installerat  
- Visual Studio 2022 eller någon C#‑kompatibel IDE  
- En giltig licens för **Aspose.BarCode for .NET** (gratis provversion fungerar för detta exempel)  

Lägg till Aspose.BarCode NuGet‑paketet i ditt projekt:

```bash
dotnet add package Aspose.BarCode
```

## Hur man skapar en PDF417-streckkod i C#?

`BarcodeGenerator` är huvudklassen för att skapa streckkods‑bilder.  
`EncodeTypes.MacroPdf417` väljer Macro PDF417‑symbologi för streckkodsgenerering.  
`Save` skriver den genererade streckkoden till en bildfil.

Läs in `BarcodeGenerator` med `EncodeTypes.MacroPdf417`‑enum och din måltext, anropa sedan `Save` – det är hela skapandeprocessen i tre rader. Generatorn hanterar Unicode automatiskt, och `using`‑satsen garanterar att resurser som inte hanteras frigörs efter att bilden sparats.

### Steg 1: skapa barcode‑generator‑instansen i C#

`BarcodeGenerator`‑klassen skapar och konfigurerar streckkods‑bilder.  

Instansiera `BarcodeGenerator` med `EncodeTypes.MacroPdf417`‑enum‑värdet och den text du vill koda. Texten kan innehålla Unicode‑tecken, vilket biblioteket hanterar automatiskt.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Varför detta är viktigt*: `EncodeTypes.MacroPdf417` talar om för motorn att producera en Macro PDF417‑symbol, vilket stöder segmenterad data och extra fil‑nivå‑metadata. `using`‑satsen garanterar att resurser som inte hanteras frigörs efter att bilden sparats.

### Steg 2: definiera grundläggande streckkodutseende

`XDimension.Pixels` anger storleken på varje streckkodmodul i pixlar.

En Macro PDF417‑streckkod består av fyrkantiga moduler. Genom att kontrollera modulstorleken och antalet kolumner påverkas både läsbarhet och filstorlek.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Varför detta är viktigt*: `XDimension.Pixels` bestämmer den visuella densiteten; ett värde på 2 pixlar fungerar bra för skärmvisning samtidigt som bilden hålls liten. Justera kolumnantalet för att passa dina layout‑begränsningar – fler kolumner ger en bredare, kortare streckkod.

### Steg 3: ange Macro PDF417‑specifik metadata

`MacroPdf417FileID` identifierar filen som alla streckkodsegment tillhör.

Macro PDF417 utökar standard‑PDF417‑formatet med fält som möjliggör återuppbyggnad av stora filer från flera streckkodsegment. Varje fält är valfritt, men att sätta dem demonstrerar API:ets fulla kapacitet.

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
- `MacroPdf417SegmentID` och `MacroPdf417SegmentsCount` gör det möjligt för avkodaren att återordna fragment korrekt.  
- `MacroPdf417Checksum` ger en snabb integritetskontroll utan att avkoda hela nyttolasten.  
- `MacroPdf417FileSize` och `MacroPdf417TimeStamp` låter efterföljande system verifiera att den återuppbyggda filen matchar originalet.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` är användbara i logistik‑ eller dokumentutbytes‑scenarier.  
- Att sätta `MacroPdf417Terminator` till `Set` markerar denna streckkod som det sista segmentet, vilket förenklar återuppbyggnadsalgoritmen.

### Steg 4: spara den genererade streckkodsbilden

`Save` skriver streckkodsbilden till den angivna filsökvägen.

Till sist sparas streckkoden som en PNG‑fil. Du kan välja vilket som helst av de stödjade formaten (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Varför detta är viktigt*: PNG bevarar förlustfri pixeldata, vilket säkerställer att skannrar läser exakt det modulmönster du konfigurerat. Att byta format kan påverka den visuella kvaliteten och filstorleken.

#### Förväntat resultat

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

Kör programmet (`dotnet run`). Efter körning, verifiera att PNG‑filen finns på den plats du angav. Använd någon streckkodsläsare som stöder Macro PDF417 för att bekräfta att metadata är korrekt inbäddade.

## Vanliga variationer och kantfall

- **Olika bildformat**: Ersätt `BarCodeImageFormat.Png` med `Jpeg`, `Bmp` eller `Tiff` om ditt efterföljande system föredrar ett annat format.  
- **Ändra modulstorlek**: Större `XDimension.Pixels`‑värden förbättrar skannings‑tillförlitlighet på lågupplösta skannrar men ökar bildstorleken.  
- **Flera segment**: För att producera en fler‑segment‑fil, generera en serie streckkoder, öka `MacroPdf417SegmentID` för varje och håll `MacroPdf417FileID` konstant. Endast det sista segmentet bör ha `MacroPdf417Terminator` satt.  
- **Unicode‑stöd**: Generatorn kodar automatiskt Unicode‑tecken; säkerställ att din källsträng använder UTF‑8‑kodning om du läser den från en extern fil.  
- **Felfångst**: Omslut `using`‑blocket med en try‑catch för att fånga `BarCodeException` vid ogiltiga parametrar (t.ex. kolumnantal utanför intervall).

## Pro‑tips

- **Prestanda**: Återanvänd en enda `BarcodeGenerator`‑instans när du skapar många streckkoder med samma inställningar; ändra bara `CodeText`‑egenskapen mellan sparningar.  
- **Filstorleks‑estimering**: `MacroPdf417FileSize`‑fältet bör matcha byte‑antalet för den ursprungliga nyttolasten; avvikelser kan orsaka valideringsfel i efterföljande system.  
- **Testning**: Validera genererade streckkoder med både Asposes inbyggda avkodare (`BarCodeReader`) och en tredjeparts‑skanner för att säkerställa interoperabilitet.

## Slutsats

Detta **Aspose.BarCode**‑exempel visar hur du **create PDF417 barcode C#** med full Macro‑metadata‑stöd, vilket ger dig en solid grund för att bygga robusta streckkod‑baserade datautbytes‑pipelines.

## Vad bör du lära dig härnäst?

Följande handledningar täcker nära besläktade ämnen som bygger vidare på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementations‑metoder i dina egna projekt.

- [Hur man skapar streckkod – Compact PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hur man skapar streckkodens tysta zon för Code 16K med Aspose.BarCode för .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Hur man skapar streckkodens tysta zon för ITF-14 med Aspose.BarCode för .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

---


**Senast uppdaterad:** 2026-10-09  
**Testad med:** Aspose.BarCode 24.11 for .NET  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man genererar Pdf417‑streckkodsbilder i C med Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Hur man skapar streckkod – Compact PDF417 med Aspose.BarCode](/barcode/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Barcode Generator‑handledning Hur man genererar Pdf417‑streckkod i](/barcode/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}