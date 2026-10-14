---
category: general
date: 2026-10-02
description: Skapa en poststreckkodsbild i C# med Aspose.BarCode. Lär dig att generera
  Planet- och RM4SCC-streckkoder, anpassa fyllda staplar och spara PNG-filer.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- Aspose.BarCode C#
- postal barcode PNG
- barcode XDimension setting
language: sv
lastmod: 2026-10-02
og_description: Skapa poststreckkodsbild i C# med Aspose.BarCode. Denna handledning
  visar hur du genererar Planet- och RM4SCC-streckkoder, justerar stapelfyllning och
  exporterar PNG-filer.
og_image_alt: Postal barcode image generated with Aspose.BarCode (filled bars)
og_title: Skapa poststreckkodsbild i C# – steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create postal barcode image in C# with Aspose.BarCode. Learn to generate
    Planet and RM4SCC barcodes, customize filled bars, and save PNG files.
  headline: How to create postal barcode image in C# using Aspose.BarCode
  type: TechArticle
- description: Create postal barcode image in C# with Aspose.BarCode. Learn to generate
    Planet and RM4SCC barcodes, customize filled bars, and save PNG files.
  name: How to create postal barcode image in C# using Aspose.BarCode
  steps:
  - name: Why each line matters
    text: '* **`new BarcodeGenerator(EncodeTypes.Planet, "123456")`** – The `EncodeTypes.Planet`
      enum tells Aspose.BarCode to use the *Planet* symbology, which is a standard
      postal barcode in many countries. This is the core of how you **generate planet
      barcode** images. * **`XDimension.Pixels = 4`** – The wid'
  - name: Expected output
    text: 'After running the program, the `YOUR_DIRECTORY` folder contains three PNG
      files:'
  - name: Change image format
    text: If you need a different format (e.g., JPEG for web delivery), replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. Keep in mind that JPEG introduces compression
      artifacts, which can affect scanner performance.
  - name: Adjust image size without scaling
    text: Instead of changing `XDimension`, you can control the overall image dimensions
      via `Parameters.Image.Height` and `Parameters.Image.Width`. This is useful when
      you have a fixed label size.
  - name: Use a different barcode symbology
    text: Aspose.BarCode supports dozens of postal symbologies (e.g., **USPS Intelligent
      Mail**, **Japan Post**). To **generate planet barcode** alternatives, replace
      `EncodeTypes.Planet` with the desired enum value.
  - name: Handling invalid data
    text: Postal barcodes have strict data length rules. If you pass a string that
      does not meet the specification, Aspose.BarCode throws an `ArgumentException`.
      Wrap the generator creation in a `try/catch` block to provide a friendly error
      message.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Hur man skapar en poststreckkodsbild i C# med Aspose.BarCode
url: /sv/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur du skapar en poststreckkodsbild i C# med Aspose.BarCode

Om du behöver **skapa poststreckkodsbild** i C#, erbjuder Aspose.BarCode ett rent API som sköter det tunga arbetet. Oavsett om du bygger ett system för postetiketter eller en adress‑verifieringstjänst, visar den här guiden exakt hur du genererar Planet- och RM4SCC‑streckkoder, växlar mellan fyllda och tomma staplar, och exporterar resultatet som PNG‑filer.

Du kommer att lära dig hur du konfigurerar streckkodens storlek, styr stapelfyllningsbeteendet och sparar bilden till disk — allt i ett enda körbart program. Inga externa verktyg krävs förutom Aspose.BarCode för .NET‑biblioteket.

## Förutsättningar

* .NET 6.0 SDK eller senare (koden fungerar också med .NET Framework 4.7+)
* Visual Studio 2022 eller någon C#‑kompatibel IDE
* En licensierad eller utvärderingskopi av **Aspose.BarCode for .NET** (tillgänglig via NuGet)

```bash
dotnet add package Aspose.BarCode
```

## Översikt av lösningen

Handledningen är indelad i tre logiska steg:

1. **Skapa en Planet‑streckkod med standard (fyllda) staplar** – detta demonstrerar det typiska utseendet för posttjänster.
2. **Skapa en Planet‑streckkod med tomma staplar** – användbart när utskriftsprocessen förväntar sig ofyllda staplar.
3. **Skapa en RM4SCC‑streckkod med fyllda staplar** – ett annat vanligt postformat som används i många länder.

Varje steg följer samma mönster: instansiera `BarcodeGenerator`, sätt `XDimension` (pixelbredden för en enskild stapel), justera eventuellt `FilledBars`, och anropa `Save` för att skriva en PNG‑fil.

---

## Skapa poststreckkodsbild med Aspose.BarCode

Nedan är det kompletta, fristående programmet. Spara det som `Program.cs` och kör det från kommandoraden eller din IDE.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Define the output folder – change this to a writable location on your machine
            string outputDir = @"YOUR_DIRECTORY";

            // -------------------------------------------------
            // Step 1: Generate a Planet barcode with filled bars
            // -------------------------------------------------
            var planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456")
            {
                // XDimension controls the width of a single bar in pixels.
                // A value of 4 gives a good balance between readability and file size.
                Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
            };
            string planetFilledPath = System.IO.Path.Combine(outputDir, "PostalPlanetFilledBars.png");
            planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Filled Planet barcode saved to {planetFilledPath}");

            // -------------------------------------------------
            // Step 2: Generate a Planet barcode with empty bars
            // -------------------------------------------------
            var planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456")
            {
                Parameters = {
                    Barcode = {
                        XDimension = { Pixels = 4 },
                        // Setting FilledBars to false renders the bars as empty outlines.
                        FilledBars = false
                    }
                }
            };
            string planetEmptyPath = System.IO.Path.Combine(outputDir, "PostalPlanetEmptyBars.png");
            planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Empty Planet barcode saved to {planetEmptyPath}");

            // -------------------------------------------------
            // Step 3: Generate an RM4SCC barcode with filled bars
            // -------------------------------------------------
            var rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
            {
                Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
            };
            string rm4sccPath = System.IO.Path.Combine(outputDir, "PostalRM4SCCFilledBars.png");
            rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Filled RM4SCC barcode saved to {rm4sccPath}");

            // End of demo
            Console.WriteLine("All barcode images have been generated successfully.");
        }
    }
}
```

### Varför varje rad är viktig

* **`new BarcodeGenerator(EncodeTypes.Planet, "123456")`** – `EncodeTypes.Planet`‑enumet talar om för Aspose.BarCode att använda *Planet*-symbologin, som är en standardpoststreckkod i många länder. Detta är kärnan i hur du **genererar planet barcode**‑bilder.
* **`XDimension.Pixels = 4`** – Bredden på en enskild stapel påverkar både skanningspålitlighet och visuell storlek. Ett värde på 4 px fungerar bra för de flesta etikettprinterar; du kan öka det för högre upplösning.
* **`FilledBars = false`** – Som standard är staplar fyllda. Att sätta detta till `false` skapar “tom stapel”-stilen som krävs av vissa postningsspecifikationer.
* **`Save(..., BarCodeImageFormat.Png)`** – PNG bevarar förlustfri kvalitet, vilket gör den idealisk för streckkodsbilder som måste läsas av skannrar.

### Förväntat resultat

Efter att ha kört programmet innehåller mappen `YOUR_DIRECTORY` tre PNG‑filer:

| Filnamn                              | Visuell beskrivning                                 |
|--------------------------------------|-----------------------------------------------------|
| `PostalPlanetFilledBars.png`         | Planet‑streckkod med solida svarta staplar           |
| `PostalPlanetEmptyBars.png`          | Planet‑streckkod där staplarna är konturerade (tomma) |
| `PostalRM4SCCFilledBars.png`         | RM4SCC‑streckkod med solida staplar                  |

Du kan öppna någon av dessa bilder i en bildvisare eller bädda in dem direkt i en PDF/HTML‑etikett.

---

## Anpassa streckkoden ytterligare (valfritt)

### Ändra bildformat

Om du behöver ett annat format (t.ex. JPEG för webbdistribution), ersätt `BarCodeImageFormat.Png` med `BarCodeImageFormat.Jpeg`. Tänk på att JPEG introducerar komprimeringsartefakter, vilket kan påverka skannerns prestanda.

### Justera bildstorlek utan skalning

Istället för att ändra `XDimension` kan du kontrollera bildens totala dimensioner via `Parameters.Image.Height` och `Parameters.Image.Width`. Detta är användbart när du har en fast etikettstorlek.

```csharp
planetFilled.Parameters.Image.Height = 150; // pixels
planetFilled.Parameters.Image.Width = 300;  // pixels
```

### Använd en annan streckkodssymbologi

Aspose.BarCode stöder dussintals post‑symbologier (t.ex. **USPS Intelligent Mail**, **Japan Post**). För att **generera planet barcode**‑alternativ, ersätt `EncodeTypes.Planet` med önskat enum‑värde.

```csharp
var uspsBarcode = new BarcodeGenerator(EncodeTypes.USPSIntelligentMail, "123456789012");
```

### Hantera ogiltig data

Poststreckkoder har strikta regler för datalängd. Om du skickar en sträng som inte uppfyller specifikationen kastar Aspose.BarCode ett `ArgumentException`. Omge generatorns skapande med ett `try/catch`‑block för att ge ett vänligt felmeddelande.

```csharp
try
{
    var invalid = new BarcodeGenerator(EncodeTypes.Planet, "ABC");
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode data: {ex.Message}");
}
```

---

## Vanliga fallgropar och pro‑tips

| Fallgrop                                 | Varför det händer                                            | Pro‑tips                                                                                                   |
|------------------------------------------|--------------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
| **Använda en för liten XDimension**      | Staplar blir tunnare än skannarens minsta upplösning, vilket orsakar läsfel. | Börja med `Pixels = 4` och testa på målskrivaren; öka vid behov.                                           |
| **Spara till en skrivskyddad mapp**      | `Save` kastar ett `UnauthorizedAccessException`.            | Se till att `outputDir` pekar på en skrivbar plats, eller använd `Environment.GetFolderPath(Environment.SpecialFolder.Desktop)`. |
| **Försumma att disponera generatorn**    | Stora bilder kan hålla ohanterade resurser.                  | Omge generatorn med ett `using`‑statement eller anropa `Dispose()` efter `Save`.                           |
| **Blanda streckkodformat i en bild**     | Vissa skrivare förväntar sig en enda symbologi per etikett. | Generera varje streckkod separat och sammansätt dem med ett grafikbibliotek om det behövs.                |

---

## Verifiera de genererade streckkoderna

För att bekräfta att streckkoderna är giltiga kan du använda den kostnadsfria **Aspose.BarCode Demo**‑sajten eller någon standardapp för streckkodsläsning. Ladda PNG‑filerna och skanna dem; det avkodade värdet bör vara `123456` för både Planet‑ och RM4SCC‑exemplen.

---

## Slutsats

I den här handledningen lärde du dig hur du **skapar poststreckkodsbild**‑filer i C# med Aspose.BarCode. Du såg hur du **genererar planet barcode**‑bilder med både fyllda och tomma staplar, hur du producerar en RM4SCC‑streckkod, och hur du anpassar storlek, format och felhantering. Med den kompletta, körbara koden kan du nu integrera poststreckkodsgenerering i vilken .NET‑applikation som helst.

**Nästa steg**

* Utforska andra post‑symbologier såsom `EncodeTypes.USPSIntelligentMail` (sekundärt nyckelord: postal barcode PNG).

## Vad bör du lära dig härnäst?

De följande handledningarna täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Skapa poststreckkodsbild i C# – Full steg‑för‑steg‑guide](/barcode/english/python-java/general/create-postal-barcode-image-in-c-full-step-by-step-guide/)
- [Generera poststreckkod i C# – Komplett guide med Planet‑streckkod](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)
- [Hur man genererar poststreckkod i C# med Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}