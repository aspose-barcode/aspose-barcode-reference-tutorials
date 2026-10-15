---
category: general
date: 2026-10-15
description: Skapa en streckkod‑PNG snabbt med C#. Lär dig hur du genererar streckkod,
  ändrar rader, konfigurerar streckkodinställningar och genererar PDF417‑streckkod
  i en enda handledning.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to generate barcode
- how to change rows
- how to configure barcode
- generate pdf417 barcode
language: sv
lastmod: 2026-10-15
og_description: Skapa en streckkod‑PNG i C# snabbt. Den här handledningen visar hur
  du genererar streckkod, ändrar rader, konfigurerar streckkod och genererar PDF417‑streckkod
  med tydlig kod.
og_image_alt: Generated PDF417 barcode saved as a PNG file
og_title: Skapa streckkod PNG med PDF417 i C# – steg-för-steg guide
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode PNG quickly using C#. Learn how to generate barcode,
    change rows, configure barcode settings, and generate PDF417 barcode in a single
    tutorial.
  headline: Create barcode PNG with PDF417 in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Skapa streckkod PNG med PDF417 i C# – komplett guide
url: /sv/net/compact-pdf417-encoding/create-barcode-png-with-pdf417-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa streckkod PNG med PDF417 i C# – komplett guide

Om du behöver **skapa streckkod PNG** från C#‑kod visar den här guiden exakt hur du gör det. Vi går igenom hur du genererar en PDF417‑streckkod, ändrar rader och konfigurerar alla nyckelparametrar innan du sparar resultatet som en PNG‑bild.

Du kommer att lära dig hur du **genererar streckkod**‑bilder programatiskt, justerar layouten för att matcha din design och förstår alternativen för att konfigurera en streckkods utseende. Inga externa verktyg krävs—endast Aspose.BarCode‑biblioteket (eller något kompatibelt .NET‑streckkodspaket) och några rader kod.

## Vad du behöver

- .NET 6.0 eller senare (exemplet använder .NET 6, men vilken recent .NET‑version som helst fungerar)
- En referens till NuGet‑paketet `Aspose.BarCode` (`Install-Package Aspose.BarCode`)
- Grundläggande kunskap om C# och Visual Studio (eller din föredragna IDE)

> **Proffstips:** Om du föredrar ett gratis alternativ finns samma API‑yta i det öppna källkods‑biblioteket `ZXing.Net`; dock riktar kodsnuttarna nedan sig mot Aspose.BarCode eftersom det ger direkta PDF417‑layoutkontroller.

## Steg 1: Ställ in projektet och lägg till streckkodsbiblioteket

Skapa en ny konsolapp och lägg till NuGet‑paketet:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Öppna sedan `Program.cs` och lägg till de nödvändiga `using`‑direktiven:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Dessa namnrymder exponerar klassen `BarcodeGenerator` och uppräkningen `EncodeTypes` som du kommer att använda för att **generera PDF417 streckkod**‑bilder.

## Steg 2: Skapa streckkod PNG – grundläggande generator

Den första handlingsbara raden skapar en `BarcodeGenerator`‑instans konfigurerad för PDF417‑kodning. Detta är kärnan i **hur man genererar streckkod**‑bilder.

```csharp
// Step 2: Initialize the generator with PDF417 and the data to encode
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test"))
{
    // The rest of the configuration goes here
}
```

> **Varför detta är viktigt:** Flaggan `EncodeTypes.Pdf417` talar om för biblioteket vilken symbolik som ska användas. Det andra argumentet (`"Layout test"`) är den råa texten som kommer att kodas till streckkoden.

## Steg 3: Hur man konfigurerar streckkod – sätt modulstorlek

En modul (eller X‑dimension) definierar det minsta utskrivbara elementet i streckkoden. Att justera den ändrar den totala bildstorleken utan att påverka datadensiteten.

```csharp
// Step 3: Set the module size (X dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Att sätta `Pixels = 2` ger ett kompakt, högupplöst **create barcode PNG**‑resultat som fungerar bra för webb‑miniaturer och utskrift.

## Steg 4: Hur man ändrar rader – anpassa PDF417‑layouten

PDF417 låter dig explicit styra antalet kolumner och rader. Detta är steget som svarar på **hur man ändrar rader** i en streckkod.

```csharp
// Step 4: Define a custom layout – 4 columns and 9 rows
generator.Parameters.Barcode.Pdf417.Columns = 4;   // number of data columns
generator.Parameters.Barcode.Pdf417.Rows    = 9;   // number of rows (the focus of “how to change rows”)
```

> **Edge case:** Om du begär fler rader än datan kräver, lägger biblioteket automatiskt till utfyllnadsrader. Om du däremot begär för få rader kan ett undantag uppstå eftersom datan inte får plats.

## Steg 5: Spara den genererade streckkoden som en PNG‑fil

Skriv slutligen bilden till disk. Detta slutför **create barcode PNG**‑arbetsflödet.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417_4x9.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode PNG saved to: {outputPath}");
```

När du kör programmet kommer du att se en fil med namnet `Pdf417_4x9.png` i projektmappen. Bilden innehåller en PDF417‑streckkod med exakt 4 kolumner och 9 rader, renderad med 2‑pixel‑moduler.

### Fullt körbart exempel

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the generator for PDF417
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test"))
        {
            // Configure module size
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Custom layout: 4 columns, 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows    = 9;

            // Save as PNG
            string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417_4x9.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode PNG saved to: {outputPath}");
        }
    }
}
```

**Förväntad utdata** (konsol):

```
Barcode PNG saved to: C:\Path\To\BarcodeDemo\Pdf417_4x9.png
```

Öppna PNG‑filen så ser du en ren PDF417‑streckkod klar för avläsning.

## Hur man genererar streckkod med annan data

Om du behöver **generera streckkod** för en annan sträng, ersätt helt enkelt det andra argumentet i `BarcodeGenerator`‑konstruktorn:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Pdf417, "New data payload"))
{
    // Keep the same configuration or adjust as needed
}
```

Samma konfigurationssteg (modulstorlek, rader, kolumner) gäller, vilket låter dig återanvända koden för flera payloads.

## Hur man ändrar rader dynamiskt baserat på innehållslängd

Ibland måste antalet rader anpassas efter längden på den kodade texten. Du kan beräkna ett säkert radantal innan du skapar generatorn:

```csharp
int estimatedRows = (int)Math.Ceiling(text.Length / (double)(columns * 2)); // rough estimate
generator.Parameters.Barcode.Pdf417.Rows = Math.Max(3, estimatedRows);
```

Detta kodstycke säkerställer att du aldrig begär färre än tre rader (bibliotekets minimum) samtidigt som du skalar upp för längre data.

## Hur man konfigurerar streckkod för olika bildformat

Även om handledningen fokuserar på PNG, kan du byta till JPEG, BMP eller TIFF genom att ändra `BarCodeImageFormat`‑enum:

```csharp
generator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

PNG förblir det bästa valet för förlustfri kvalitet, särskilt när streckkoden ska skrivas ut.

## Vanliga fallgropar och felsökning

| Symptom | Trolig orsak | Åtgärd |
|---------|--------------|-----|
| Streckkoden är suddig | X‑dimension för stor eller bildskalning efter sparning | Håll `XDimension.Pixels` ≤ 3 för skärmbruk, eller skala upp med ett vektorformat (PDF) |
| Scanner kan inte läsa streckkoden | För få rader för datalängden | Öka `Pdf417.Rows` eller låt biblioteket auto‑storleksanpassa genom att utelämna explicit radinställning |
| `ArgumentOutOfRangeException` vid sparning | Utdatakatalogen finns inte | Säkerställ att `outputPath` pekar på en giltig mapp eller skapa den med `Directory.CreateDirectory` |

## Sammanfattning

Denna handledning demonstrerade hur man **skapar streckkod PNG**‑filer i C# med PDF417‑symboliken. Du har lärt dig:

- **Hur man genererar streckkod** med klassen `BarcodeGenerator`  
- **Hur man ändrar rader** och kolumner för att styra layouten  
- **Hur man konfigurerar streckkod**‑inställningar såsom modulstorlek och bildformat  
- Hur man **genererar PDF417 streckkod** och sparar den som en PNG‑bild

Du har nu ett återanvändbart kodblock som du kan anpassa för olika data‑payloads, bildformat eller layoutkrav.

## Nästa steg

- Experimentera med `Pdf417.ErrorCorrectionLevel` för att förbättra läsbarheten vid lågkvalitetsutskrifter.  
- Kombinera flera streckkoder i en enda PDF med Aspose.PDF för batch‑etikettgenerering.  
- Utforska andra symboliker (`EncodeTypes.Code128`, `EncodeTypes.QR`) genom att byta enum‑värde—detta matchar det sekundära nyckelordet **generate pdf417 barcode** samtidigt som du visar bredare möjligheter.

Lycka till med kodandet, och njut av att skapa skarpa streckkod PNG‑filer för alla applikationer!


## Vad bör du lära dig härnäst?


Följande handledningar täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar PDF417‑streckkod och exporterar PNG i C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/)
- [Hur man genererar PDF417‑streckkoder i C# med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [Hur man skapar streckkod PNG med anpassat bildförhållande i C#](/barcode/english/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}