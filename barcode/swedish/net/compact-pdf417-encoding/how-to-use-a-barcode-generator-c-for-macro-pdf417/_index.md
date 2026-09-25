---
category: general
date: 2026-08-22
description: barcode generator C#‑handledning visar hur man skapar en Macro PDF417‑streckkod
  med metadata och sparar den som PNG med Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- Macro PDF417
- Aspose.BarCode
- C# barcode library
- PDF417 barcode
- barcode metadata
language: sv
lastmod: 2026-08-22
og_description: barcode generator C# låter dig skapa en Macro PDF417‑streckkod med
  fullständig filnivåmetadata och exportera den som PNG. Följ den här guiden för att
  implementera lösningen.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: streckkodsgenerator C# – skapa Macro PDF417‑streckkoder steg för steg
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to create a Macro PDF417 barcode
    with metadata and save it as PNG using Aspose.BarCode.
  headline: How to use a barcode generator C# for Macro PDF417
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Hur man använder en streckkodsgenerator i C# för Macro PDF417
url: /sv/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så använder du en barcode‑generator C# för Macro PDF417

Om du behöver en **barcode generator C#** som kan skapa en Macro PDF417‑symbol med metadata på filnivå, ger den här guiden en komplett, färdig‑att‑köra‑lösning. Du får se hur du konfigurerar streckkodens utseende, bäddar in makroinformation såsom fil‑ID och segmentantal, och slutligen sparar resultatet som en PNG‑bild.

Exemplet använder Aspose.BarCode‑biblioteket, ett allmänt använt **C# barcode library** som stödjer hela PDF417‑funktionsuppsättningen. Inga externa tjänster krävs, och koden fungerar med .NET 6 eller senare.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6 SDK (eller någon senare version) installerad.  
* Visual Studio 2022, VS Code eller någon annan C#‑IDE.  
* En NuGet‑referens till **Aspose.BarCode** (`dotnet add package Aspose.BarCode`).

Att förstå grundläggande C#‑syntax och konceptet med PDF417‑streckkoder hjälper dig att följa stegen, men tutorialen förklarar varje konfigurationsalternativ i detalj.

## Vad tutorialen täcker

* Initiering av en **barcode generator C#**‑instans för Macro PDF417‑formatet.  
* Justering av visuella parametrar såsom X‑dimension och kolumnantal.  
* Tillhandahållande av Macro PDF417‑fält på filnivå: fil‑ID, segment‑ID, segmentantal, filnamn, kontrollsumma, filstorlek, tidsstämpel, mottagare, avsändare och terminator.  
* Sparande av den genererade symbolen som en PNG‑fil.  
* Tips för att hantera kantfall som stora filstorlekar eller anpassade tidsstämplar.

När du har läst hela artikeln har du ett självständigt program som producerar en fullt kompatibel Macro PDF417‑streckkod.

## Steg 1: Skapa barcode‑generator C#‑instansen

Den första operationen är att instansiera `BarcodeGenerator` med enum‑värdet `EncodeTypes.MacroPdf417` och den text du vill koda. Konstruktorn accepterar också payload‑strängen, som blir datadelen av makrostreckkoden.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for Macro PDF417
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent configuration goes here
}
```

**Varför detta är viktigt** – Flaggan `EncodeTypes.MacroPdf417` talar om för Aspose.BarCode att behandla symbolen som en makrostreckkod, vilket aktiverar de extra fält som följer. Utan denna flagga skulle biblioteket generera en vanlig PDF417‑streckkod utan metadata på filnivå.

## Steg 2: Justera grundläggande streckkodens utseende (PDF417‑visuella inställningar)

Visuell klarhet är avgörande för pålitlig avläsning. Två vanliga parametrar är modulbredd (`XDimension`) och antalet kolumner. Att sätta dessa värden balanserar storlek och läsbarhet.

```csharp
    // Step 2: Adjust basic barcode appearance
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol
```

* `XDimension.Pixels` styr bredden på varje svart/vit stapel. Ett värde på **2** fungerar bra för de flesta etikett‑skrivare.  
* `Pdf417.Columns` definierar hur många kolumner streckkoden ska använda. Fem kolumner ger en kompakt symbol utan att offra datakapacitet.

## Steg 3: Definiera Macro PDF417‑information på filnivå

Macro PDF417 utökar standard‑PDF417‑formatet med fält som beskriver hur en stor fil delas upp i flera streckkodsegment. Att ange dessa fält säkerställer att mottagande skannrar kan återkonstruera den ursprungliga filen.

```csharp
    // Step 3: Define Macro PDF417 file‑level information
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;          // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;            // current segment number (0‑indexed)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;       // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";      // optional logical file name
```

* `MacroPdf417FileID` måste vara samma för varje segment som tillhör samma logiska fil.  
* `MacroPdf417SegmentID` ökas från **0** till `SegmentsCount‑1`.  
* `MacroPdf417SegmentsCount` talar om för avkodaren hur många delar som förväntas.  
* `MacroPdf417FileName` är valfritt men hjälpsamt för mänsklig identifiering.

## Steg 4: Ange ytterligare makro‑metadata

Utöver den grundläggande filinformationen tillåter specifikationen extra fält såsom kontrollsumma, filstorlek, tidsstämpel, mottagare, avsändare och en terminator‑flagga. Att fylla i dessa fält förbättrar dataintegritet och spårbarhet.

```csharp
    // Step 4: Set additional macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;                  // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

* `MacroPdf417Checksum` ger en 16‑bit CCITT‑kontrollsumma för hela filen; avkodaren kan verifiera integriteten efter återuppbyggnad.  
* `MacroPdf417FileSize` bör motsvara exakt byte‑antal i den ursprungliga filen; värden större än `2^31‑1` kräver ett 64‑bit‑fält, vilket Aspose hanterar automatiskt.  
* `MacroPdf417TimeStamp` registrerar när streckkoden genererades. Använd UTC för att undvika tidszons‑ambiguitet.  
* `MacroPdf417Addressee` och `MacroPdf417Sender` är fria textsträngar som kan lagra routningsinformation.  
* `MacroPdf417Terminator` signalerar att detta är det sista segmentet; sätt den till `Set` för den sista delen, annars lämna standard (`NotSet`).

**Tips för kantfall** – Om din filstorlek överstiger 4 GB, dela innehållet i flera makrosegment och justera `SegmentsCount` därefter. Biblioteket hanterar det stora fältet utan overflow.

## Steg 5: Spara streckkoden som en PNG‑bild

Det sista steget skriver den genererade symbolen till disk. PNG bevarar de exakta pixel‑dimensionerna och stöds brett av skannings‑hardware.

```csharp
    // Step 5: Save the generated barcode as a PNG image
    generator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

Byt ut `YOUR_DIRECTORY` mot en absolut eller relativ sökväg som den körande processen kan skriva till. Enum‑värdet `BarCodeImageFormat.Png` säkerställer förlustfri output.

**Varför PNG?** – Rasterformat som PNG håller modul‑kanterna skarpa, vilket är viktigt för skannrar som förlitar sig på högkontrast‑kanter. Om du behöver ett vektorformat stödjer Aspose även `Pdf` och `Svg`.

## Fullt körbart exempel

Nedan är hela programmet som du kan kopiera in i en konsolapplikation. Det innehåller nödvändiga `using`‑direktiv och en `Main`‑metod.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for Macro PDF417 with sample payload
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Adjust visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // Define macro file‑level fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Add optional metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export to PNG
                generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

### Förväntad output

När programmet körs skapas en fil med namnet **MacroPdf417.png** i projektets arbetskatalog. Att öppna bilden visar en kompakt PDF417‑streckkod med de inbäddade makrofälten. Skannar du bilden med en PDF417‑kompatibel läsare (t.ex. ZXing, Aspose.BarCode‑decoder) får du tillbaka den ursprungliga `"Sample text"`‑payloaden samt makro‑metadata.

## Vanliga frågor och felsökning

| Fråga | Svar |
|----------|--------|
| *Vad gör jag om streckkoden blir för stor för den avsedda etiketten?* | Minska `XDimension.Pixels` eller öka `Pdf417.Columns`. Båda parametrarna påverkar den totala storleken. |
| *Kan jag generera en vektorbild istället för PNG?* | Ja. Anropa `generator.Save("MacroPdf417.svg", BarCodeImageFormat.Svg);` för skalbar output. |
| *Hur verifierar jag kontrollsumman efter skanning?* | Aspose.BarCode‑decodern validerar automatiskt `MacroPdf417Checksum` och rapporterar avvikelser i `MacroPdf417Result`‑objektet. |
| *Är biblioteket kompatibelt med .NET Core?* | NuGet‑paketet stödjer .NET Standard 2.0+, vilket täcker .NET Core, .NET 5, .NET 6 och senare. |
| *Vad gör jag om jag måste bädda in binär data istället för text?* | Konvertera den binära payloaden till Base64 eller använd `EncodeTypes.MacroPdf417`‑överladdningen som accepterar en byte‑array. |

## Pro‑tips för produktionsanvändning

* **Cachea generatorn** –


## Vad bör du lära dig härnäst?


Följande tutorials behandlar närliggande ämnen som bygger vidare på teknikerna i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar streckkod – Compact PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hur man läser streckkod från PDF i Java med Aspose.BarCode](/barcode/english/java/document-barcode-recognition/recognizing-barcodes-from-pdf/)
- [Skapa Codabar‑streckkod med Aspose.Barcode – Generator & Reader API](/barcode/english/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}