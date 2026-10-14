---
category: general
date: 2026-10-05
description: barcode‑generatorexempel i C# som visar hur du genererar planet‑streckkod
  och skapar streckkodsbild i C#. Följ den här steg‑för‑steg‑guiden.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- generate planet barcode
- create barcode image c#
language: sv
lastmod: 2026-10-05
og_description: Exempel på streckkodsgenerator i C# guidar dig genom hur du genererar
  planet‑streckkod och skapar en streckkodbild i C#. Få en komplett, körbar lösning.
og_image_alt: Screenshot of a generated Planet barcode image created by a C# barcode
  generator example
og_title: Exempel på streckkodsgenerator i C# – generera Planet-streckkod snabbt
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: barcode generator example in C# that shows you how to generate planet
    barcode and create barcode image c#. Follow this step‑by‑step guide.
  headline: How to build a barcode generator example in C# with Planet symbology
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Hur man bygger ett exempel på en streckkodsgenerator i C# med Planet‑symbologi
url: /sv/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-planet-sy/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode‑generatorexempel i C# – generera Planet‑streckkod och skapa streckkodsbild

Om du behöver ett **barcode‑generatorexempel** i C#, visar den här guiden exakt hur du genererar en Planet‑streckkod och skapar en streckkodsbild i C# med bara några rader kod. Du får se en komplett, färdig‑att‑köra lösning som du kan lägga in i vilket .NET‑projekt som helst.

En Planet‑streckkod används av posttjänster för att koda routningsinformation. I slutet av den här handledningen kommer du att förstå varför biblioteket automatiskt bestämmer streckkodens höjd, hur du styr X‑dimensionen och hur du sparar resultatet som en PNG‑fil. Inga externa verktyg krävs—endast Aspose.BarCode for .NET‑paketet och en .NET‑utvecklingsmiljö.

## Förutsättningar

* .NET 6.0 SDK eller senare installerat  
* Visual Studio 2022 (eller någon IDE som stödjer .NET)  
* **Aspose.BarCode for .NET** NuGet‑paketet (`Aspose.BarCode`)  

Du kan installera paketet från kommandoraden:

```bash
dotnet add package Aspose.BarCode
```

## Steg 1: Initiera streckkodsgeneratorn för Planet‑kodning

Det första steget i varje **barcode‑generatorexempel** är att skapa en `BarcodeGenerator`‑instans och ange kodningstypen. För en Planet‑streckkod använder du `EncodeTypes.Planet` och skickar den datasträng du vill koda.

```csharp
using Aspose.BarCode.Generation;

// Create a Planet barcode generator with the data to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

**Varför detta är viktigt:** `EncodeTypes.Planet`‑enumet talar om för biblioteket att använda Planet‑symbologi, som har ett fast modulmönster som krävs av poststandarder. Att ange data (`"123456"` i detta fall) säkerställer att streckkoden innehåller rätt numeriska routningskod.

## Steg 2: Konfigurera X‑dimensionen (modulbredd) i pixlar

X‑dimensionen styr bredden på varje enskild modul (den minsta stapeln). Att justera den förändrar den totala storleken på streckkoden utan att påverka läsbarheten.

```csharp
// Set the X dimension (module width) to 4 pixels
generator.Parameters.Barcode.XDimension.Pixels = 4;
```

**Varför detta är viktigt:** En större X‑dimension ger en större streckkod, vilket kan vara användbart vid utskrift på stora kuvert. Biblioteket skalar automatiskt höjden för att behålla korrekt bildförhållande för Planet‑streckkoder.

## Steg 3: Spara streckkodsbilden till disk

Till sist sparar du den genererade bilden. Biblioteket bestämmer den optimala höjden, så du behöver bara ange utskrifts‑sökvägen och formatet.

```csharp
using Aspose.BarCode;

// Define the output file path
string outputFile = @"C:\Barcodes\PlanetAutoHeight.png";

// Save the barcode as a PNG image
generator.Save(outputFile, BarCodeImageFormat.Png);
```

**Varför detta är viktigt:** Att spara som PNG bevarar de skarpa kanterna på streckkoden, vilket är avgörande för pålitlig skanning. `Save`‑metoden stödjer även andra format (JPEG, BMP, TIFF) om du behöver ett annat utdataformat.

### Förväntad utdata

Efter att ha kört koden hittar du en fil med namnet **PlanetAutoHeight.png** i `C:\Barcodes`. Bilden kommer att se liknande ut som illustrationen nedan (alt‑text: *barcode‑generatorexempel som visar en Planet‑streckkod*).

![Planet‑streckkod genererad av C#‑exemplet](/images/planet-barcode-example.png){alt="barcode‑generatorexempel som visar en Planet‑streckkod"}

## Steg 4: Valfritt – anpassa förgrunds‑ och bakgrundsfärger

Om din applikation kräver en annan visuell stil kan du ändra streckkodens färger innan du sparar.

```csharp
// Set foreground (bars) to dark blue and background to light gray
generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.LightGray;

// Save the customized image
generator.Save(@"C:\Barcodes\PlanetCustomColors.png", BarCodeImageFormat.Png);
```

**Tips:** Testa alltid den anpassade streckkoden med en riktig scanner för att bekräfta att färgändringar inte påverkar läsbarheten.

## Steg 5: Hantera fel och validering

Aspose.BarCode‑biblioteket kastar `ArgumentException` om data inte uppfyller Planet‑symbologins krav (t.ex. icke‑numeriska tecken). Omge genereringskoden med ett try‑catch‑block för att ge tydlig återkoppling.

```csharp
try
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "ABC123");
    generator.Save(@"C:\Barcodes\InvalidPlanet.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for Planet barcode: {ex.Message}");
}
```

**Varför detta är viktigt:** Planet‑streckkoder accepterar endast numerisk data av specifika längder. Korrekt validering förhindrar körningsfel och sparar tid under integrationstestning.

## Fullt, körbart exempel

Genom att samla alla stegen får du ett självständigt program som du kan kopiera, klistra in och köra.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Initialize the generator with Planet encoding
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Step 2: Set the X dimension (module width) to 4 pixels
        generator.Parameters.Barcode.XDimension.Pixels = 4;

        // Optional: customize colors (comment out if not needed)
        // generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
        // generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.LightGray;

        // Step 3: Save the barcode image
        string outputFile = @"C:\Barcodes\PlanetAutoHeight.png";
        generator.Save(outputFile, BarCodeImageFormat.Png);

        Console.WriteLine($"Planet barcode saved to {outputFile}");
    }
}
```

Kompilera och kör programmet:

```bash
dotnet run
```

Du bör se ett konsolmeddelande som bekräftar filens plats, och PNG‑filen kommer att innehålla den genererade Planet‑streckkoden.

## Vanliga variationer och kantfall

| Variation | Hur man implementerar | När man använder |
|-----------|-----------------------|------------------|
| **Olika datalängd** | Ändra det andra argumentet i `new BarcodeGenerator(EncodeTypes.Planet, "987654321")` | Posttjänster som kräver längre routningsnummer |
| **Högre upplösning** | Sätt `generator.Parameters.ImageResolution = 300;` före `Save` | Utskrift på hög‑dpi‑skrivare |
| **Annat bildformat** | Använd `BarCodeImageFormat.Jpeg` eller `BarCodeImageFormat.Tiff` | När PNG inte är lämpligt för ditt arbetsflöde |
| **Dynamiskt filnamn** | `string outputFile = Path.Combine(folder, $"Planet_{DateTime.Now:yyyyMMdd_HHmmss}.png");` | Batch‑bearbetning av flera streckkoder |

## Pro‑tips för ett robust barcode‑generatorexempel

* **Återanvänd generator‑instansen** när du skapar många streckkoder med samma inställningar; ändra bara `EncodeTypes` eller datasträngen för att förbättra prestandan.  
* **Validera indata** innan du skickar den till `BarcodeGenerator`. Ett enkelt regex som `^\d{6,9}$` säkerställer att data uppfyller Planet‑kraven.  
* **Frigör resurser** om du genererar tusentals bilder i en långvarig tjänst. `BarcodeGenerator` implementerar `IDisposable`, så omslut den i ett `using`‑block när det är lämpligt.  

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, data))
{
    // configure and save...
}
```

## Slutsats

Detta **barcode‑generatorexempel** visar hur man **genererar Planet‑streckkod** och **skapar streckkodsbild i C#** med Aspose.BarCode för .NET. Du har lärt dig hur man initierar generatorn, sätter X‑dimensionen, valfritt anpassar färger, hanterar valideringsfel och sparar resultatet som en PNG‑fil. Med den kompletta källkoden kan du omedelbart integrera Planet‑streckkodsgenerering i vilken C#‑applikation som helst.

Nästa steg kan vara att utforska andra symbologier som QR, Code128 eller DataMatrix—var och en följer samma mönster: skapa en `BarcodeGenerator`, konfigurera parametrar och anropa `Save`. Samma principer gäller, vilket gör det enkelt att utöka dina streckkodsgenereringsmöjligheter över ett brett spektrum av affärsscenarier. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [skapa planet streckkodsbild – steg‑för‑steg‑guide](/barcode/english/python-java/general/create-planet-barcode-image-step-by-step-guide/)
- [Barcode generator C# – skapa Planet‑streckkod och RM4SCC‑exempel](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Skapa streckkodsbild C# med barcode‑generatorexempel](/barcode/english/python-java/general/create-barcode-image-c-with-barcode-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}