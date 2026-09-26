---
category: general
date: 2026-09-26
description: Lär dig hur du skapar streckkod i C# med Aspose.BarCode. Denna steg‑för‑steg‑guide
  innehåller ett exempel på en streckkodsgenerator och visar hur du justerar stapelhöjden.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode c#
- barcode generator example
- how to adjust bar height
- change barcode height
- generate barcode aspose
language: sv
lastmod: 2026-09-26
og_description: Skapa streckkod i C# med Aspose.BarCode. Följ den här guiden för att
  generera en streckkod, justera stapelhöjden och spara PNG‑bilder.
og_image_alt: Diagram illustrating how to create barcode in C# using Aspose.BarCode
og_title: Skapa streckkod i C# med Aspose.BarCode – fullständig guide
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  headline: How to create barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  name: How to create barcode in C# with Aspose.BarCode
  steps:
  - name: Import required namespaces
    text: '```csharp using System; using Aspose.BarCode.Generation; using Aspose.BarCode;
      ```'
  - name: Initialise the barcode generator
    text: We’ll generate a **Databar Omni‑Directional** symbol that encodes a GTIN‑14
      value. The constructor takes the symbology and the raw data string.
  - name: Set common barcode parameters
    text: 'Two visual parameters are most often tweaked: the X‑dimension (the narrow
      bar width) and the overall bar height.'
  - name: Save the first image (30‑pixel height)
    text: '```csharp // Save the barcode as a 30‑pixel‑high PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: Change the bar height to 60 pixels
    text: Now we demonstrate **how to adjust bar height** at runtime. The same `generator`
      instance is reused; only the `BarHeight` property changes.
  - name: Full source code
    text: 'Putting everything together yields a concise, runnable program:'
  - name: Switching to a different symbology
    text: 'If you need a QR code instead of a Databar, replace the `EncodeTypes` value:'
  - name: Using `BarHeight` in millimetres
    text: 'Aspose.BarCode also supports physical units. To set a height of 10 mm:'
  - name: Handling errors
    text: 'If the data string does not conform to the selected symbology, `BarcodeGenerator`
      throws an `ArgumentException`. Wrap the generation logic in a try‑catch block
      to provide a friendly message:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Hur man skapar streckkod i C# med Aspose.BarCode
url: /sv/python-java/general/how-to-create-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar streckkod i C# med Aspose.BarCode  

Om du snabbt behöver **create barcode c#**-projekt, erbjuder Aspose.BarCode ett smidigt API som hanterar det tunga arbetet. I den här handledningen kommer du att se ett komplett **barcode generator example**, lära dig **how to adjust bar height**, och exportera resultatet som PNG-filer.  

Oavsett om du bygger ett detaljhandelskassasystem, genererar lageretiketter eller automatiserar fraktetiketter, är förmågan att programatiskt ändra den visuella storleken på en streckkod avgörande. Denna guide förutsätter att du har en grundläggande förståelse för C# och en utvecklingsmiljö som Visual Studio 2022.  

## Förutsättningar  

Innan du börjar, se till att du har:  

* .NET 6.0 SDK eller senare installerat.  
* Visual Studio 2022 (eller någon C#-IDE).  
* En aktiv Aspose.BarCode-licens (gratisprovperioden fungerar för lärande).  

Du måste också lägga till Aspose.BarCode NuGet-paketet i ditt projekt:

```bash
dotnet add package Aspose.BarCode
```

> **Proffstips:** Om du planerar att generera många streckkoder i en loop, återanvänd en enda `BarcodeGenerator`-instans och ändra bara de parametrar som förändras. Detta minskar minnesallokeringar och förbättrar prestandan.

## Hur man skapar streckkod i C# med Aspose.BarCode  

Följande avsnitt går igenom varje steg i **barcode generator example**. Koden är självständig; kopiera den till en ny konsolapplikation och kör den.

### Steg 1: Importera nödvändiga namnrymder  

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Dessa namnrymder ger dig åtkomst till klassen `BarcodeGenerator` och uppräkningen `EncodeTypes`.

### Steg 2: Initiera streckkodsgeneratorn  

Vi kommer att generera en **Databar Omni‑Directional**-symbol som kodar ett GTIN‑14‑värde. Konstruktorn tar symbologin och den råa datatsträngen.

```csharp
// Initialise a generator for Databar Omni‑Directional
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

`EncodeTypes.DatabarOmniDirectional`-värdet talar om för Aspose.BarCode vilken streckkodstandard som ska användas. Datatsträngen följer GS1 Application Identifier-formatet, vilket är vanligt för detaljhandelsstreckkoder.

### Steg 3: Ställ in vanliga streckkodparametrar  

Två visuella parametrar justeras oftast: X‑dimensionen (den smala stapelbredden) och den totala stapelhöjden.  

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set the initial bar height to 30 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**X‑dimension** styr streckkodens densitet, medan **BarHeight** bestämmer den vertikala storleken på varje stapel. Att justera **BarHeight** är exakt vad du behöver när du vill **change barcode height** för olika tryckmedia.

### Steg 4: Spara den första bilden (30‑pixel hög)  

```csharp
// Save the barcode as a 30‑pixel‑high PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

`Save`‑metoden skriver den renderade bilden till disk. Filnamnet visar tydligt den använda höjden, vilket underlättar när du jämför olika resultat.

### Steg 5: Ändra stapelhöjden till 60 pixlar  

Nu demonstrerar vi **how to adjust bar height** vid körning. Samma `generator`‑instans återanvänds; endast egenskapen `BarHeight` ändras.

```csharp
// Increase the bar height to 60 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the larger barcode
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Eftersom generatorn behåller alla andra inställningar (symbologi, data, X‑dimension) är den enda visuella skillnaden mellan de två PNG-filerna den vertikala storleken på staplarna.

### Fullständig källkod  

När allt sätts ihop får du ett koncist, körbart program:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for Databar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Configure visual parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // narrow bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // first height

            // 3️⃣ Save the 30‑pixel‑high image
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30‑pixel barcode.");

            // 4️⃣ Change the bar height to 60 pixels (how to adjust bar height)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 5️⃣ Save the 60‑pixel‑high image
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60‑pixel barcode.");

            // Optional: clean up resources
            generator.Dispose();
        }
    }
}
```

**Förväntat resultat**  

När programmet körs skapas två PNG-filer i den körbara filens arbetskatalog:

* `DatabarBarHeight30Pixels.png` – en streckkod med 30 px stapelhöjd.  
* `DatabarBarHeight60Pixels.png` – samma streckkod, men varje stapel är dubbelt så hög.

Öppna bilderna i en valfri visare; du kommer att se att det övergripande mönstret förblir identiskt medan den vertikala dimensionen förändras, vilket bekräftar att **change barcode height**‑operationen lyckades.

## Avancerade varianter  

### Byta till en annan symbologi  

Om du behöver en QR‑kod istället för en Databar, ersätt `EncodeTypes`‑värdet:

```csharp
generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

Alla andra parameterinställningar (X‑dimension, BarHeight) gäller fortfarande där de är meningsfulla.

### Använda `BarHeight` i millimeter  

Aspose.BarCode stöder också fysiska enheter. För att sätta en höjd på 10 mm:

```csharp
generator.Parameters.Barcode.BarHeight.Millimeters = 10;
```

Detta är praktiskt när du genererar streckkoder för utskriftslayouter som kräver exakta mått.

### Hantera fel  

Om datatsträngen inte följer den valda symbologin kastar `BarcodeGenerator` ett `ArgumentException`. Omslut genereringslogiken i ett try‑catch‑block för att ge ett vänligt meddelande:

```csharp
try
{
    generator.Save("output.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode data: {ex.Message}");
}
```

## Vanliga frågor besvarade  

* **Påverkar ändring av BarHeight läsbarheten?**  
  Streckkoden förblir läsbar så länge X‑dimensionen och den totala tysta zonen uppfyller symbologins specifikationer. Att öka höjden gör bara staplarna längre; den minskar aldrig kontrasten.

* **Kan jag sätta olika höjder för enskilda staplar?**  
  Nej. `BarHeight`‑egenskapen tillämpas jämnt på hela symbolen. För design med variabel höjd skulle du behöva en anpassad renderingsrutin utanför Aspose.BarCode:s räckvidd.

* **Är PNG det bästa formatet för utskrift?**  
  PNG bevarar förlustfri pixeldata, vilket gör det idealiskt för skärmvisning. För högupplösta utskriftsjobb, överväg `BarCodeImageFormat.Tiff` eller `Pdf` för att behålla vektorinformation.

## Slutsats  

Du vet nu hur du **create barcode c#**-applikationer med Aspose.BarCode, har sett ett komplett **barcode generator example**, och förstår **how to adjust bar height** för att möta olika layoutkrav. Genom att återanvända samma generatorinstans och bara ändra `BarHeight` kan du effektivt **change barcode height** utan att bygga om hela objektet.

Från här kan du utforska:

* Generera andra symbologier (`EncodeTypes.Code128`, `EncodeTypes.EAN13`).  
* Exportera till SVG eller PDF för skalbara grafik.  
* Bädda in streckkoder direkt i Word- eller Excel-dokument med Aspose.Words eller Aspose.Cells.

Lycka till med kodningen, och njut av den flexibilitet som Aspose.BarCode ger dina C#-streckkodprojekt!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Hur man genererar och justerar streckkodshöjd för endimensionell Databar med Aspose.BarCode för .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Hur man skapar en streckkod PNG-fil med justerbar höjd i C#](/barcode/english/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/)
- [Hur man genererar streckkod i C# – Komplett Aspose.BarCode-guide](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}