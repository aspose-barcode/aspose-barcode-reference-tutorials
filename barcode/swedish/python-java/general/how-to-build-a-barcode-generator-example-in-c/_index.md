---
category: general
date: 2026-09-19
description: Exempel på streckkodsgenerator som visar hur man ändrar höjd, skapar
  DataBar Omni‑Directional och justerar streckkodens dimensioner för C#‑bildutmatning.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to change height
- how to create databar
- adjust barcode dimensions
- create barcode image c#
language: sv
lastmod: 2026-09-19
og_description: exempel på streckkodsgenerator som visar hur man ändrar höjd, skapar
  DataBar Omni‑Directional och justerar streckkodens dimensioner för en C# PNG‑bild
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode generated in C#
og_title: Exempel på streckkodsgenerator i C# – steg‑för‑steg guide
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example showing how to change height, create DataBar
    Omni‑Directional, and adjust barcode dimensions for C# image output
  headline: How to build a barcode generator example in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Hur man bygger ett exempel på en streckkodsgenerator i C#
url: /sv/python-java/general/how-to-build-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator‑exempel i C# – komplett programmeringsguide

Om du behöver ett **barcode generator‑exempel** för ett .NET‑projekt visar den här guiden exakt hur du skapar, konfigurerar och sparar en DataBar Omni‑Directional‑streckkod med C#. Du lär dig hur du ändrar höjd, justerar streckkodens dimensioner och sparar en högkvalitativ PNG‑bild – allt i en enda körbar konsolapplikation.

Stegen nedan täcker allt från installation av nödvändigt SDK till finjustering av X‑dimension och stapelhöjd. När du är klar har du en färdig streckkodsgenerator som du kan integrera i fakturering, lagerhantering eller någon annan skanningsprocess.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare installerat  
* Visual Studio 2022 (eller någon IDE som stödjer .NET)  
* En aktiv licens för **Aspose.BarCode for .NET** (gratis provversion fungerar för test)  

Om du föredrar ett annat bibliotek är koncepten för att justera dimensioner och spara bilden desamma; byt bara ut API‑anropen enligt det bibliotek du använder.

## Steg 1: Skapa projektet och lägg till Aspose.BarCode‑paketet

Skapa ett nytt konsolprojekt och referera streckkodsbiblioteket.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Kommandot `dotnet add package` hämtar den senaste stabila versionen av Aspose.BarCode, som innehåller fullt stöd för DataBar Omni‑Directional‑symboler.

## Steg 2: Skriv det kompletta barcode generator‑exemplet

Öppna **Program.cs** och ersätt innehållet med följande kod. Detta block innehåller hela **barcode generator‑exemplet** – inga saknade delar.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a DataBar Omni‑Directional symbol
            // The GTIN‑14 value "(01)12345678901231" is encoded as a numeric string.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Adjust barcode dimensions
            // Set the X‑dimension (module width) to 2 pixels – this controls the thin bar width.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ How to change height
            // Set the bar height to 30 pixels. Height influences readability on larger scanners.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Optional: fine‑tune additional properties (quiet zone, color, etc.)
            generator.Parameters.Barcode.QrCodeErrorLevel = QRErrorLevel.LevelM; // example property
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // 5️⃣ Create barcode image C#
            // Save the generated barcode as a PNG file in the output folder.
            string outputPath = "DatabarOmniDirectional.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Varför varje rad är viktig

* **Create a barcode generator** – `BarcodeGenerator`‑konstruktorn kopplar kodningstypen (`EncodeTypes.DatabarOmniDirectional`) till den data du vill bädda in. Detta är kärnan i **how to create databar**‑steget.  
* **Adjust barcode dimensions** – `XDimension.Pixels`‑egenskapen definierar bredden på den smalaste stapeln. Att ändra detta värde påverkar den totala storleken och skanningspålitligheten.  
* **How to change height** – `BarHeight.Pixels`‑egenskapen styr den vertikala storleken. En högre stapelhöjd förbättrar läsbarheten för handhållna skannrar, medan en lägre höjd sparar utrymme på små etiketter.  
* **Optional tweaks** – Att sätta förgrund‑/bakgrundsfärger eller felkorrigeringsnivåer är valfritt men visar hur du kan utöka konceptet **adjust barcode dimensions**.  
* **Create barcode image C#** – `Save`‑metoden skriver streckkoden till disk. Genom att använda `BarCodeImageFormat.Png` säkerställs förlustfri komprimering, vilket är idealiskt för de flesta tillämpningar.

## Steg 3: Bygg och kör exemplet

Kompilera och kör programmet:

```bash
dotnet run
```

Du bör se konsolutdata:

```
Barcode saved to DatabarOmniDirectional.png
```

En fil med namnet **DatabarOmniDirectional.png** skapas i projektmappen. När du öppnar bilden ser du en skarp DataBar Omni‑Directional‑streckkod redo för skanning.

## Hur du ändrar höjd i efterhand

Om du behöver generera streckkoder med varierande höjder, omge höjdtilldelningen med en metod:

```csharp
static void SetBarHeight(BarcodeGenerator gen, int heightPixels)
{
    gen.Parameters.Barcode.BarHeight.Pixels = heightPixels;
}
```

Anropa `SetBarHeight(generator, 45);` före `Save`. Detta tillvägagångssätt låter dig **how to change height** dynamiskt baserat på användarinmatning eller konfigurationsfiler.

## Hur du skapar DataBar Omni‑Directional‑streckkoder med olika data

DataBar Omni‑Directional‑symbolen stödjer GTIN‑14, GTIN‑13 och andra numeriska identifierare. För att koda ett annat värde, ersätt helt enkelt strängen i konstruktorn:

```csharp
new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)98765432109876");
```

Kom ihåg att hålla datan numerisk och korrekt formaterad; annars kastar generatorn ett `BarcodeException`.

## Justera streckkodens dimensioner för olika utskriftsscenarier

Olika skrivare och etikettstorlekar kräver olika X‑dimensioner och höjder. Använd tabellen nedan som en snabb referens:

| Scenario                     | X‑Dimension (pixels) | Stapelhöjd (pixels) |
|------------------------------|----------------------|---------------------|
| Liten etikett (25 mm × 15 mm) | 1                    | 20                  |
| Medelstora etikett (50 mm × 30 mm) | 2                    | 30                  |
| Stor etikett (100 mm × 50 mm) | 3                    | 45                  |

Applicera dessa värden genom att sätta `generator.Parameters.Barcode.XDimension.Pixels` och `BarHeight.Pixels` enligt tabellen.

## Proffstips: validera den genererade streckkoden

Innan du skickar en etikett kan du programatiskt verifiera dess läsbarhet:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.DatabarOmniDirectional);
if (reader.Read())
{
    Console.WriteLine("Validation succeeded: " + reader.GetCodeText());
}
else
{
    Console.WriteLine("Validation failed – barcode may be unreadable.");
}
```

Detta kodsnutt demonstrerar en snabb **adjust barcode dimensions**‑sanity‑check, så att streckkoden uppfyller skanningskraven.

## Vanliga fallgropar och hur du undviker dem

| Fallgrop                              | Varför det händer                              | Åtgärd                                                                 |
|---------------------------------------|-----------------------------------------------|-----------------------------------------------------------------------|
| Använder icke‑numerisk data för DataBar | DataBar förväntar sig numeriska GTIN‑format    | Säkerställ att strängen matchar mönstret `(01)XXXXXXXXXXXXX`.        |
| Sätter X‑dimension till 0 eller negativ | Biblioteket kastar `ArgumentOutOfRangeException` | Använd minst 1 pixel; testa på målskrivaren först.                  |
| Sparar till en skrivskyddad mapp      | `UnauthorizedAccessException` vid `Save`      | Välj en skrivbar katalog eller kör appen med rätt behörigheter.     |
| Glömmer att disponera `BarCodeReader` | Minnesläckage i långlivade tjänster            | Omge läsaren med ett `using`‑block eller anropa `Dispose()` manuellt. |

Att hantera dessa problem tidigt sparar felsökningstid och förbättrar produktionsstabiliteten.

## Fullständig källkodssammanfattning

Nedan är det kompletta, färdiga programmet som implementerar **barcode generator‑exemplet** från början till slut.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create generator – how to create databar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Adjust barcode dimensions
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // how to change height

            // Optional visual tweaks
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // Save image – create barcode image c#
            string filePath = "DatabarOmniDirectional.png";
            generator.Save(filePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {filePath}");

            // Validate barcode (optional)
            using (BarCodeReader reader = new BarCodeReader(filePath, DecodeType.DatabarOmniDirectional))
            {
                if (reader.Read())
                    Console.WriteLine($"Validation succeeded: {reader.GetCodeText()}");
                else
                    Console.WriteLine("Validation failed – barcode may be unreadable.");
            }
        }
    }
}
```

När du kör programmet får du en PNG‑fil som ser ut så här (illustrativt):

![DataBar Omni‑Directional barcode generated in C#](https://example.com/og-image.png "DataBar Omni‑Directional barcode generated in C#")

*Bildens alt‑text*: **DataBar Omni‑Directional barcode generated in C#** (matches `og_image_alt`).

## Slutsats

Du har nu ett **barcode generator‑exempel** som visar hur du ändrar höjd, hur du skapar DataBar Omni‑Directional‑symboler och hur du **adjust barcode dimensions** för optimal skanning. Den kompletta C#‑koden sparar en PNG‑bild, validerar den och kan utökas för massgenerering eller integration i webbtjänster.

Utforska sedan relaterade ämnen som **skapa QR‑koder med Aspose.BarCode**, **batch‑bearbetning av flera streckkodsvärden** eller **bädda in streckkoder i PDF‑dokument**. Alla dessa bygger på samma grunder som behandlas i den här guiden.

Lycka till med kodningen, och må dina streckkoder alltid vara skannbara!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}