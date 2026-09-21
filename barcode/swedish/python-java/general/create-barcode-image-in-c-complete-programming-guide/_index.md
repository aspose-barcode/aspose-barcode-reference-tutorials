---
category: general
date: 2026-08-09
description: Skapa streckkodbild i C# med den här steg‑för‑steg‑guiden. Lär dig hur
  du genererar streckkod, justerar streckkodens höjd i pixlar och skapar flera streckkoder
  effektivt.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create multiple barcodes
- barcode height pixels
language: sv
lastmod: 2026-08-09
og_description: Skapa streckkodbild i C# snabbt. Följ den här handledningen för att
  lära dig hur du genererar streckkod, ställer in streckkodens höjd i pixlar och skapar
  flera streckkoder.
og_image_alt: Screenshot of barcode images generated with C# code showing different
  heights
og_title: Skapa streckkodbild i C# – fullständig guide för utvecklare
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  headline: Create barcode image in C# – complete programming guide
  type: TechArticle
- description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  name: Create barcode image in C# – complete programming guide
  steps:
  - name: Define the output folder
    text: Choose a folder where the generated PNG files will be stored. Using an absolute
      path avoids permission surprises.
  - name: Instantiate the barcode generator
    text: For a DataBar Omnidirectional barcode, pass `EncodeTypes.DatabarOmniDirectional`
      and the GS1‑128 data string.
  - name: Set common barcode parameters
    text: The most common visual tweaks are the X‑dimension (module width) and the
      bar height. Both are expressed in pixels.
  - name: Save the first barcode image
    text: '```csharp // Step 4: Save the barcode image with a 30 px height string
      file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"); barcode.Save(file30,
      BarCodeImageFormat.Png); ```'
  - name: Adjust the barcode height pixels
    text: Changing the height does not require a new `BarcodeGenerator` instance—just
      modify the parameter.
  - name: Save the second barcode image
    text: '```csharp // Step 6: Save the barcode image with the new 60 px height string
      file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"); barcode.Save(file60,
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'After running the full sample, the `Barcodes` folder contains:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Skapa streckkodbild i C# – komplett programmeringsguide
url: /sv/python-java/general/create-barcode-image-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa streckkodbild i C# – komplett programmeringsguide

Om du behöver **create barcode image** i en .NET-applikation, visar den här guiden exakt **how to generate barcode** med hjälp av Aspose.BarCode-biblioteket. Du kommer att se hur du styr **barcode height pixels**, sparar bilden och skapar **multiple barcodes** utan att duplicera kod.

Handledningen täcker allt från installation av paketet till anpassning av dimensioner, så att du kan copy‑paste ett färdigt exempel som kan köras direkt in i ditt projekt idag.

## Förutsättningar

* .NET 6.0 SDK eller senare installerat  
* Visual Studio 2022 (eller någon C# IDE)  
* NuGet‑paketet `Aspose.BarCode` – installera med  

```bash
dotnet add package Aspose.BarCode
```

Inga ytterligare beroenden krävs.

## Så här genererar du streckkodbild med BarcodeGenerator C#

Kärnklassen för att skapa en streckkodbild är `BarcodeGenerator`. Den kapslar in kodningstypen, datasträngen och alla renderingsparametrar.

### Steg 1: Definiera utdatamappen

Välj en mapp där de genererade PNG‑filerna ska lagras. Att använda en absolut sökväg undviker behörighetsöverraskningar.

```csharp
// Step 1: Define the output folder
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputFolder);
```

> **Varför?** Att skapa mappen programatiskt garanterar att de efterföljande `Save`‑anropen lyckas även på en ny maskin.

### Steg 2: Instansiera streckkodsgeneratorn

För en DataBar Omnidirectional‑streckkod, skicka `EncodeTypes.DatabarOmniDirectional` och GS1‑128‑datasträngen.

```csharp
// Step 2: Create a DataBar Omnidirectional barcode generator with the data to encode
var barcode = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

> **Obs:** `BarcodeGenerator`‑objektet är återanvändbart; du kan ändra dess parametrar mellan sparningar för att **create multiple barcodes** från samma data.

### Steg 3: Ställ in vanliga streckkodparametrar

De vanligaste visuella justeringarna är X‑dimensionen (modulbredd) och stapelhöjden. Båda uttrycks i pixlar.

```csharp
// Step 3: Set common barcode parameters (X‑dimension and initial height)
barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin modules for sharper output
barcode.Parameters.Barcode.BarHeight.Pixels = 30;  // initial height – 30 px
```

> **Varför sätta X‑dimension?** En mindre X‑dimension ger högre upplösning, vilket är viktigt när bilden ska skrivas ut eller visas på hög‑DPI‑skärmar.

### Steg 4: Spara den första streckkodbilden

```csharp
// Step 4: Save the barcode image with a 30 px height
string file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png");
barcode.Save(file30, BarCodeImageFormat.Png);
```

Filen `DatabarBarHeight30Pixels.png` innehåller nu en 30‑pixel‑hög DataBar Omnidirectional‑streckkod.

### Steg 5: Justera streckkodens höjd i pixlar

Att ändra höjden kräver ingen ny `BarcodeGenerator`‑instans – ändra bara parametern.

```csharp
// Step 5: Change the bar height to 60 px for the same barcode
barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

### Steg 6: Spara den andra streckkodbilden

```csharp
// Step 6: Save the barcode image with the new 60 px height
string file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png");
barcode.Save(file60, BarCodeImageFormat.Png);
```

Nu har du två PNG‑filer med olika **barcode height pixels**, vilket visar hur enkelt det är att **create barcode image**‑varianter.

## Ställa in streckkodens höjd i pixlar dynamiskt

Ofta behöver du en serie streckkoder med höjder som matchar UI‑element eller utskrivna etiketter. Följande hjälpfunktion abstraherar höjdändringen:

```csharp
/// <summary>
/// Saves a barcode image with a custom height.
/// </summary>
/// <param name="generator">Configured BarcodeGenerator instance.</param>
/// <param name="heightPx">Desired bar height in pixels.</param>
/// <param name="fileName">Target file name (including path).</param>
void SaveBarcodeWithHeight(BarcodeGenerator generator, int heightPx, string fileName)
{
    generator.Parameters.Barcode.BarHeight.Pixels = heightPx;
    generator.Save(fileName, BarCodeImageFormat.Png);
}
```

Du kan nu anropa `SaveBarcodeWithHeight(barcode, 45, "BarHeight45.png");` för att **create barcode image** med en 45‑pixel hög höjd i ett enda anrop.

## Skapa flera streckkoder i en loop

När du har en samling produktidentifierare eliminerar en `foreach`‑loop repetitiv kod. Detta exempel visar hur du **create multiple barcodes** från en array av GTIN‑värden.

```csharp
string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
int[] heights = { 30, 45, 60 }; // different heights for visual variety

for (int i = 0; i < gtins.Length; i++)
{
    // Encode each GTIN as a DataBar Omnidirectional barcode
    var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                   $"(01){gtins[i]}");

    // Reuse the X‑dimension setting for consistency
    gen.Parameters.Barcode.XDimension.Pixels = 2;

    // Choose a height from the heights array (or calculate dynamically)
    int height = heights[i % heights.Length];
    string filePath = Path.Combine(outputFolder,
        $"Databar_{gtins[i]}_Height{height}px.png");

    SaveBarcodeWithHeight(gen, height, filePath);
}
```

Loopen producerar tre PNG‑filer, var och en med ett distinkt **barcode height pixels**‑värde. Eftersom `SaveBarcodeWithHeight`‑hjälpen kapslar in höjdändringen, förblir huvudloopen ren och fokuserad på data.

### Förväntad output

Efter att ha kört hela exemplet innehåller `Barcodes`‑mappen:

```
DatabarBarHeight30Pixels.png
DatabarBarHeight60Pixels.png
Databar_01234567890123_Height30px.png
Databar_09876543210987_Height45px.png
Databar_12345098765432_Height60px.png
```

Att öppna någon PNG visar en skarp DataBar Omnidirectional‑streckkod som kan skannas av vanliga mobilappar.

## Vanliga fallgropar och proffstips

| Problem | Varför det händer | Hur du undviker det |
|---------|-------------------|----------------------|
| **Fel EncodeTypes** | Att använda en 1D‑typ för en DataBar ger en oläslig bild. | Välj alltid `EncodeTypes.DatabarOmniDirectional` (eller en annan DataBar‑variant) för GS1‑128‑payloads. |
| **Otillräcklig X‑dimension** | Mycket låg X‑dimension kan göra tunna staplar osynliga på lågupplösta bildskärmar. | Behåll `XDimension.Pixels` ≥ 2 för skärmvisning; öka till 3‑4 för utskrift. |
| **Fel i filsökväg** | Relativa sökvägar kan lösas till oväntade kataloger. | Använd `Path.Combine` och `Environment.CurrentDirectory` för att bygga absoluta sökvägar. |
| **Överskriva bilder** | Att återanvända samma filnamn i en loop skriver över tidigare resultat. | Inkludera unika identifierare (t.ex. GTIN eller tidsstämpel) i filnamnet. |
| **Saknat NuGet‑paket** | Koden kompileras men kastar `FileNotFoundException` vid körning. | Verifiera att `Aspose.BarCode` är installerat och att projektet refererar till det. |

## Fullt fungerande exempel

Nedan är det kompletta programmet som du kan kopiera in i en konsolapplikation. Det inkluderar alla steg, hjälpfunktioner och felhantering.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Prepare output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // ---------- Single barcode with two heights ----------
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        barcode.Parameters.Barcode.XDimension.Pixels = 2;
        barcode.Parameters.Barcode.BarHeight.Pixels = 30;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);

        // ---------- Helper for dynamic heights ----------
        void SaveBarcodeWithHeight(BarcodeGenerator gen, int heightPx, string fileName)
        {
            gen.Parameters.Barcode.BarHeight.Pixels = heightPx;
            gen.Save(fileName, BarCodeImageFormat.Png);
        }

        // ---------- Multiple barcodes ----------
        string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
        int[] heights = { 30, 45, 60 };

        for (int i = 0; i < gtins.Length; i++)
        {
            var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                           $"(01){gtins[i]}");
            gen.Parameters.Barcode.XDimension.Pixels = 2;

            int height = heights[i % heights.Length];
            string filePath = Path.Combine(outputFolder,
                $"Databar_{gtins[i]}_Height{height}px.png");

            SaveBarcodeWithHeight(gen, height, filePath);
        }

        Console.WriteLine($"Barcode images created in: {outputFolder}");
    }
}
```

Att köra detta program

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Skapa streckkod med anpassad höjd – Endimensionella streckkoder](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Skapa streckkodbild C# – GS1 DataMatrix‑exempel](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Skapa DotCode‑streckkodbild – rader & kolumner (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}