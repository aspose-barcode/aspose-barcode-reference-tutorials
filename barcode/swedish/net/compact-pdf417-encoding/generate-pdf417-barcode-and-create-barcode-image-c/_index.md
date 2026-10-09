---
category: general
date: 2026-10-08
description: Generera PDF417‑streckkod i C# och lär dig hur du effektivt genererar
  PDF417‑bilder med Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create barcode image c#
language: sv
lastmod: 2026-10-08
og_description: Generera PDF417‑streckkod i C# med en steg‑för‑steg‑guide. Lär dig
  hur du genererar PDF417 och sparar streckkodsbilden som PNG.
og_image_alt: Generated PDF417 barcode saved as a PNG image
og_title: Generera PDF417‑streckkod och skapa streckkodsbild i C#
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Generate PDF417 barcode in C# and learn how to generate PDF417 images
    efficiently with Aspose.BarCode.
  headline: Generate PDF417 barcode and create barcode image C#
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Generera PDF417‑streckkod och skapa streckkodbild C#
url: /sv/net/compact-pdf417-encoding/generate-pdf417-barcode-and-create-barcode-image-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera PDF417-streckkod och skapa streckkodsbild C#

Om du behöver **generera PDF417-streckkod** i en .NET-applikation visar den här handledningen exakt hur du gör det. Du får se ett komplett, körbart exempel som skapar en streckkod, anpassar dess layout och sparar resultatet som en PNG-bild.

Att generera en PDF417-streckkod är ett vanligt krav för fraktetiketter, boardingkort och lagersystem. I slutet av den här guiden kommer du att kunna **generera PDF417** med finjusterad kontroll över storlek och layout, och du kommer också att lära dig hur du **skapar streckkodsbild C#**‑filer som kan visas i ett UI eller skickas till en skrivare.

## Förutsättningar

- .NET 6.0 eller senare (koden fungerar också med .NET Framework 4.7.2+)
- Visual Studio 2022 eller någon C#‑kompatibel IDE
- Aspose.BarCode för .NET (gratis provversion eller licensierad version)  
  Installera den via NuGet:

```bash
dotnet add package Aspose.BarCode
```

Ingen ytterligare konfiguration krävs; biblioteket hanterar PNG‑kodning internt.

## Steg 1: Ställ in projektet och importera namnrymder

Skapa ett nytt konsolprojekt och lägg till de nödvändiga `using`‑direktiven. Detta block innehåller allt du behöver för att kompilera exemplet.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // All barcode generation code lives here
        }
    }
}
```

*Varför detta steg är viktigt*: Att importera namnrymden `Aspose.BarCode.Generation` ger dig åtkomst till `BarcodeGenerator`, `EncodeTypes` och parameterobjekten som används för att anpassa streckkoden.

## Steg 2: Generera PDF417-streckkod med önskad text

Inuti `Main`, skapa en instans av `BarcodeGenerator` med `EncodeTypes.Pdf417`. Konstruktorn tar streckkodstypen och den text du vill koda.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo");
```

*Förklaring*: `EncodeTypes.Pdf417` instruerar biblioteket att producera en PDF417‑symbologi. Strängen `"Layout demo"` blir data‑payloaden som kodas i streckkoden.

## Steg 3: Finjustera streckkodens storlek med X‑dimension

X‑dimensionen styr bredden på en enskild modul (den minsta svarta/vita kvadraten). Att ange den i pixlar ger exakt kontroll över den slutliga bildstorleken.

```csharp
// Step 3: Define the module (X) dimension in pixels for finer control over barcode size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Varför detta är viktigt*: En mindre X‑dimension ger en mer kompakt streckkod, vilket är användbart när du har begränsat utrymme på en etikett eller UI‑element.

## Steg 4: Anpassa PDF417‑layouten (kolumner och rader)

PDF417 låter dig ange antalet kolumner och rader. Att justera dessa värden förändrar streckkodens bildförhållande.

```csharp
// Step 4: Set the layout – 4 columns and 9 rows for this example
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;
```

*Förklaring*: Med 4 kolumner och 9 rader blir streckkoden högre än den är bred, vilket matchar många biljettskrivningsformat.

## Steg 5: Spara den genererade streckkoden som en PNG‑bild

Slutligen skriv streckkoden till en fil. Enum‑värdet `BarCodeImageFormat.Png` säkerställer förlustfri komprimering.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY\LayoutPdf417.png";
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

*Vad som händer här*: `Save` skapar bildfilen på disken. Du kan ersätta `BarCodeImageFormat.Png` med `Jpeg` eller `Bmp` om ett annat format krävs.

### Fullständigt exempel i ett block

Nedan är det kompletta, färdiga programmet. Ersätt `YOUR_DIRECTORY` med en faktisk mappväg på din maskin.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a PDF417 barcode generator with the desired text
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo");

            // Define the module (X) dimension in pixels for finer control over barcode size
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set the layout – 4 columns and 9 rows for this example
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
            barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;

            // Save the generated barcode as a PNG image
            string outputPath = @"YOUR_DIRECTORY\LayoutPdf417.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Kör programmet (`dotnet run`) och öppna den resulterande `LayoutPdf417.png`. Du bör se en ren PDF417‑streckkod som kodar texten *Layout demo*.

![Exempel på genererad PDF417-streckkod](image-placeholder.png){: .responsive-img alt="Genererad PDF417-streckkod sparad som PNG"}

*Förväntat resultat*: En PNG‑fil på ungefär 150 × 300 pixlar (storleken varierar med X‑dimensionen) som innehåller en skannbar PDF417‑streckkod.

## Vanliga variationer och kantfall

| Scenario | Så anpassar du koden |
|----------|----------------------|
| **Olika data payload** | Ändra det andra argumentet till `BarcodeGenerator` (`"Layout demo"` → valfri sträng, upp till 1 800 tecken). |
| **Högre upplösning** | Öka `XDimension.Pixels` (t.ex. `4`) eller sätt `Resolution` via `barcodeGenerator.Parameters.ImageResolution.Dpi = 300;`. |
| **Transparent bakgrund** | Använd `barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent });`. |
| **Inbäddning i en Windows Forms PictureBox** | Istället för `Save`, anropa `barcodeGenerator.Save(pictureBox1.CreateGraphics(), BarCodeImageFormat.Png);`. |
| **Felhantering** | Omge genereringskoden med ett `try…catch`‑block för att fånga `BarCodeException` för tecken som inte stöds. |

## Pro‑tips

- **Validera streckkoden**: Efter att ha sparat kan du läsa in PNG‑filen med ett streckkodsläsar‑SDK för att säkerställa att data matchar den ursprungliga strängen.
- **Prestanda**: Att återanvända en enda `BarcodeGenerator`‑instans för flera streckkoder minskar allokeringskostnaden.
- **Säkerhet**: Om den kodade datan innehåller känslig information, överväg att kryptera den innan du skickar den till generatorn.

## Slutsats

Du vet nu hur du **genererar PDF417-streckkod** i C# och **skapar streckkodsbild C#**‑filer som uppfyller anpassade layoutkrav. Det kompletta exemplet visar hur man initierar generatorn, finjusterar storlek och layout samt sparar resultatet som en PNG. Härifrån kan du utforska ytterligare funktioner såsom färganpassning, inbäddning av logotyper eller batch‑generering av flera streckkoder för massutskrift.

---

*Nästa steg*:
- Experimentera med andra symbologier (Code128, QR) med samma `BarcodeGenerator`‑klass.
- Lär dig hur du läser PDF417‑streckkoder med Aspose.BarCode:s `BarCodeReader`.
- Integrera den genererade PNG‑filen i ASP.NET Core MVC‑vyer för dynamisk streckkodsrendering.

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Hur man sparar streckkod och genererar PDF417 med Aspose i C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [Hur man genererar PDF417-streckkod med Aspose – Komplett guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Hur man genererar PDF417-streckkod i C# med anpassade dimensioner](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}