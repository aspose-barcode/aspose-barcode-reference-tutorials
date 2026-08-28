---
category: general
date: 2026-08-12
description: Skapa streckkodbild i C# med BarCodeGenerator. Lär dig hur du genererar
  DataBar, styr streckkodens bildstorlek och skapar flera streckkoder effektivt.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- create multiple barcodes
- how to generate databar
- barcode image size
language: sv
lastmod: 2026-08-12
og_description: Skapa streckkodbild i C# med BarCodeGenerator. Denna handledning visar
  steg för steg hur du genererar DataBar‑koder, justerar streckkodens bildstorlek
  och skapar flera streckkoder.
og_image_alt: Screenshot of a generated DataBar barcode image saved as PNG
og_title: Skapa streckkodbild i C# – komplett guide till BarCodeGenerator
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  headline: Create barcode image in C# with BarCodeGenerator
  type: TechArticle
- description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  name: Create barcode image in C# with BarCodeGenerator
  steps:
  - name: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
    text: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
  - name: Adjusting **barcode image size** by changing X‑dimension and bar height.
    text: Adjusting **barcode image size** by changing X‑dimension and bar height.
  - name: Using a loop to **create multiple barcodes** with different heights.
    text: Using a loop to **create multiple barcodes** with different heights.
  - name: Saving the images as PNG files and verifying the output.
    text: Saving the images as PNG files and verifying the output.
  type: HowTo
tags:
- barcode
- csharp
- barcodegenerator
- databar
- image-processing
title: Skapa streckkodbild i C# med BarCodeGenerator
url: /sv/python-java/general/create-barcode-image-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa streckkodbild i C# med BarCodeGenerator

Om du behöver **skapa streckkodbild** i en .NET‑applikation visar den här guiden exakt hur du gör det med `BarCodeGenerator`‑klassen. Oavsett om du bygger ett detaljhandels‑POS‑system eller ett verktyg för lager‑spårning, kommer du att lära dig att generera DataBar‑symboler, kontrollera streckkodens bildstorlek och producera flera streckkoder i ett kör.

Du kommer också att upptäcka hur **barcode generator c#**‑API:t låter dig justera dimensioner, byta utdataformat och hantera kantfall som ogiltiga datasträngar. I slutet av tutorialen kan du självsäkert **skapa flera streckkoder** utan att skriva repetitiv kod.

## Förutsättningar

Innan du börjar, se till att du har:

- .NET 6.0 eller senare installerat  
- En utvecklingsmiljö (Visual Studio, Rider eller VS Code)  
- Aspose.BarCode for .NET NuGet‑paketet (eller något kompatibelt bibliotek som tillhandahåller `BarCodeGenerator`)  

Du kan lägga till paketet med:

```bash
dotnet add package Aspose.BarCode
```

## Vad den här tutorialen täcker

1. Skapa en **barcode generator c#**‑instans för DataBar Omni‑directional‑kodning.  
2. Justera **barcode image size** genom att ändra X‑dimension och stapelhöjd.  
3. Använda en loop för att **create multiple barcodes** med olika höjder.  
4. Spara bilderna som PNG‑filer och verifiera resultatet.  

Alla kodsnuttar är kompletta och redo att kopieras in i ett nytt konsolprojekt.

![Create barcode image example](barcode-example.png){alt="Create barcode image example"}

## Steg 1: Initiera generatorn – grunderna för att skapa streckkodbild

Det första steget är att instansiera `BarCodeGenerator` med önskad symbolik. För en DataBar Omni‑directional‑symbol använder du `EncodeTypes.DatabarOmniDirectional`.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for DataBar Omni‑directional.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarCodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // The rest of the steps are performed below.
        }
    }
}
```

**Varför detta är viktigt:** Att instansiera generatorn definierar kodningsreglerna och datapayloaden. Om du utelämnar rätt `EncodeTypes`‑värde kommer biblioteket att producera en icke‑stödd streckkod eller kasta ett undantag.

## Steg 2: Konfigurera X‑dimension och stapelhöjd – kontrollera streckkodens bildstorlek

Den visuella storleken på en streckkod styrs av två parametrar:

| Parameter | Vad den styr | Typiskt intervall |
|-----------|--------------|-------------------|
| `x_dimension.pixels` | Bredden på den minsta modulen (”punkten”) | 1 – 4 px |
| `bar_height.pixels`  | Höjden på de vertikala staplarna | 30 – 150 px |

```csharp
// Set the module width to 2 px for a crisp, readable image.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set an initial bar height of 30 px.
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**Proffstips:** En mindre X‑dimension ger en högre upplösning men kan bli svårare att skanna på lågkvalitativa skrivare. Justera värdet baserat på den skanningsutrustning du riktar dig mot.

## Steg 3: Spara den första streckkoden – skapa streckkodbild för 30 px höjd

Nu kan du generera bilden och skriva den till disk. `Save`‑metoden accepterar en filsökväg och ett bildformat‑enum.

```csharp
// Save the 30 px high barcode as a PNG file.
string outputFolder = @"C:\Barcodes";
generator.Save($"{outputFolder}\\Databar30.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar30.png (30 px height)");
```

**Förväntat resultat:** En PNG‑fil med namnet `Databar30.png` visas i `C:\Barcodes`. När du öppnar filen ser du en DataBar Omni‑directional‑symbol med ett tydligt, högkontrastmönster.

## Steg 4: Ändra höjden och generera ytterligare bilder – skapa flera streckkoder

För att **create multiple barcodes** med olika dimensioner behöver du bara ändra egenskapen `BarHeight` och anropa `Save` igen. Detta undviker att åter‑instansiera generatorn, vilket sparar minne och CPU‑tid.

```csharp
// Increase the bar height to 60 px for a larger barcode.
generator.Parameters.Barcode.BarHeight.Pixels = 60;
generator.Save($"{outputFolder}\\Databar60.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar60.png (60 px height)");

// You can repeat the process for any height you need.
int[] heights = { 90, 120 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputFolder}\\Databar{h}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved Databar{h}.png ({h} px height)");
}
```

**Varför detta fungerar:** `BarCodeGenerator`‑objektet behåller all konfigurationsstatus. Att ändra en enda egenskap uppdaterar renderingsmotorn för nästa `Save`‑anrop, vilket låter dig **create multiple barcodes** effektivt.

## Steg 5: Avancerat – hur man genererar DataBar med anpassad data

Exemplet ovan använder en statisk GS1‑payload. I verkliga scenarier måste du ofta bädda in variabla produktidentifierare. Biblioteket accepterar vilken sträng som helst som uppfyller DataBar‑specifikationen.

```csharp
string[] gtins = { "01234567890123", "98765432109876", "12345678901234" };
foreach (var gtin in gtins)
{
    // GS1 Application Identifier (01) + GTIN
    generator.CodeText = $"(01){gtin}";
    generator.Parameters.Barcode.BarHeight.Pixels = 50; // uniform height
    generator.Save($"{outputFolder}\\Databar_{gtin}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode for GTIN {gtin}");
}
```

**Viktigt:** Att sätta `generator.CodeText` uppdaterar den kodade datan utan att återskapa objektet. Detta är det rekommenderade **how to generate databar**‑mönstret när du hanterar stora datamängder.

## Steg 6: Verifiera och felsöka – säkerställ korrekt streckkodbildsstorlek

Efter att ha genererat bilderna kan du vilja programatiskt bekräfta att dimensionerna matchar dina förväntningar. `Image`‑klassen från `System.Drawing` kan läsa filen och rapportera dess storlek.

```csharp
using System.Drawing;

// Verify image dimensions
string[] files = { "Databar30.png", "Databar60.png", "Databar90.png" };
foreach (var file in files)
{
    using var img = Image.FromFile($"{outputFolder}\\{file}");
    Console.WriteLine($"{file}: {img.Width}px × {img.Height}px");
}
```

Om höjden inte motsvarar det värde du angav, kontrollera:

- **X‑dimension**: Ett mycket litet värde kan få renderaren att avrunda höjden.  
- **Bildformat**: Vissa format (t.ex. JPEG) applicerar kompression som kan ändra pixeldimensioner vid sparning. PNG bevarar exakta dimensioner.

## Steg 7: Bästa praxis för streckkodbildsstorlek och prestanda

| Rekommendation | Orsak |
|----------------|-------|
| Håll `x_dimension.pixels` mellan 2 – 3 px för de flesta skannrar. | Balans mellan läsbarhet och filstorlek. |
| Använd PNG för förlustfri output när bilden ska skrivas ut. | Garanti för exakta dimensioner och skarpa kanter. |
| Återanvänd en enda `BarCodeGenerator`‑instans när du genererar många streckkoder. | Minskar objektallokeringskostnaden. |
| Validera inmatningssträngen mot GS1‑standarden innan du tilldelar den till `CodeText`. | Förhindrar körningstid‑undantag och ogiltiga skanningar. |
| Spara genererade bilder i en dedikerad mapp med ett tydligt namnschema (t.ex. `Databar_{GTIN}.png`). | Förenklar efterföljande bearbetning och auditspår. |

## Fullt fungerande exempel

Nedan är det kompletta programmet som inkluderar alla steg från initiering till verifiering. Kopiera koden till ett nytt konsolprojekt och kör det.



## Vad du bör lära dig härnäst?

Följande tutorialer täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationssätt i dina egna projekt.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}